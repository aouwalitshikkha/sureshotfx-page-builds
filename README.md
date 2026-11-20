# SureShotFX page builds

Ten pages rebuilt as standalone Tailwind-CDN HTML files, each with its own GSC keyword analysis and changelog.

| Folder | Page | Live URL |
|---|---|---|
| `forex-vip-signals/` | Forex VIP Signals | `https://sureshotfx.com/forex-vip-signals` |
| `gold-vip-signals/` | Gold VIP Signals | `https://sureshotfx.com/gold-vip-signals` |
| `indices-vip-signals/` | Indices VIP Signals | `https://sureshotfx.com/indices-vip-signals` |
| `combo/` | Combo Signals (Forex + Gold + Indices) | `https://sureshotfx.com/combo` |
| `trade-copier/` | Trade Copier (MT4 & MT5) | `https://sureshotfx.com/trade-copier` |
| `lot-size-calculator/` | Lot Size Calculator (forex, gold, indices) | `https://sureshotfx.com/lot-size-calculator` |
| `pip-calculator-mobile-app/` | Pip Calculator App (Android) | `https://sureshotfx.com/pip-calculator-mobile-app` |
| `currency-heatmap/` | Currency Heat Map (live forex strength) | `https://sureshotfx.com/currency-heatmap` |
| `sure-profit-trading-secret/` | Sure Profit Trading Secret (beginner book) | `https://sureshotfx.com/sure-profit-trading-secret` |
| `behind-the-candle/` | Behind the Candle (SMC book) | `https://sureshotfx.com/behind-the-candle` |

Each folder contains:

- `<page>.html` — the page (open directly in a browser, no build step)
- `assets/` — local images, where the page uses them
- `keyword-coverage-comparison.md` — previous vs new coverage, per GSC query
- `<page>-keywords.md` — brand / non-brand keyword map, priorities, exclusions
- `<page>-changes.md` — what was removed, added, changed, and the pre-launch checklist
- `README.md` — folder-level notes

## Shared rules

- Tailwind CDN, brand tokens from the live site (`#00F595`, black base, Sora + Inter).
- Black Friday sale preserved: same plans, prices and coupon codes.
- Keyword variants carried in body copy, not stuffed into headings.
- Performance claims are qualified with a risk line.
- Video testimonials (where a page uses them) run in a stacked carousel with a lightbox; real Vimeo IDs still need to be supplied.

## GitHub Pages

- `index.html` — review hub linking all eight pages.
- `robots.txt` — `Disallow: /` for every crawler.
- Every page (including the hub) carries `<meta name="robots" content="noindex, nofollow">`.
