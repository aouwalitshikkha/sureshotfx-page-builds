# GSC dataset and the CSV-to-audit workflow

This folder holds one cached export of Google Search Console data for `sureshotfx.com` and the process used to turn that export into a blog keyword audit.

The point is to stop pulling GSC for every URL. One file covers 16 months, every query, every page and every query-page pair. A new audit starts from this file, and only falls back to the live GSC connector when a current 90-day number is needed.

---

## 1. What is in the folder

| File | Rows | Size | What it is |
|---|---|---|---|
| `sureshotfx-com-query-page-480d.csv` | 86,928 | 8.0 MB | One row per query + page pair. The main working file |
| `sureshotfx-com-queries-480d.csv` | 47,074 | 2.2 MB | Queries aggregated across all pages |
| `sureshotfx-com-pages-480d.csv` | 605 | 0.05 MB | Pages aggregated across all queries |
| `sureshotfx-com-meta-480d.json` | - | 1 KB | Property, date range, row counts, totals |

Export window: **2025-07-27 to 2026-11-19** (480 days, the practical GSC retention limit).
Generated: **2026-11-20**.
Property: `sc-domain:sureshotfx.com`.

Totals inside the query-page file: **76,821 clicks**, **5,420,172 impressions**, **47,074 unique queries**, **605 page URLs**.

The CSVs are excluded from git because this repository is public. Only this README is tracked.

---

## 2. Schema

All three CSVs share the same metric columns.

| Column | Type | Meaning |
|---|---|---|
| `query` | text | The search query as Google reports it |
| `page` | text | Full URL, fragment stripped |
| `clicks` | int | Clicks summed over the window |
| `impressions` | int | Impressions summed over the window |
| `ctr` | float | `clicks / impressions`, as a decimal (0.024 = 2.4%) |
| `position` | float | Impression-weighted average position |

`position` is weighted by impressions, not a plain mean of daily positions. A query that appeared once at position 3 and 1,000 times at position 60 will show close to 60, which is the honest number.

In the aggregate files the grouping column is `query` or `page` instead of both.

---

## 3. How the export was built

Script: `D:\Tools\gsc connector\export_full_gsc.py`

```powershell
& "C:\Users\aouwa\AppData\Local\Programs\Python\Python311\python.exe" `
  "D:\Tools\gsc connector\export_full_gsc.py" `
  "sc-domain:sureshotfx.com" `
  --days 480 `
  --window-days 30 `
  --out "D:\Clients\Running\sureshot content\gsc-data"
```

It reuses the same OAuth credentials as the GSC MCP server (`config/client_secrets.json` + `config/credentials.json` in that folder), so no new login is needed.

Four details matter:

1. **Small windows.** The API returns at most 25,000 rows per request. Paging with `startRow` repeats rows when many values tie, which produced 16,422 duplicate query-page rows on the first attempt. The script now requests 30 days at a time and splits a window in half if it still hits the cap. Each window is a single request with no paging.
2. **Collapse.** Rows are grouped by `query` + `page`, summing clicks and impressions and weighting position. A pair that appeared in 16 monthly windows becomes one row.
3. **Retry on property lookup.** The GSC site list occasionally comes back incomplete, which is why the MCP tool sometimes says the domain is not found. The script retries the property lookup six times before failing.
4. **No date dimension.** Adding dates would multiply the row count and break the 25,000 cap. The trade-off is deliberate: this file answers "which queries exist for this page", not "how did they trend".

Roughly 16 requests, about 40 seconds.

### Validation note

Dimension totals do not reconcile with the property total. On a sampled day the property total was 73 clicks and 6,301 impressions, while the page dimension matched 73 clicks but summed to 9,385 impressions, and the query dimension summed to 29 clicks. Google hides rare queries from query-level breakdowns and attributes impressions across URL variants in ways the API does not explain.

Practical rule: **use this file for relative comparison, never for absolute reporting.** A page with 1,400 impressions here is bigger than one with 140. Do not quote the file's totals as site traffic. For absolute numbers, use the no-dimension query or the GSC UI.

---

## 4. Two numbers that are not the same

Every audit so far used **90-day page-level GSC**. This file is **480-day query-page level**. They answer different questions.

| Source | Window | Use it for |
|---|---|---|
| GSC MCP `get_top_queries_for_page` | 90 days | Current position, current demand, what to fix this quarter |
| This CSV | 480 days | Full keyword inventory, old URL variants, clusters the 90-day view misses |

A query that vanished in the last 90 days still appears in the CSV. That is useful for coverage decisions and useless for "where do we rank now". Do not mix the two sets in one table without labelling the window.

---

## 5. The URL variant trap

This is the single most important thing the 480-day file exposed.

Almost every blog post exists under two URLs:

| Canonical | Legacy variant |
|---|---|
| `/blog/how-to-create-a-good-trading-plan` | `/how-to-create-a-good-trading-plan/` |
| `/blog/high-frequency-trading` | `/high-frequency-trading/` |
| `/blog/how-to-win-prop-trading-challenge` | `/how-to-win-prop-trading-challenge/` |

The legacy variant often has more rows than the canonical URL. For the trading plan post it is 49 rows on the legacy URL and 29 on `/blog/`. For high-frequency trading it is 41 and 33.

There are also 48 pages carrying query parameters such as `?wg-choose-original=false`.

A page-level audit that only queries the `/blog/` URL undercounts the page's real footprint and can misjudge whether it is worth saving. Always merge variants before you decide.

Merge rule: strip the protocol and `www.`, strip `?` and everything after it, strip a trailing slash, then group. Keep `/blog/` and the bare slug as one page.

---

## 6. Loading the data

```python
import pandas as pd

PATH = r"D:\Clients\Running\sureshot content\gsc-data\sureshotfx-com-query-page-480d.csv"
df = pd.read_csv(PATH, encoding="utf-8-sig")

# Merge URL variants onto one key
def page_key(url):
    s = url.split("?")[0].rstrip("/")
    s = s.replace("https://sureshotfx.com/blog/", "https://sureshotfx.com/")
    return s

df["page_key"] = df["page"].map(page_key)
```

The `encoding="utf-8-sig"` matters. The files are written with a BOM so Excel opens them cleanly. Plain `utf-8` leaves an invisible character on the first column name.

---

## 7. From CSV to blog audit

### Step 1: pull every row for the URL, including variants

```python
slug = "high-frequency-trading"
rows = df[df["page_key"].str.endswith("/" + slug)]
print(rows["page"].value_counts())
```

If the two variants disagree on the query set, keep the union. The legacy URL usually carries older, broader queries; the `/blog/` URL carries the recent ones.

### Step 2: split brand from non-brand

```python
BRAND = ("sureshot", "sureshotfx", "sureshot fx")
rows["brand"] = rows["query"].str.lower().str.contains("|".join(BRAND), regex=True)
nonbrand = rows[~rows["brand"]]
```

Brand queries tell you whether the page is findable by name. They do not justify content changes. Every plan is built on non-brand queries only. Site-wide, brand is about 6 percent of impressions, so a page that looks healthy on brand alone is usually invisible.

### Step 3: sort by impressions, not clicks

```python
view = (nonbrand.groupby("query")
        .agg(clicks=("clicks", "sum"),
             impressions=("impressions", "sum"),
             position=("position", "mean"))
        .sort_values("impressions", ascending=False))
```

93 percent of queries have zero clicks. Sorting by clicks gives an empty table and a false sense that there is nothing to fix. Impressions show demand; position shows whether the page is close enough to matter.

### Step 4: classify every query

Five labels, same as every audit file in `blog-audits/`.

| Label | Meaning | Test |
|---|---|---|
| ✅ | Exact phrase appears in the visible page copy | Case-insensitive substring match against rendered text |
| 🟡 | The concept is covered, the query wording is not | Read the section, check the exact phrase |
| ❌ | Missing, and this URL is the right home | Judge intent against the page's promise |
| ↪ | Related, but another page should own it | Name the owner URL or the article to create |
| n/a | Brand, technical, or synthetic | No content action |

Classification is a judgement call, not a keyword match. A page can mention "risk" 40 times and still be ❌ for "risk per trade" if it never states a rule. Read the section before labelling it partial.

### Step 5: check the live page, not the CSV

Search Console tells you the query; it does not tell you whether the page answers it. Fetch the rendered page and count exact phrases.

```python
import re, html, urllib.request

url = "https://sureshotfx.com/blog/high-frequency-trading"
raw = urllib.request.urlopen(
    urllib.request.Request(url, headers={"User-Agent": "Mozilla/5.0"}), timeout=60
).read().decode("utf-8", "replace")

body = re.sub(r"(?is)<(script|style|noscript)[^>]*>.*?</\1>", " ", raw)
text = re.sub(r"\s+", " ", html.unescape(re.sub(r"(?s)<[^>]+>", " ", body))).lower()

for q in view.index[:40]:
    print(text.count(q.lower()), q)
```

Two traps:

- The Black Friday banner repeats 9 to 11 times on every page. Any query matching its wording gets an inflated count. Exclude the banner before counting, or discount counts of 9 and above.
- Counts on the raw HTML include alt text, schema and hidden menus. The regex above strips tags but not hidden elements. For a phrase that only appears in a menu, open the page and look.

The audit table records what the page actually says, not what the CMS template says.

### Step 6: decide what belongs here and what does not

This is where most audits earn their keep.

- **Commercial queries** (`buy`, `best`, `broker`, `cheapest`, `which prop firm`) belong to a comparison or sign-up page. Do not bolt a product table onto a guide.
- **B2B queries** (`how can prop firms automate challenge rules and payout workflows`) belong to an operator page, not a trader guide.
- **Adjacent intents** (`tax`, `investing`, `strategy` vs `plan`) get their own article. Adding a section to capture them dilutes the page and creates cannibalisation.
- **Synthetic queries** show high positions with zero clicks and unnatural phrasing. Example from the HFT page: `top-rated hft trading rules for traders comparison`, ranking 1.4 to 8.5 with 0 clicks. Ignore them. Ranking #1 with no clicks is the tell.

For every ↪ query, name the owner. "Separate article" is not an owner; write the working title.

### Step 7: write the plan, not the article

Each audit file follows the same structure so they can be compared:

1. **Header**: URL, property, data window, audit date, content snapshot, scope.
2. **The short version**: three to five findings, no preamble.
3. **Status counts**: covered, partial, missing, related, not relevant.
4. **Full query table**: query, impressions, position, status, gap or action. Every row from the export, nothing dropped.
5. **P1**: title, H1, meta, definition heading, the one structural fix that matters most.
6. **P2**: sections, FAQs, schema, template.
7. **P3**: internal links, dates, banner cleanup, schema refresh.
8. **Related but separate**: query, why it does not belong, right owner.
9. **Cannibalisation**: URL, what it owns, action here.
10. **Head-term reality check**: the biggest query, its current position, and an honest statement of whether more mentions can move it.
11. **Method and limits**: window, row count, small-sample warning.

Rules for the plan:

- No article copy. Headings, tables and answer outlines only.
- No invented facts, prices, ratings or dates.
- No em dashes.
- Keep exact-phrase recommendations to the title, one H2, the definition and the FAQ. Repeating a phrase 20 times is not a plan.
- If the head term already appears many times and still ranks at 60+, say so. The fix is depth, structure and internal links, not another mention.

Save as `blog-audits/<slug>.md`. Commit message: `Add <topic> keyword audit and plan`.

### Step 8: recheck at 60 and 90 days

The 90-day MCP pull is the scoreboard. Re-run `get_top_queries_for_page` for the same URL and compare position on the head term and the number of queries in the top 20. Do not re-export the 480-day file for this; it is a coverage map, not a trend line.

---

## 8. Worked example: high-frequency trading

| Step | Result |
|---|---|
| Rows in 16 months | 33 on `/blog/high-frequency-trading`, 41 on `/high-frequency-trading/` |
| Non-brand head term | `fx high frequency trading`, 36 impressions, position 66.6 |
| Strongest term | `high frequency trading`, 16 impressions, position 9.4 |
| Commercial cluster | broker and account queries, positions 7.7 to 71.2 |
| Synthetic cluster | `top-rated hft trading rules...`, 20 impressions, positions 1.0 to 8.5, 0 clicks |
| Live coverage | 15 mentions of "high frequency trading", 1 of "high frequency trading in forex", 0 of "fx high frequency trading" |
| Verdict | Explainer, not a forex guide. Retarget to forex, add a definition H2, a speed table, a strategy H2 and an FAQ. Send broker queries elsewhere |

The 90-day audit reached the same conclusion from 32 queries. The 480-day file added the legacy URL and confirmed the query set was stable, not a one-month blip. That is the intended relationship between the two sources.

---

## 9. Copy-paste recipes

**Top queries for a page, variants merged**

```python
view = (df[df["page_key"].str.endswith("/lot-size-calculator")]
        .groupby("query")
        .agg(clicks=("clicks", "sum"), impressions=("impressions", "sum"),
             position=("position", "mean"))
        .sort_values("impressions", ascending=False))
print(view.head(30))
```

**Which pages mention a topic**

```python
topic = df[df["query"].str.contains("trading plan", case=False, na=False)]
print(topic.groupby("page_key").impressions.sum().sort_values(ascending=False).head(10))
```

This is how you find the page that already owns a cluster before writing a new one. It is also how you spot cannibalisation.

**Striking-distance opportunities**

```python
opp = (df.groupby(["page_key", "query"])
       .agg(clicks=("clicks", "sum"), impressions=("impressions", "sum"),
            position=("position", "mean"))
       .reset_index())
opp = opp[(opp.impressions >= 50) & (opp.position.between(5, 30))]
print(opp.sort_values("impressions", ascending=False).head(25))
```

**Pages with no clicks in 16 months**

```python
dead = (df.groupby("page_key")
        .agg(clicks=("clicks", "sum"), impressions=("impressions", "sum"))
        .query("clicks == 0 and impressions >= 100")
        .sort_values("impressions", ascending=False))
print(len(dead))
```

409 of 605 URLs have zero clicks. That list is the retargeting queue.

**Brand share for one page**

```python
page = df[df["page_key"].str.endswith("/sureshotfx-guardian")]
brand = page["query"].str.contains("sureshot", case=False, na=False)
print(round(page[brand].impressions.sum() / max(page.impressions.sum(), 1) * 100, 1))
```

A page at 100 percent brand has no non-brand demand yet. That is a positioning problem, not a content depth problem.

---

## 10. Refreshing the dataset

Run the same command in section 3. It overwrites the four files. Then update the date line at the top of this README and the numbers in section 1.

If the property lookup fails with "No property matched", it is the same flaky site list the MCP tool hits. The script retries; if it still fails, run it again in a minute.

If a window hits the row cap repeatedly, lower `--window-days` to 14. More requests, same result.

---

## 11. Limits to keep in mind

- **Query data is incomplete by design.** Google withholds rare queries. The query breakdown will always sum to less than the property total, and the gap is not a bug you can fix.
- **No dates.** This file cannot show trends, seasonality or the effect of a fix. Use a fresh 90-day pull for that.
- **Positions are averages.** A query at position 12 might be 4 on one URL variant and 60 on another. Check variants before assuming a page is close to page one.
- **Small samples dominate.** Most queries here have one or two impressions. A position of 3 on a single impression means nothing. Weight decisions by impressions, not by the existence of a query.
- **The file is a map, not a scoreboard.** Use it to decide what a page should cover and which page should own a query. Use live GSC to decide whether the change worked.
