# Keyword coverage: previous vs new targeting

**Page:** `https://sureshotfx.com/behind-the-candle`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, 90 days. 1 click, ~24 impressions, 8 queries.
**Live page measured:** 2,566 visible words, one H1, nine H2s, `Book` + `FAQPage` schema, 8 FAQs.

### The short version

The live page owns its product name but not its category. It ranks 5.7 for `behind the candle` and 99 for `smc trading pdf`. The rebuild keeps the brand term and adds the Smart Money Concepts category to the title, H1 and body.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page |
| ❌ | Not covered |
| n/a | Technical or irrelevant |

---

## 1. Old GSC queries

| Query | Clicks | Impr. | Pos | Previous | New | Decision |
|---|---|---|---|---|---|---|
| behind the candle | 1 | 3 | 5.7 | ✅ | ✅ | Brand, keep in H1 and title |
| sureshotfx | 0 | 3 | 28.3 | ✅ | ✅ | Brand, title and footer |
| smc trading pdf | 0 | 1 | 99.0 | ❌ | ✅ | FAQ answer now says "SMC trading PDF" |
| summarise the book | 0 | 1 | 2.0 | ❌ | ✅ | Book summary intro uses the phrase |
| guess | 0 | 1 | 1.0 | ✅ | ✅ | "Done guessing" copy |
| indices pip calculator | 0 | 3 | 140.3 | ❌ | ❌ | Sitewide nav leakage, not this page |
| telegram signal copier | 0 | 1 | 138.0 | ❌ | ❌ | Sitewide nav leakage, not this page |
| site:sureshotfx.com | 0 | 11 | 24.6 | n/a | n/a | Technical |

**Old-query score:** 3 of 6 targetable queries before, 5 of 6 after.

The two irrelevant queries come from the global navigation, not the page content. Do not optimise for them here.

---

## 2. New target cluster (no history on this URL yet)

These are the terms the rebuild is built around. The live page used most of the concepts but never the search phrases.

| Keyword | Intent | Where it lives |
|---|---|---|
| **smart money concepts book** | Commercial | Title, H1, meta, opening paragraph |
| SMC trading book | Commercial | Hero, FAQ |
| smart money concepts pdf | Transactional | What-is paragraph, FAQ |
| SMC trading pdf | Transactional | FAQ answer |
| liquidity sweeps | Topic / education | SMC glossary, liquidity section |
| order blocks | Topic / education | SMC glossary, chapter 3 |
| fair value gap | Topic / education | SMC glossary, chapter 3 |
| breaker zones | Topic / education | SMC glossary, chapter 3 |
| market structure trading | Topic / education | SMC glossary, chapter 1 |
| SMC entry model | Method | Entry model section |
| funded account trading book | Outcome | Chapter 5, who it's for |
| Behind the Candle | Brand | H1, title, schema |
| William | Brand / author | Author section, FAQ |

---

## 3. Cannibalisation check

- The beginner book `/sure-profit-trading-secret` targets forex foundations. This page explicitly sends beginners there.
- The books blog post `/blog/books-for-beginner-forex-traders` owns the "best forex books" list cluster. This page does not target list queries.
- No SMC or liquidity blog post was found in the 50 pages with search impressions, so this page can be the SMC hub without competing with another URL.

---

## 4. Overall

| Metric | Previous design | New design |
|---|---|---|
| Visible words | 2,566 | 2,261 |
| H1 tags | 1 | 1 |
| FAQ questions | 8 | 10 |
| Schema | `Book`, `FAQPage` | `Book`, `Offer`, `BreadcrumbList`, `FAQPage` |
| Category terms in H1 | 0 | 2 (Smart Money Concepts) |
| Category definitions on page | 0 | 6-term SMC glossary |
| Chapter summary | Implicit | Explicit, with a "summarise the book" line |
| Duplicate Black Friday bars | 11 | 1 |

**What the old page was doing:** it had good sales copy, a strong cover, a chapter list and an 8-question FAQ, but the title and H1 sold only the product name. A trader searching for an SMC book had no reason to find it. `smc trading pdf` at position 99 is the proof.

**What the new page does differently:**

1. Puts "Smart Money Concepts" in the title, H1 and first paragraph, while keeping "Behind the Candle" as the brand.
2. Adds a six-term SMC glossary so definition queries have a direct answer.
3. Makes the five-chapter overview an explicit "book summary", which also answers the `summarise the book` query.
4. Adds `Offer` and `BreadcrumbList` schema and two new FAQs (`What is SMC trading?`, `Is it a PDF?`).

**What still needs work**

1. The page needs internal links from an SMC-related blog post. None exists today.
2. The live copy says the book maps **six** liquidity types but names four. The rebuild keeps that claim and lists the four named types. Confirm the other two before making a fuller list.
3. `Behind the Candle` is the only brand term with a click. Keep it prominent in the H1.
4. Page count is not published, so the schema does not claim one.
