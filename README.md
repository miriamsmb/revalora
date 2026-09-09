# Revalora — O valor da sobra

Static implementation of the Figma design ["Dataviz - Infográfico"](https://www.figma.com/design/ELSfPAusG40l5B3696feDf/Dataviz---Infogr%C3%A1fico?node-id=96-2) (node `96:2`).

A single-page infographic about municipal solid waste and circular economy in Brazil/Recife, built with plain HTML, CSS and self-hosted webfonts — no build step or framework required.

## Running locally

```
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Structure

```
index.html          Page markup, section by section
css/fonts.css        @font-face declarations (self-hosted DM Sans, Playfair Display, Material Symbols Outlined)
css/styles.css        Layout, color tokens, responsive rules
assets/fonts/          Downloaded .woff2 font files
assets/favicon.svg     Site favicon
```

## Placeholder assets

The network policy in the environment this was built in blocked direct access to Figma's asset CDN (`figma.com`), so the original photography, the Brazil/Recife map illustration, and a few decorative vector graphics from the design could not be downloaded.

To keep the page visually complete these were substituted with:

- **Icons** — [Material Symbols](https://fonts.google.com/icons) (self-hosted), matching the icon names used in the Figma file (recycling, bar_chart, groups, domain, local_shipping, search, handshake, paid, error, eco, etc).
- **Photography** (hero image, step/cycle photos, artisan/product photos, phone-mockup screen) — soft gradient placeholder blocks (`.ph-image`) sized and positioned to match the design.
- **Brazil → Nordeste → Recife map** — a simplified nested-circle diagram instead of the literal map illustration.

**To finish the page with real assets:** export the corresponding images from the Figma file and drop them into `assets/images/`, then swap each `.ph-image` placeholder `<div>` in `index.html` for an `<img>` tag pointing at the new file.

## Content notes

- The Figma file included small "cursor" and "tip" annotations (e.g. "o ícone da setinha te mostra onde tem mais informações") that describe hotspot interactions in the Figma prototype itself. These aren't part of the shipped page, since there's no corresponding interactive layer here.
- The vertical, rotated "REVALORA" wordmark from the design was implemented as a horizontal logo lockup for legibility/accessibility on a real page.
- The 4-step "economia circular" cycle graphic was simplified into a labeled step sequence (Coleta → Triagem → Transformação → Novo produto); the original photos for these steps were not available (see above).
