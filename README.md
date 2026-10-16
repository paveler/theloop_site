# theloopengine.com

Landing page for [theloop](https://github.com/paveler/theloop), the agent loop as a stateless HTTP service.

Plain static HTML: no build, no JS. Everything that gets published is in `site/`; a push to `main` deploys it to GitHub Pages.

- `site/index.html` — the page, with inline CSS and JSON-LD (the FAQ in JSON-LD must match the visible FAQ word for word)
- `site/llms.txt`, `robots.txt`, `sitemap.xml` — for crawlers and AI assistants; bump `lastmod` in the sitemap when content changes
- `site/fonts/` — self-hosted latin subsets (OFL), preloaded in `<head>`
- `src-assets/` — sources for the OG image and icons

Preview locally:

```bash
python3 -m http.server 4173 --directory site
```

Regenerate the OG image (needs Chrome):

```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --hide-scrollbars --force-device-scale-factor=1 --window-size=1200,630 --virtual-time-budget=8000 --screenshot="$PWD/site/og.png" "file://$PWD/src-assets/og.html"
```
