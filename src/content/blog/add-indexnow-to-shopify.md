---
title: "How to Add IndexNow to Shopify: Manual Setup vs. Apps"
description: "Shopify won't let you host the IndexNow key file at your domain root. Here's the manual workaround, the app route, and how to get Bing indexing faster."
pubDate: 2026-07-19
---

If you have ever published a new product on your Shopify store and then waited days — sometimes weeks — for it to show up in Bing search results, IndexNow is the fix. It is a simple protocol that lets your store *tell* search engines the moment a URL changes, instead of waiting for a crawler to stumble across it.

The catch: Shopify does not support IndexNow out of the box, and the manual setup runs into a platform limitation almost immediately. This guide covers what IndexNow is, why it matters for Shopify stores, where the manual route breaks down, and how to set it up properly with an app in a few minutes.

## What is IndexNow?

[IndexNow](https://www.indexnow.org) is an open protocol, originally introduced by Microsoft Bing and Yandex, that flips the usual crawling model on its head. Instead of search engines repeatedly re-crawling your site to discover changes, your site sends a lightweight ping — "this URL was added," "this URL was updated," "this URL was deleted" — the moment something happens.

One ping is enough. Any search engine participating in IndexNow shares submitted URLs with the others, so a single notification reaches:

- **Bing**
- **Yandex**
- **Naver** (dominant in South Korea)
- **Seznam.cz** (major engine in Czechia)
- **Yep**

One important honesty note up front: **Google does not participate in IndexNow.** Pinging IndexNow does nothing for your Google rankings or Google indexing. Google relies on its own crawling and sitemap system. IndexNow is a Bing-ecosystem tool — and as we will see, that ecosystem is bigger than most merchants think.

## Why IndexNow matters for Shopify stores

### Your store changes constantly — Bing's crawler doesn't keep up

Shopify stores are unusually dynamic websites. Products go in and out of stock, prices change, variants get added, collections get reshuffled, seasonal pages launch and retire. Every one of those changes creates or modifies URLs.

Bing's crawler, left to its own devices, tends to visit smaller e-commerce sites infrequently. It is common to see new Shopify product pages sit unindexed on Bing for weeks, or to find Bing still showing an old price or a deleted product. If you have seen pages stuck in limbo in Bing Webmaster Tools, we cover that exact situation in [why your pages show as discovered but not crawled](/blog/bing-discovered-but-not-crawled/).

IndexNow short-circuits the waiting. The moment a product goes live, Bing knows about it.

### Bing's index reaches further than Bing.com

It is easy to dismiss Bing as a small slice of search traffic. But Bing's index powers far more than bing.com:

- **DuckDuckGo** sources results largely from Bing
- **Yahoo Search** is powered by Bing
- **ChatGPT search** uses Bing's index when it browses the web
- **Microsoft Copilot** answers shopping and product questions using Bing results

When someone asks ChatGPT "what's a good ceramic pour-over coffee dripper," the products it can find are the ones in Bing's index. If your new product is not indexed there, you are invisible across that entire ecosystem. (More on that in [how to get your Shopify products into ChatGPT](/blog/get-shopify-products-into-chatgpt/).)

So: faster Bing indexing is not just about Bing. It is about DuckDuckGo, Yahoo, and increasingly the AI assistants people use to shop.

## The manual route: how IndexNow setup normally works

On a normal website you control, adding IndexNow takes three steps:

1. **Generate an API key.** This is just a random hexadecimal string (you can generate one at indexnow.org or in Bing Webmaster Tools).
2. **Host the key file at your domain root.** You create a plain-text file named `{your-key}.txt` containing the key, and it must be reachable at `https://yourstore.com/{your-key}.txt`. This is how search engines verify that the pings for your domain actually come from you.
3. **Send pings.** Whenever a URL changes, you (or your platform) send an HTTP request to `https://api.indexnow.org/indexnow` with the URL and your key.

Simple enough — on WordPress, there is a plugin toggle for this. On a custom site, it is an afternoon of work.

### The Shopify catch: you can't host the key file

Here is where Shopify merchants hit a wall. **Shopify does not let you host arbitrary files at your domain root.** There is no way, through the admin or the theme editor, to make `https://yourstore.com/abc123yourkey.txt` serve a plain text file.

People have tried workarounds, and they are all hacky:

- **Theme template tricks** — manipulating Liquid templates to fake a `.txt` response. Fragile, breaks on theme updates, and often serves the wrong `Content-Type`, which can fail verification.
- **Redirects** — pointing the key URL at a file hosted elsewhere. Verification expects the file at your root; redirects are unreliable for this.
- **Proxying through a third-party server** — now you are maintaining infrastructure to serve one text file.

And even if you solve the key file problem, you still have step 3: something needs to actually *send the pings* every time a product, collection, page, or blog post changes. Shopify has no built-in mechanism for that — you would need to build and host your own webhook listener, which is real development work and one more thing to maintain.

This is exactly the kind of platform gap that apps exist to fill.

> **Skip the workarounds — [install Bing SEO: IndexNow for Bing free on the Shopify App Store](https://apps.shopify.com/bing-seo-indexnow-for-bing).** It handles key generation, verification, and automatic pings for every store change, with no theme edits and no code.

## The app route: automatic IndexNow in a few minutes

A dedicated IndexNow app solves both problems at once:

- **Key verification** — the app generates the API key and handles verification with the search engines for you, so you never touch a `.txt` file.
- **Automatic pings** — the app listens to Shopify's own webhooks, so every time you add, update, or delete a product, collection, page, or blog post, the corresponding URL is submitted instantly. No cron jobs, no manual submissions, no forgetting.

### Step-by-step: setting up Bing SEO: IndexNow for Bing

Here is the full setup with [Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) (free):

1. **Install the app.** Open the listing on the Shopify App Store, click **Install**, and approve the permissions. The app needs read access to your products, collections, pages, and blogs so it knows when URLs change.
2. **Let the app verify your store.** On first run, the app generates your IndexNow API key and completes domain verification automatically. There is nothing to upload and no DNS records to add.
3. **Run an initial bulk submission.** Automatic pings only cover *future* changes — your existing catalog also needs to get in front of Bing. Use the app's bulk submission feature to submit all your current product, collection, page, and blog URLs in one go. For a typical store this takes a couple of minutes.
4. **Verify it is working.** Make a small edit to a product (tweak the description) and check the app's submission history — you should see the URL pinged within moments. Over the following days, watch indexed-page counts in Bing Webmaster Tools trend upward.

From that point on, the app runs in the background. Publish a product, it gets pinged. Delete a discontinued item, Bing is told to drop it. You never think about it again.

### Pair it with the fundamentals

IndexNow works best on top of a healthy Bing setup, not instead of one. If you have not already:

- [Set up Bing Webmaster Tools for your Shopify store](/blog/bing-webmaster-tools-for-shopify/) so you can actually see indexing progress.
- [Submit your Shopify sitemap to Bing](/blog/submit-shopify-sitemap-to-bing/) as a baseline discovery channel.
- If your store is entirely missing from Bing, start with [why your Shopify store isn't showing up on Bing](/blog/shopify-store-not-showing-up-on-bing/).

## What about manual URL submission instead?

To be fair to the no-app route: Bing Webmaster Tools has a **URL Submission** feature that lets you paste in URLs by hand, and it works fine. If you run a tiny store that adds one product a month, logging into [Bing Webmaster Tools](/blog/bing-webmaster-tools-for-shopify/) and submitting the new URL manually is a reasonable workflow.

The trade-offs are the obvious ones: it only happens when you remember, it only covers Bing (not the other IndexNow engines), and it does not scale. If you update products weekly, run sales, or publish blog content, manual submission becomes a chore that quietly stops happening.

## Manual vs. app: the quick verdict

| | Manual IndexNow setup | Manual URL submission (BWT) | IndexNow app |
|---|---|---|---|
| Key file hosting | Blocked by Shopify | Not needed | Handled for you |
| Automatic on changes | Requires custom server | No | Yes |
| Covers Bing + Yandex + others | Yes (if you build it) | Bing only | Yes |
| Effort | High (dev work) | Ongoing manual work | One-time install |
| Cost | Your dev time + hosting | Free | Free (with our app) |

For virtually every Shopify merchant, the app route wins: the manual protocol setup is effectively blocked by the platform, and manual submission does not scale past a handful of URLs.

> **Ready to stop waiting on Bing's crawler?** [Install Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing) — it's free, takes about two minutes to set up, and automatically submits every product, collection, page, and blog change to Bing and Yandex from then on.

## FAQ

### Does IndexNow work with Google?

No. Google does not participate in the IndexNow protocol. IndexNow reaches Bing, Yandex, Naver, Seznam.cz, and Yep — and through Bing's index, surfaces like DuckDuckGo, Yahoo, ChatGPT search, and Copilot. For Google, keep relying on your sitemap and Google Search Console.

### Can I add IndexNow to Shopify without an app?

Not cleanly. IndexNow requires hosting a key verification file at your domain root, and Shopify does not allow arbitrary root-level file hosting. Workarounds involving theme template hacks or external proxies are fragile. You would also need your own server to send pings on every store change. An app handles both parts automatically.

### Will IndexNow improve my rankings?

IndexNow speeds up *indexing* — how quickly search engines learn about new and changed URLs. It does not directly change how those pages rank. Faster indexing means your pages are eligible to rank sooner, but ranking still depends on your content, relevance, and overall [Bing SEO](/blog/bing-seo-for-shopify/).

### How quickly does Bing index pages after an IndexNow ping?

The ping is received instantly, and Bing typically crawls submitted URLs much faster than it would through normal discovery — often within hours rather than days or weeks. Exact timing varies by site; indexing itself is still at Bing's discretion.

### Does submitting a URL repeatedly help it index faster?

No. One ping per change is all that is needed. IndexNow is designed for notifying engines *when something changes* — re-submitting an unchanged URL does not speed anything up.
