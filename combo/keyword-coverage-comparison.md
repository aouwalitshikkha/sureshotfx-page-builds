# Keyword coverage — previous vs new design

**Page:** `https://sureshotfx.com/combo`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, last 90 days. 1 click, 107 impressions, 23 queries.
**Method:** exact on-page phrase match against the rendered text of both versions (navigation, footer and duplicate blocks included), then a manual concept check.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page (exact match) |
| 🟡 | Concept covered, but not as the exact query string |
| ❌ | Not covered anywhere on the page |
| n/a | Out of scope for this page (technical query) |

---

## 1. Non-brand — market intent

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | forex vip signals | 2 | 1.5 | ✅ | ✅ | Markets card heading, FAQ 5, popular searches |
| 2 | forex vip signal | 4 | 62.5 | ✅ | ✅ | FAQ 5 answer, popular searches |
| 3 | gold vip signals | 1 | 30.0 | ✅ | ✅ | Markets card heading, FAQ 13, popular searches |
| 4 | vip gold signals | 3 | 9.0 | ❌ | ✅ | Popular searches chip |
| 5 | vip signal forex | 1 | 30.0 | ❌ | ✅ | Popular searches chip |
| 6 | vip access | 1 | 5.0 | ✅ | ✅ | FAQ 1 ("one VIP access"), popular searches |
| 7 | forex vip | 3 | 6.3 | ✅ | ✅ | Hero bundle card, markets, footer |
| 8 | how much are they? | 1 | 6.0 | ❌ | ✅ | FAQ 3 heading + chip |
| 9 | is it included | 1 | 4.0 | ❌ | ✅ | FAQ 7 heading ("Is it included in every plan…") |
| 10 | mt5 | 1 | 2.0 | ✅ | ✅ | Copier FAQ, how-it-works, footer |
| 11 | sure fx trading | 1 | 16.0 | ❌ | ✅ | Brand FAQ 12 + chip |
| 12 | ceny | 1 | 2.0 | ❌ | ✅ | Popular searches chip (Polish "prices") |

**Score — 12 market queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 6 | 0 | 6 |
| New design | 12 | 0 | 0 |

---

## 2. Brand keywords

| # | Keyword | Impr. | Pos | Previous | New | Where it now lives |
|---|---|---|---|---|---|---|
| 1 | sureshotfx | 13 | 15.7 | ✅ | ✅ | Title, logo, nav, footer, FAQ |
| 2 | sureshot gold | 12 | 10.8 | ✅ | ✅ | Popular searches chip |
| 3 | sureshotfx gold | 6 | 1.0 | ✅ | ✅ | Popular searches chip |
| 4 | sureshot signals | 3 | 1.0 | ❌ | ✅ | Popular searches chip |
| 5 | sureshot fx | 2 | 16.0 | ✅ | ✅ | Review quote, brand FAQ, chip |
| 6 | sureshot | 1 | 9.0 | ✅ | ✅ | Logo and footer bio |
| 7 | sureshot forex | 1 | 56.0 | ❌ | ✅ | Popular searches chip |
| 8 | sure shot forex | 1 | 59.0 | ❌ | ✅ | Popular searches chip |
| 9 | sureshot trading | 1 | 72.0 | ❌ | ✅ | Brand FAQ 12 + chip |
| 10 | surefire forex | 1 | 72.0 | ❌ | ✅ | Brand FAQ 12 + chip |

**Score — 10 brand queries**

| | ✅ Covered | 🟡 Partial | ❌ Missing |
|---|---|---|---|
| Previous design | 5 | 0 | 5 |
| New design | 10 | 0 | 0 |

---

## 3. Not coverable (and why)

| Keyword | Impr. | Pos | Why it is not covered |
|---|---|---|---|
| site:sureshotfx.com | 46 | 3.9 | Technical query — not page copy. It is the largest impression source on this URL, which means Google already treats `/combo` as a brand hub. |
| ceny | 1 | 2.0 | Polish for "prices". Covered by a search chip, not by stuffing Polish copy into the sales page. |

---

## 4. Overall

| Metric | Previous design | New design |
|---|---|---|
| Targetable queries covered (exact phrase) | 11 / 22 | 22 / 22 |
| Partial (concept only) | 0 | 0 |
| Not covered | 11 | 0 |
| FAQ questions | 5 | 13 |
| Duplicate Black Friday bars in DOM | 11 | 1 |
| Duplicate "Why trade together" grids | 2 | 1 |
| Duplicate onboarding blocks | 2 | 1 |
| Internal links to the three single-channel pages | 4 (mega menu only) | 14 |
| Sections with a distinct search intent | 2 (hero, FAQ) | 9 |

**What the old page was doing:** GSC shows no "combo" query at all. The URL ranks for brand terms (`sureshotfx`, `sureshot gold`, `sureshotfx gold`) and for sibling product terms (`forex vip signals`, `gold vip signals`) because the mega menu and duplicated market tabs mention them. It did not own the bundle category, and it did not answer the six cheapest objections — price, inclusion, MT5, Polish price intent, VIP access and the brand misspellings.

**What the new page does differently:**

1. States the bundle offer in the H1, meta and first paragraph, so "combo signals", "VIP combo" and "combo bundle" finally exist as page copy.
2. Answers "how much are they?", "is it included" and "mt5" in the FAQ with exact phrasing.
3. Surfaces the ten brand variants in visible copy and chips instead of leaving them to the mega menu.
4. Routes single-market intent to `/forex-vip-signals`, `/gold-vip-signals` and `/indices-vip-signals` so the combo page does not cannibalise them.

**What still needs work**

1. The combo category has no search volume yet in GSC. That is expected for a bundle page; track `combo signals`, `vip combo` and `forex gold indices` over the next 90 days before judging it.
2. `site:sureshotfx.com` is 46 of the 107 impressions — the page is being crawled as a brand URL, not a product URL. Internal links from the three single-channel pages will matter more than on-page edits.
3. `sureshot gold` (12 impressions, position 10.8) is the highest-volume non-tech query. It is handled by a chip and a review; if it keeps growing, give it a sentence in the brand FAQ.
