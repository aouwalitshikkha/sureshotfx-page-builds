# SureShotFX Guardian: what changed from the live page

Rebuild of `https://sureshotfx.com/sureshotfx-guardian` as a single Tailwind-CDN HTML file. Same design system as the other rebuilds, with a green-to-amber guard accent.

**Size:** 70 KB, 1,953 visible words (live: 1,765), 12 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **Trade Copier feature block** | "Dynamic Spread", "Exclude Trade", "Set Slippage" and "SSF copier is your friend" describe the copier, not Guardian | Eight drawdown-specific features |
| **Duplicated feature block** | The copier block appeared twice on the page | One feature grid |
| **Brand-only title** | "SureShotFX Guardian - SureShotFX" gave Google no category | "Prop Firm Drawdown EA for MT4 & MT5" |
| **Awkward H1 spacing** | "Max/ Daily Loss Limit" | "Prop Firm Drawdown Protection for MT4 & MT5" |
| **11 stacked Black Friday bars** | Repeated promo | One bar with countdown and coupon |
| **25-destination mega menu** | Not needed on a product page | 6 anchor links + Get Guardian |

---

## 2. Added

### 2.1 Category content

| Section | Covers | Notes |
|---|---|---|
| What is a drawdown EA? | prop firm drawdown EA | Definition, TL;DR, key takeaways |
| Features | daily / overall drawdown | Eight Guardian-only cards |
| How it works | prop firm challenge EA | Three steps + a $10,000 limit example |
| Compatibility | MT4/MT5 drawdown EA | Table: platforms, accounts, firms, updates |
| Pricing | Guardian EA | $19.99, 2 accounts, GUARDIAN19 |
| FAQ | commercial objections | 12 questions, including "is it a copier?" |

### 2.2 A visual explanation

The hero now includes an **illustrative Guardian console**: daily loss against a $500 limit, overall drawdown against a $1,000 limit, status, reset time, Telegram alerts and the CLOSE command. It is labelled as an example, not a live account.

### 2.3 Technical SEO

- JSON-LD: `SoftwareApplication` (9 features, $19.99 offer, `priceValidUntil`), `BreadcrumbList`, `FAQPage` (6 questions).
- No `aggregateRating`.
- One H1, question-led H2s, `<details>` FAQ, internal links to the copier, the prop-firm EA guide, the calculator, VIP signals and the blog.
- No images, so the page is fast and cannot break on a CDN change.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| Title | "SureShotFX Guardian - SureShotFX" | "Prop Firm Drawdown EA for MT4 & MT5 \| SureShotFX Guardian" | Category + brand |
| H1 | "Protect Your Funded Account From Max/ Daily Loss Limit" | "Guardian: Prop Firm Drawdown Protection for MT4 & MT5" | Keyword-led and grammatical |
| Meta | "SSF Guardian offers real-time monitoring…" | "Guardian is a drawdown EA for prop firm challenges. Set daily and overall loss limits, auto-close trades at the limit and get Telegram alerts. $19.99 lifetime for 2 accounts." | States the product, limits and price |
| Price | $29.99 → $19.99, no saving label | Same numbers, "Save 33%" and a six-item includes list | Clearer offer |
| Reviews | Three quotes, "sureshotf" typo | Same quotes, brand typo corrected, one light edit | Readability |
| H1 size | 3.4rem at desktop, 4 lines | 2.8rem, three lines | Removes the orphaned "MT5" line |
| Disclaimer | Standard software disclaimer | Adds "no guarantee of a challenge pass" | Honest claim |

---

## 4. Before going live

1. **Connect the checkout.** The CTA is a placeholder (`#pricing`). Apply GUARDIAN19 in the real checkout.
2. **Confirm the licence.** $19.99 lifetime for 2 accounts, MT4 and MT5, free updates.
3. **Confirm the prop-firm claim.** The page says "any MT4/MT5 firm that permits EAs". Do not name firms without confirmation.
4. **Confirm "runs beside other EAs"** with the current build, and the CLOSE command behaviour.
5. **Approve the review edits** (Christ, Lenny Pasho, Dominiq Diosio).
6. **Keep the "no guaranteed pass" line** in marketing and support replies.
7. **Label the console mock** as illustrative if the design changes; it is not a screenshot.
8. **Check the 72% banner** elsewhere on the site; Guardian uses its own 33% discount.
9. **Add an OG image** and set the countdown end date.

---

## 5. Verification performed

- Desktop 1440×1000, mobile 390×844 and 320×700: no horizontal overflow; hero, features and pricing checked visually.
- Countdown ticks; anchors resolve (`features`, `how`, `compatibility`, `pricing`, `reviews`, `faq`); no duplicate IDs.
- 12 FAQ items; JSON-LD parses (`SoftwareApplication`, `BreadcrumbList`, `FAQPage`); HTML balance checked.
- Zero em dashes and no AI-footprint filler.
- Only console message is the Tailwind CDN warning.
