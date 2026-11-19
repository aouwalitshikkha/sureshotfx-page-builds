# Forex VIP Signals — page build

Redesign of `https://sureshotfx.com/forex-vip-signals` with Tailwind CDN (single file, no build step).

| File | What it is |
|---|---|
| `forex-vip-signals.html` | The page. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `forex-vip-signals-keywords.md` | GSC keyword map — brand vs non-brand, priorities, where each is covered, what was excluded and why. |
| `forex-vip-signals-changes.md` | Changelog vs the live page: removed, added, unchanged, and the pre-launch checklist. |

## Before publishing

1. Add real Vimeo IDs to the video testimonials (`stories` array + `data-video` on the matching `.v-card`). The current ID `568002656` is password-protected.
2. Replace `href="#"` on the plan CTAs with real checkout URLs.
3. Confirm the placeholder stats (12,400+ traders, 147 signals / 78.2% / 1:2.1 / +1,284 pips).
4. Set the Black Friday countdown end date (`2026-11-30T23:59:59Z` in the countdown script).

## Structure

Announcement bar → header → hero (signal card + trust strip) → Black Friday pricing → inside the channel → pairs → sessions → free vs VIP → performance → how to start → reviews + video testimonials + media → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.
