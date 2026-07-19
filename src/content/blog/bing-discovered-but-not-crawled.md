---
title: "'Discovered but Not Crawled' in Bing Webmaster Tools: How to Fix It on Shopify"
description: "Shopify pages stuck on 'Discovered but not crawled' in Bing? Learn what the status really means and the fixes that make Bing prioritize your URLs."
pubDate: 2026-07-19
---

You open Bing Webmaster Tools, inspect a product page, and see it: **"Discovered but not crawled."** You check another URL. Same thing. Half your catalog, sitting in limbo.

If it's any consolation, this is probably the single most common Bing indexing complaint from Shopify merchants — the forums are full of threads about it, most ending without a real answer. This guide is the real answer: what the status actually means, why Shopify stores are especially prone to it, and the fixes that work, roughly in order of impact.

## What "Discovered but not crawled" actually means

The status is exactly what it says, and understanding the two halves matters:

- **Discovered**: Bing knows the URL exists. It found it in your sitemap, through a link on another page, or via a submission. Your basic setup is working — this is *not* a robots.txt problem, a password problem, or a verification problem. If it were, Bing wouldn't know the URL at all.
- **Not crawled**: Bing has chosen not to fetch the page yet. It has the URL in a queue and hasn't prioritized spending crawl resources on it.

That second half is the key insight: **this is a prioritization decision, not an error.** There's nothing "broken" to repair. Bing crawls a finite number of pages per site per day — its crawl budget for you — and it allocates that budget based on how valuable it expects each URL to be. "Discovered but not crawled" means your page lost that internal auction.

So the fix isn't debugging. It's persuasion: give Bing stronger signals that the URL is worth crawling, and use the channels that let you say so directly.

## Why this hits Shopify stores so often

A few things about how Shopify stores are structured make them especially likely to pile up discovered-but-not-crawled URLs:

### Crawl budget vs. catalog size

A Shopify store with 300 products can easily expose over a thousand URLs: products, collections, tag-filtered collection pages, blog posts, policy pages. A new domain gets a small crawl budget. Small budget, big URL list — most of the list waits in the queue.

### Thin and near-duplicate pages

Bing's crawler learns from what it has already fetched. If the product pages it *has* crawled carry one-line descriptions, manufacturer boilerplate shared with fifty other stores, or near-identical content across variants, it lowers its expectations for the rest of your URLs — and deprioritizes them. Shopify's tag pages (`/collections/all/tag-name`) are notorious here: dozens of URLs showing reshuffled subsets of the same products.

### Weak external signals

Backlinks and mentions tell Bing a site is worth crawling deeply. A new store that no one links to yet gives Bing little reason to raise its crawl budget. This isn't unfair — it's how crawlers ration resources across the entire web.

### Domain age

New domains start with minimal trust. Even with perfect content, a store that launched last month will see more URLs held in "discovered" status than one with two years of history. Some of the cure here is simply time — but not all of it, as we'll see.

If your store has broader visibility problems than just this status — like not appearing on Bing at all — start with our full [troubleshooting guide for Shopify stores not showing up on Bing](/blog/shopify-store-not-showing-up-on-bing/) and come back here.

## Fix 1: Request indexing for your priority pages

The quickest lever, best for a small number of high-value URLs:

1. In [Bing Webmaster Tools](https://www.bing.com/webmasters), open **URL Inspection** from the left sidebar.
2. Paste the stuck URL and run the inspection.
3. Confirm the status and click **Request Indexing**.

This tells Bing directly: a verified site owner considers this URL important. It often gets individual pages crawled where passive waiting wouldn't.

The limitation is obvious: it's manual, one URL at a time, with submission limits. Use it for your homepage, top collections, and best sellers. For the other four hundred URLs, keep reading.

> **Four hundred URLs is not a copy-paste job.** [Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) bulk-submits your whole catalog to Bing via IndexNow and keeps it synced automatically. Free.

## Fix 2: Strengthen internal linking

Bing partly infers a page's importance from how your own site treats it. A product URL that appears only in the sitemap, buried on page six of a paginated collection, looks unimportant. The same URL linked from your homepage looks like a priority.

Practical moves on Shopify:

- **Feature key products on the homepage.** A "Best sellers" or "Featured collection" section (Shopify admin → Online Store → Themes → Customize) creates direct homepage-to-product links — the strongest internal signal you can send.
- **Tighten your navigation.** Make sure every collection you care about is reachable from the main menu (Online Store → Navigation), not orphaned.
- **Cross-link between products.** "Pairs well with" or related-products sections give crawlers more paths into deep pages.
- **Link products from blog posts.** A buying guide that links to ten product pages hands each of them a contextual internal link.

The test worth applying: can a crawler reach every important page within three clicks of the homepage? If not, restructure until it can.

## Fix 3: Deal with thin variants and tag pages

This is the uncomfortable one, because it sometimes means *removing* URLs from Bing's view — and it's often the highest-impact fix for stores with large discovered-but-not-crawled backlogs.

- **Beef up product descriptions.** Replace manufacturer boilerplate with original copy: who the product is for, sizing guidance, materials, real answers to real questions. Pages worth crawling get crawled.
- **Stop exposing thin tag pages.** If your theme links to dozens of `/collections/all/tag-name` URLs that merely reshuffle the same products, you're spending crawl budget on pages with no unique value. Either build those tags into real curated collections with their own descriptions, or keep them out of internal links so the budget flows to pages that matter.
- **Consolidate near-duplicate products.** Five separate product pages for five colors of the same t-shirt, each with identical copy, is four pages of wasted budget. Use Shopify's variants on a single product page instead.

The principle across all three: every URL you expose competes with your other URLs for the same crawl budget. Fewer, stronger pages beat many thin ones.

## Fix 4: Push the queue with IndexNow

Everything above improves the signals Bing weighs. This fix changes the mechanism entirely.

**IndexNow** is an open protocol (indexnow.org), supported by Bing, Yandex, Naver, Seznam.cz and Yep — not Google — that lets a site notify search engines the moment a URL is added or changed, rather than waiting to be crawled. And notification-driven discovery is treated differently from passive discovery: a fresh IndexNow ping is a signal from the verified site owner that *this URL, right now,* has something new. That's precisely the prioritization nudge a "discovered but not crawled" URL is missing — it's the exact scenario the protocol was designed for.

Two honest caveats. First, IndexNow prompts Bing to *crawl and evaluate*; it doesn't force indexing, and it doesn't rescue genuinely thin pages — which is why Fix 3 still matters. Second, indexing is not ranking; getting crawled is the entry ticket, not the prize.

You can implement IndexNow yourself — generate a key, host the key file, call the API on every change. Our [step-by-step IndexNow setup guide for Shopify](/blog/add-indexnow-to-shopify/) walks through it. But since Shopify doesn't let you hook into product updates without an app anyway, most merchants are better served by letting one do the work.

**Bing SEO: IndexNow for Bing** (free, by ArcSpeed, rated 4.6 stars with 29 reviews) handles both halves of the problem:

- **Bulk submission** of your existing URLs — the direct treatment for a backlog of discovered-but-not-crawled pages.
- **Automatic submission** to Bing and Yandex whenever a product, collection, page, or blog post changes, so new and updated URLs never sit in the passive-discovery queue in the first place.

> **Make Bing come to you.** Install [Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) once and every product change pings Bing the moment it happens. No key files, no API calls, no cost.

## What to expect after applying the fixes

Set realistic expectations:

- **Requested URLs** are usually the first movers — recheck them in URL Inspection after a few days.
- **Bulk IndexNow submissions** put your whole list in front of Bing at once, but Bing works through it at its own pace; expect gradual movement, not an overnight flip.
- **Internal linking and content improvements** compound slowly as Bing re-crawls and recalibrates how much budget your store deserves.
- **Some URLs may never be crawled** — and if they're thin tag pages or duplicate variants, that's Bing making the right call. Judge success by whether your *important* pages move, not by the total count.

If pages move from "discovered" to crawled but then don't rank, that's the next battle — content, relevance, and authority — covered in our [Bing SEO guide for Shopify](/blog/bing-seo-for-shopify/).

## FAQ

### Is "Discovered but not crawled" an error I need to fix?

It's not a technical error — nothing is misconfigured. It's Bing deciding your URL isn't yet worth its crawl budget. The "fix" is changing that calculation: stronger internal links, better content, and direct signals like Request Indexing and IndexNow submissions.

### How long do pages stay in "Discovered but not crawled"?

There's no set duration. Some URLs get crawled within days; others sit for weeks or months; genuinely low-value URLs may never be crawled at all. The fixes in this guide shorten the wait for pages Bing judges worthwhile — they can't force a crawl on a fixed schedule.

### Will submitting my sitemap again fix it?

No. Your sitemap is how these URLs got *discovered* in the first place — resubmitting it repeats a step that already succeeded. The bottleneck is crawl prioritization, which sitemaps don't influence. Use Request Indexing or IndexNow to send a priority signal instead.

### Does IndexNow force Bing to index my pages?

No, and be wary of anything that claims otherwise. IndexNow gets your URL in front of Bing immediately and flags it as freshly changed by the site owner — a strong prioritization signal. Bing then crawls and decides on indexing based on page quality. It moves you up the queue; it doesn't skip the evaluation.

### Does this status affect Google too?

No. This is a Bing Webmaster Tools status about Bing's crawler only (Google Search Console has its own similar status, "Discovered — currently not indexed," managed separately). Note that fixing it on Bing pays off beyond Bing itself: Bing's index also powers DuckDuckGo, Yahoo, ChatGPT search and Microsoft Copilot.
