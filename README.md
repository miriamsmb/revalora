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
index.html               Page markup, section by section
css/fonts.css             @font-face declarations (self-hosted DM Sans, Playfair Display, Material Symbols Outlined)
css/styles.css             Layout, color tokens, responsive rules
assets/fonts/               Downloaded .woff2 font files
assets/icons/                Logo + Figma-exported SVG icons (badges, needs-card icons)
assets/images/                Photos, the Brazil map SVG, and the background texture
assets/favicon.svg          Site favicon
```

## Assets

The Figma file's asset CDN wasn't reachable from the environment this was first built in, so the page originally shipped with placeholder blocks and a Material Symbols icon substitute. All real assets (photography, the Brazil/Nordeste/Recife map, icons, and the app logo) have since been supplied directly and are in place under `assets/`.

A couple of adaptations from the original Figma design are worth noting:

- The 4-step "economia circular" cycle uses the real step photos, captioned Coleta → Triagem → Transformação → Novo produto.
- The plastic-transformation section uses a single product photo (bag + reclaimed material) rather than the original two-image collage.

## Content notes

- The Figma file included small "cursor" and "tip" annotations (e.g. "o ícone da setinha te mostra onde tem mais informações") that describe hotspot interactions in the Figma prototype itself. These aren't part of the shipped page, since there's no corresponding interactive layer here.
- The vertical, rotated "REVALORA" wordmark from the design was implemented as a horizontal logo lockup for legibility/accessibility on a real page.
- The 4-step "economia circular" cycle graphic was simplified into a labeled step sequence (Coleta → Triagem → Transformação → Novo produto); the original photos for these steps were not available (see above).
