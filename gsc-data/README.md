# Blog audit workflow

This folder contains a frozen export of Google Search Console data. You do not need Search Console access to use it.

The export lists every search query that showed a sureshotfx.com page in Google, the page it showed, and how it performed. From that, you can audit any blog post and write a keyword coverage plan.

**Data window:** 27 July 2025 to 19 November 2026.
**Freshness:** everything is a 16-month total. Nothing here is live.

---

## 1. What you have

| File | What it is |
|---|---|
| `sureshotfx-com-query-page-480d.csv` | The working file. One row per query and page pair |
| `sureshotfx-com-queries-480d.csv` | Queries totalled across all pages |
| `sureshotfx-com-pages-480d.csv` | Pages totalled across all queries |

Start with the query-page file. The other two are shortcuts for site-wide questions.

### Columns

| Column | Meaning |
|---|---|
| `query` | What the person typed into Google |
| `page` | The URL Google showed |
| `clicks` | How many people clicked through |
| `impressions` | How many times the page appeared in results |
| `ctr` | Clicks divided by impressions. 0.024 means 2.4 percent |
| `position` | Average ranking. 1 is the first result, 60 means page six |

`position` is weighted by impressions, so a query that appeared once at position 3 and a thousand times at position 60 reads close to 60. That is the honest number.

These are totals, not daily rows. A query that ran for ten months is summed into one line. That makes the file small enough to work with, and it means you cannot see trends inside it.

### Two things to know before you read any number

**Google hides rare queries.** The query rows will never add up to the site's real traffic. That is normal. Use the file to compare queries and pages against each other, never to report total traffic.

**Most queries have no clicks.** 93 percent of the 47,074 queries have zero. That is not a bug. It is the long tail of searches where the page appeared deep in the results. Rank by impressions, not clicks, or you will see an empty table.

---

## 2. Set up

You need:

- Python with pandas, or Excel
- A browser, to read the live article

Load the file:

```python
import pandas as pd

PATH = "sureshotfx-com-query-page-480d.csv"
df = pd.read_csv(PATH, encoding="utf-8-sig")

def page_key(url):
    s = url.split("?")[0].rstrip("/")
    s = s.replace("https://sureshotfx.com/blog/", "https://sureshotfx.com/")
    return s

df["page_key"] = df["page"].map(page_key)
```

`encoding="utf-8-sig"` matters. Without it the first column name carries an invisible character.

**Excel instead:** open the CSV directly, turn on Filter, and filter the `page` column by the slug. Insert a PivotTable with `query` in Rows, `impressions` and `clicks` in Values set to Sum, and `position` in Values set to Average. Note that the Excel average is unweighted, so treat it as approximate.

---

## 3. Pull every row for the URL

```python
slug = "high-frequency-trading"
rows = df[df["page_key"].str.endswith("/" + slug)]
print(rows["page"].value_counts())
```

Read that output before going further. Every blog post appears under two URLs: `/blog/slug` and `/slug/`. The old URL redirects to the new one. Google still reports the impressions it served before the redirect, which is why the old URL often carries most of the traffic in this file.

Those rows are history, not a second live page.

| What you see | What it means |
|---|---|
| `/slug/` and `/blog/slug` | Same article. The old URL redirects. Merge the rows |
| Old URL has most impressions | Historical demand. Still valid for choosing keywords |
| Old URL has better positions | Rankings from before the move. Not a current ranking |
| New URL has fewer impressions | Expected after a redirect. Judge it on position, not volume |

Merge the two for demand. Use only the live URL's position as the current position. Averaging them mixes pre-redirect and post-redirect rankings and produces a number that describes neither.

```python
# Demand: both URLs
demand = (rows.groupby("query")
          .agg(clicks=("clicks", "sum"),
               impressions=("impressions", "sum")))

# Current position: the live URL only
live = rows[rows["page"].str.contains("/blog/")]
current = live.groupby("query").agg(position=("position", "mean"))

view = (demand.join(current["position"])
        .sort_values("impressions", ascending=False))
```

If the live URL has no row for a query, the position is blank. Do not fill it from the old URL. A blank position means the live page did not rank for that query in the window, which is a finding in itself.

If you skip the variant check, you will undercount the page and may wrongly decide it is not worth fixing.

---

## 4. Remove brand queries

```python
brand = view.index.str.contains("sureshot", case=False)
nonbrand = view[~brand]
```

Brand queries tell you the page is findable by name. They never justify a content change, because the person was already looking for the brand. Build the whole plan on non-brand queries.

A page where almost all impressions are brand has a positioning problem, not a depth problem. Say that in the audit instead of padding the article.

---

## 5. Rank by impressions

Impressions show demand. Position shows whether the page is close enough to matter.

Work top down by impressions. Ignore anything under 3 impressions unless it is the head term for the topic. One impression at position 2 means nothing.

Striking distance is **position 5 to 30 with real impressions**. Those are the queries a rewrite can realistically move.

---

## 6. Classify every query

| Label | Meaning | How to test |
|---|---|---|
| ✅ | The exact phrase appears on the page | Case-insensitive search of the live text |
| 🟡 | The idea is covered, the wording is not | Read the section, then check the phrase |
| ❌ | Missing, and this page is the right home | Judge intent against what the page promises |
| ↪ | Related, but another page should own it | Name that page or the article to create |
| n/a | Brand, technical or fake | No content action |

This is a judgement call, not a keyword match. A page can say "risk" forty times and still be ❌ for "risk per trade" if it never states a number. Read the section before calling it partial.

Record the reason in the table. "Partial" with no explanation is not useful to the writer.

---

## 7. Check the live page

Search Console data tells you the query. It does not tell you whether the article answers it.

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

- The Black Friday banner repeats 9 to 11 times on every page. Any query that matches its wording looks covered when it is not. Discount counts of 9 and above.
- Raw HTML includes menus, alt text and schema. A phrase that appears only in navigation is not coverage. Open the page and confirm.

---

## 8. Decide what does not belong

This is where most of the value is. A page should not try to answer everything.

- **Commercial** queries (`buy`, `best`, `broker`, `cheapest`, `which prop firm`) belong to a comparison or sign-up page. Do not bolt a product table onto a guide.
- **B2B** queries (`how can prop firms automate challenge rules and payout workflows`) belong to an operator page, not a trader guide.
- **Adjacent intent** (`tax`, `investing`, `strategy` when the page is about a plan) gets its own article. Adding a section here creates cannibalisation.
- **Fake or synthetic** queries show a high position with zero clicks and unnatural phrasing. Example: `top-rated hft trading rules for traders comparison`, ranking 1.4 with 0 clicks. Ranking first with no clicks is the tell. Ignore them.

For every ↪ query, name the owner. "Separate article" is not an owner. Write the working title.

---

## 9. Write the plan

Same structure every time, so plans can be compared:

1. **Header:** URL, data file, window, audit date, content snapshot, scope.
2. **The short version:** three to five findings, no preamble.
3. **Status counts:** covered, partial, missing, related, not relevant.
4. **Full query table:** query, impressions, position, status, gap or action. Every row, nothing dropped.
5. **P1:** title, H1, meta, definition heading, the one structural fix that matters most.
6. **P2:** sections, FAQs, schema, template.
7. **P3:** internal links, dates, banner cleanup, schema refresh.
8. **Related but separate:** query, why it does not belong, right owner.
9. **Cannibalisation:** URL, what it owns, action here.
10. **Head-term reality check:** biggest query, current position, and an honest answer to whether more mentions can move it.
11. **Method and limits:** file, window, row count, what the data cannot show.

Rules:

- No article copy. Headings, tables and answer outlines only.
- No invented facts, prices, ratings or dates.
- No em dashes.
- Put the exact phrase in the title, one H2, the definition and the FAQ. Repeating it twenty times is not a plan.
- If the head term already appears many times and still sits at position 60, say so. The fix is depth, structure and internal links.
- Never write "currently ranks" without the phrase "16-month average, to 19 November 2026". You do not know where it ranks today.
- When a page has two URLs, say which one is live and quote positions from that one only. Label the old URL's numbers as pre-redirect history.

Save as `blog-audits/<slug>.md`. Commit: `Add <topic> keyword audit and plan`.

### Skeleton

```markdown
# <Topic>: keyword coverage audit and plan

**Page:** <url>
**Data:** 16-month export, 27 Jul 2025 to 19 Nov 2026
**Audited:** <date>
**Scope:** coverage audit and plan only. No article rewrite.

## 1. The short version
## 2. Query coverage
## 3. Plan
### P1
### P2
### P3
## 4. Related but separate
## 5. Cannibalisation
## 6. Head-term reality check
## 7. Method and limits
```

---

## 10. Handoff

The audit is read by a writer who will not open the CSV. Make the file stand alone:

- Quote the impressions and position for every query you mention.
- State the window next to the first number, not only in the footer.
- Explain why a query is ❌ or ↪ in one sentence, not in one word.
- List the exact phrases the writer must use, and where.
- Do not send the CSV as the deliverable. Send the audit.

---

## 11. What this data cannot tell you

Set expectations with whoever receives the audit.

- **No live rankings.** Everything is an average over 16 months.
- **No trends.** There are no dates in the file, so you cannot show growth or decline.
- **No redirect dates.** You cannot tell when an old URL stopped serving, so treat all of its rows as pre-redirect history by default.
- **No device, country or SERP feature data.** The export does not include it.
- **No total traffic.** Google hides rare queries, so query rows never sum to the site total.
- **No indexing or technical data.** If a page is missing from the file entirely, that is not proof it is deindexed. It may simply have no impressions in the window.

If a decision depends on any of those, say it is out of scope rather than guessing.

---

## 12. Quick reference

| Situation | Action |
|---|---|
| Query has 0 clicks and 200 impressions | Normal. Judge it on position |
| Position 8, 40 impressions | Striking distance. Include in P1 or P2 |
| Position 1, 0 clicks | Suspicious. Check for a fake or branded query |
| Query matches the Black Friday banner | False coverage. Discount it |
| Page has two URLs | Old URL redirects. Merge demand, quote only the live URL's position |
| Old URL ranks better than the new one | Pre-redirect history. Do not report it as a current ranking |
| All traffic is brand | Positioning problem, not a content gap |
| Query asks for a broker, price or sign-up | Send it to a commercial page |
| Query asks about tax, investing or automation | Send it to its own article |
