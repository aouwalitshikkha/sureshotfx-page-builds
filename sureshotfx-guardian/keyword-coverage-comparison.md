# Keyword coverage: previous vs new targeting

**Page:** `https://sureshotfx.com/sureshotfx-guardian`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, 90 days. 0 clicks, 28 impressions, 5 queries.
**Live page measured:** 1,765 visible words, title only the product name, 9 FAQs, a duplicated Trade Copier feature block, 11 Black Friday bars.

### The short version

The live page targets the brand name and "protect your fund". GSC shows no non-brand query at all. The product is a **prop firm drawdown EA for MT4/MT5**, so the rebuild targets that category and removes the copier copy that was confusing the page.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page |
| ❌ | Not covered |
| n/a | Technical or different brand |

---

## 1. Old GSC queries

| Query | Impr. | Pos | Previous | New | Decision |
|---|---|---|---|---|---|
| site:sureshotfx.com | 15 | 17.4 | n/a | n/a | Technical |
| sureshotfx | 8 | 20.0 | ✅ | ✅ | Brand, title and body |
| ssf trading | 2 | 96.5 | ❌ | ✅ | Brand spelling list in FAQ |
| the sure fx group | 2 | 79.0 | ❌ | ❌ | Different group; not targeted |
| sure shot fx | 1 | 7.0 | ❌ | ✅ | Brand spelling list in FAQ |

**Old-query score:** 1 of 4 targetable queries before, 3 of 4 after.

There was no `prop firm`, `drawdown` or `EA` query at all. That is the real gap.

---

## 2. New target cluster (no history on this URL yet)

| Keyword | Intent | Where it lives |
|---|---|---|
| **prop firm drawdown EA** | Commercial | Title, H1, opening paragraph |
| drawdown protection EA MT4/MT5 | Commercial | H1, meta, body |
| SureShotFX Guardian / Guardian EA | Brand | H1, title, schema |
| daily drawdown EA | Commercial | Feature card, FAQ |
| max drawdown EA | Commercial | Feature card, body |
| prop firm risk management EA | Commercial | Definition section |
| funded account protection EA | Commercial | Hero, who it's for |
| prop firm challenge EA | Commercial | Body, FAQ |
| MT4 drawdown EA / MT5 drawdown EA | Platform | Compatibility table |
| EA that closes trades at drawdown limit | Long-tail | "Does it close trades automatically?" |
| how to avoid breaching prop firm daily loss limit | Informational | Blog, not this page |
| prop firm daily drawdown rules | Informational | Blog, not this page |

The page now defines the category, lists Guardian-only features, explains the limits and answers the commercial questions.

---

## 3. Cannibalisation check

- `/blog/prop-firms-that-allow-ea-trading` has **5,941 impressions** for prop-firm EA queries. It should keep the list/informational intent and link to Guardian. Guardian owns the commercial drawdown-EA intent.
- `/trade-copier` mentions Guardian as a cross-sell, but the copier page owns execution and signal copying. Guardian owns drawdown protection.
- `/algo` is an automated strategy product, not a risk manager. No overlap.

The rebuild links to the copier and the prop-firm EA guide instead of repeating their content.

---

## 4. Overall

| Metric | Previous design | New design |
|---|---|---|
| Title | "SureShotFX Guardian - SureShotFX" | "Prop Firm Drawdown EA for MT4 & MT5 \| SureShotFX Guardian" |
| H1 | "Protect Your Funded Account From Max/ Daily Loss Limit" | "Guardian: Prop Firm Drawdown Protection for MT4 & MT5" |
| Visible words | 1,765 | 1,953 |
| FAQ questions | 9 | 12 |
| Category terms in title/H1 | 0 | prop firm, drawdown, EA |
| Copier copy on the page | Yes, duplicated | Removed |
| Schema | `SoftwareApplication`, `FAQPage` | `SoftwareApplication`, `Offer`, `BreadcrumbList`, `FAQPage` |
| Duplicate Black Friday bars | 11 | 1 |

**What the old page was doing:** it had a reasonable H1 and nine FAQs, but the title was the brand only, the body included a duplicated block about spread, slippage and "SSF copier", and no section explained what a drawdown EA is. Google had no category phrase to rank.

**What the new page does differently:**

1. Puts "prop firm drawdown EA" in the title and "prop firm drawdown protection" in the H1.
2. Defines a drawdown EA in the first content section.
3. Replaces the copier block with eight Guardian-only features.
4. Adds how-it-works, a $10,000 limit example, compatibility table and pricing.
5. Adds three FAQs: automatic close, any prop firm, and "is it a trade copier?".

**What still needs work**

1. The category terms have no GSC history here. Internal links from the prop-firm EA blog and the copier page will decide whether this ranks.
2. The page needs the real checkout link and a confirmation of the $19.99 / 2-account licence.
3. Claims about "any prop firm" should stay qualified, because firms calculate daily loss differently.
