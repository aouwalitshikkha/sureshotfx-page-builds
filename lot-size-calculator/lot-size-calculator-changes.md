# Lot Size Calculator — what changed from the live page

Rebuild of `https://sureshotfx.com/lot-size-calculator` as a single Tailwind-CDN HTML file. Same design system as the rebuilt signal, combo and copier pages — brand `#00F595`, black base, Sora + Inter — with a green accent and gold/sky tab states for the gold and indices modes.

**Size:** 124 KB, 4,220 visible words (live: 1,542), 16 sections, 16 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the same promo 11 times in the visible DOM | One announcement bar with a live countdown |
| **25-destination mega menu** | Not needed on a single tool page | 7 anchor links + Free Signals + Buy Now |
| **"Loading exchange rates…" placeholder** | The live widget shows the placeholder text in the static HTML and only resolves after JS | Live mid-market rates with an explicit "updated" date and an offline fallback |
| **Static "Money: 0.00 / Lots: 0.000" result** | The live markup ships zeroed output; if JS fails the page shows a false result | The result is calculated on load and every input change, with a visible error state |
| **Recognize By badge images** | Assets not supplied | Omitted — supply the badge files and they can return in the footer |
| **The 3-question FAQ** | Too thin for 613 queries | Kept all three, expanded to 16 |

Nothing factual was deleted: the lot-size table, the 15-pip example, the six-step how-to, the benefits list, the FAQ answers and every disclaimer are still present.

---

## 2. Added

### 2.1 A working calculator

The live page has five inputs and two outputs. The rebuild keeps the same mental model and adds:

| Feature | Detail |
|---|---|
| **Three modes** | Forex, Gold (XAUUSD/XAGUSD), Indices (US30, NAS100, SPX500, GER40, UK100, JP225) |
| **30 account currencies** | USD, EUR, GBP, JPY, CHF, CAD, AUD, NZD, SGD, HKD, AED, SAR, INR, PKR, PHP, NGN, ZAR, TRY, MXN, PLN, SEK, NOK, DKK, CNY, KRW, THB, IDR, MYR, VND, BRL |
| **16 forex pairs** | Majors, JPY crosses and EUR/GBP/AUD crosses, with quote-currency conversion |
| **Live exchange rates** | `open.er-api.com` mid-market rates, with a built-in fallback table if the fetch fails |
| **Result detail** | Lot size, risk amount, pip/point value, position size in units, loss at stop, and the formula with the actual numbers |
| **Broker-step rounding** | Rounds **down** to 0.01 and shows the raw value, because 0.537 lots is not tradeable |
| **Minimum-lot warning** | If the correct size is below 0.01, the panel says so instead of showing a false 0.01 |
| **Quick chips** | Balance 1k/5k/10k/50k and risk 0.5/1/2/3% |
| **Copy result** | Copies a one-line summary (lots, instrument, risk, stop, loss) to the clipboard |
| **Validation** | Zero balance, >100% risk, zero stop and missing point value all produce a readable error |
| **Editable point value** | Indices default to $1 per point, but the user can enter their broker's tick value |

### 2.2 Content sections that did not exist

| Section | Covers | Notes |
|---|---|---|
| Quick answers | 1 lot, 0.01 lot, $1,000, $10,000 | Four cards with the numbers people search for |
| Lot sizes | standard/mini/micro/nano | Table with units, pip value and best use; 15-pip example |
| What is a lot size calculator | position size, forex risk calculator | Two definition cards |
| Search terms | 12 word-order and misspelling variants | Explains that they all mean the same tool |
| How to use | six inputs | Live page had this; kept and tightened |
| Formula | lot size formula | Formula box + EURUSD, XAUUSD and US30 worked examples + pip-value table by pair type |
| Gold | XAUUSD/XAGUSD | 100 oz contract, $1 per point, stop-loss calculator framing, two worked risk cards |
| Indices | US30/NAS100/SPX500 | Contract-size warning, how to find tick value in MT4/MT5, one-line formula |
| MT4/MT5 | platform placement | Volume field, minimum/step, where to read the specification |
| Risk management | 1–2% rule | Table from $100 to $100,000, leverage, cent accounts, prop firms |
| Benefits | six live benefits | Kept, restructured as cards |
| Black Friday cross-sell | VIP signals | Countdown, Combo CTA, link to Forex VIP |

### 2.3 FAQ expanded 3 → 16

The three live questions are kept word-for-word in intent:

1. Can I use the SureShotFX lot calculator for a micro account?
2. Do I need to know the pip value manually?
3. What is a position size calculator?

Added: what a lot size calculator is, how to calculate lot size in forex, MT4/MT5 support, gold/XAUUSD, indices, the $1,000 answer, 0.01 lot in dollars, leverage, cent accounts, prop firms, broker differences, whether it is free, and whether it is the official SureShotFX tool.

### 2.4 Technical SEO

- JSON-LD: `WebApplication` (free offer), `HowTo` (6 steps), `BreadcrumbList`, `FAQPage` (8 questions) — parity with the live page's `WebApplication` + `HowTo` + `FAQPage`.
- No `aggregateRating`.
- Semantic headings, `<details>` FAQ (answers stay in the HTML), internal links to `/pip-calculator/forex-pip-calculator`, `/trade-copier`, `/forex-vip-signals`, `/gold-vip-signals`, `/indices-vip-signals`, `/combo`, `/live-signals`, `/blog`.
- `html { background:#000; color-scheme: dark }` so the scrollbar and overscroll canvas stay dark.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Lot Size Calculator: Find the Right Forex Trade Size" | "Lot Size Calculator for Forex, Gold & Indices" | Names the three instruments the tool actually supports |
| Title tag | "SureShotFX Lot Size Calculator for Better Risk Control" | "Lot Size Calculator — Forex, Gold & Indices \| SureShotFX" | Category first, brand last, within display limits |
| Meta description | "Calculate exact lot size for trades instantly using SureShotFX lot size calculator for Forex trading. Manage risk and trade precisely." | "Free lot size calculator for forex, gold and indices. Enter your balance, risk percentage and stop loss to get the exact lot size for MT4 and MT5 — no signup." | States the inputs, platforms and the no-signup objection |
| Calculator result | Money + standard lots | Lots, risk, pip/point value, units, loss at stop, formula | The extra fields answer "why is it that number?" |
| Risk input | Free number | 0.01–100 validation + quick chips | Prevents the "risk 1000%" input that returns nonsense |
| Default state | Zeroed until calculated | EURUSD, $10,000, 1%, 20 pips → 0.50 lots | A visitor sees a correct result immediately |
| FAQ heading | "Frequently Asked Questions" / "All You Need to Know About the Lot Size Calculator" | "Lot Size Calculator — Common Questions" | Names the tool |
| FAQ answer "how to calculate" | Not present | "How to calculate lot size in forex?" with the formula | 142 impressions at position 31.3 |
| Gold copy | A "Gold Calculator" tab with no explanation | 100 oz contract, $1 per point, worked example, risk cards | 89 gold queries had nothing to match |
| Indices copy | A tab with no explanation | Contract-size warning, tick-value instructions, example | 19 index queries, 0 covered before |
| Tables at 320 px | N/A | Horizontal scroll inside the card, page never overflows | The four-column tables cannot fit 320 px without clipping |

---

## 4. Before going live

1. **Decide on the exchange-rate API.** The calculator fetches `open.er-api.com` in the browser. That sends the visitor's IP to a third party and adds an external dependency. Options: keep it (free, no key, daily rates), proxy it server-side, or ship a static rate table with a visible "reference rates" label.
2. **Confirm index contract sizes.** The Indices tab defaults to **$1 per point per lot**, which matches many CFD brokers but not all. Check the brokers your audience uses (US30, NAS100, SPX500, GER40, UK100, JP225) and adjust the defaults if needed.
3. **Confirm the gold/silver contract sizes.** XAUUSD 100 oz and XAGUSD 5,000 oz are the common retail specs. Cent and non-US brokers sometimes differ.
4. **Check the "up to 72%" banner.** It is the sitewide claim, carried into the Black Friday cross-sell. The calculator page itself sells nothing, so the claim is inherited — make sure it matches the live sale.
5. **Add an OG image.** `og:image` is not set because no asset was supplied.
6. **Supply the Recognize By badge images** if they should return to the footer.
7. **Review the Arabic support line** with a native speaker.
8. **Set the countdown end date** (`2026-11-30T23:59:59Z`) and remove the bar after the sale.
9. **Confirm the support link** (`https://t.me/ssf_adminbot`) is still the correct Telegram entry point.
10. **Validate the HowTo schema** after any change to the six steps, or Google may drop the rich result.

---

## 5. Verification performed

- Desktop 1440×1000, 1280×800 and tablet 1024×800: no horizontal overflow; header nav fits on one line; hero and calculator checked visually.
- Mobile 390×844 (touch emulation) and 320×700: no horizontal overflow; calculator stacks; sticky CTA visible; mobile menu opens inside the viewport.
- Calculator maths checked by hand:
  - EURUSD, $10,000, 1%, 20 pips → 0.50 lots, $100 risk, $10/pip, 50,000 units.
  - XAUUSD, $5,000, 1%, 500 points → 0.10 lots, $50 risk, $1/point, 10 oz.
  - US30, $10,000, 1%, 100 points, $1/point → 1.00 lot; at $10/point → 0.10 lots.
  - EUR account on EURUSD: $10 pip value converts to €9.11 and the result scales correctly.
  - Balance 0, zero stop and >100% risk produce readable errors.
  - Reset restores EURUSD / $10,000 / 1% / 20 pips; Copy flips to "Copied!".
- Live rates loaded ("Live mid-market rates · updated 19 Nov"); the fallback path is in place for offline use.
- All in-page anchors resolve (`calculator`, `lot-sizes`, `how`, `formula`, `gold`, `indices`, `mt4-mt5`, `faq`); no duplicate IDs.
- 16 FAQ items; `textContent` covers 106 of 613 GSC queries (98 of 560 English product-intent queries) — see the coverage comparison.
- JSON-LD parses (`WebApplication`, `HowTo`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked with a parser; UTF-8 clean, no mojibake.
- Only console message is the expected Tailwind CDN warning.
