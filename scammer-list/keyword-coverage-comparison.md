# Scam alert: keyword coverage and decision

**Page:** `https://sureshotfx.com/scammer-list`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, 90 days. 0 clicks, 37 impressions, 6 queries.
**Live page measured:** 921 visible words, H1 "Terms And Conditions", a stale "2025" title, no FAQ, no schema, ~20 handles with two duplicates.

## The decision

**Keep the page live, noindex it.** It has a real user-safety job and no SEO job.

- 0 clicks in 90 days.
- It appears only for brand, brand-review and unrelated group names.
- The indexed snippet would be a list of accused Telegram handles, which is the riskiest possible snippet for the brand.
- The current H1 is wrong and the title is a year out of date.

The rebuild keeps the URL, fixes the content and sets `noindex, follow`. It stays reachable from the footer and support replies.

---

## 1. Old GSC queries

| Query | Impr. | Pos | Previous | New | Decision |
|---|---|---|---|---|---|
| site:sureshotfx.com | 15 | 16.2 | n/a | n/a | Technical |
| sureshotfx | 11 | 24.4 | ✅ | ✅ | Brand, in title and body |
| surefx review | 5 | 63.2 | ❌ | ❌ | Different brand; not targeted |
| the sure fx group | 3 | 81.3 | ❌ | ✅ | FAQ: "Is The Sure FX Group official?" |
| sureshotfx review | 2 | 51.0 | ❌ | ❌ | Review intent; belongs on the review pages |
| sureshot forex | 1 | 78.0 | ❌ | ✅ | Brand spelling list |

**Score:** 1 of 5 non-technical queries before, 3 of 5 after. The two that remain are a different brand and a review query, both deliberately left alone.

---

## 2. New cluster (only relevant if the page is ever indexed)

The page is noindexed, so these are not active targets. If legal review later approves indexing, the only honest cluster is brand-trust:

| Keyword | Intent |
|---|---|
| sureshotfx scam | Brand trust |
| fake sureshotfx telegram | Brand trust |
| sureshotfx impersonator | Brand trust |
| is sureshotfx legit | Brand trust |
| fake forex telegram account | Category, risky |

Never target "scammer list" generically. It invites legal exposure and the wrong audience.

---

## 3. Overall

| Metric | Previous design | New design |
|---|---|---|
| H1 | "Terms And Conditions" | "SureShotFX scam alert: fake accounts and impersonators" |
| Title | "…Scammer List – Stay Safe in 2025" | "SureShotFX Scam Alert 2026: Fake Telegram Accounts" |
| Visible words | 921 | 1,516 |
| FAQ questions | 0 | 10 |
| Schema | None | `WebPage`, `BreadcrumbList`, `FAQPage` |
| Duplicate handles | 2 | 0 |
| Handles listed | ~20 | 18 unique |
| Official channels block | No | Yes |
| Reporting steps | No | 4 steps |
| Legal disclaimer | No | Yes |
| Robots | Indexable | `noindex, follow` |

**Still needs work:** legal review of the handle list, confirmation that the list is current, and a decision on whether the page should ever be indexed. Keep it noindexed until both are done.
