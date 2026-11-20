# Blog audit workflow

How to go from the cached Search Console CSV to a finished keyword audit and content plan.

Input: `gsc-data/sureshotfx-com-query-page-480d.csv` (16 months, one row per query and page pair).
Output: `blog-audits/<slug>.md`, plan only, no article copy.

---

## Load the file

```python
import pandas as pd

PATH = r"D:\Clients\Running\sureshot content\gsc-data\sureshotfx-com-query-page-480d.csv"
df = pd.read_csv(PATH, encoding="utf-8-sig")

def page_key(url):
    s = url.split("?")[0].rstrip("/")
    s = s.replace("https://sureshotfx.com/blog/", "https://sureshotfx.com/")
    return s

df["page_key"] = df["page"].map(page_key)
```

Columns: `query`, `page`, `clicks`, `impressions`, `ctr`, `position`.

`position` is impression-weighted. `ctr` is a decimal: 0.024 means 2.4%. `encoding="utf-8-sig"` is required, otherwise the first column name carries an invisible character.

---

## Step 1: pull every row for the URL

```python
slug = "high-frequency-trading"
rows = df[df["page_key"].str.endswith("/" + slug)]
print(rows["page"].value_counts())
```

Every blog post exists under two URLs: `/blog/slug` and `/slug/`. The legacy URL often has more rows than the canonical one. Merge them before judging the page.

```python
view = (rows.groupby("query")
        .agg(clicks=("clicks", "sum"),
             impressions=("impressions", "sum"),
             position=("position", "mean"))
        .sort_values("impressions", ascending=False))
```

---

## Step 2: remove brand queries

```python
brand = view.index.str.contains("sureshot", case=False)
nonbrand = view[~brand]
```

Brand queries show whether the page is findable by name. They never justify a content change. Build the whole plan on non-brand queries. Site-wide, brand is about 6 percent of impressions, so a page that looks healthy on brand alone is usually invisible.

---

## Step 3: rank by impressions, not clicks

93 percent of queries in the file have zero clicks. Sorting by clicks returns an empty table.

Impressions show demand. Position shows whether the page is close enough to matter. Work top down by impressions, and ignore anything with fewer than 3 impressions unless it is the head term.

---

## Step 4: classify every query

| Label | Meaning | Test |
|---|---|---|
| ✅ | Exact phrase appears in the page copy | Case-insensitive substring match on rendered text |
| 🟡 | Concept covered, exact wording missing | Read the section, check the phrase |
| ❌ | Missing, and this URL is the right home | Judge intent against the page's promise |
| ↪ | Related, another page should own it | Name the owner URL or working title |
| n/a | Brand, technical or synthetic | No content action |

Classification is a judgement call, not a keyword match. A page can say "risk" 40 times and still be ❌ for "risk per trade" if it never states a number. Read the section before calling it partial.

---

## Step 5: check the live page, not the CSV

Search Console tells you the query. It does not tell you whether the page answers it.

```python
import re, html, urllib.request

url = "https://sureshotfx.com/blog/high-frequency-trading"
raw = urllib.request.urlopen(
    urllib.request.Request(url, headers={"User-Agent": "Mozilla/5.0"}), timeout=60
).read().decode("utf-8", "replace")

body = re.sub(r"(?is)<(script|style|noscript)[^>]*>.*?</\1>", " ", raw)
text = re.sub(r"\s+", " ", html.unescape(re.sub(r"(?s)<[^>]+>", " ", body))).lower()

for q in nonbrand.index[:40]:
    print(text.count(q.lower()), q)
```

Two traps:

- The Black Friday banner repeats 9 to 11 times on every page. Any query matching its wording gets a false positive. Discount counts of 9 and above, or strip the banner first.
- Raw HTML includes menus, alt text and schema. A phrase that appears only in navigation is not coverage. Open the page and confirm.

The audit table records what the article says, not what the template says.

---

## Step 6: decide what belongs here and what does not

- **Commercial** (`buy`, `best`, `broker`, `cheapest`, `which prop firm`): comparison or sign-up page. Do not bolt a product table onto a guide.
- **B2B** (`how can prop firms automate challenge rules and payout workflows`): operator page, not a trader guide.
- **Adjacent intent** (`tax`, `investing`, `strategy` vs `plan`): its own article. Adding a section creates cannibalisation.
- **Synthetic** (high position, zero clicks, unnatural phrasing): ignore. Example: `top-rated hft trading rules for traders comparison` ranking 1.4 with 0 clicks. Ranking #1 with no clicks is the tell.

For every ↪ query, name the owner. "Separate article" is not an owner. Write the working title.

---

## Step 7: write the plan

Same structure for every audit:

1. **Header**: URL, property, window, audit date, content snapshot, scope.
2. **The short version**: three to five findings, no preamble.
3. **Status counts**: covered, partial, missing, related, not relevant.
4. **Full query table**: query, impressions, position, status, gap or action. Every row, nothing dropped.
5. **P1**: title, H1, meta, definition heading, the one structural fix that matters most.
6. **P2**: sections, FAQs, schema, template.
7. **P3**: internal links, dates, banner cleanup, schema refresh.
8. **Related but separate**: query, why it does not belong, right owner.
9. **Cannibalisation**: URL, what it owns, action here.
10. **Head-term reality check**: biggest query, current position, honest statement of whether more mentions can move it.
11. **Method and limits**: window, row count, small-sample warning.

Rules:

- No article copy. Headings, tables and answer outlines only.
- No invented facts, prices, ratings or dates.
- No em dashes.
- Exact phrase goes in the title, one H2, the definition and the FAQ. Repeating it 20 times is not a plan.
- If the head term already appears many times and still ranks at 60+, say so. The fix is depth, structure and internal links.
- Separate the 90-day and 480-day numbers, or use only one. Never mix them in one table unlabelled.

Save as `blog-audits/<slug>.md`. Commit: `Add <topic> keyword audit and plan`.

---

## Step 8: recheck at 60 and 90 days

Pull 90-day page data with `get_top_queries_for_page` and compare:

- position on the head term
- number of queries in the top 20
- clicks on the page

The 480-day file is a coverage map. It is not a trend line.

---

## Rules that keep the audit honest

- Use the file for relative comparison only. Dimension totals do not reconcile with the property total, so never quote the CSV as site traffic.
- Weight decisions by impressions. A position of 3 on one impression means nothing.
- Position 5 to 30 with real impressions is the striking distance worth planning for.
- A page at 100 percent brand has a positioning problem, not a depth problem.
- If the data contradicts the brief, say so at the top of the audit.
