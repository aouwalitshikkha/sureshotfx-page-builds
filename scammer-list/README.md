# Scam alert — page build

Redesign of `https://sureshotfx.com/scammer-list` with Tailwind CDN (single file, no build step). The URL stays live but the page is **`noindex, follow`**: it is a safety notice, not an SEO asset.

| File | What it is |
|---|---|
| `scammer-list.html` | The page. Open directly in a browser. |
| `keyword-coverage-comparison.md` | Old GSC queries, the noindex decision and the coverage change. |
| `scammer-list-keywords.md` | Brand-trust keywords, exclusions and content rules. |
| `scammer-list-changes.md` | Changelog vs the live page, verification and pre-launch checklist. |

## Before publishing

1. Legal review of the handle list and disclaimer.
2. Verify every handle; remove inactive, reassigned or mistaken entries.
3. Confirm `@ssf_adminbot` is still the official support handle.
4. Keep the page noindexed and out of the sitemap.
5. Set a monthly review cadence and update the date when the list changes.
6. Confirm the "what we never ask" list, especially the broker-password line.

## Structure

Announcement bar → header → hero + "before you pay" card → quick facts → official channels → what we never ask → how to report → reported handles + search → FAQ → support → newsletter → footer → sticky report CTA.

## Notes

- Handles only. No personal names, photos or allegations beyond impersonation.
- The page says "reported", not "proven", and includes a correction route through support.
- The current list has 18 unique handles, deduplicated from the live page.
- No em dashes, no non-English lines, no Popular searches block.
