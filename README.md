# indexnow.io

Marketing + SEO content site for the free Shopify app
[Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing).

Goal: rank for Shopify + Bing indexing queries ("shopify store not showing up on
bing", "add indexnow to shopify", "bing seo shopify", ...) and funnel readers to
the app. The app itself lives at `api.indexnow.io` / `dashboard.indexnow.io`
(separate repo); this repo is the apex-domain content site only.

## Stack

- [Astro](https://astro.build) — static output, zero client JS
- Articles are markdown in `src/content/blog/`
- Deployed to GitHub Pages via `.github/workflows/deploy.yml` (custom domain via `public/CNAME`)

## Development

```bash
npm install
npm run dev        # localhost:4321
npm run build      # static build into dist/
```

## Adding an article

Drop a markdown file in `src/content/blog/` with frontmatter:

```yaml
---
title: "..."
description: "..."   # meta description, 140-160 chars
pubDate: 2026-07-19
---
```

The filename becomes the URL: `my-post.md` → `/blog/my-post/`. Add the slug to
the `featured` array in `src/pages/blog/index.astro` to control listing order,
and link it from related articles.

## DNS (one-time)

Point the apex domain at GitHub Pages:

- `A` records for `indexnow.io` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- In the repo: Settings → Pages → Source: GitHub Actions, custom domain `indexnow.io`, enforce HTTPS
