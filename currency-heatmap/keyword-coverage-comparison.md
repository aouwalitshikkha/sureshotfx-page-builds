# Keyword coverage — previous vs new design

**Page:** `https://sureshotfx.com/currency-heatmap`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, last 90 days. 3 clicks, 34 impressions, 8 queries.
**Method:** exact on-page phrase match against the rendered text of both versions, then a manual concept check. Live page measured on 19 Nov 2026: 828 visible words, one H1 ("Heat-Map"), zero H2s, 11 duplicate Black Friday bars, and a single TradingView iframe doing the actual work.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page (exact match) |
| 🟡 | Concept covered, but not as the exact query string |
| ❌ | Not covered anywhere on the page |
| n/a | Out of scope for this page |

---

## 1. Non-brand — tool intent (6 queries)

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | currency heatmap | 6 | 19.8 | ✅ | ✅ | Title, H1, meta, FAQ, chip |
| 2 | currency heat map | 4 | 61.0 | ❌ | ✅ | H1, intro, how-to-read section, chip |
| 3 | forex heat map | 1 | 107.0 | ❌ | ✅ | How-to-read section, chip |
| 4 | forex heatmap | 1 | 72.0 | ❌ | ✅ | How-to-read section, chip |
| 5 | live currency heat map | 1 | 63.0 | ❌ | ✅ | Hero badge, chip |
| 6 | liquidity heatmap gold | 1 | 115.0 | ❌ | ✅ | FAQ heading and answer, chip |

**Score — 6 tool queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 1 | 0 | 5 |
| New design | 6 | 0 | 0 |

`liquidity heatmap gold` is not a currency query. The new page answers it directly — this grid is not a liquidity or order-flow map, and gold sizing belongs in the lot size calculator — rather than pretending to be something it is not.

---

## 2. Brand and localized (2 queries)

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | sureshotfx | 1 | 1.0 | ✅ | ✅ | Title, header, footer, brand FAQ |
| 2 | الخريطة الحرارية للفوركس | 4 | 44.8 | ❌ | ✅ | Arabic subheading under the hero |

**Score — 2 brand/localized queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 1 | 0 | 1 |
| New design | 2 | 0 | 0 |

---

## 3. Not coverable (1 query, 16 impressions)

| Keyword | Impr. | Pos | Why it is not covered |
|---|---|---|---|
| site:sureshotfx.com | 16 | 19.6 | Technical operator, not page copy. It is 47% of the page's impressions, which means Google treats the URL as a site page, not a tool page. |

---

## 4. Overall

| Metric | Previous design | New design |
|---|---|---|
| Queries covered (exact, all 8) | 2 | 7 |
| Product queries covered (of 6) | 1 | 6 |
| Impressions covered | 7 (20.6%) | 18 (52.9%) |
| Non-technical impressions covered | 7 of 18 (38.9%) | 18 of 18 (100%) |
| Visible words | 828 | 1,597 |
| Content sections | 1 | 7 |
| H2 headings | 0 | 6 |
| FAQ questions | 0 | 10 |
| Duplicate Black Friday bars | 11 | 1 |
| Heat map implementation | Third-party TradingView iframe | Self-contained grid, live daily rates |
| Interactive detail | None | 56 pairs, 3 timeframes, movers, per-pair detail |

**What the old page was doing:** the entire page is a TradingView embed with an H1 ("Heat-Map") and one line of copy ("Avoid blowing out your account"). There is no explanation of what the grid shows, no timeframe guidance, no FAQ and no content for Google to index. It ranks for `currency heatmap` at position 19.8 because of the title, and for almost nothing else.

**What the new page does differently:**

1. Replaces the iframe with a self-contained 8×8 grid of 56 major pairs, computed from live mid-market rates — so the page owns the tool instead of renting it.
2. Adds the content the tool needs: what the colours mean, what each timeframe is for, and how correlated positions inflate risk.
3. Answers the query that Google already associates with the page (`liquidity heatmap gold`) honestly: this is not a liquidity map.
4. Covers all six tool queries on the page itself, plus the Arabic phrase that already has four impressions.

**What still needs work**

1. **The URL has almost no authority as a tool.** 34 impressions in 90 days. Internal links from `/lot-size-calculator`, `/pip-calculator/forex-pip-calculator`, `/forex-vip-signals` and the blog will do more than another section.
2. **`site:sureshotfx.com` is 16 of 34 impressions.** That is a crawl/index signal, not a keyword problem.
3. **The Arabic query (4 impressions) is answered with one line.** A full Arabic version would be the next step if that traffic grows.
4. **Data cadence is daily.** The page says so. If the client wants intraday heat, that needs a tick provider and a different cost model.
