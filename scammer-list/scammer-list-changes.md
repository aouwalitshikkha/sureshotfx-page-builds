# Scam alert: what changed from the live page

Rebuild of `https://sureshotfx.com/scammer-list` as a single Tailwind-CDN HTML file. The URL stays live, but the page is now `noindex, follow`.

**Size:** 58 KB, 1,516 visible words (live: 921), 10 FAQs, 18 unique handles.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **H1 "Terms And Conditions"** | A copy-paste bug on a page about impersonation | H1 names the scam alert |
| **Stale "2025" title** | The page is published in 2026 | "SureShotFX Scam Alert 2026" |
| **11 stacked Black Friday bars** | The live page repeats the promo 11 times | One bar with a countdown |
| **25-destination mega menu** | Not needed on a safety page | 5 anchor links + Report a scam |
| **Two duplicate handles** | The live list repeats handles | 18 unique handles |
| **Raw handle dump** | A wall of text with no context or search | Searchable list with a "Reported" label and a legal note |
| **Indexability** | A list of accused handles is the riskiest possible search snippet | `noindex, follow` |

Nothing factual was lost: all unique handles from the live page are present, plus the core warning that SureShotFX never asks for money outside its service charges.

---

## 2. Added

### 2.1 Safety content

| Section | Purpose |
|---|---|
| Before you pay | Three checks: handle, checkout, support |
| Official channels | Website, `@ssf_adminbot`, free signals page, social profiles |
| What we never ask | Six red flags: personal transfers, crypto, card details, release fees, broker passwords, profit guarantees |
| How to report | Four steps, plus bank and police advice if money was sent |
| Reported handles | 18 unique handles, searchable, with a report-list disclaimer |
| FAQ | 10 questions including "Is The Sure FX Group official?" and refunds |

### 2.2 Technical

- `noindex, follow` so the page remains reachable but out of the index.
- JSON-LD: `WebPage`, `BreadcrumbList`, `FAQPage` (6 questions). No `ItemList` of accused accounts.
- Updated date: 20 November 2026.
- Search filter for the handle list.
- Sticky mobile CTA that opens official support.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Terms And Conditions" | "SureShotFX scam alert: fake accounts and impersonators" | Correct topic |
| Title | "…Scam List – Stay Safe in 2025" | "SureShotFX Scam Alert 2026: Fake Telegram Accounts" | Current year, accurate framing |
| Tone | "BEWARE OF THESE SCAMMERS" + raw list | Calm safety notice with a correction route | Reduces legal and brand risk |
| Handle list | Unstructured, duplicates | 18 unique, searchable, dated note | Usable |
| Robots | Indexable | `noindex, follow` | Do not amplify accusations |
| Structure | No FAQ, no channels, no reporting steps | Full safety page | Users can act on it |

---

## 4. Before going live

1. **Legal review.** Confirm the wording is acceptable in the client's jurisdiction. The page now says "reported", not "proven", and includes a correction route.
2. **Verify every handle.** Remove any that is inactive, reassigned or was listed in error.
3. **Confirm the official channels.** `@ssf_adminbot` is the support handle used across the site. Confirm it is still correct.
4. **Keep it noindexed.** Do not add it to the sitemap. Revisit only after legal sign-off and a fresh handle review.
5. **Set a review cadence.** Handles change; review monthly or when a new report arrives.
6. **Confirm the "never asks" list** with the client, especially the broker-password line.
7. **Update the date** whenever the list changes.
8. **Check the 72% banner** against the live sale; this page is not part of the discount.

---

## 5. Verification performed

- Desktop 1440×1000 and mobile 390×844 / 320×700: no horizontal overflow; hero, channels and handle list checked visually.
- 18 handles render; the search filter returns 5 for "gold" and shows an empty state for an unmatched query.
- Countdown ticks; all anchors resolve (`official`, `never`, `report`, `handles`, `faq`); no duplicate IDs.
- 10 FAQ items; JSON-LD parses (`WebPage`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked.
- Zero em dashes; no non-English lines; no Popular searches block.
- Only console message is the Tailwind CDN warning.
