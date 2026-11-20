# Behind the Candle: what changed from the live page

Rebuild of `https://sureshotfx.com/behind-the-candle` as a single Tailwind-CDN HTML file. Same design system as the other rebuilds, with a gold-to-emerald accent taken from the cover.

**Size:** 75 KB, 2,261 visible words (live: 2,566), 5 chapter rows, 10 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the promo 11 times | One bar with a countdown and the FIRSTREAD code |
| **25-destination mega menu** | Not needed on a product page | 5 anchor links + Get the book |
| **Hotlinked cover and media images** | A CDN path change would break the page | Local assets in `assets/` |
| **Duplicate media-logo strip** | The live page renders the "As featured on" logos twice | One strip, six logos |
| **Payment-gateway image** | A screenshot of payment logos adds no information | Text note with the support handle |
| **"Recognize By" badges** | Assets not supplied | Omitted |

The sales copy, 5 chapters, 10+ examples, 3 reviews, 8 FAQs, author bio and $24.99 price are all retained.

---

## 2. Added

### 2.1 Category targeting

The H1 previously said only "Behind the Candle". It now says:

> Behind the Candle
> The Smart Money Concepts Book

The title, meta description and opening paragraph use "SMC trading book" and "smart money concepts PDF", the phrases the category actually searches for.

### 2.2 New sections

| Section | Covers | Notes |
|---|---|---|
| TL;DR | smart money concepts book | Definition and price in one box |
| Book summary | summarise the book | Five chapters, explicit chapter overview |
| SMC glossary | smart money concepts | Six definitions: SMC, liquidity sweep, MSB, order block, FVG, breaker zone |
| Liquidity | liquidity types | Four named pools; notes the book maps six |
| Entry model | SMC entry model | Four steps plus a four-stage stop-hunt example |
| Risk math | 1:2 R:R | 3/7, 4/6, 5/5 and 6/4 win tables with a disclaimer |
| Who it's for | intermediate traders | Includes "start with Sure Profit" routing |
| FAQ | level, SMC, PDF | 10 questions, including two new ones |

### 2.3 Technical SEO

- JSON-LD: `Book` (Person author, EBook, $24.99 offer, `priceValidUntil`), `BreadcrumbList`, `FAQPage` (6 questions).
- No `aggregateRating`.
- One H1, question-led H2s, `<details>` FAQ, internal links to Sure Profit, VIP signals, the lot size calculator, the blog and the book list.
- Media logos and cover are local.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| Title | "Behind the Candle: A Trader's Guide to Liquidity & Precision Entries" | "Behind the Candle: Smart Money Concepts Book \| SureShotFX" | Adds the category |
| H1 | "Behind the Candle" | "Behind the Candle: The Smart Money Concepts Book" | Brand plus category |
| Meta | Long feature list | "An advanced SMC book: market structure, six liquidity types, order blocks, fair value gaps and a criteria-based entry model with 10 worked examples. $24.99 PDF." | Keyword-led and under 160 characters |
| H2s | Creative labels | Question-led: What is it, What's inside, What are smart money concepts, How does the entry model work | Extractable structure |
| FAQ | 8 questions | 10 questions | Adds "What is SMC trading?" and "Is it a PDF?" |
| Cover asset | 1.3 MB PNG | 87 KB JPEG at 760×1074 | Faster load |
| Price card | $50 struck, $24.99, coupon | Same numbers, includes list and support note | Clearer offer |
| Media strip | Duplicated | Single local strip | Less repetition |

---

## 4. Before going live

1. **Connect the checkout.** The CTA is a placeholder (`href="#pricing"`). Apply the FIRSTREAD coupon in the real checkout.
2. **Confirm the six liquidity types.** The live copy says six but names four. The rebuild names the four and says the book maps six. Supply the other two if the page should list all six.
3. **Check the risk math.** 4 wins and 6 losses at 1:2 is +2R before costs. The table excludes spreads, commissions and slippage, and says so.
4. **Confirm the $50 reference price** and the 50% saving, plus the coupon's expiry.
5. **Confirm media-logo usage rights** for AP News, Digital Journal, Business Insider, Street Insider, Benzinga and Apple News.
6. **Approve the review quotes** (James O., Khalid M., Priya R.) and the author bio.
7. **Check the "up to 72%" claim** elsewhere on the site; this page uses the product's own 50%.
8. **Add an OG image**, supply the Recognize By badges if needed, and set the countdown end date.

---

## 5. Verification performed

- Desktop 1440×1000: no horizontal overflow; hero, chapter rows, glossary and pricing checked visually.
- Mobile 390×844 and 320×700: no horizontal overflow; CTAs stack; sticky CTA visible.
- Cover and all six media logos load locally.
- All in-page anchors resolve (`inside`, `smc`, `author`, `reviews`, `pricing`, `faq`); no duplicate IDs.
- 10 FAQ items; JSON-LD parses (`Book`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked.
- Zero em dashes and no AI-footprint filler.
- Only console message is the Tailwind CDN warning.
