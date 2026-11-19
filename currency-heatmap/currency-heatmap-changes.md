# Currency Heat Map — what changed from the live page

Rebuild of `https://sureshotfx.com/currency-heatmap` as a single Tailwind-CDN HTML file. Same design system as the rebuilt signal, combo, copier, lot-size and pip-app pages — brand `#00F595`, black base, Sora + Inter — with a green→sky→gold accent for the heat gradient.

**Size:** 60 KB, 1,597 visible words (live: 828), 7 sections, 10 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **Third-party TradingView iframe** | The live page's entire product is an embedded widget. The client does not own the data, the layout or the content, and the page has nothing for Google to index | A self-contained 8×8 grid computed in the page from live daily rates |
| **11 stacked Black Friday bars** | The live page repeats the promo 11 times in the visible DOM | One announcement bar with a countdown |
| **25-destination mega menu** | Not needed on a single tool page | 5 anchor links + Free Signals + Buy Now |
| **"Avoid blowing out your account" as a one-line slogan** | The line is good; the page did nothing with it | A full correlation/risk section that shows the arithmetic |
| **Recognize By badge images** | Assets not supplied | Omitted — supply the files if they should return |

---

## 2. Added

### 2.1 A working heat map

| Feature | Detail |
|---|---|
| **56 pairs** | 8 majors (EUR, USD, GBP, JPY, AUD, CAD, CHF, NZD) in an 8×8 matrix |
| **Three timeframes** | 1 day, 1 week, 1 month, each computed from the same rate set |
| **Live data** | European Central Bank daily reference rates via Frankfurter, loaded on page open |
| **Colour scale** | Green = base outperforming, red = underperforming, grey = flat; intensity scales with the move |
| **Biggest movers** | Top three and bottom three pairs for the selected timeframe |
| **Pair detail** | Click any cell for price, 1D/1W/1M changes and a plain-English read |
| **Focus filter** | Highlight one currency's row and column; the movers list follows the filter |
| **Refresh** | Re-fetches the rate set without a page reload |
| **Graceful fallback** | If the API fails, the grid renders clearly labelled illustrative values instead of a blank box |

### 2.2 Content sections that did not exist

| Section | Covers | Notes |
|---|---|---|
| How to read it | colour meanings, relative strength | Four colour cards + three limits of the tool |
| Timeframes | 1D / 1W / 1M | What each window is for, and why the same pair can be green on one and red on another |
| Correlation | risk stacking | The "one thesis, three tickets" table: three 1% longs = 3% on one dollar move |
| FAQ | 10 questions | Data source, prediction limits, liquidity/gold, official app, free |
| Popular searches | 12 chips | All heat-map spellings, plus `liquidity heatmap gold` |
| Support / newsletter / footer | — | Same components as the other rebuilds |

### 2.3 Technical SEO

- JSON-LD: `WebApplication` (free offer, 56 pairs), `BreadcrumbList`, `FAQPage` (6 questions).
- No `aggregateRating`.
- Semantic headings, `<details>` FAQ, internal links to `/lot-size-calculator`, `/pip-calculator/forex-pip-calculator`, `/pip-calculator-mobile-app`, `/forex-vip-signals`, `/gold-vip-signals`, `/trade-copier`, `/combo`, `/live-signals`, `/blog`.
- Arabic subheading for the query `الخريطة الحرارية للفوركس` (4 impressions), reviewed as a single line rather than a fake translation.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Heat-Map" | "Currency Heat Map — Live Forex Strength & Weakness" | The live H1 does not contain the query |
| Title tag | "Currency Heatmap - SureShotFX" | "Currency Heat Map — Live Forex Strength & Weakness \| SureShotFX" | Covers both spellings |
| Meta description | "Visualize currency strength and weakness across multiple timeframes…" | "Free live currency heat map for forex. Compare currency strength and weakness across 1 day, 1 week and 1 month…" | Tool + data + timeframes |
| Data source | TradingView widget | ECB daily reference rates via Frankfurter | Owns the tool and the markup |
| Default timeframe | Widget default | **1 week** | Daily snapshots make a 1-day view flat until the next ECB publication; 1 week is the useful first read |
| "Live" wording | Implied by the widget | "ECB reference rates via Frankfurter · date" | It is a daily reference rate, not a tick feed |
| Page copy | One line | Six content sections + FAQ | The live page had nothing to index |

---

## 4. Before going live

1. **Confirm the data arrangement.** The page calls `api.frankfurter.dev` in the browser (free, no key, CORS open; rates are ECB daily reference rates, usually published around 16:00 CET on business days). It is not a broker feed and not intraday. If you need intraday heat, that requires a paid tick provider.
2. **Label it correctly in marketing.** "Live" in the hero means "current published rates", not streaming. The status line and FAQ both say ECB reference rates; keep that wording if the hero copy is edited.
3. **Decide on TradingView.** This build removes the embed. If the client prefers to keep the widget, it can be added back as a secondary block — but the self-contained grid should stay for SEO.
4. **Check the "up to 72%" banner** against the live sale.
5. **Add an OG image** and supply the Recognize By badges if they should return.
6. **Review the Arabic line** with a native speaker.
7. **Set the countdown end date** (`2026-11-30T23:59:59Z`).
8. **Keep the "not a liquidity map" answer.** It protects the page from a query it cannot honestly satisfy (`liquidity heatmap gold`).

---

## 5. Verification performed

- Desktop 1440×1000: no horizontal overflow; hero, grid, movers and detail panel checked visually.
- 1024×800: header nav fits; grid remains readable.
- Mobile 390×844 and 320×700: page never overflows; the 680 px grid scrolls inside its own container; a "swipe" hint is shown under the grid.
- Live data loaded (ECB reference date 2026-11-18). Sample checks: EURUSD −1.02% on 1W, −2.20% on 1M; USD/EUR detail price 0.91174; movers top JPYAUD +1.51%, bottom AUDJPY −1.49%.
- Timeframe buttons recalculate the grid and movers; focus filter dims non-matching cells and filters the movers; clicking a cell updates the detail panel; refresh re-fetches.
- All in-page anchors resolve (`heatmap`, `read`, `timeframes`, `correlation`, `faq`); no duplicate IDs.
- 10 FAQ items; `textContent` covers 7 of the 8 GSC queries (all except `site:`).
- JSON-LD parses (`WebApplication`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked with a parser; JS syntax checked with `node --check`; UTF-8 clean.
- Only console message is the expected Tailwind CDN warning.
