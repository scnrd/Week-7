# Design System

> **Mors Anima — Portfolio Website Poster Lab** for ARTGR4840 (Iowa State University, Summer 2026). The visual language is reverse-engineered from a four-poster mood board (editorial + acid-graphic posters) and applied to a **vibe-coding portfolio** that showcases four AI-assisted web products developed across eight weeks. Stated creative direction: **dripping/liquid aesthetic, bold color contrast, noise & static for a dreamy atmosphere, crowded and interesting.** This is a *graphic/editorial poster* design language adapted into a portable UI system.

---

## Site Architecture

**Current implementation:** plain HTML + CSS (no framework). Two stylesheets:

| File | Role |
|------|------|
| `index.html` | Studio home — hero, work grid, about, manifesto (inline `<style>`) |
| `product.css` | Shared product-page styles (linked by all product HTML files) |
| `product-apertif.html` | Encyclopedia Apertif showcase |
| `product-fittrack.html` | FitTrack showcase |
| `product-botanica.html` | Botanica Gardens showcase |
| `product-conrad.html` | S.L. Conrad portfolio showcase |

**Fonts (Google Fonts):** Anton (condensed display), Archivo (UI), Instrument Serif (liquid/display), Space Mono (micro-labels).

---

## Design Philosophy

**High Confidence**

This is an **experimental editorial / acid-graphic** system applied to an **AI-forward design portfolio**. It sits at the intersection of four moves visible across the original poster references:

- **Swiss-brutalist editorial** — tight grids, dense micro-typography, monochrome (Poster 1: *CASSE CROUTE*).
- **Maximalist layered composition** — vertical running text, halftone photography, clashing accents (Poster 2: *NON / MIXTURE STANDARD*).
- **Liquid / acid psychedelia** — dripping blobs, starbursts, gradient meshes on saturated fields (Poster 3: *MORS ANIMA / VETITI*).
- **Dreamy gradient minimalism** — soft purple mesh, chrome serif, generous negative space (Poster 4: *NATURAL DARKNESS / nocta*).

Guiding principle: **controlled chaos.** Layouts are dense and "crowded and interesting," but anchored by a rigid underlying grid and a single dominant headline. Texture (grain, halftone, static) and liquid distortion are core to the identity, not decoration.

**Site purpose:** chronicle progressive complexity across four real working web applications built with AI tools (Cursor, Figma, Netlify, GitHub, ReactJS, APIs). The poster system is the frame; the products are the content.

**Design maturity:** high-craft, art-directed, print-first. **Interaction philosophy:** expressive over conventional — the interface should feel like a poster you can move through.

---

## Visual Personality

**High Confidence**

- **Adjectives:** bold, saturated, tactile, nocturnal, experimental, youthful, art-house, AI-native.
- **Tension:** structured (grid, small caps, editorial) vs. molten (drips, gradients, glow).
- **Emotional register:** dreamy and slightly unsettling — evolved from "beautiful noise" to **"real working"** web craft.
- **Reference lineage:** contemporary risograph/print posters, Y2K acid revival, Japanese layout typography, brutalist web, vibe-coding portfolio culture.

Style classification: **Neo-brutalist / Editorial / Acid-native** (not SaaS, not corporate).

---

## Color System

**High Confidence** (palette) / **Medium Confidence** (exact hex values, sampled from compressed JPEG-style artwork)

The palette pairs a **deep near-black/indigo base** with **electric high-chroma accents** (cobalt, magenta, coral, lime) and a **soft lavender-to-cream** dreamy family. Contrast is intentionally *loud*: complementary clashes (blue↔orange, magenta↔lime) drive the "bold color contrast" brief. Note: the seed accent `#D14836` (a burnt vermillion) is carried in as an optional warm signal color.

```yaml
colors:
  # Brand
  primary:    "#1E33E6"   # electric cobalt blue (Poster 3 field)
  secondary:  "#E6318A"   # hot magenta / flower pink (Poster 2)
  accent:     "#FF6A2C"   # liquid coral-orange (Poster 3 drips)
  highlight:  "#C3ED2E"   # acid lime / chartreuse (Poster 2 "NON")
  signal:     "#D14836"   # seed vermillion (warm alert accent)

  # Dreamy / soft family
  lavender:   "#B9A9D6"   # gradient mesh purple (Poster 4)
  lavender_soft: "#DCD3EC"

  # Surface
  background: "#0E0A24"   # deep indigo-black (Poster 2 base)
  surface:    "#171041"   # elevated indigo panel
  surface_alt:"#F4F1EA"   # cream paper (light-mode / editorial)
  card:       "#1E1650"

  # Text
  text:          "#F5F3FF"  # near-white on dark
  text_secondary:"#B9B4D6"  # soft lavender-gray (feature-list detail on dark)
  text_muted:    "#7A7595"
  text_inverse:  "#0A0A0A"  # ink on cream

  # Border
  border:        "#2A2360"
  border_strong: "#F5F3FF"  # editorial hairline on light
  border_subtle: "#211A52"

  # Semantic
  success: "#C3ED2E"
  warning: "#FF6A2C"
  error:   "#E6318A"
  info:    "#1E33E6"

  # Product accents (off-palette brand colors accepted per product)
  fittrack_periwinkle: "#9395D3"
  conrad_lime:         "#C3ED2E"  # uses core highlight token on dark only
```

**Rules:**
- One saturated field color dominates a screen; accents appear as *drips, glows, and type*, not large blocks.
- Never place two loud complementaries at full saturation in equal area — one leads, one punctuates.
- Text is either near-white on indigo or pure ink on cream. Avoid mid-gray body text on dark — use `--text-2` (`#B9B4D6`) for secondary detail on dark canvases.

**Hero liquid gradient (index):** the single liquid-serif word **Website** uses `linear-gradient(100deg, accent → secondary)` — orange/coral into magenta/pink.

---

## Typography

**High Confidence** (roles & mixing strategy) / **Implemented typefaces**

Two-part strategy: a **condensed/geometric grotesque** for structure and micro-labels, and an **expressive display face** (high-contrast italic serif or "chrome"/liquid serif) for hero moments.

```yaml
typography:
  display:   { font: "Instrument Serif", size: "72–200px", weight: 400, italic: true, tracking: "-2%" }
  h1:        { font: "Anton (+ Archivo fallback)", size: "48–168px", weight: 400, tracking: "-1%", transform: "uppercase" }
  h2:        { font: "Anton", size: "32–88px", weight: 400, tracking: "-1%", transform: "uppercase" }
  h3:        { font: "Anton", size: "22–48px", weight: 400 }
  body:      { font: "Archivo", size: "15–18px", weight: 400, line_height: 1.55 }
  small:     { font: "Archivo", size: "13–14px", weight: 400, line_height: 1.45 }
  caption:   { font: "Space Mono", size: "8–11px", weight: 400–700, tracking: "20–30%", transform: "uppercase" }
  manifesto_b: { font: "Anton", color: "#C3ED2E", transform: "uppercase" }  # acid green emphasis words in .big
```

**Rules:**
- Micro-typography matters: small uppercase, wide-tracked mono/grotesk labels stacked in margins create the "crowded" density.
- Use **vertical / rotated running text** on edges as a signature layout device.
- Reserve the liquid-serif display face for a single hero word per view; never for body.
- Extreme scale jump between display and body — no timid mid-sizes.
- Manifesto `.big b` uses condensed Anton in acid lime; surrounding copy uses Instrument Serif italic.

---

## Layout

**High Confidence**

Poster-format thinking: **portrait canvases, full-bleed color fields, and a strict editorial grid that content is then allowed to break.**

```yaml
layout:
  format: "portrait / A-series poster ratio for hero canvases"
  max_width: 1200px
  columns: 12
  gutters: 24px
  margin: 32px
  breakpoints:
    sm: 640
    md: 768
    lg: 1024
    xl: 1280
    nav_hide: 720    # index nav links
    vtext_hide: 900  # vertical running text
    product_nav_hide: 820
```

**Patterns:**
- **Hero canvas:** one dominant subject (blobs/gradient) centered, headline overlapping it, micro-labels pinned to all four margins.
- **Edge running text:** vertical text columns hugging left/right edges.
- **Full-bleed color** backgrounds; content floats on top with layered z-index.
- **Overlap over separation:** type sits *on* imagery; elements intentionally collide.
- Cream "paper" layouts (About section) use wide margins and a lighter grid for contrast.

---

## Spacing Scale

**Medium Confidence**

Editorial density suggests an **8px base** with tight component padding but large sectional rhythm.

```yaml
spacing:
  base: 8
  scale: [4, 8, 12, 16, 24, 32, 48, 64, 96, 128]
  tokens: { sp-1: 4px, sp-2: 8px, sp-3: 12px, sp-4: 16px, sp-6: 24px, sp-8: 32px, sp-12: 48px, sp-16: 64px, sp-24: 96px, sp-32: 128px }
```

**Rules:**
- Tight inside components (labels, chips): 4–8px.
- Generous between hero sections: 64–128px (the cream-poster breathing room).
- Micro-label clusters use 4px stacking to read as "printed metadata."

---

## Components

**Medium Confidence** (translated from print artifacts into UI equivalents)

### Button
```yaml
button:
  variants: [solid, outline, ghost, pill-badge]
  states: [default, hover, active, focus, disabled, loading]
  radius: full
  primary:   { bg: "#1E33E6", text: "#F5F3FF" }
  accent:    { bg: "#FF6A2C", text: "#0A0A0A" }
  hover:     "add outer glow + slight scale(1.02–1.03)"
  transform: uppercase
  tracking:  "4%"
```

### Card / Panel
```yaml
card:
  bg: "#171041"
  radius: 12
  border: "1px solid #2A2360"
  texture: "subtle grain/noise overlay via ::after or global .grain"
```

### Work Card (index `#work`)
- 4-column grid (2-col tablet, 1-col mobile).
- Thumbnail with accent dot glow, mono work-num, condensed title + liquid-serif `<em>`, meta pills, arrow foot.
- **Display order (chronological development):** 01 FitTrack → 02 Botanica → 03 Encyclopedia Apertif → 04 S.L. Conrad.

### Badge / Chip
- Small circular or pill labels, uppercase, wide tracking — the recurring "stamp" motif.

### Navigation
- Fixed top bar, blurred indigo backdrop, condensed wordmark, mono nav links, ghost CTA.

**States** (all interactive elements): Default → Hover (glow + micro-scale) → Active (invert/fill) → Focus (2px cobalt ring) → Disabled (40% opacity) → Loading (liquid/pulse shimmer).

---

## Shape Language

**High Confidence**

Dual system: **rigid rectangles/hairlines** (editorial grid) coexisting with **organic liquid blobs** (drips, metaballs) and **circular stamps/starbursts**.

```yaml
radius:
  xs: 2
  sm: 4
  md: 8
  lg: 12
  xl: 24
  full: 9999
blob: "irregular metaball shapes — border-radius morph keyframes + optional SVG #goo filter"
```

**Liquid motion keyframes (shared site-wide):**
- `float1/2/3` — gentle translate + scale drift
- `morph` — organic border-radius shift between two blob shapes
- `drip` — vertical scaleY ooze for hanging tendrils
- `spin` — slow starburst rotation
- `static` — grain overlay jitter

---

## Shadows & Elevation

**Medium Confidence**

Print references have little depth-shadow; elevation is expressed via **color glow and layering**, not soft drop shadows.

```yaml
elevation:
  card:     "0 0 0 1px #2A2360"
  dropdown: "0 12px 32px rgba(10,8,36,0.6)"
  modal:    "0 24px 64px rgba(10,8,36,0.75)"
  glow:     "0 0 24px rgba(30,51,230,0.55)"
  glow_pink: "0 0 28px rgba(230,49,138,0.55)"
  glow_lime: "0 0 26px rgba(195,237,46,0.5)"
  product_glow: "per-theme — see Product Page System"
```

**Rule:** prefer **neon glow** and z-layering over realistic shadows.

---

## Motion & Interaction Rules

```yaml
motion:
  fast:   120ms
  medium: 240ms
  slow:   480ms
  easing: "cubic-bezier(0.22, 1, 0.36, 1)"
  reduced_motion: "animation: none !important on all elements via prefers-reduced-motion"
```

**Micro-interactions:**
- Liquid/blob shapes slowly morph in backgrounds (hero, manifesto, about, product heroes).
- Grain/static overlay subtly animates (`static` keyframe, steps).
- Hover = neon glow bloom + 1–3% scale.
- Marquee = infinite horizontal scroll on acid-lime strip.

---

## Design Principles

**High Confidence** — original poster-system rules (still govern visual craft):

1. Controlled chaos: crowd the canvas, but anchor it to a strict grid.
2. One dominant color field per screen; accents only punctuate.
3. Always add texture — grain, halftone, or static — never flat-clean.
4. Bold complementary contrast (blue↔orange, magenta↔lime) drives hierarchy.
5. Exactly one liquid-serif hero word per view.
6. Micro-labels everywhere: small, uppercase, wide-tracked, margin-pinned.
7. Overlap elements; let type collide with imagery.
8. Use vertical/rotated running text as a signature device.
9. Prefer neon glow over drop shadows for elevation.
10. Circular stamps and starbursts as recurring accent motifs.
11. Two type voices only: rigid grotesque + expressive serif.
12. High-contrast text pairs only (near-white on indigo, ink on cream).
13. Blobs and drips live in decorative/background layers, not on content.
14. Alternate loud dark canvases with quiet cream "breathing" screens.
15. Extreme type scale jumps — no timid middle sizes.

**Site manifesto principles** (index `#manifesto` — content-specific, 5 items in a 3-column grid):

| # | Principle | Body |
|---|-----------|------|
| 01 | AI as a tool for designers, not a replacement. | Col 1, row 1 |
| 02 | Clean AI assisted workflows create guiding documents and user friendly interfaces mean that once the coding is done, so is the AI. | Col 2, row 1 |
| 03 | Interesting designs made to elicit passion and interest. | Col 3, row 1 |
| 04 | Websites with real functionality | Col 1, row 2 (under 01) |
| 05 | Dynamic prompts and smart usage of different AI models to produce the best result. | Col 3, row 2 (under 03) |

Grid layout: 3 columns; row 2 col 2 intentionally blank (space beneath Principle 02).

Manifesto headline (`.big`): *"Using AI tools to develop, design, and launch **real working** web applications"* — wide measure (`min(900px, 92vw)`), `<b>` in acid lime with `white-space: nowrap`.

---

## Studio Index Page (`index.html`)

### Section order
1. **Global** — `.grain` overlay, SVG `#goo` filter defs, fixed `nav`
2. **`header.hero`** — liquid blobs (4), starbursts (2), corner micro-labels (4), vertical running text, hero inner
3. **`.marquee`** — acid-lime keyword strip
4. **`#work`** — 4 product cards (chronological order above)
5. **`#about.cream`** — dreamy lavender liquid layer (`.about-blobs`), ink drips (`.about-drips`), split copy + morphing portrait ring
6. **`#manifesto`** — bold liquid blobs + drip tendrils, manifesto headline, 5 principles, site footer

### Hero copy (current)
- **Kicker:** Experimental Vibe Coding Studio
- **H1:** Portfolio / **Website** (liquid) / Poster Lab
- **CTAs:** View the work · Read manifesto

### About copy (current)
- **H2:** Samantha Conrad / **ARTGR4840** (liquid gradient em)
- **Focus:** Creating beautiful web applications with the power of AI
- **Taught by:** Aaron Yang Ph.D.
- **Founded:** 2026 — Iowa State University
- **Utilizing:** Cursor, Figma, Netlify, Github, ReactJS, API, and more

### Liquid layer variants (index)
| Section | Character | Colors | Notes |
|---------|-----------|--------|-------|
| Hero | Loud metaballs | primary, secondary, accent, highlight | Circular blobs + goo filter; unchanged by About/Manifesto morph rules |
| About | Quiet breathing room | lavender, lavender-soft, low-opacity secondary | `mix-blend-mode: multiply`; ink drips off top hairline; portrait mask morphs |
| Manifesto | Bold drips | accent blobs + `.drip` tendrils | Scoped morph on `#manifesto .blob`; stronger goo blur |

---

## Accessibility Notes

**Medium Confidence**

- **Enforce WCAG AA (4.5:1) for body text** by keeping body copy on solid `#0E0A24` or `#F4F1EA`, never over blobs or grain.
- **`prefers-reduced-motion`** disables all animations (grain, liquid morph, marquee, spin) site-wide.
- Never rely on neon glow alone for focus — pair with a solid 2px ring.
- Acid lime `#C3ED2E` only on dark surfaces (fails on cream).
- Decorative layers (`.blobs`, `.starburst`, `.grain`, `.marquee`, `.about-blobs`, `.about-drips`) use `aria-hidden="true"`.
- Every product screenshot needs descriptive `alt` text.

---

## Design Tokens

```yaml
tokens:
  colors:
    primary: "#1E33E6"
    secondary: "#E6318A"
    accent: "#FF6A2C"
    highlight: "#C3ED2E"
    signal: "#D14836"
    background: "#0E0A24"
    surface: "#171041"
    surface_alt: "#F4F1EA"
    text: "#F5F3FF"
    text_secondary: "#B9B4D6"
    text_muted: "#7A7595"
    border: "#2A2360"
  spacing:
    base: 8
    scale: [4, 8, 12, 16, 24, 32, 48, 64, 96, 128]
  typography:
    display_font: "Instrument Serif"
    cond_font: "Anton"
    ui_font: "Archivo"
    mono_font: "Space Mono"
    scale: { display: 96, h1: 48, h2: 32, h3: 22, body: 16, small: 13, caption: 10 }
  radius:
    sm: 4
    md: 8
    lg: 12
    xl: 24
    full: 9999
  shadows:
    hairline: "0 0 0 1px #2A2360"
    modal: "0 24px 64px rgba(10,8,36,0.75)"
    glow: "0 0 24px rgba(30,51,230,0.55)"
  motion:
    fast: 120ms
    medium: 240ms
    slow: 480ms
    easing: "cubic-bezier(0.22, 1, 0.36, 1)"
```

---

## Implementation Guidance

**Actual stack (current build):**

- **HTML + CSS** — `index.html` with inline tokens/styles; `product.css` for all product pages. No Tailwind, no component library.
- **Google Fonts** — Anton, Archivo, Instrument Serif, Space Mono via `<link>`.
- **SVG `#goo` filter** — metaball merge on hero/manifesto blobs (`feGaussianBlur` + `feColorMatrix`).
- **Global `.grain`** — fixed fractalNoise SVG overlay with `static` animation.
- **No JavaScript** — purely static showcase site.

When extending: add new product pages by cloning an existing `product-*.html`, linking `product.css`, assigning a `theme-*` body class, and following the Product Page System below. Update `index.html` work grid and product-nav prev/next chain.

---

## Product Page System

**Applies to:** `product-apertif.html`, `product-fittrack.html`, `product-botanica.html`, `product-conrad.html`. All share `product.css`.

### Page skeleton (in order)
1. `nav` — fixed top bar; wordmark links home; `.nav-links` with Home + all four products + `.active` on current; `← Studio` ghost button.
2. `header.product-hero` — poster hero (liquid rules below).
3. `section.showcase` — primary/home screenshot in `.showcase-frame-wrap` > `.frame` + independent `.frame-label` pill below (not overlaid on image).
4. `.marquee` — acid-lime scrolling keyword strip (product-specific keywords).
5. `section.gallery` — secondary screens in `.gallery-grid` variants.
6. Feature spotlight — `.feature` (cream, Apertif only) or `.features-dark` + `.feature-stack` of `.feature-block`s (alternate `.reverse`).
7. `section.product-nav` — previous/next product cards.
8. `footer` — copyright + asset count + back-to-studio link.

### Product roster & nav cycle

| # | Product | File | Theme class | Screens |
|---|---------|------|-------------|---------|
| 01 | FitTrack | `product-fittrack.html` | `theme-fittrack` | 6 |
| 02 | Botanica Gardens | `product-botanica.html` | `theme-botanica` | 7 |
| 03 | Encyclopedia Apertif | `product-apertif.html` | `theme-apertif` | 5 |
| 04 | S.L. Conrad | `product-conrad.html` | `theme-conrad` | 5 |

**Prev/next cycle:** FitTrack ↔ Botanica ↔ Conrad ↔ Apertif ↔ FitTrack

*(Work grid on index uses the same chronological 01–04 order.)*

### Per-product theming
Set the theme on `<body>` via one class; never hard-code accent colors inline. Each theme defines three variables:

```css
.theme-apertif  { --product-accent:#FF6A2C; --product-glow:0 0 28px rgba(255,106,44,.5);  --hero-tint:rgba(255,106,44,.16); }
.theme-fittrack { --product-accent:#9395D3; --product-glow:0 0 28px rgba(147,149,211,.55); --hero-tint:rgba(147,149,211,.18); }
.theme-botanica { --product-accent:#E6318A; --product-glow:0 0 28px rgba(230,49,138,.45); --hero-tint:rgba(230,49,138,.16); }
.theme-conrad   { --product-accent:#C3ED2E; --product-glow:0 0 28px rgba(195,237,46,.42); --hero-tint:rgba(195,237,46,.14); }
```

**Rules:**
- `--product-accent` drives kicker, `.shot-num`, `.feature-num`, starburst fill, hero blob b1.
- `--hero-tint` drives `.product-hero::before` top radial glow — MUST match product accent.
- `--product-glow` is neon bloom on `.frame`, `.frame-dark`, and hover states.
- FitTrack periwinkle `#9395D3` and Conrad lime `#C3ED2E` are accepted product-brand accents (Conrad uses core `highlight` token — dark surfaces only).

### Hero liquid rules (Principles 3, 10, 13)
Every `product-hero` carries decorative layers behind `.hero-grid` (z-index 2):

- **Liquid blobs** — `.blobs` layer (blurred, opacity ~.55) with three morphing `.blob`s: b1 accent, b2 secondary, b3 primary. Edge-weighted; never under body text.
- **Starburst** — one SVG, filled `var(--product-accent)`, slow spin. Hidden ≤900px.
- **Vertical running text** — `.vtext.left` / `.vtext.right`.
- **Corner micro-labels** — `.corner.bl` / `.corner.br`, stacked mono labels. Hidden ≤900px.

### Showcase frame & label
```html
<div class="showcase-frame-wrap">
  <div class="frame"><img … /></div>
  <span class="frame-label label">01 / Primary view</span>
</div>
```
- `.frame` — bordered, rounded, grain overlay, product-glow shadow; image only inside.
- `.frame-label` — **independent pill** below frame with gap (`showcase-frame-wrap` flex column); never overlaid on screenshot.
- Mobile products (FitTrack): wrap gets `max-width:420px; margin:0 auto`.

### Gallery shot variants
| Class | Use |
|-------|-----|
| *(default)* | 16/10 crop, `object-fit: cover` |
| `.shot--mobile` | 9/19 aspect for phone screens |
| `.shot--wide` | 16/9 aspect |
| `.shot--full` | No crop — full-page captures at natural height (`object-fit: contain`). Used on Conrad portfolio/about views. |
| `.gallery-grid-2` | 2-column gallery |
| `.gallery-grid-4` | 2×2 gallery (Apertif) |

### Feature blocks (`.features-dark`)
- `.feature-block` — 2-col grid, **`align-items: start`** (top-align copy with tall screenshots).
- `.feature-block.reverse` — RTL flip for alternating image side.
- `.frame-dark` — bordered screenshot frame with product glow.
- `.frame-dark.mobile` — `max-width: 380px; margin: 0 auto` (FitTrack phone UI).
- `.frame-dark.modal` — `max-width: min(480px, 100%); margin: 0 auto` (narrow modal/overlay UI, e.g. Botanica plant detail).
- `.features-dark .feature-list li` — body text `--text-2` (`#B9B4D6`), not ink `#322d45`.
- `.features-dark .feature-list li b` — labels at `13px` mono uppercase (readable against dark, not smaller than body).

### Shared motion
`product.css` defines `float1/2/3`, `morph`, `drip`, `spin`, `static` — mirroring index. All covered by `prefers-reduced-motion`.

### Accessibility on product pages
- Body copy on solid `--bg` or `--cream`; never over blob fields.
- Decorative layers `aria-hidden="true"`.
- Descriptive `alt` on every screenshot.

---

*Confidence summary: palette / personality / principles = High. Spacing, components, tokens = Medium. Site content & product roster = Current as of Summer 2026 ARTGR4840 portfolio iteration.*
