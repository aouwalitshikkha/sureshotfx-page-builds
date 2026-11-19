# Currency Heat Map — page build

Redesign of `https://sureshotfx.com/currency-heatmap` with Tailwind CDN (single file, no build step). Same design system as the rebuilt signal, combo, copier, lot-size and pip-app pages, with a green→sky→gold accent.

| File | What it is |
|---|---|
| `currency-heatmap.html` | The page, including the self-contained heat map. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one. |
| `currency-heatmap-keywords.md` | Keyword map — tool intent, brand, exclusions, section map. |
| `currency-heatmap-changes.md` | Changelog vs the live page: removed, added, changed, verification, pre-launch checklist. |

## Before publishing

1. Confirm the data arrangement — the grid calls `api.frankfurter.dev` (free, no key) for ECB daily reference rates, not a broker tick feed.
2. Keep "live" honest: the hero means "current published rates", not streaming. The status line and FAQ say ECB reference rates.
3. Decide whether the TradingView embed should return as a secondary block. The self-contained grid should stay for SEO.
4. Check the "up to 72%" Black Friday claim against the live sale.
5. Add an OG image; supply the Recognize By badges if they should return.
6. Set the countdown end date.

## Structure

Announcement bar → header → hero + heat map (timeframes, focus, movers, pair detail) → how to read → timeframes → correlation risk → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.

## Notes

- 56 major pairs across 8 currencies, computed in the page from live daily rates. No iframe dependency.
- The grid scrolls horizontally inside its card on mobile; the page itself never overflows.
- The fallback values are clearly labelled illustrative, so a failed API never displays fake "live" data.
