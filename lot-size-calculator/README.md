# Lot Size Calculator — page build

Redesign of `https://sureshotfx.com/lot-size-calculator` with Tailwind CDN (single file, no build step). Same design system as the rebuilt signal, combo and copier pages, with a green accent and gold/sky tab states for the gold and indices modes.

| File | What it is |
|---|---|
| `lot-size-calculator.html` | The page, including a working calculator. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `lot-size-calculator-keywords.md` | GSC keyword map — brand vs non-brand, priorities, exclusions, section map. |
| `lot-size-calculator-changes.md` | Changelog vs the live page: removed, added, changed, verification, pre-launch checklist. |

## Before publishing

1. Decide how to handle exchange rates — the page currently fetches `open.er-api.com` in the browser (free, no key, daily rates) and falls back to a static table offline.
2. Confirm the index contract defaults (currently $1 per point per lot) against the brokers your audience uses.
3. Confirm the gold (100 oz) and silver (5,000 oz) contract sizes for your main brokers.
4. Check the "up to 72%" Black Friday claim in the cross-sell band against the live sale.
5. Add an OG image; supply the two Recognize By badge images if they should return.
6. Set the countdown end date (`2026-11-30T23:59:59Z`) and review the Arabic support line.

## Structure

Announcement bar → header → hero + calculator → quick answers → lot sizes → what is a calculator → search-terms table → how to use → formula + examples → gold → indices → MT4/MT5 → risk management → benefits → Black Friday cross-sell → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.

## Notes

- The calculator is the product: 16 forex pairs, XAUUSD/XAGUSD, six indices, 30 account currencies, live rates, broker-step rounding and a minimum-lot warning.
- The four-column tables scroll horizontally inside their cards on small screens; the page itself never overflows.
- All maths is standard retail contract maths. Gold and index contract sizes vary by broker, so the page states the assumption and lets the user override the value per point.
