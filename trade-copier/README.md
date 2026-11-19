# Trade Copier — page build

Redesign of `https://sureshotfx.com/trade-copier` with Tailwind CDN (single file, no build step). Same design system as the rebuilt `/forex-vip-signals`, `/gold-vip-signals`, `/indices-vip-signals` and `/combo` pages, with a green→sky-blue accent instead of the combo's three-colour gradient.

| File | What it is |
|---|---|
| `trade-copier.html` | The page. Open directly in a browser. |
| `assets/` | Four installer/console screenshots used on the page (local copies of the live assets). |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one, per keyword. |
| `trade-copier-keywords.md` | GSC keyword map — brand vs non-brand, priorities, where each is covered, what was excluded and why. |
| `trade-copier-changes.md` | Changelog vs the live page: removed, added, changed, verification, and the pre-launch checklist. |

## Before publishing

1. Confirm the copier really is included with the Combo Bundle — the page cross-sells on that basis.
2. Resolve the banner: this page says "save 33%" ($74.99 → $49.99); the sitewide banner says "up to 72%".
3. Confirm the checkout price — live structured data says $74.99, the live card says $49.99. This build uses $49.99 everywhere.
4. Replace `href="#"` on the plan CTA with the real checkout URL.
5. Verify "requires an active VIP subscription" and "pause copying from the console" before shipping.
6. Approve the copy-edited reviews, or restore the verbatim originals.
7. Supply the two "Recognize By" badge images if they should return to the footer.
8. Replace the hero console mock with a real screenshot, or label it as illustrative.
9. Set the countdown end date (`2026-11-30T23:59:59Z`) and add an OG image.

## Structure

Announcement bar → header → hero (console mock + trust strip) → why automate → features → how it works → install → requirements → Black Friday pricing + Combo/Guardian cross-sell → reviews → FAQ + popular searches → support → newsletter → footer → sticky mobile CTA.

## Notes

- The FAQ is 15 questions: the ten copier-relevant live ones, plus what the copier is, whether it is included in VIP, brokers/account types, the news filter, and whether it is the official product. Two live questions about SSF Guardian and SureShotFX Algo were removed.
- `trade copier news filter` is answered honestly — the copier has no news filter; the answer links to `/algo`.
- The four screenshots are local copies of `sureshotfx.com/assets/images/projects/trade-copier/*`, trimmed by 14 px to remove the surrounding border.
