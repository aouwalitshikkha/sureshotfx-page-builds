# Pip Calculator App — page build

Redesign of `https://sureshotfx.com/pip-calculator-mobile-app` with Tailwind CDN (single file, no build step). Same design system as the rebuilt signal, combo, copier and lot-size pages, with a teal accent matching the Android app UI.

| File | What it is |
|---|---|
| `pip-calculator-mobile-app.html` | The page. Open directly in a browser. |
| `assets/` | Hero image, app icon and six real Android screenshots. |
| `keyword-coverage-comparison.md` | Table: which GSC keywords the old page covered vs the new one. |
| `pip-calculator-mobile-app-keywords.md` | Keyword map — app intent, brand, exclusions, adjacent cluster, section map. |
| `pip-calculator-mobile-app-changes.md` | Changelog vs the live page: removed, added, changed, verification, pre-launch checklist. |

## Before publishing

1. **Resolve iOS.** The live App Store link is dead (404 + empty iTunes lookup). This build ships Android-only plus a note. Restore the badge only if the listing is relisted.
2. Re-check the store figures (4.0★, 134 reviews, 10,000+ downloads, as of 19 Nov 2026).
3. Confirm the gold pip convention against the current Android build.
4. Check the "up to 72%" Black Friday claim against the live sale.
5. Add an OG image; supply the Recognize By badges if they should return.
6. Set the countdown end date and review the Arabic support line.

## Structure

Announcement bar → header → hero (app image + Play CTA + rating) → trust strip → features → screenshots (lightbox) → how it works → what is a pip → markets → buy vs sell → download → web fallback → Black Friday cross-sell → FAQ → popular searches → support → newsletter → footer → sticky mobile CTA.

## Notes

- Store facts come from the Google Play listing and the shipping screenshots, not from marketing copy.
- Nothing unverifiable is claimed: no ad-free promise, no offline-mode promise, no iOS availability.
- All images are local, so a CDN path change on the live site cannot break the page.
