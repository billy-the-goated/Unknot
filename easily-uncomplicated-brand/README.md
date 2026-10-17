# Easily Uncomplicated: Brand Kit (v1)

**Tagline:** *Simple on purpose.*

## Colours
| Role | Name | Hex |
|---|---|---|
| Primary | Royal blue | `#1E4BD2` |
| Accent | Signal red | `#E5383B` |
| Dark | Deep navy | `#0B1B4D` |
| Surface | Soft blue-grey | `#F1F4FB` |
| Background | White | `#FFFFFF` |

Font: **Outfit** SemiBold (free on Google Fonts). The wordmark in the logo files is already converted to shapes, so you do not need the font to use the logos.

## What's in this kit

### `logo/` (SVG: use these first, they scale to any size)
| File | Use it on |
|---|---|
| `logo-full-color.svg` | White or light backgrounds (main logo) |
| `logo-full-reversed.svg` | Navy or dark backgrounds |
| `logo-full-mono-dark.svg` | One-colour printing, stamps, light backgrounds |
| `logo-full-mono-white.svg` | One-colour on dark or photo backgrounds |
| `logo-full-color-tagline.svg` | Main logo with the tagline underneath (headers, presentations, print) |
| `mark-color.svg` | Icon only: blue square with the line and red dot |
| `mark-reversed.svg` | Icon only on dark backgrounds |
| `mark-mono-dark.svg` / `mark-mono-white.svg` | One-colour icon |

`logo/png/` has transparent PNGs: logos at 2000 px wide, and the mark at 512 and 1024 px. The `reversed` and `mono-white` PNGs have white text, so they look blank on a white page. That is expected.

### `favicon/`
| File | Purpose |
|---|---|
| `favicon.ico` | Browser tab icon (16, 32 and 48 px inside one file) |
| `favicon.svg` | Modern browsers (sharp at any size) |
| `favicon-16/32/48.png` | Individual sizes |
| `apple-touch-icon-180.png` | iPhone/iPad home screen |
| `icon-192.png`, `icon-512.png` | Web app (PWA) icons |
| `icon-maskable-512.png` | Android adaptive icon (extra padding so nothing gets cropped) |
| `site.webmanifest` | PWA manifest, ready to use |
| `head-snippet.html` | Paste into your page `<head>` |

The favicon files use a slightly bolder, larger line than the main logo so they stay readable at 16 px.

### `social/`
All banners and link-preview images include the tagline.

| File | Size | Notes |
|---|---|---|
| `avatar-400.png` | 400 x 400 | Profile picture, safe for circle crops |
| `banner-x-1500x500.png` (+ `-dark`) | 1500 x 500 | X / Twitter header |
| `banner-linkedin-1584x396.png` | 1584 x 396 | LinkedIn banner |
| `banner-youtube-2560x1440.png` | 2560 x 1440 | YouTube banner; logo sits inside the safe area |
| `og-image-1200x630.png` (+ `-dark`) | 1200 x 630 | Link preview image for the website |
| `github-social-1280x640.png` | 1280 x 640 | GitHub repo social preview |

## Simple usage rules
- **Clear space:** keep at least the height of the red dot's diameter times 3 empty around the logo (about a quarter of the mark's height).
- **Minimum size:** full logo at least 120 px wide; mark at least 16 px.
- **Don't** stretch, rotate, recolour, add shadows, or put the colour logo on a busy or blue background (use the reversed version).
- Red is an accent. Use it for the dot and "money out" or warnings, not as a background.
