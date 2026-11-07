# Levidev Studio — `assets/` (documented tree)

**Public reference** for brand SVGs, GBP uploads, kit collateral, posts, letterhead, and JSON-LD snippets. Root README and shareable links should use paths under `assets/`. An optional internal `final/` tree may mirror this layout; when both exist, `final/` can win for regeneration — sync into `assets/` before publishing links.

Legal name **PT. Levidev Studio Digital** appears on letterhead only, not in logo SVGs.

## Layout

| Path | Purpose |
|------|---------|
| **Root `*.svg`** | Canonical lockups (`icon-only-*`, `full-icon-*`, `wordmark-*`, `wordmark-text-*`, `banner-*`, `cover-*`). |
| `marks/` | Wordmark variants aligned with root SVGs (light/dark and animated). |
| `gbp/` | Google Business Profile PNG/SVG exports. **Banner previews** as `banner*.svg` beside `banner.png` / `banner-light.png`. |
| `kit/` | Brand kit (platform icons, social cards, boards, HTML previews). Open `kit/presentation-board.html` from this folder. |
| `posts/` | GBP post images (`services-*`, `start-*`, EN/ID). |
| `letterhead/` | A4 HTML/PDF/SVG kopsurat — see `letterhead/README.md`. |
| `schema-*.jsonld` | Structured data snippets for the site. |

## Naming cheat sheet (canonical root → GBP PNG)

| Canonical (`assets/` root) | `assets/gbp/` PNG (static source) |
|---------------------------|-----------------------------------|
| `icon-only-light.svg` | `icon-only.png`, `logo-symbol.png` |
| `icon-only-dark.svg` | `icon-only-dark.png`, `logo-symbol-dark.png` |
| `full-icon-light.svg` | `logo-wordmark.png` |
| `full-icon-dark.svg` | `logo-dark.png` |
| `wordmark-light.svg` | `wordmark.png` |
| `wordmark-dark.svg` | `wordmark-dark.png` |
| `wordmark-text-light.svg` / `marks/wordmark-text-light.svg` | `logo-text-light.png` |
| `wordmark-text-dark.svg` / `marks/wordmark-text-dark.svg` | `logo-text-dark.png` |
| `wordmark-text-wide-light.svg` / `marks/wordmark-wide-light.svg` | `wordmark-text-wide-light.png` |
| `wordmark-text-wide-dark.svg` / `marks/wordmark-wide-dark.svg` | `wordmark-text-wide-dark.png` |
| `banner-dark.svg` | `banner.png` |
| `banner-light.svg` | `banner-light.png` |
| `cover-en.svg` | `cover-en.png` |
| `cover-id.svg` | `cover-id.png` |

## Hero / GBP banners (904×256)

| Static | Animated (CSS in `<defs><style>`; tagline **Smartest way forward**) |
|--------|---------------------------------------------------------------------|
| `assets/banner-dark.svg` | `assets/banner-animated-dark.svg` |
| `assets/banner-light.svg` | `assets/banner-animated-light.svg` |

**`assets/gbp/` mirrors** for preview next to GBP PNGs:

| Static | Animated |
|--------|----------|
| `assets/gbp/banner.svg` | `assets/gbp/banner-animated.svg` |
| `assets/gbp/banner-light.svg` | `assets/gbp/banner-light-animated.svg` |

Upload raster: `assets/gbp/banner.png`, `assets/gbp/banner-light.png` (from the matching **static** SVG via `rsvg-convert` at 904×256).

Animated banners keep full opacity at frame 0 so static IDE preview stays readable; motion is rose float, cursor blink, and service-row emphasis (see `@keyframes` in the animated SVGs).

## Quick open

- Letterhead blank: `assets/letterhead/letterhead-blank.html`
- Letterhead sample: `assets/letterhead/letterhead-sample.html`
- Kit board: `assets/kit/presentation-board.html`
- GBP cover ID: `assets/gbp/cover-id.png`
- GBP banner (dark, animated): `assets/gbp/banner-animated.svg`
- GBP banner (light, static PNG): `assets/gbp/banner-light.png`

## Validation

After edits, run `xmllint --noout` on touched SVGs. Re-render GBP PNGs with `rsvg-convert` from the matching canonical SVG. Letterhead PDFs: Chrome headless (see `letterhead/README.md`).
