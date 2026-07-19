---
title: "How to Submit Your Shopify Sitemap to Bing (2-Minute Guide)"
description: "Submit your Shopify sitemap to Bing in two minutes: where the sitemap lives, exact steps in Bing Webmaster Tools, and how to fix common sitemap errors."
pubDate: 2026-07-19
---

Submitting your sitemap is the single fastest way to hand Bing a complete map of your Shopify store. The good news: Shopify already built the sitemap for you, and the actual submission takes about two minutes. Here's exactly how to do it, plus how to confirm it worked and what to do when it doesn't.

## Where Shopify's Sitemap Lives

Every Shopify store automatically gets a sitemap at:

```
https://yourstore.com/sitemap.xml
```

Open that URL in your browser and you'll see it's actually a **sitemap index** — a parent file that links out to child sitemaps for each content type:

- `sitemap_products_1.xml` — all your product pages
- `sitemap_collections_1.xml` — collection pages
- `sitemap_pages_1.xml` — standard pages (About, Contact, etc.)
- `sitemap_blogs_1.xml` — blog posts

Two things to know about it:

- **You can't edit it.** Shopify generates the sitemap automatically and there's no setting to add, remove, or reorder URLs. (Hidden or draft products are excluded for you.)
- **It updates itself.** Add a product, publish a blog post, or delete a collection, and the sitemap reflects the change automatically. You never resubmit it after edits.

You only ever submit the parent `sitemap.xml` — Bing follows it to all the child sitemaps on its own.

## Prerequisite: Verify Your Store in Bing Webmaster Tools

You can only submit a sitemap for a site you've verified. If you haven't added your store to Bing Webmaster Tools yet, do that first — it takes about ten minutes, and if you already use Google Search Console you can import your verification in one click. Full walkthrough here: [how to set up Bing Webmaster Tools for Shopify](/blog/bing-webmaster-tools-for-shopify/).

Already verified? Carry on — the rest really is two minutes.

## How to Submit the Sitemap: Exact Steps

1. Go to [bing.com/webmasters](https://www.bing.com/webmasters) and sign in.
2. Select your store from the site list (top left) if you have more than one site.
3. In the left sidebar, click **Sitemaps**.
4. Click the **Submit sitemap** button (top right).
5. Enter your full sitemap URL: `https://yourstore.com/sitemap.xml` — use your real domain, with `https://`.
6. Click **Submit**.

Done. Bing queues the sitemap for processing immediately.

## How to Confirm It Processed

Back on the **Sitemaps** screen, your sitemap appears in the list with a status column:

- **Pending / Processing** — normal right after submission. Give it anywhere from a few minutes to a couple of days.
- **Success** — Bing read the sitemap. The **Discovered URLs** count should roughly match the number of live products, collections, pages, and posts in your store.
- **Error** or **Couldn't fetch** — Bing couldn't read the file. Check that the URL opens in your browser without a redirect to a password page (common on stores that are still password-protected pre-launch — Bing can't crawl behind Shopify's storefront password).

A useful second check: open **Site Explorer** in the sidebar a few days later. You should see Bing's picture of your store filling in with the URLs from the sitemap.

> **Why submit by hand at all?** [Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) pushes every product, collection, page, and blog change straight to Bing the moment it happens — and can bulk-submit your whole catalog on install. Free, by ArcSpeed, rated 4.6 stars.

## Common Errors and Fixes

**Sitemap shows "Success" but 0 pages indexed.** This is the most common complaint, and it's usually not a sitemap problem at all. A successful sitemap means Bing *discovered* your URLs — it doesn't mean Bing chose to crawl or index them yet. Bing often sits on discovered URLs for weeks, especially on newer or low-authority stores. We wrote a full guide on this exact situation: [Bing discovered but not crawled](/blog/bing-discovered-but-not-crawled/).

**"Couldn't fetch" or HTTP errors.** Almost always one of: the store is still password-protected, the URL was typed with a typo or `http://` instead of `https://`, or you submitted a child sitemap URL that has since changed. Fix the underlying issue, then resubmit.

**Discovered URL count looks too low.** Remember the sitemap only includes *live* content. Draft and hidden products, and pages restricted to specific markets, won't appear. If genuinely live pages are missing from Bing, check them individually with **URL Inspection**.

**Old deleted pages still showing.** The sitemap drops deleted URLs automatically, but Bing removes them from its index on its own schedule. There's nothing to fix on the Shopify side.

## A Sitemap Is Passive — IndexNow Is Active

Here's the limitation nobody mentions: submitting a sitemap doesn't make Bing crawl anything. It just publishes a list and hopes Bing checks it soon. Bing still crawls on its own schedule, which means:

- A new product can sit unindexed for days or weeks until the next crawl.
- Price and inventory updates reach Bing's index late.
- Deleted pages linger in results until Bing recrawls them.

The active alternative is **IndexNow** — an open protocol ([indexnow.org](https://www.indexnow.org)) supported by Bing, Yandex, Naver, Seznam.cz, and Yep (not Google). Instead of waiting to be crawled, your store pings the search engine the instant a URL is added, changed, or deleted. Shopify has no built-in support for it, but it's straightforward to add with an app — here's [how to add IndexNow to Shopify](/blog/add-indexnow-to-shopify/), and a comparison of the [best IndexNow apps for Shopify](/blog/best-indexnow-apps-for-shopify/) if you want options.

The best setup uses both: the sitemap as Bing's complete reference map of your store, and IndexNow as the real-time change feed. Neither guarantees rankings — nothing does — but together they remove every indexing delay that's within your control.

> **Two minutes for the sitemap, zero for everything after.** Install [Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) and every future change to your products, collections, pages, and posts is submitted to Bing automatically. Free to install.

## FAQ

### Do I need to resubmit my Shopify sitemap when I add products?

No. Shopify updates the sitemap automatically, and Bing rechecks submitted sitemaps periodically. Submit once and you're done — though if you want Bing notified of changes immediately rather than at its next check, that's what [IndexNow](/blog/add-indexnow-to-shopify/) is for.

### Should I submit the child sitemaps (products, collections) separately?

No — submit only the parent `sitemap.xml`. Bing follows the index file to every child sitemap automatically, and child sitemap URLs can change as your catalog grows.

### How long does Bing take to index my store after sitemap submission?

There's no fixed timeline. The sitemap itself usually processes within hours to a couple of days, but crawling and indexing the URLs inside it can take days to weeks, at Bing's discretion. If your store still isn't appearing after a few weeks, see [why your Shopify store isn't showing up on Bing](/blog/shopify-store-not-showing-up-on-bing/).

### My sitemap says "Success" but zero pages are indexed. Is it broken?

Probably not — discovery and indexing are separate steps, and Bing can take weeks to crawl discovered URLs. See the dedicated guide to [Bing discovered but not crawled](/blog/bing-discovered-but-not-crawled/) for how to diagnose and speed it up.

### Does submitting my sitemap to Bing help with Google too?

No. Bing Webmaster Tools only affects Bing and the engines it powers (DuckDuckGo, Yahoo, ChatGPT search, Copilot). Google needs its own submission through Google Search Console — though Shopify's sitemap URL is the same for both.
