# Changelog — `/forex-vip-signals` redesign

Comparison: **live page** (`https://sureshotfx.com/forex-vip-signals`, captured 18 Nov 2026) → **new design** (`forex-vip-signals.html`).
Scope: layout, content, keyword coverage, technical SEO. Prices, coupons and the Black Friday offer are unchanged.

---

## Quick summary

| Area | Change |
|---|---|
| Total sections (desktop) | 17 → 12 top-level sections (duplicates merged, 8 new blocks added) |
| Pricing blocks | 2 duplicated blocks → 1 |
| FAQ items | 6 → 12 |
| Reviews on page | 8 written → 6 written + 3 video stories |
| Images used | ~20 (logos, badges, payment gateway, video thumbs) → 0 (CSS/SVG only) |
| Structured data | none → Product + FAQPage + BreadcrumbList |
| Meta / OG / Twitter | partial → complete |
| Headings | 1 H1 + mixed H3s → 1 H1 + 11 H2s + H3s |

---

## 1. Removed

### 1.1 Sections removed

| Removed | Why | Note |
|---|---|---|
| **Mega-menu dropdowns** (Services / Products / Learn / Proof panels with descriptions) | Replaced by a flat anchor nav (What You Get, Pairs, Sessions, Performance, Reviews, FAQ) + a mobile hamburger menu. Deep links now live in the footer. | Product links kept in footer |
| **Duplicate pricing block** (the same 3 plans were rendered twice — once as BF cards, once as a plain plan row) | Redundant; both were visible output of the same component. Consolidated into one pricing section. | No content lost |
| **Payment gateway image** (`ssf_payment_gateway_825.png`) | Replaced with a text line: "Visa · Mastercard · Crypto · PayPal" + secure-checkout note. | Re-add the image if brand requires it |
| **Video testimonials** — original "Real Traders. Real Experiences" block (3 Vimeo slots, 2 of them empty placeholders) | Rebuilt as a designed 3-story carousel with a lightbox player. Same slot count, no broken placeholders. | Add real Vimeo IDs — see §2.6 |
| **"Recognize By" Saashub badges** (2 badge images) | Outbound badge images, low value in this layout. | Restore in footer if required |
| **Media logos as images** (AP News, Digital Journal, Business Insider, Street Insider, Benzinga, Apple News — 6 linked PNGs) | Replaced with an animated text marquee (same names, no outbound links). | **Swap back to logo images** if brand assets are approved |
| **"Follow us on" strip at the page bottom** | Merged into the footer as icon buttons (Facebook, X, Telegram, YouTube, TikTok dropped). | TikTok icon not included |
| **Second "Why Traders Choose" feature list** (the same 8 features were output twice — desktop + mobile duplicate) | Deduplicated into one feature grid. | — |
| **Original hero paragraph** (single 2-sentence block) | Rewritten into two shorter paragraphs with keyword intent split. | — |

### 1.2 Reviews removed (8 → 6)

Dropped to keep the grid balanced and avoid Gold-VIP duplication on a Forex page:

- **Tom Barry** — "Fantastic! I'm truly impressed…"
- **Lydla Hayes** — "SureshotFX provides a solid, mostly consistent signal service…"

Kept: Emily Carter, Nika, David Thompson, Jonathan Reed, Andrew Miller, Matthew Cole.

### 1.3 Footer links removed / condensed

- `Learn` column removed as a standalone column — `Sure Profit Trading Secret` and `Behind the Candle` are no longer footer links (both are now contextual in-body links).
- `Affiliates` (FirstPromoter) link removed.
- `Pip Calculator App`, `Currency Heatmap`, `Scammer List` kept only partially (`Scammer List` moved into an FAQ answer; `Currency Heatmap` and `Pip Calculator App` dropped from footer).
- `News` and `Blog` moved into the "Proof & Learn" column.

> Restore any of the above if they are required for internal-link equity or partner obligations.

### 1.4 Content claims removed

- The unsupported "since 2020" line in the footer.
- The broken heading text "Unlock Exclusive Black72% Friday Deals" (a rendering bug on the live page) — replaced with clean copy.
- The duplicated inline `CouponCopied!BFFOREX79` / `CouponCopied!BFFOREX129` fragments (they appeared twice per card and collided with the copy button label).
- The "RISE (1 month) SAVE $0" contradiction — Rise now simply reads "Save $0 · monthly rolling".
- Unverifiable "+6 more on high-probability setups" blurb rewritten (pair count kept, wording clarified).

---

## 2. Added

### 2.1 New sections

| # | Section | Purpose |
|---|---|---|
| 1 | **Sticky Black Friday bar** with live countdown (`02d 14h 33m`) + "Claim deal" | Urgency, site-wide promo visibility |
| 2 | **Sticky header** with anchor nav + mobile hamburger menu | Navigation, sticky CTA |
| 3 | **Hero signal card** — EUR/USD sample with entry / SL / TP1 / TP2 / R:R 1:2.4 / "4 of 6 delivered" | Shows the product instead of describing it |
| 4 | **Trust strip** — 12,400+ traders · 4.7 Myfxbook · 2–8 signals/day · 24/7 support | Above-the-fold proof |
| 5 | **"Every Forex VIP Signal Is A Complete Trade Plan"** — signal anatomy block + 6 feature cards + 3 bonus cards | Replaces the old 8-item feature list with a clearer hierarchy |
| 6 | **Free vs VIP comparison table** (7 rows) | Directly answers `difference between free and VIP forex signals` |
| 7 | **Performance panel** — 30-day stats (147 signals, 78.2% win rate, avg 1:2.1, +1,284 pips) + sample trade ticker + risk disclaimer | Turns "proven track record" text into data |
| 8 | **"Popular searches"** chip block (12 queries) | Covers long-tail variants without stuffing body copy |
| 9 | **Sticky mobile CTA bar** — "Black Friday · 72% off · from $13.33/mo" | Mobile conversion |
| 10 | **Multilingual support note** — English, Arabic, Persian, Urdu, Hindi | Responds to Arabic/Persian queries seen in GSC |

### 2.2 New pricing elements

- **"Most popular" badge** on the Pro card.
- **Copy-coupon buttons** for `BFFOREX79` and `BFFOREX129` with a "Copied!" state.
- **Corrected price presentation**:
  - Pro: `$119.99 billed once · ~~$399.99~~` (was an ambiguous `$13.33/monthly $119.99`).
  - Advance: `~~$229.99~~ pay once, access forever` (struck price was previously static text).
- **Combo card** rebuilt as a full-width upsell band (was a 4th narrow card): Gold + Indices included, All Advance features, Copier, Guardian, FX Academy, eBooks.
- **Checkout reassurance** row: secure checkout · payment methods · instant Telegram access · `@SSF_Support` fallback.

### 2.3 New FAQ items (6 → 12)

Added:

1. **What is the Forex VIP lounge?** — covers `forex vip lounge`
2. **Is this an FX VIP AI signal or a signal bot?** — covers `fx vip ai signal`, `fx vip`, `vip signal bot`, `sureshot bot`
3. **Is it price action based?** — covers `price action forex vip`
4. **What are the best VIP trading signals for forex?** — covers `vip trading signals`, `trading vip signals`, `forex trading vip signals`, `signal vip`
5. **Do I need a forex trading VIP account to start?** — covers `forex trading vip accounts`
6. **Is this the official SureShotFX website?** — covers `sure shot fx`, `sureshot fx`, `sure shot forex`, `sureshot forex`, `sureshot signals`, `sureshot trading`, `sureshotfx official website`, `sureshotfx gold / sureshot gold`

Rewritten (kept): *"Do you send forex and crypto signals?"* now handles `forex crypto`; *"Are the reviews and track record verifiable?"* now carries Myfxbook / Trustpilot / press proof instead of the competitor warning.

### 2.6 Video testimonials (rebuilt)

Section "Real Traders. Real Experiences", placed between the written review grid and the "As featured on" marquee.

- **Stacked card deck** — matches the live page: the active story in front, the next two offset by 40px / 80px, scaled to 0.92 / 0.84, rotated `rotateY(-5deg)` in a 1400px perspective and blurred 2px. 700ms ease-out transitions.
- **Auto-advance every 7 seconds**, like the original carousel. Pauses on hover, on keyboard focus inside the block, when the tab is hidden, while the lightbox is open, and is disabled entirely for `prefers-reduced-motion` users. Any arrow/dot click restarts the timer.
- **Quote panel** — the quote, name, avatar initial and role swap with the active slide, so the video and the words always match.
- **Controls** — prev/next buttons plus 3 progress dots.
- **Lightbox player** — clicking the front card opens a full-screen overlay with the Vimeo iframe (`autoplay=1`), closes on ✕, backdrop click or `Esc`, and restores page scroll.
- **Risk note** under the player: "Individual results vary. Past performance is not indicative of future results."
- **Posters** — CSS gradients + grid, so no dependency on `vumbnail.com` (the live page's thumbnail for video 568002656 currently returns Vimeo's "Password protected" image).
- **Slots 2 and 3** — Tom Barry and Lydla Hayes (the two reviews removed from the written grid), marked "Coming soon" until real footage exists.

**To go live:** add the Vimeo IDs in two places in `forex-vip-signals.html` — the `video:` field in the `stories` array, and the `data-video` attribute on the matching `.v-card`.

### 2.7 New copy / keyword placements

- Hero paragraph 2: `forex signals VIP`, `premium forex signals`.
- Inside section: `forex VIP signal`, `vip signal group`, `premium analysis`, `intraday & swing`.
- Pairs section: `price action`, `fx VIP AI signal`.
- Sessions: `daily forex signals`, session routing.
- Compare table: `free forex signals`, `VIP forex signals`, `premium signals`, `VIP access`.
- FAQ: `vip signals telegram`, `vip signal forex`, `signal vip`, `vip forex signals`, `vip signals forex`, `daily VIP signals`, `forex VIP lounge`.
- Footer: brand variants (`Sure Shot FX`, `SureShot FX`, `SureShot Forex`).

### 2.8 Technical SEO added

- `<title>` + meta description rewritten around `forex VIP signals` / `premium forex signals`.
- Canonical, `robots`, Open Graph (title, description, url, type, site_name), Twitter card.
- Single `<h1>`; 11 descriptive `<h2>`s; `<h3>` per card/FAQ.
- **JSON-LD**: `BreadcrumbList`, `Product` (3 offers + 4.7 aggregateRating), `FAQPage` (8 Q&As mirroring visible content).
- Semantic `<article>`, `<figure>`, `<figcaption>`, `<details>/<summary>`, `<dl>`, `<ol>` for the process.
- Accessibility: `aria-label` on icon links and the email field, `name` on the newsletter input, keyboard-operable FAQ (`<details>`).
- Internal links preserved/added: Gold VIP, Indices VIP, Combo, Live Signals, Performance, Growth calculator, Trade Copier, Algo, Guardian, Lot Size Calculator, Pip Calculator, Sure Profit Trading Secret, Scammer List, Risk Disclosure, FAQs, About.
- Performance: zero raster images, one CSS/JS payload (Tailwind CDN), no layout shift from images.

---

## 3. Unchanged

- All prices: Rise `$44.99/mo`, Pro `$119.99/6 months`, Advance `$129.99 lifetime`, Combo "up to 69% off".
- Coupons `BFFOREX79` and `BFFOREX129`; headline "Save up to 72%".
- Free-signals positioning, Telegram delivery, 2–8 signals/day, 4.7 Myfxbook rating.
- All 14 covered pairs (EUR/USD, GBP/USD, USD/JPY, AUD/USD, USD/CAD, NZD/USD, GBP/JPY, EUR/GBP, EUR/JPY, AUD/JPY, CHF/JPY, NZD/JPY, USD/ZAR, USD/SGD).
- Session times (Asia 00:00–09:00, London 07:00–16:00, New York 13:00–22:00 UTC).
- The 4-step onboarding flow.
- All legal disclaimers (trading, software, jurisdiction, payments & refunds) — condensed visually but not altered in meaning.

---

## 4. Before going live

1. **Add the real Vimeo IDs** to the video testimonials (the current public ID `568002656` is password-protected, so the player shows a blank/password frame until a working video is supplied).
2. Restore **Saashub badges** if they are contractually or editorially required.
3. Replace **text marquee** with the real media logos (and restore outbound links).
4. Swap the hero/pricing **CTA `href="#"`** for real checkout URLs.
5. Re-add **payment gateway image** if brand guidelines require it.
6. Confirm **12,400+ traders** and the **30-day performance numbers** (147 / 78.2% / 1:2.1 / +1,284 pips) — these are illustrative placeholders in the design.
7. Set the **countdown end date** in the script (`2026-11-30T23:59:59Z`) to the actual campaign end.
8. Re-check the **6 removed footer links** for internal-linking requirements.
