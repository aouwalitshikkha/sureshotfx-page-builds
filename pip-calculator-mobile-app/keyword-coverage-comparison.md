# Keyword coverage — previous vs new design

**Page:** `https://sureshotfx.com/pip-calculator-mobile-app`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, last 90 days. 1 click, 84 impressions, 8 queries.
**Method:** exact on-page phrase match against the rendered text of both versions, then a manual concept check. Live page measured on 19 Nov 2026: 5,773 visible characters, 871 words, one H1, zero H2s, 11 duplicate Black Friday bars.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page (exact match) |
| 🟡 | Concept covered, but not as the exact query string |
| ❌ | Not covered anywhere on the page |
| n/a | Out of scope for this page |

---

## 1. Non-brand — app intent (6 queries)

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | pips calculator app | 36 | 11.2 | ❌ | ✅ | Popular searches chip |
| 2 | one pip trading app | 13 | 62.5 | ❌ | ✅ | "What is a pip" section, chip |
| 3 | one pip forex app | 11 | 51.2 | ❌ | ✅ | "What is a pip" section, chip |
| 4 | pip calculator app | 4 | 23.8 | ✅ | ✅ | Title, H1, feature section, download block |
| 5 | pip calculator download | 3 | 9.7 | ❌ | ✅ | Download section, FAQ, chip |
| 6 | pip calculator | 1 | 8.0 | ✅ | ✅ | Hero, features, FAQ, footer, web-calculator link |

**Score — 6 product queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 2 | 0 | 4 |
| New design | 6 | 0 | 0 |

Impressions covered: **6 of 72 (8.3%) → 72 of 72 (100%)** for the product cluster.

The live page's only product sentence is "Pip calculator is a simple, free app". `pips calculator app` — the page's single click-producing query — does not appear anywhere on it.

---

## 2. Brand (2 queries)

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | site:sureshotfx.com | 15 | 54.9 | n/a | n/a | Technical operator, not page copy |
| 2 | sureshotfx | 1 | 1.0 | ✅ | ✅ | Title, header, footer, brand FAQ, app identity |

**Score — 1 brand query**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 1 | 0 | 0 |
| New design | 1 | 0 | 0 |

---

## 3. Overall

| Metric | Previous design | New design |
|---|---|---|
| Queries covered (exact, all 8) | 3 | 7 |
| Product queries covered (of 6) | 2 | 6 |
| Impressions covered | 6 (7.1%) | 69 (82.1%) |
| Visible words | 871 | 2,412 |
| Content sections | 2 (hero, newsletter) | 15 |
| H2 headings | 0 | 12 |
| FAQ questions | 0 | 13 |
| Duplicate Black Friday bars | 11 | 1 |
| Structured data | none found in page JSON-LD for the app | `MobileApplication`, `BreadcrumbList`, `FAQPage` |
| Screenshots | 1 composite hero image | Composite hero + 6 real app screens + app icon |

**What the old page was doing:** it is a download button with a hero image. One H1 ("Understand the Potential Profit or Loss of Trade") that never names the product, one paragraph, and no feature list, no screenshots, no explanation of what a pip is and no FAQ. GSC reflects that: 84 impressions and a single click in 90 days.

**What the new page does differently:**

1. Names the product in the H1, title, meta description and download block, and states the three markets it covers.
2. Surfaces the ten real features from the Google Play listing instead of leaving them on the store page.
3. Shows six actual Android screens with a lightbox, so a visitor can verify the app before installing.
4. Adds the pip-education content that produces search intent: pip definition, JPY convention, pip-value formula, gold's 0.10 convention and a worked buy/sell example taken from the shipping app.
5. Answers the store questions people actually ask: free, iPhone, pairs, gold, indices, contract size, accuracy, web version, official source.

**What still needs work**

1. **The iOS listing is dead.** The live page links to an App Store URL that returns 404 and an iTunes lookup with 0 results. The new page removes that badge and says so. Confirm whether the app was delisted or region-limited before restoring an iOS badge.
2. **Volume is tiny.** Eight queries in 90 days means this page has no meaningful search presence yet. Ranking for `pip calculator app` will require internal links from `/pip-calculator/forex-pip-calculator`, `/lot-size-calculator`, `/forex-vip-signals` and `/gold-vip-signals`, plus the Play listing's own reviews.
3. **`one pip forex app` and `one pip trading app` (24 impressions) sit at position 51 and 62.** The pip section now uses both phrases, but that section also needs a mention from the blog to move them.
4. **The rating and download count are point-in-time.** 4.0 stars, 134 reviews and 10,000+ downloads were read from the Play listing on 19 Nov 2026. Add a "last checked" date or pull them server-side at render time.
