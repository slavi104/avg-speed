# sredna-skorost.online – SEO and AdSense notes

## What was added
- Canonical and SEO meta on `index.html`, `privacy.html`, `terms.html`
- OpenGraph/Twitter meta and JSON-LD `WebSite` schema on `index.html`
- `robots.txt` and `sitemap.xml` at the site root
- `ads.txt` already present with your publisher id

## AdSense
- Head contains `<meta name="google-adsense-account" content="ca-pub-5938719335702831">` and a consent-gated loader.
- Replace or keep the same publisher id if this is correct.
- To comply for EEA/UK, consider integrating a certified CMP for consent.

## Google Search Console
- Replace the placeholder token in `index.html`:
  `<meta name="google-site-verification" content="REPLACE_WITH_GSC_TOKEN">`
- Or add a file-based verification HTML if you prefer.

## Sitemap / Robots
- `robots.txt` references the sitemap at `https://sredna-skorost.online/sitemap.xml`.
- Update `sitemap.xml` if you add new pages.

## Deployment
- Ensure the site is deployed at the root of the domain (no subpath).
- After deploy, submit the sitemap URL in GSC.