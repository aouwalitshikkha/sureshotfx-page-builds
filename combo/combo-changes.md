# Combo Signals — what changed from the live page

Rebuild of `https://sureshotfx.com/combo` in a single Tailwind-CDN HTML file. Same design system as the rebuilt `/forex-vip-signals`, `/gold-vip-signals` and `/indices-vip-signals` pages — brand `#00F595`, black base, Sora + Inter — with a three-colour accent (green forex, gold, sky-blue indices) and a `text-gradient-combo` treatment for the bundle H1.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the same promo 11 times in the DOM | One announcement bar with a live countdown |
| **Duplicated benefit grid** — the 8 "Why Trade…" cards appear twice back to back | Same content twice on a 20k-character page | 6 bundle feature cards + 3 tool cards, once |
| **Duplicated onboarding** — the 4-step process is rendered twice | Repetition with no new information | One 4-step section |
| **~30-link mega menu** | Not needed on a single product page | 7 anchor links + Free Signals + Buy Now |
| **Empty "Video 2 / Video 3" boxes** | Placeholder boxes with no content | Designed "Coming soon" story cards in the carousel |
| **"Recognize By" logo images** | Assets not supplied | Text marquee ("As featured on") |
| **"AV" avatar images** | Assets not supplied | Initial-based avatars |
| **Channel selector checkboxes** ("Select Signal Channels — select at least 2 services") | The rebuilt pricing states that all three channels are included in every plan; the checkbox UI implied a configurable 2-channel bundle that the cards do not reflect | A single "all three channels, every plan" band under the pricing cards — **restore the selector if checkout supports 2-channel bundles** |
| **Embedded "Signals History" widget** | Third-party embed with no supplied markup or key | Links to `/live-signals` and the Myfxbook profile |

Nothing factual was deleted: every plan price, coupon, market, session, review and disclaimer from the live page is still present.

---

## 2. Added

### 2.1 Page shell

- Full `<head>`: title, meta description, canonical, robots, Open Graph, Twitter card.
- Sticky header with anchor nav and a `<details>` mobile menu.
- Black Friday bar with countdown to `2026-11-30T23:59:59Z` (update before launch).
- Sticky mobile CTA bar.

### 2.2 Hero

- H1 "Forex, Gold & Indices / One VIP Subscription" — the live H1 was "Forex, Gold & Indices Combo Signals Package".
- Two-paragraph intro carrying `combo signals`, `VIP combo`, `forex VIP`, `gold VIP` and `indices VIP`.
- Bundle card listing all three channels, the tools row and the lifetime price with the `$969.93` strike.
- Trust strip: 3 markets, 6–13 signals/day, 40–55 signals/week, 24/7 support.

### 2.3 Pricing (one block)

- RISE $129.99/month (save 21%, strike $163.98).
- PRO $31.67/month effective, $189.99 billed once for 6 months (save 55%).
- ADVANCE $299.99 lifetime (save 69%, strike $969.93).
- Coupon copy button for `LEGENDARY299` on Advance (one click → clipboard).
- "All three channels, every plan" band linking to the markets section and FAQ.
- Payment / support footnote.

### 2.4 New sections

| Section | Covers | Notes |
|---|---|---|
| Inside the bundle | `combo signals` | Three mini signal cards (forex, gold, indices) + 6 features + 3 tool cards |
| Three markets | `forex vip signals`, `gold vip signals` | One card per desk with counts, instruments and links to the single-channel pages |
| Sessions | `forex gold indices` | Asia / London / New York with UTC windows and per-market chips |
| Bundle value | `combo bundle` | 3 reasons + a $969.93 → $299.99 receipt with the full item breakdown |
| Track record | `sureshotfx` | 40–55 signals/week, 4.7 Myfxbook, publishing since 2019, links to history |
| How it works | `telegram account link` | 4 steps — fixes the live copy that only mentions the Forex VIP channel |
| Reviews | `sureshotfx` | 6 curated live reviews + video carousel |
| FAQ | 13 queries | See §2.6 |
| Popular searches | 28 brand + non-brand chips | Handles variants without stuffing body copy |
| Support | `combo signals` | Telegram CTA + Arabic line |
| Newsletter | — | "Combo Market Brief", email capture |

### 2.5 Video testimonials (rebuilt)

"Real Traders. Real Experiences" sits between the review grid and the media marquee.

- **Stacked deck** — front card flat, next two offset 40px / 80px, scaled 0.92 / 0.84, `rotateY(-5deg)` inside a 1400px perspective, blurred 2px.
- **Auto-advance every 7s**. Pauses on hover, keyboard focus, hidden tab and while the player is open; disabled for `prefers-reduced-motion`.
- **Synced quote panel** — quote, name, avatar and role change with the active card.
- **Lightbox** — Vimeo iframe with `autoplay=1`, closes on ✕ / backdrop / `Esc`, restores scroll and removes `src`.
- **Risk line** under the player.
- **Slots 2 and 3** are marked "Coming soon" and use real reviewer names/quotes from the live page. Clicking a placeholder advances the deck.

### 2.6 FAQ expanded 5 → 13

The five live questions are kept and tightened. Added: markets and instruments, "is it included", MT4/MT5 requirement, what else is included, upgrade path, single-market alternative, and the brand/legitimacy answer. The live heading "Frequently Asked Questions About Indices VIP Signals" is corrected to the combo.

### 2.7 Technical SEO

- JSON-LD: `Product` with three offers, `FAQPage` (8 questions), `BreadcrumbList`.
- `Product` intentionally has **no** `aggregateRating` — 4.7 is displayed but not marked up, to avoid fabricated review rich results.
- Semantic headings, `<details>` FAQ (content stays in the HTML), internal links to all three VIP pages, `/trade-copier`, `/live-signals`, `/sureshotfx-guardian`, `/sure-profit-trading-secret`, calculators and the blog.
- `html { background:#000; color-scheme: dark }` so the scrollbar and overscroll canvas stay dark.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Forex, Gold & Indices Combo Signals Package" | "Forex, Gold & Indices / One VIP Subscription" | Puts the bundle proposition in the largest heading |
| Title tag | "Combo Signals: Expert Alerts for Forex, Gold & Indices" | "Forex, Gold & Indices Combo Signals — Save 69% \| SureShotFX" | Brand + category + offer, within display limits |
| FAQ heading | "Frequently Asked Questions About Indices VIP Signals" | "Combo Signals — Common Questions Answered" | Copy-paste error on the live page |
| Onboarding step 2 | "Join Forex VIP Telegram channel" only | "Join all three channels" with one invite per market | The combo includes Forex, Gold and Indices; the live copy forgot two |
| FAQ price list | $99/month, $349 lifetime, $163.98 separate | $129.99 / $189.99 / $299.99, $969.93 separate | The live FAQ contradicts its own cards; cards are treated as current |
| PRO presentation | $189.99 + "SAVE 55%" | $31.67/month effective, $189.99 billed once, save 55% | Makes the 6-month price comparable to Rise |
| ADVANCE value | $299.99 + "SAVE 69%" | $299.99 + `$969.93` strike and a full receipt | Shows what the 69% refers to |
| Reviews | 19+ cards in a scrolling strip | 6 curated reviews in a 3-column grid | Keeps the strongest, removes repetition; all six are verbatim from the live page |
| Review typos | "l had", "1 am", extra spaces | Corrected to "I had", "I am" | Quoted text cleanup; wording unchanged |
| Video stories | One real video + two empty boxes | One real video + two "Coming soon" cards with real reviewer quotes | Turns dead space into a working carousel |
| Banner claim | "Save up to 72%" | Carried over verbatim | But see the checklist — the cards compute to 69% |

Everything else — plans, coupons, session UTC windows, market coverage, disclaimers — is unchanged.

---

## 4. Before going live

1. **Resolve the pricing contradiction.** Cards say Rise $129.99, Pro $189.99, Advance $299.99; the live FAQ says $99/month and $349 lifetime. This build uses the cards. Decide which is current before publishing.
2. **Check the 72% banner.** The announcement says "up to 72%", but the maximum saving shown on the cards is 69% ($969.93 → $299.99). Either raise the Advance discount or change the banner to 69%.
3. **Confirm the Pro "Save 55%" reference price.** The card shows no strike because the live page does not publish one. Add the real list price if the badge is to be substantiated.
4. **Decide on the channel selector.** The live page lets buyers tick two or three services. This build says all three are included in every plan. If checkout supports 2-channel bundles, restore a selector and a 2-channel price.
5. **Add real Vimeo IDs.** `568002656` is password-protected, so the player opens to a blank/password frame. Update the `stories` array `video:` field and the matching `data-video` attribute.
6. **Replace `href="#"`** on the three plan CTAs with real checkout URLs.
7. **Confirm the stats** — 4.7 Myfxbook rating, 40–55 signals/week, and "publishing since 2019" are taken from the live page; re-verify before launch.
8. **Set the countdown end date** (`2026-11-30T23:59:59Z` in the countdown script).
9. **Swap the text marquee** for the real media logos.
10. **Review the Arabic support line** with a native speaker.
11. **Add an OG image** (`og:image` is not set because no asset was supplied).
12. **Confirm permission for the six quoted reviews** — they are reproduced from the live page, with two typo fixes.

---

## 5. Verification performed

- Desktop 1440×1000 and 1280×800: no horizontal overflow, hero / pricing / markets / value / reviews checked visually.
- Tablet 1024×800: header fits on one line after shortening the nav labels and moving Free Signals to `xl`.
- Mobile 390×844 (touch emulation) and 320×700: no horizontal overflow, sticky CTA visible, mobile menu opens inside the viewport, countdown stays on one line.
- Countdown ticks every second; both desktop and pricing clocks stay in sync.
- Carousel: manual next/prev, 7s auto-advance, synced quote panel, placeholder click advances.
- Lightbox: opens with the correct Vimeo URL, closes on ✕ / backdrop / `Esc`, restores body scroll, iframe `src` removed.
- Coupon button changes its label to "Copied!" and back.
- All in-page anchors resolve (`pricing`, `included`, `markets`, `sessions`, `value`, `performance`, `how`, `reviews`, `faq`); no duplicate IDs.
- 13 FAQ items; `textContent` covers all 22 non-technical GSC queries (collapsed answers included).
- JSON-LD parses; HTML tag balance checked with a parser; only console message is the expected Tailwind CDN warning.
