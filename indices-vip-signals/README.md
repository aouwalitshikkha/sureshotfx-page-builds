# Indices VIP Signals — page build

Redesign of `https://sureshotfx.com/indices-vip-signals` with Tailwind CDN (single file, no build step). Same design system as the rebuilt `/forex-vip-signals` and `/gold-vip-signals` pages, with a sky-blue accent for indices.

| File | What it is |
|---|---|
| `indices-vip-signals.html` | The page. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `indices-vip-signals-keywords.md` | GSC keyword map — brand vs non-brand, priorities, where each is covered, what was excluded and why. |
| `indices-vip-signals-changes.md` | Changelog vs the live page: removed, added, changed, verification, and the pre-launch checklist. |

## Before publishing

1. Confirm pricing — live cards say RISE $64.99, PRO $159.99, ADVANCE $149.99; the live FAQ says $44 / $89 / $144. This page uses the card prices.
2. Verify the PRO strike price `$449.99` (inferred from "SAVE $290").
3. Add real Vimeo IDs to the video testimonials (`stories` array + `data-video` on the matching `.v-card`). The current ID `568002656` is password-protected.
4. Replace `href="#"` on the plan CTAs with real checkout URLs.
5. Confirm the placeholder stats (12,400+ points, 85–95%, 2,000–3,000 points/month, 4.7 rating) and the five rows in the recent-signals table.
6. Replace or remove the five added reviews; only Marqees is taken from the live page.
7. Set the Black Friday countdown end date (`2026-11-30T23:59:59Z` in the countdown script).

## Structure

Announcement bar → header → hero (index signal card + trust strip) → Black Friday pricing → inside the indices channel → indices covered → sessions → free vs VIP → performance → how it starts → reviews + video testimonials + media → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.
