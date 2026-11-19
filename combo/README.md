# Combo Signals — page build

Redesign of `https://sureshotfx.com/combo` with Tailwind CDN (single file, no build step). Same design system as the rebuilt `/forex-vip-signals`, `/gold-vip-signals` and `/indices-vip-signals` pages, with a three-colour accent for the bundle (green forex, gold, sky-blue indices).

| File | What it is |
|---|---|
| `combo.html` | The page. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `combo-keywords.md` | GSC keyword map — brand vs non-brand, priorities, where each is covered, what was excluded and why. |
| `combo-changes.md` | Changelog vs the live page: removed, added, changed, verification, and the pre-launch checklist. |

## Before publishing

1. Resolve pricing — live cards say Rise $129.99, Pro $189.99, Advance $299.99; the live FAQ says $99/month and $349 lifetime. This page uses the card prices.
2. Check the banner — it says "up to 72%", but the cards compute to 69% ($969.93 → $299.99).
3. Confirm the Pro "Save 55%" reference price; no strike is shown because the live page publishes none.
4. Decide whether the live 2-channel selector should return. This build states all three channels are included in every plan.
5. Add real Vimeo IDs to the video testimonials (`stories` array + `data-video` on the matching `.v-card`). The current ID `568002656` is password-protected.
6. Replace `href="#"` on the three plan CTAs with real checkout URLs.
7. Confirm the stats (4.7 Myfxbook, 40–55 signals/week, publishing since 2019) and set the Black Friday countdown end date (`2026-11-30T23:59:59Z`).
8. Confirm permission for the six quoted reviews; they are reproduced from the live page with two typo fixes.

## Structure

Announcement bar → header → hero (bundle card + trust strip) → Black Friday pricing → what's included → three markets → sessions → bundle value → track record → how it works → reviews + video testimonials + media → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.
