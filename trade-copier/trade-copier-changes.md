# Trade Copier — what changed from the live page

Rebuild of `https://sureshotfx.com/trade-copier` in a single Tailwind-CDN HTML file. Same design system as the rebuilt `/forex-vip-signals`, `/gold-vip-signals`, `/indices-vip-signals` and `/combo` pages — brand `#00F595`, black base, Sora + Inter — with a green→sky-blue accent (`.text-gradient-copier`, `#22FFA9 → #38BDF8 → #7DD3FC`) instead of the combo's three-colour gradient.

**Size:** 106 KB, 3,105 visible words (live page: 2,140), 11 sections, 15 FAQs.

---

## 1. Removed

| Removed | Why | Replacement |
|---|---|---|
| **11 stacked Black Friday bars** | The live page repeats the same promo 11 times in the visible DOM | One announcement bar with a live countdown |
| **25-destination mega-menu header** | Not needed on a single product page | 7 anchor links + Free Signals + Buy Now |
| **FAQ "Is SSF Guardian compatible with both MT4 and MT5?"** | Copy-paste from the Guardian product; nothing to do with the copier | Replaced with "What is the Trade Copier…" and "Is the copier included in my VIP subscription?" |
| **FAQ "Which account type should I use for SureShotFX Algo?"** | Copy-paste from the Algo product | Replaced with brokers/account types, news filter and official-product answers |
| **"Recognize By" award badges** (2 images) | Assets not supplied | Omitted — see the checklist; supply the badge files and they can return in the footer |
| **Hotlinked screenshots** | Four `<img>` tags pointed at `sureshotfx.com/assets/...`, so the page broke if the CDN path changed | Four local copies in `assets/` (trimmed 14 px border, 149 KB total) |
| **`AV` avatar placeholders** on all six reviews | The live page renders the letters "AV" as the avatar for every reviewer | Initial-based avatars (FL, ES, F, AK, LM, DR) |

Nothing factual was deleted: every price, coupon, feature, requirement, review and disclaimer from the live page is still present.

---

## 2. Added

### 2.1 Page shell

- Full `<head>`: title, meta description, canonical, robots, Open Graph, Twitter card.
- Sticky header with anchor nav and a `<details>` mobile menu.
- Black Friday bar with countdown to `2026-11-30T23:59:59Z` (update before launch).
- Sticky mobile CTA bar ("Trade Copier — $49.99 lifetime").

### 2.2 Hero

- H1 "Copy Every VIP Signal / Straight To MT4 & MT5" — the live H1 was "Hassle Free And Auto-Pilot Earning Opportunities", which describes a feeling, not a product.
- Two-paragraph intro: what the copier mirrors, what it does not do (no EA, no coding, no VPS scripts), and who holds the funds.
- **Illustrative console panel** — an HTML mock of a copy event (VIP → MT5, XAUUSD, SL/TP, "copied to Account #1 & #2"). It is not a screenshot of the shipped software; replace it with a real capture if one exists.
- Trust strip: MT4 + MT5 · up to 3 accounts · Windows PC or VPS · free updates for life.

### 2.3 Sections that did not exist as distinct blocks

| Section | Covers | Notes |
|---|---|---|
| Why automate | `forex signal trade copier` | Three value cards: helps you, built for you, protects you — the live page had these headings but no structure around them |
| Features | `forex signal copier service` | Eight cards: execution, notifications, auto updates, risk, spread, exclude trade, slippage, installation |
| How it works | setup path | Four steps: licence → VIP channels → install → attach and arm |
| Install | `tradecopier` | Three annotated installer screenshots + `SSF-TradeCopier-Setup.exe` |
| Compatibility | MT4/MT5, Windows, VPS | Requirements list + a support table (platform, OS, connection, broker, accounts, updates, setup time) |
| Pricing | `lifetime trade copier` | One lifetime card, $49.99 vs $74.99, coupon `FRIDAYCOPY`, save 33% |
| Reviews | `sureshotfx review` | Six reviews in a grid, with a risk line |
| FAQ | 15 queries | See §2.5 |
| Popular searches | 21 chips | Brand spellings, product terms, geo term |
| Support | — | Telegram CTA + Arabic line |
| Newsletter | — | "Market Brief — Every Sunday" |

### 2.4 Pricing and cross-sell

- Single lifetime plan: **$49.99** (strike **$74.99**, **save 33%**), lifetime for **3 accounts**, all 8 features, free updates, video documentation, 24/7 support, free first-install dev help.
- Coupon copy button for `FRIDAYCOPY` (one click → clipboard, label flips to "Copied!").
- "Included with Combo" panel linking to `/combo` — the copier is bundled there, so the page does not pretend the $49.99 licence is the only route.
- Guardian cross-sell for funded-account traders.
- Refund/payment footnote.

### 2.5 FAQ expanded 12 → 15

The ten copier-relevant live questions are kept and tightened. Added: what the copier is, "is it included in my VIP subscription", brokers/account types, whether it is the official product, and the news filter. The two live questions about other products are gone.

### 2.6 Technical SEO

- JSON-LD: `SoftwareApplication` (8 features, Windows, offer $49.99, `priceValidUntil` 2026-11-30), `BreadcrumbList`, `FAQPage` (9 questions).
- No `aggregateRating` — the page shows no star rating, so none is marked up.
- Semantic headings, `<details>` FAQ (answers stay in the HTML for crawlers), internal links to `/combo`, `/forex-vip-signals`, `/gold-vip-signals`, `/indices-vip-signals`, `/algo`, `/sureshotfx-guardian`, `/live-signals` and the blog.
- `html { background:#000; color-scheme: dark }` so the scrollbar and overscroll canvas stay dark.

---

## 3. Changed

| Item | Live page | New page | Why |
|---|---|---|---|
| H1 | "Hassle Free And Auto-Pilot Earning Opportunities" | "Copy Every VIP Signal / Straight To MT4 & MT5" | Puts the product and the platforms in the largest heading |
| Title tag | "SureShotFX Trade Copier - SureShotFX" | "SureShotFX Trade Copier for MT4 & MT5 \| Auto-Copy Signals" | Brand + category + platform, within display limits |
| Meta description | "SSF Trade Copier enhances your trading profit potential with it's seamless automation…" | "Copy every SureShotFX VIP signal to MT4 or MT5 automatically. Up to 3 accounts, dynamic lot sizing, spread and slippage control, free updates. Lifetime licence $49.99 with code FRIDAYCOPY." | Fixes the apostrophe error and states the offer |
| Banner | "Black Friday Deals — Save upto 72% for a Limited Time!" (sitewide) | "Black Friday — save 33%" (copier-specific) | The copier's own card computes to 33% ($74.99 → $49.99). See the checklist. |
| FAQ heading | "Frequently Asked Questions" / "All You Need to Know About the SSF Copier" | "Trade Copier — Common Questions" | Names the product in the heading |
| FAQ answers | Guardian and Algo answers on a copier page | Copier-only answers, with `/algo` linked from the news-filter answer | Removes the wrong-product copy-paste |
| Price presentation | $74.99 struck, $49.99, "Lifetime for 3 accounts" | Same numbers, plus a "One-time" badge, "save 33%" and a feature list | Same offer, clearer maths |
| JSON-LD price | `"price":"74.99"` while the card says $49.99 | `"price":"49.99"` with `priceValidUntil` | The structured data now matches the visible price |
| Reviews | Six quotes, grammar errors ("They give signal accurate…", "SureShotX", "\| think") | Same six, copy-edited (see below) | Readability; **not verbatim any more** |
| Image alt text | `alt="sureshortfx"` on every screenshot | Descriptive alt per screen | Accessibility + image search |
| Hero proof | Badge images with no labels | Text trust strip | Removes unlabelled badge art, keeps the claims readable |

### Review editing — read before publishing

The quotes are **not verbatim**. Three were rewritten for grammar, one brand typo was fixed:

- **Fitness lifeline:** live text reads "They give signal accurate and high accuracy and there copier is magic, nothing do anything only auto mode and gain profit high, follow risk management and lot size surely gain your profit." → rewritten to "They give accurate signals with high accuracy and their copier is magic — nothing to do, only auto mode, and you gain profit…" Meaning preserved; wording is not.
- **Fendy:** "SureShotX" → "SureShotFX"; "\| think" → "I think".
- **Eban Szelesl:** unchanged apart from apostrophes.
- **Ayaan Khan, Lucas Meyer, Daniel Rossi:** unchanged apart from curly apostrophes.

If the client needs verbatim testimonials, restore the original strings (including the errors) or get the reviewers to approve the edited versions.

---

## 4. Before going live

1. **Confirm the Combo claim.** The page says the copier is included with the Combo Bundle and that Combo members do not need to buy the $49.99 licence separately. If that is not true, remove the panel — it is a refund/chargeback risk.
2. **Resolve the banner percentage.** This build says "save 33%" because $74.99 → $49.99 is 33%. The sitewide banner says "up to 72%". Pick one story.
3. **Confirm the checkout price.** The live JSON-LD says `74.99`; the live card says `49.99`. This build uses $49.99 everywhere. Verify what the checkout actually charges.
4. **Replace `href="#"`** on "Start Auto-Pilot Now" with the real checkout URL.
5. **Verify two copy claims:** "requires an active VIP subscription" and "you can pause copying at any time from the console". Both are plausible but not stated on the live page.
6. **Approve the edited reviews** (see §3) or restore the originals.
7. **Supply the two "Recognize By" badge images** if they should return to the footer.
8. **Replace the hero console mock** with a real screenshot of the software, or label it as illustrative.
9. **Set the countdown end date** (`2026-11-30T23:59:59Z` in the countdown script) and remove the bar after the sale.
10. **Add an OG image** (`og:image` is not set because no asset was supplied).
11. **Review the Arabic support line** with a native speaker.
12. **Confirm the Guardian cross-sell wording** ("enforces daily loss and drawdown limits") against the Guardian product page.

---

## 5. Verification performed

- Desktop 1440×1000 and 1280×800: no horizontal overflow; hero, features, how, install, pricing, reviews and FAQ checked visually.
- Tablet 1024×800: header fits on one line; H1 re-sized to `lg:text-[2.9rem]` so it stays on two lines.
- Mobile 390×844 (touch emulation) and 320×700: no horizontal overflow, sticky CTA visible, mobile menu opens inside the viewport, countdown stays on one line, pricing card readable.
- Four local screenshots load (verified after lazy-load scroll); explicit `width`/`height` set to prevent layout shift.
- Countdown ticks every second; the hero clock and the pricing clock stay in sync.
- Coupon button copies `FRIDAYCOPY` and flips its label to "Copied!".
- All in-page anchors resolve (`features`, `how`, `install`, `compatibility`, `pricing`, `reviews`, `faq`); no duplicate IDs.
- 15 FAQ items; `textContent` covers all 20 targetable GSC queries (collapsed answers included).
- JSON-LD parses (`SoftwareApplication`, `BreadcrumbList`, `FAQPage`); HTML tag balance checked with a parser; UTF-8 clean, no mojibake.
- Only console message is the expected Tailwind CDN warning. DevTools also flags "lazy-loaded images should have explicit dimensions" — the attributes and CSS aspect ratios are present (`auto 439 / 578`), so this is an audit false positive, not a layout risk.
