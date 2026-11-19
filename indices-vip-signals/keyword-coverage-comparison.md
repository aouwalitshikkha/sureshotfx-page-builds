# Keyword coverage — previous vs new design

**Page:** `https://sureshotfx.com/indices-vip-signals`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, last 90 days.
**Method:** exact on-page phrase match against the rendered text of both versions, then a manual concept check.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page (exact match) |
| 🟡 | Concept covered, but not as the exact query string |
| ❌ | Not covered anywhere on the page |
| n/a | Out of scope for this page (served by another page or purely technical) |

---

## 1. Non-brand — indices intent (coverable here)

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | vip signals | 28 | 8.6 | ✅ | ✅ | Title, H1, hero, pricing, FAQ |
| 2 | index frx vip | 5 | 3.6 | ❌ | 🟡 | "index forex vip" chip — typo variant, not forced into copy |
| 3 | indices signals telegram | 2 | 29.5 | ❌ | ✅ | FAQ "Do you send indices signals on Telegram?" |
| 4 | vip access | 1 | 8.0 | ❌ | ✅ | Hero, FAQ, popular searches |
| 5 | how much are they? | 1 | 5.0 | ❌ | ✅ | FAQ pricing question + popular searches |
| 6 | index signals | 1 | 57.0 | ✅ | ✅ | Hero P2, indices section, comparison table |
| 7 | index vip | 1 | 8.0 | ❌ | ✅ | Hero P2, popular searches |
| 8 | precos | 1 | 5.0 | ❌ | ✅ | Popular searches chip (Portuguese "prices") |
| 9 | telegram account link | 1 | 3.0 | ❌ | ✅ | How-it-works step 2 |

**Score — 9 targetable queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 2 | 0 | 7 |
| New design | 8 | 1 | 0 |

---

## 2. Non-brand — sibling intent (served by other pages)

These queries are already landing on this URL, but the intent belongs to the Forex or Gold service page. The new page acknowledges them with chips that link to the correct product instead of competing for them.

| # | Keyword | Impr. | Pos | Previous | New | Handling |
|---|---|---|---|---|---|---|
| 1 | vip trading signals | 13 | 34.9 | ❌ | ✅ | Chip → `/forex-vip-signals` |
| 2 | vip signal forex | 11 | 50.8 | ❌ | ✅ | Chip → `/forex-vip-signals` |
| 3 | forex vip signal | 4 | 27.8 | ✅ | ✅ | Chip → `/forex-vip-signals` |
| 4 | forex vip lounge | 2 | 88.0 | ❌ | ❌ | No "lounge" product exists; not invented |
| 5 | fx vip | 2 | 46.0 | ✅ | ✅ | Chip → `/forex-vip-signals` |
| 6 | forex vip signals | 1 | 14.0 | ✅ | ✅ | Chip → `/forex-vip-signals` |
| 7 | vip forex signals | 1 | 47.0 | ❌ | ✅ | Chip → `/forex-vip-signals` |
| 8 | gold vip signals | 1 | 130.0 | ✅ | ✅ | Chip → `/gold-vip-signals` |

---

## 3. Brand keywords

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | sureshotfx | 33 | 10.0 | ✅ | ✅ | Logo, nav, footer, meta, FAQ |
| 2 | site:sureshotfx.com | 12 | 39.5 | ❌ | n/a | Technical query — not page copy |
| 3 | sureshot fx | 3 | 17.7 | ❌ | ✅ | Brand FAQ + popular searches |
| 4 | sureshotfx review | 2 | 18.5 | ❌ | ✅ | Brand FAQ + popular searches |
| 5 | sure shot fx | 2 | 40.0 | ❌ | ✅ | Brand FAQ + footer |
| 6 | sureshotfx signals | 2 | 7.5 | ❌ | ✅ | Footer bio |
| 7 | sureshot forex | 1 | 71.0 | ❌ | ✅ | Brand FAQ + chips |
| 8 | sure shot forex | 1 | 76.0 | ❌ | ✅ | Popular searches chip |
| 9 | sureshot signals | 1 | 78.0 | ❌ | ✅ | Popular searches chip |

**Score — 8 brand queries (excluding `site:`)**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 1 | 0 | 7 |
| New design | 8 | 0 | 0 |

---

## 4. Not coverable (and why)

| Keyword | Impr. | Pos | Why it is not covered |
|---|---|---|---|
| yes pls | 1 | 2.0 | Conversational reply, not a search intent. Answered implicitly by the pricing section. |
| forex vip lounge | 2 | 88.0 | No such product exists; inventing a "lounge" would be misleading. Chip route handles the intent. |
| index frx vip | 5 | 3.6 | Misspelling of "index forex VIP" — covered conceptually, never forced as a typo string. |

---

## 5. Overall

| Metric | Previous design | New design |
|---|---|---|
| Targetable queries covered (exact phrase) | 7 / 25 | 23 / 25 |
| Partial (concept only) | 0 | 1 |
| Not covered | 18 | 1 |
| Sections with a single keyword focus | 2 (hero, FAQ) | 12 |
| Internal links to Forex / Gold / Combo | 3 | 8 |
| FAQ questions | 7 | 13 |
| Duplicate promo / benefit blocks in DOM | 11 BF bars + 2 benefit grids + 2 onboarding blocks | 1 each |

**Why the old page plateaued:** the live page has the right product but only one keyword angle — "Indices VIP Signals" — repeated through the hero, two pricing blocks and seven FAQs. It never spells the surrounding intent that GSC already associates with the URL (`vip signals`, `vip access`, `index vip`, `indices signals telegram`, `telegram account link`), and it never confirms the brand variants (`sureshot fx`, `sureshotfx review`, `sure shot forex`). Those clusters sit at positions 8–78, where exact-phrase additions move rankings quickly.

**What still needs work to close the last gaps**

1. `index frx vip` (5 impressions, position 3.6) is the highest-value partial. If the typo keeps appearing, add it as a search chip exactly as typed — do not put it in the H1.
2. `forex vip lounge` (2 impressions, position 88) has no matching product. If a community tier launches, this page can link to it.
3. Re-check the monthly GSC export before launch; indices queries rotate faster than the brand set.
