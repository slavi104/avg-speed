# sredna-skorost.online – Average Speed (GPS) Calculator

[![Buy Me A Coffee](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=%E2%98%95%EF%B8%8F&slug=slavi104&button_colour=22c55e&font_colour=ffffff&font_family=Inter&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/slavi104)

Live site: https://sredna-skorost.online/

Medium: Bulgarian (bg). The app UI is in Bulgarian; this README is in English for wider context.

## What it is
Client‑side web app that calculates your average speed using the browser's GPS. It can automatically start and stop tracking inside predefined average‑speed enforcement segments on Bulgarian roads (e.g., AM "Тракия", "Хемус", "Струма"). Works offline after the first load.

## Key features
- Offline after first load (no backend; purely client‑side)
- Auto start/stop inside predefined road segments (configurable)
- Live readouts: current speed, elapsed time, and distance
- Average speed computed continuously from distance and elapsed time
- Dark/light theme toggle with persistence
- Privacy‑first: geolocation stays on device; consent‑gated AdSense
- SEO ready: canonical, OpenGraph/Twitter, JSON‑LD, robots and sitemap

## How it works
- Uses `navigator.geolocation.watchPosition` for continuous fixes.
- Computes distance via the Haversine formula and time via accumulated elapsed milliseconds; average speed = distance_km / time_h.
- Detects if you are inside a configured segment start/end to auto start/stop.
- Consent banner stores a local preference; AdSense loads only if accepted.

## Project structure
- `index.html` – main single‑page app (UI, logic, consent, theme)
- `privacy.html` – privacy policy (Bulgarian)
- `terms.html` – terms of use (Bulgarian)
- `robots.txt` – points to the sitemap
- `sitemap.xml` – lists public pages
- `ads.txt` – your AdSense publisher id
- `CNAME` – custom domain config (GitHub Pages / similar)

## Configuration
- Google Search Console: in `index.html`, replace
  `<meta name="google-site-verification" content="REPLACE_WITH_GSC_TOKEN">`.
- AdSense: the head includes `<meta name="google-adsense-account" content="ca-pub-5938719335702831">` and loads the AdSense JS only after consent. Replace the publisher id if needed.
- Road segments: edit the `ROAD_RANGES` array in `index.html` with accurate coordinates and radii for each segment start/end.

## Privacy and ads
- Geolocation is processed locally in the browser; nothing is sent to a server.
- A cookie/LS value stores only the consent choice for ads (accept/reject).
- Google AdSense loads only after explicit consent (satisfying EEA/UK expectations). See `privacy.html` for details and helpful Google links.

## SEO
- Canonical and alternate locales, OpenGraph/Twitter metadata, and JSON‑LD `WebSite` schema are included on `index.html`.
- `robots.txt` advertises the sitemap at `https://sredna-skorost.online/sitemap.xml`.

## Development
Because this is a static site, you can open `index.html` directly in a browser. For a cleaner experience (and to avoid some browser geolocation restrictions), serve it over a local HTTP server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

Tip: when testing geolocation on desktop, most browsers let you emulate location in devtools.

## Support the project
If this app helps you, you can support development:

[![Buy Me A Coffee](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=%E2%98%95%EF%B8%8F&slug=slavi104&button_colour=22c55e&font_colour=ffffff&font_family=Inter&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/slavi104)

Or open an issue with ideas, road segment corrections, or improvements.