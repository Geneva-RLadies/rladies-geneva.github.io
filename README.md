# RLadies+ Geneva — Quarto site

The Geneva chapter of [RLadies+](https://rladies.org/), a worldwide organisation
promoting gender diversity in the R community.

Built with [Quarto](https://quarto.org). The page is a single `index.qmd` that
carries the design as a raw-HTML block; the visual identity lives in
`styles.css`. Bootstrap is disabled (`theme: none`) so the custom styling
renders exactly as designed.

## Files
| File | Purpose |
|------|---------|
| `_quarto.yml` | Project + HTML format configuration |
| `index.qmd` | The page content (hero, about, evidence, events, …) |
| `styles.css` | RLadies+ brand styling (Blue Violet, Poppins, Inconsolata) |
| `head.html` | Google Fonts, favicon, social-preview meta |
| `.github/workflows/publish.yml` | CI that renders and deploys on every push |

## Preview locally
Install Quarto (bundled with RStudio, or from quarto.org), then:

```bash
quarto preview      # live-reloading local preview
quarto render       # one-off build into _site/
```

No R or Python is executed — the page is pure content — so a bare Quarto
install is enough.

## Publish to GitHub Pages

**Option A — CI (recommended).** Push this folder to a GitHub repo. The included
workflow renders the site and pushes the output to a `gh-pages` branch. Then set
**Settings → Pages → Source: Deploy from a branch → `gh-pages` / `(root)`**.
Every later push to `main` redeploys automatically.

**Option B — one command.** With Quarto and git installed locally:

```bash
quarto publish gh-pages
```

## Editing
Content is the raw HTML inside the ` ```{=html} ` block in `index.qmd`. Search
for `TODO` to fill in the Meetup URL, contact email, social handles, and the
next-event block. Swap the placeholder favicon in `head.html` for the official
one from [rladies/branding-materials](https://github.com/rladies/branding-materials).

To grow this into a multi-page site later, add `.qmd` pages and a `navbar:` under
`website:` in `_quarto.yml`; an events **listing** page is a natural next step.

Content licensed CC BY 4.0.
