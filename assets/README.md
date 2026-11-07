# Levidev Studio — `final/` (day-to-day)

**Source of truth** for brand SVGs, GBP uploads, kit collateral, posts, and letterhead. On conflict, `final/` wins over `assets/` and `sample/`.

Legal name **PT. Levidev Studio Digital** appears on letterhead only, not in logo SVGs.

## Layout

| Path | Purpose |
|------|---------|
| **Root `*.svg`** | Canonical lockups (`icon-only-*`, `full-icon-*`, `wordmark-*`, `wordmark-text-*`, `banner-*`). Legacy **`assets/`-style aliases** (`icon.svg`, `wordmark.svg`, `logo.svg`, …) are optional symlinks; GBP PNGs use the canonical names below. |
| `marks/` | Same filenames as `assets/marks/` — copied from canonical root SVGs (light/dark naming mapped to assets names). |
| `gbp/` | Google Business Profile PNG/SVG exports (re-rendered from canonical root SVGs). **Banner previews** here as `banner*.svg` symlinks beside `banner.png` / `banner-light.png`. |
| `kit/` | Brand kit (platform icons, social cards, boards, HTML previews). Open `kit/presentation-board.html` from this folder. |
| `posts/` | GBP post images (`services-*`, `start-*`, EN/ID). |
| `letterhead/` | A4 HTML/PDF/SVG kopsurat — see `letterhead/README.md`. |
| `schema-*.jsonld` | Structured data snippets for the site. |

## Naming cheat sheet (canonical → GBP PNG / legacy alias)

| Canonical (`final/` root) | `final/gbp/` PNG (static source) | Legacy doc alias |
|---------------------------|-----------------------------------|------------------|
| `icon-only-light.svg` | `icon-only.png`, `logo-symbol.png` | `icon-only.svg` |
| `icon-only-dark.svg` | `icon-only-dark.png`, `logo-symbol-dark.png` | `icon-only-dark.svg` |
| `full-icon-light.svg` | `logo-wordmark.png` | `icon.svg` |
| `full-icon-dark.svg` | `logo-dark.png` | `icon-dark.svg` |
| `wordmark-light.svg` | `wordmark.png` | `wordmark.svg` |
| `wordmark-dark.svg` | `wordmark-dark.png` | `wordmark-dark.svg` |
| `wordmark-text-light.svg` | `logo-text-light.png` | `marks/wordmark-text-light.svg` |
| `wordmark-text-dark.svg` | `logo-text-dark.png` | `marks/wordmark-text-dark.svg` |
| `wordmark-text-wide-light.svg` | `wordmark-text-wide-light.png` | `marks/wordmark-wide-light.svg` |
| `wordmark-text-wide-dark.svg` | `wordmark-text-wide-dark.png` | `marks/wordmark-wide-dark.svg` |
| `banner-dark.svg` | `banner.png` | `logo.svg` (removed) |
| `banner-light.svg` | `banner-light.png` | `logo-light.svg` (removed) |
| `cover-en.svg` | `cover-en.png` | — |
| `cover-id.svg` | `cover-id.png` | — |

## Hero / GBP banners (904×256)

Canonical names at **`final/` root**:

| Static | Animated (CSS in `<defs><style>`; tagline **Smartest way forward**) |
|--------|---------------------------------------------------------------------|
| `final/banner-dark.svg` | `final/banner-animated-dark.svg` |
| `final/banner-light.svg` | `final/banner-animated-light.svg` |

**`final/gbp/` mirrors** for preview next to GBP PNGs (symlinks to the same four files):

| Static symlink | Animated symlink |
|----------------|------------------|
| `final/gbp/banner.svg` → `banner-dark.svg` | `final/gbp/banner-animated.svg` → `banner-animated-dark.svg` |
| `final/gbp/banner-light.svg` → `banner-light.svg` | `final/gbp/banner-light-animated.svg` → `banner-animated-light.svg` |

Upload raster: `final/gbp/banner.png`, `final/gbp/banner-light.png` (from the matching **static** SVG via `rsvg-convert` at 904×256).

Animated banners keep full opacity at frame 0 so static IDE preview stays readable; motion is rose float, cursor blink, and service-row emphasis (see `@keyframes` in the animated SVGs).

## Quick open

- Letterhead blank: `final/letterhead/letterhead-blank.html`
- Letterhead sample: `final/letterhead/letterhead-sample.html`
- Kit board: `final/kit/presentation-board.html`
- GBP cover ID: `final/gbp/cover-id.png`
- GBP banner (dark, animated): `final/gbp/banner-animated.svg`
- GBP banner (light, static PNG): `final/gbp/banner-light.png`

## Validation

After edits, run `xmllint --noout` on touched SVGs. Re-render GBP PNGs with `rsvg-convert` from the matching canonical SVG. Letterhead PDFs: Chrome headless (see `letterhead/README.md`).
