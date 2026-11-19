# Pip Calculator App — what changed from the live page

Rebuild of `https://sureshotfx.com/pip-calculator-mobile-app` as a single Tailwind-CDN HTML file. Same design system as the rebuilt signal, combo, copier and lot-size pages — brand `#00F595`, black base, Sora + Inter — with a teal accent matching the Android app UI.

**Size:** 84 KB, 2,412 visible words (live: 871), 15 sections, 13 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the same promo 11 times in the visible DOM | One announcement bar with a live countdown |
| **25-destination mega menu** | Not needed on a single app landing page | 6 anchor links + Free Signals + Download |
| **App Store (iOS) badge** | The linked listing returns **HTTP 404** and iTunes `lookup?id=6740566255` returns **0 results**. Shipping a dead download button is worse than omitting it | Google Play button + a plain note that the iOS listing is currently unavailable + a web-calculator fallback |
| **One-paragraph hero** | H1 was "Understand the Potential Profit or Loss of Trade" and never named the product | H1 that names the app and its markets, plus a Play CTA, rating and downloads |
| **Recognize By badge images** | Assets not supplied | Omitted — supply the files if they should return |

Nothing factual was deleted: the live page's single claim about profit and loss is now covered by the features section, the pip section and the buy/sell example.

---

## 2. Added

### 2.1 Hero

- H1 "Pip Calculator App for Forex, Gold & Indices".
- Two-paragraph intro on pip value and the SL/TP amounts.
- Google Play button linking to `org.dasadweb.sureshotfx`, plus a secondary link to the web calculator.
- Real store figures: **4.0 stars, 134 reviews, 10,000+ downloads** (read from the Play listing on 19 Nov 2026).
- Transparent hero image of three phones showing an actual XAUUSD calculation.
- A visible iPhone note instead of a dead App Store badge.

### 2.2 Features (from the Play listing)

Ten cards: multiple currencies, all forex pairs, indices, gold and silver, lot size and entry price, SL and TP prices, custom contract size, separate buy and sell, and profit/loss in the account currency.

### 2.3 Screenshots

Six real Android screens in a grid, each opening a lightbox: forex pairs, indices pairs, custom contract size, multiple currencies, buy calculation, sell calculation. Sources are the app's own Play listing images, re-encoded to ~25–33 KB each.

### 2.4 New sections

| Section | Covers | Notes |
|---|---|---|
| Trust strip | free, 10k+, 4.0★ | Store facts only |
| Features | ten app features | As listed on Google Play |
| Screenshots | six app screens | With a working lightbox |
| How it works | four fields | Instrument → lot/entry → SL/TP → calculate |
| What is a pip | pip education | Definition, JPY convention, formula, pip-value table |
| Markets | forex, metals, indices | Contract notes and links to the three VIP pages |
| Buy vs sell | long vs short | Real numbers from the shipping screens (198 pips/$198, 202/$202, 102/$102) |
| Download | free download | Play CTA, store figures, iPhone note |
| Web fallback | no Android? | Links to the browser pip and lot calculators |
| Black Friday | VIP cross-sell | Countdown, Combo CTA, free signals |
| FAQ | 13 questions | Free, iPhone, pairs, gold, indices, maths, accuracy, login, web version, official app |
| Popular searches | 17 chips | Includes all six product queries |
| Support | app support | Telegram, Arabic line |
| Newsletter | weekly brief | Same as the other rebuilds |

### 2.5 Technical SEO

- JSON-LD: `MobileApplication` (Android, free offer, download URL), `BreadcrumbList`, `FAQPage` (8 questions).
- **No `aggregateRating`** — the 4.0 rating is a Play-store figure shown as text, not a rating collected on this page.
- Semantic headings, `<details>` FAQ, internal links to `/pip-calculator/forex-pip-calculator`, `/lot-size-calculator`, `/forex-vip-signals`, `/gold-vip-signals`, `/indices-vip-signals`, `/trade-copier`, `/combo`, `/live-signals`, `/blog`.
- Local assets in `assets/` (hero, icon, six screenshots) instead of hotlinks.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Understand the Potential Profit or Loss of Trade" | "Pip Calculator App for Forex, Gold & Indices" | The live H1 never names the product |
| Title tag | "Pip Calculator Mobile App - SureShotFX" | "Pip Calculator App for Forex, Gold & Indices \| SureShotFX" | Product + markets, matches the query `pip calculator app` |
| Meta description | "Calculate the potential profit or loss of trade…" | "Free pip calculator app for Android. Work out pip value, profit and loss for forex pairs, XAUUSD and indices — 10,000+ downloads, 4.0 stars on Google Play." | Adds platform, instruments, price and social proof |
| Download CTA | "Download for free" text link | Official-style Play button + rating + downloads | Store proof instead of a bare text link |
| iOS availability | App Store badge linking to a 404 | Plain note + web fallback | Removes a broken download |
| Screenshots | One composite image | Composite hero plus six enlargable app screens | Proves the app exists before the install |
| Pip explanation | None | Definition, formula, pip-value table, buy/sell numbers | The queries are about pips, so the page now explains them |
| Page structure | H1 + paragraph | 15 sections | Features, screenshots, education, FAQ, support |

---

## 4. Before going live

1. **Resolve the iOS listing.** This is the biggest issue on the page. The live App Store link is dead: `https://apps.apple.com/us/app/sureshotfx-pip-calculator/id6740566255` returns 404 and `https://itunes.apple.com/lookup?id=6740566255` returns `resultCount: 0`. Either relist the app and restore the badge, or ship the Android-only version built here. Do not restore a broken badge.
2. **Confirm the store figures.** 4.0 stars, 134 reviews, 10,000+ downloads were read from the Play listing on 19 Nov 2026. Re-check before launch or render them server-side.
3. **Confirm the gold convention.** The screenshots imply one gold pip = 0.10 and 0.10 lots ≈ $1 per pip. Verify against the current Android build before publishing the pip-value table.
4. **Check the "up to 72%" banner** against the live sale.
5. **Confirm the in-app free-signals claim.** The screenshots show a "Get FREE Telegram Signals" button; the page repeats it. Verify the button still exists and does not upsell.
6. **Add an OG image** and supply the Recognize By badge images if they should return.
7. **Review the Arabic support line** with a native speaker.
8. **Set the countdown end date** (`2026-11-30T23:59:59Z`) and remove the bar after the sale.
9. **Confirm screenshot usage rights.** The six screens come from the app's own Play listing, which is the client's property, so reuse is expected — but confirm.

---

## 5. Verification performed

- Desktop 1440×1000 and tablet 1024×800: no horizontal overflow; header nav fits; H1 stays on three lines at 1024; hero image renders on the transparent background correctly.
- Mobile 390×844 (touch emulation) and 320×700: no horizontal overflow, sticky CTA visible, mobile menu opens inside the viewport, two-column screenshot grid readable.
- All nine images load (hero, app icon, six screenshots). Lazy-loaded ones load on scroll.
- Lightbox opens on each of the six screenshots, shows the correct image and caption, and closes via the ✕ button (also verified `dialog.open` toggles).
- Lightbox width bug found and fixed: `w-auto` stretched the dialog to 92 vw. It now uses `w-fit`, so the dialog fits the image.
- All in-page anchors resolve (`features`, `screenshots`, `how`, `pips`, `markets`, `download`, `faq`); no duplicate IDs.
- 13 FAQ items; `textContent` covers 7 of the 8 GSC queries (all except the technical `site:` operator).
- JSON-LD parses (`MobileApplication`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked with a parser; UTF-8 clean, no mojibake.
- Only console messages are the expected Tailwind CDN warning and the lazy-image dimension audit note (all images carry `width` and `height`).
