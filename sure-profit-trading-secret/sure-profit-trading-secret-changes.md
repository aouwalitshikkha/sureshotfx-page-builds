# Sure Profit Trading Secret: what changed from the live page

Rebuild of `https://sureshotfx.com/sure-profit-trading-secret` as a single Tailwind-CDN HTML file. Same design system as the other rebuilds, with a gold accent taken from the book cover.

**Size:** 67 KB, 1,785 visible words (live: 1,236), 9 H2 sections, 10 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the promo 11 times in the DOM | One announcement bar with a live countdown |
| **25-destination mega menu** | Not needed on a product page | 5 anchor links + Get the book |
| **Four H1s** | The live page uses H1 for the hero, a second headline, the reviews heading and the offer heading | One H1: product name + category |
| **Generic "secret strategy" hero** | It never says what the product is or who it is for | H1 and opening paragraph name the beginner forex book |
| **Payment-gateway image** | A screenshot of payment logos adds no information | Text note: secure checkout, contact support if a method is missing |
| **"Recognize By" badge images** | Assets not supplied | Omitted |
| **Repeated pricing CTAs** | The live page repeats the same offer block twice | One pricing card |

Nothing factual was deleted. The $4.99 price, the four learning bullets, the three reviews and the limited-offer framing are all still present.

---

## 2. Added

### 2.1 Structure

| Section | Covers | Notes |
|---|---|---|
| Hero | forex trading book for beginners | Book cover, $4.99 CTA, 81 pages / 6 chapters |
| Quick facts | format, level, delivery | Four-fact strip |
| What is it | forex trading ebook | Definition, TL;DR, key takeaways |
| What's inside | forex technical analysis book | Six chapters with page ranges from the cover |
| Who it's for | beginner forex trading book | Beginners, stuck traders, intermediate refresher |
| What you will learn | learn forex trading book | Six outcome cards |
| Reviews | product name | Three live reviews, punctuation cleaned |
| Author | SureShotFX desk | Credentials and experience |
| Pricing | forex trading book pdf | $4.99 card, includes list, checkout |
| Cross-sell | Behind the Candle / VIP signals | Beginner vs advanced path |
| FAQ | format, level, pages, delivery | 10 questions |
| Support / newsletter / footer | — | Standard components |

### 2.2 A real contents breakdown

The cover image shows the book's contents page. That gave six chapter names and page ranges:

1. Mindset For Trading, p. 1-12
2. Trading Economics, p. 12-20
3. Start Trading, p. 23-36
4. Understanding The Market, p. 39-58
5. Technical Analysis In-Depth, p. 58-71
6. Introduction To Trading Patterns, p. 72-81

This is the first time the page has told a buyer what is actually inside.

### 2.3 Technical SEO

- JSON-LD: `Book` (81 pages, EBook, $4.99 offer), `BreadcrumbList`, `FAQPage` (6 questions).
- No `aggregateRating`.
- One H1, question-led H2s, `<details>` FAQ, internal links to Behind the Candle, the lot size calculator, VIP signals, the blog and the book list.
- Local assets, no hotlinks.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| Title | "Sure Profit Trading Secret - SureShotFX" | "Forex Trading Book for Beginners \| Sure Profit Trading Secret" | Category + brand |
| H1 | "UNLOCK PROVEN FOREX TRADING STRATEGIES…" plus three more H1s | "Sure Profit Trading Secret: A Forex Trading Book for Beginners" | One H1, product + category |
| Meta | "…sure profit trading secrets premium trading book" | "An 81-page beginner forex trading book covering technical analysis, indicators, market basics and how to place a trade. Instant PDF for $4.99." | Category, format and price |
| Author | "our years of experience" | "SureShotFX trading desk" | Names the source without inventing a person |
| Reviews | Three quotes with "AV" avatars | Same quotes with initials, light punctuation edits | Readability |
| Price block | Repeated twice, no includes list | One card with six inclusions and a support note | Clearer offer |
| BF banner | Sitewide "up to 72%" only | "VIP plans up to 72% off · this ebook stays $4.99" | Does not imply the book is discounted |

---

## 4. Before going live

1. **Connect the checkout.** The CTA is a placeholder (`href="#pricing"`). Replace it with the live payment flow or a hosted checkout link.
2. **Confirm the page count.** 81 pages and the chapter page ranges come from the contents page shown on the cover image. Verify against the current PDF.
3. **Confirm the $4.99 price** and whether the offer still has an end date. The live page says "limited offer" but publishes no date.
4. **Confirm the author credit.** The live page says "our years of experience", not a named author. The rebuild says "SureShotFX trading desk".
5. **Approve the review punctuation edits** (Ben, Kennedy, Nia).
6. **Check the 72% banner** against the live sale. The book itself is not part of that discount.
7. **Confirm cover image usage** and add an OG image.
8. **Supply the Recognize By badges** if they should return.
9. **Set the countdown end date** (`2026-11-30T23:59:59Z`).

---

## 5. Verification performed

- Desktop 1440×1000: no horizontal overflow; hero, chapter grid and pricing checked visually.
- Mobile 390×844 and 320×700: no horizontal overflow; hero CTAs stack; sticky CTA visible; H1 forced to a clean two-block break.
- Cover image loads on the paper card; the contents text is legible.
- Countdown ticks; all in-page anchors resolve (`inside`, `who`, `reviews`, `pricing`, `faq`); no duplicate IDs.
- 10 FAQ items; JSON-LD parses (`Book`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked.
- Zero em dashes and no AI-footprint filler.
- Only console message is the Tailwind CDN warning.
