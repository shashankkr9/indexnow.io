# indexnow.io — Task List

Goal: rank top-5 for Shopify + Bing indexing queries and funnel organic traffic to
[Bing SEO: IndexNow for Bing](https://apps.shopify.com/bing-seo-indexnow-for-bing).

## Launch (done 2026-07-19)

- [x] Research SERP landscape (winnable queries: "shopify store not showing up on bing", "add indexnow to shopify", "bing seo shopify", "discovered but not crawled bing")
- [x] Archive old Lovable repo (`indexnow.io-old-lovable-archive`)
- [x] Build Astro content site: homepage + 8 guides with internal linking, JSON-LD, sitemap, robots.txt, llms.txt
- [x] Deploy to Vercel, attach `indexnow.io` + `www`, connect GitHub for auto-deploy
- [x] Namecheap DNS: apex A → 76.76.21.21, www CNAME → cname.vercel-dns.com
- [x] Site live at https://indexnow.io

## Immediate

- [x] Verify indexnow.io in **Bing Webmaster Tools** and submit `https://indexnow.io/sitemap-index.xml`
- [x] Verify in **Google Search Console** and submit the same sitemap
- [ ] Set up IndexNow pings for this site itself (dogfooding — we should practice what we sell)
- [x] Add an OG image (`/og.png`) so shares look good on social/Slack
- [ ] Delete old Netlify site `indexnowio` (nothing points to it anymore)
- [ ] Delete archived GitHub repo `shashankkr9/indexnow.io-old-lovable-archive` (needs `gh auth refresh -h github.com -s delete_repo`)

## Distribution (the fast wins)

- [x] Answer ranking forum threads (closed 2026-07-19 — answered the 2 highest-value ones):
  - [x] https://community.shopify.com/t/how-to-integrate-bings-indexnow-api-with-my-online-store/279297 (highest intent — people asking for exactly what the app does)
  - [x] https://community.shopify.com/t/bing-webmaster-zero-indexed-pages/566064
  - Skipped for now: "store not appearing on Bing" + "store not visible on Bing" threads (drafts exist in session notes); Microsoft Q&A thread is locked (migrated), can't reply
- [ ] Link indexnow.io from the app listing and from the app's dashboard/onboarding emails
- [ ] Cross-link from llms-txt app properties where relevant

## Content (next articles)

- [ ] "How to fix 'URL cannot appear on Bing' errors"
- [ ] "Bing Places for Shopify stores with a physical location"
- [ ] "DuckDuckGo SEO for Shopify" (same Bing plumbing, separate query demand)
- [ ] "How long does Bing take to index a new Shopify store?" (question-format, featured-snippet bait)
- [ ] Case study: indexing speed before/after IndexNow on a real store (screenshots from app data)
- [ ] Refresh comparison article whenever competitor pricing/ratings change

## Bigger levers

- [ ] **Bing Index Checker** free tool — enter store URL → sitemap pages vs `site:` indexed pages → show the gap → app CTA. Link magnet + lead gen. (Build on api.indexnow.io Django stack; needs a Bing results source.)
- [ ] IndexNow key validator / ping tester (captures non-Shopify developer traffic)
- [ ] Collect app reviews mentioning outcomes ("indexed in X days") to quote on the homepage
- [ ] Track rankings for target queries in Bing Webmaster Tools + GSC monthly

## Conventions

- Articles: markdown in `src/content/blog/`, slug = filename = URL. Frontmatter: title, description (140–160 chars), pubDate.
- Tone: honest (indexing ≠ ranking), step-by-step, exact UI paths, CTA blockquotes to the app, internal links between guides.
- Add new posts to the `featured` array in `src/pages/blog/index.astro` and to `public/llms.txt`.
