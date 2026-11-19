# Gold VIP Signals — page build

Redesign of `https://sureshotfx.com/gold-vip-signals` with Tailwind CDN (single file, no build step). Same design system as the rebuilt `/forex-vip-signals` page.

| File | What it is |
|---|---|
| `gold-vip-signals.html` | The page. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `gold-vip-signals-keywords.md` | GSC keyword map — brand vs non-brand, priorities, where each is covered, what was excluded and why. |
| `gold-vip-signals-changes.md` | Changelog vs the live page: removed, added, changed, and the pre-launch checklist. |

## Before publishing

1. Add real Vimeo IDs to the video testimonials (`stories` array + `data-video` on the matching `.v-card`). The current ID `568002656` is password-protected.
2. Replace `href="#"` on the plan CTAs with real checkout URLs.
3. Confirm the placeholder stats (37,742+ pips, ~90%, 2,000–3,000 pips/month, 4.7 rating) and the five rows in the recent-signals table.
4. Resolve the RISE price — the live card says $54.99, the live FAQ says $69.99. This page uses $54.99.
5. Set the Black Friday countdown end date (`2026-11-30T23:59:59Z` in the countdown script).

## Structure

Announcement bar → header → hero (gold signal card + trust strip) → Black Friday pricing → inside the gold channel → XAUUSD focus → sessions → free vs VIP → performance → how it starts → reviews + video testimonials + media → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.
