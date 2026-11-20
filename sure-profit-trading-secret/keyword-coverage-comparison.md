# Keyword coverage: previous vs new targeting

**Page:** `https://sureshotfx.com/sure-profit-trading-secret`
**Data:** Google Search Console, `sc-domain:sureshotfx.com`, 90 days. 0 clicks, 30 impressions, 7 queries.
**Live page measured:** 1,236 visible words, 4 H1s, 2 H2s, no structured data, no FAQ.

### The short version

The live page targets the product name and generic "secret" words. GSC shows no demand for the product name and page-six rankings for vague "profit secret" / "forex secret" phrases. The page is a **$4.99 beginner forex ebook**, so the rebuild targets the beginner-book category instead.

### Legend

| Symbol | Meaning |
|---|---|
| ✅ | Query phrase appears on the page |
| ❌ | Not covered |
| n/a | Out of scope (technical or irrelevant) |

---

## 1. Old GSC queries

| Query | Impr. | Pos | Previous | New | Decision |
|---|---|---|---|---|---|
| site:sureshotfx.com | 15 | 45.8 | n/a | n/a | Technical, not page copy |
| profit secret | 6 | 63.7 | ❌ | ❌ | Too generic; no purchase intent |
| surefire forex trading | 4 | 72.2 | ❌ | ❌ | Different brand or misspelling, not this book |
| surefire forex | 2 | 79.5 | ❌ | ❌ | Same |
| forex secret | 1 | 66.0 | ❌ | ❌ | Too generic |
| forex secret trading | 1 | 65.0 | ❌ | ❌ | Too generic |
| sure shot forex | 1 | 80.0 | ❌ | ✅ | Brand FAQ spelling list |

**Old-query score:** 0 of 6 targetable queries covered before, 1 after. That is intentional. Five of the six are the wrong target and should not be chased.

The one exception is `sure shot forex`, a brand misspelling, now absorbed by the brand FAQ.

---

## 2. New target cluster (no history on this URL yet)

These are the terms the rebuild is built around. They do not appear in this URL's GSC data because the page never used them.

| Keyword | Intent | Where it lives |
|---|---|---|
| **forex trading book for beginners** | Commercial | Title, H1, opening paragraph |
| forex trading ebook | Commercial | Hero, meta, FAQ |
| forex trading book pdf | Transactional | Pricing, FAQ, schema |
| beginner forex trading book | High intent | H1, body |
| learn forex trading book | Commercial investigation | What you learn |
| forex technical analysis book | Topic | Chapter 5, FAQ |
| forex trading basics book | Beginner | What is it, chapters |
| Sure Profit Trading Secret | Brand | H1, title, schema |
| SureShotFX ebook / book | Brand | Author block, FAQ |

The page now has one H1, a definition, a six-chapter breakdown, an audience section, a price card and a 10-question FAQ to support these terms.

---

## 3. Cannibalisation check

`/blog/books-for-beginner-forex-traders` already has **1,986 impressions** for the "forex books" cluster:

- best forex trading books: 238 impressions, position 49.4
- books on forex trading: 175, position 43.8
- forex trading books: 164, position 48.2
- forex trading book: 29, position 27.0
- best books on forex trading for beginners: 10, position 57.1

That blog post is the **list hub**. The product page should own the single-book/PDF intent and link to the blog, not compete for "best books" list queries. The rebuild does that: the blog is not targeted, and the page links to Behind the Candle and VIP signals instead of publishing another list.

---

## 4. Overall

| Metric | Previous design | New design |
|---|---|---|
| Visible words | 1,236 | 1,785 |
| H1 tags | 4 | 1 |
| H2 tags | 2 | 9 |
| FAQ questions | 0 | 10 |
| Structured data | None | `Book`, `Offer`, `BreadcrumbList`, `FAQPage` |
| Pages / chapters stated | Not stated | 81 pages / 6 chapters (from cover) |
| Duplicate Black Friday bars | 11 | 1 |
| Original price | $4.99 | $4.99 |

**What the old page was doing:** it repeated the product name in four H1s, used generic "secret strategy" copy and had no chapter list, no FAQ and no schema. It ranked for vague "secret" phrases at position 63-80, which is where a page with no category language ends up.

**What the new page does differently:**

1. Names the category in the H1 and title: a forex trading book for beginners.
2. Uses the real cover image, which shows the contents page, to document 81 pages and six chapters.
3. Adds the audience, outcomes, author, reviews, price and a 10-question FAQ.
4. Adds `Book` and `Offer` schema with the $4.99 price and page count.

**What still needs work**

1. The new category terms have no GSC history on this URL. Rankings will depend on internal links from the books blog post, the Behind the Candle page and the footer.
2. `surefire forex` should be confirmed with the client. If it is another brand, keep ignoring it. If it is a known misspelling of SureShotFX, handle it in the brand FAQ only.
3. The page needs a real checkout URL and a confirmation that the book is still 81 pages before launch.
