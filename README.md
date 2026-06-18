# Onix Digital — Marketing & SEO Template

A pixel-perfect, **pure HTML + CSS** recreation of the **Templatemo 565 – Onix Digital** template. Built from scratch with no JavaScript, no animations, and no external frameworks beyond Google Fonts. Layout is powered entirely by **CSS Grid**, and the carousel uses a clever **CSS-only radio + `:checked` pattern**.

---

## 📑 Table of Contents

1. [Overview](#-overview)
2. [Tech Stack](#-tech-stack)
3. [Architecture](#-architecture)
4. [File & Folder Structure](#-file--folder-structure)
5. [Page Sections](#-page-sections)
6. [Design System](#-design-system)
7. [Responsive Breakpoints](#-responsive-breakpoints)
8. [CSS-Only Carousel](#-css-only-carousel)
9. [Pure CSS Hero with Absolutely Positioned Artwork](#-pure-css-hero-with-absolutely-positioned-artwork)
10. [Setup & Local Preview](#-setup--local-preview)
11. [Customization Guide](#-customization-guide)
12. [Browser Support](#-browser-support)
13. [Accessibility](#-accessibility)
14. [Performance](#-performance)
15. [Credits & License](#-credits--license)

---

## 🌟 Overview

**Onix Digital** is a one-page marketing/SEO landing-page template featuring:

- A bold hero banner with overlapping hero illustration
- 4 service cards with icons
- An about section with counter statistics (320 / 640 / 120)
- A pure-CSS portfolio carousel with 4 slides
- 3 pricing tiers (Starter / Standard / Advanced)
- A newsletter subscribe panel with curved background art
- A video showcase with main player + thumbnail list
- A contact section with embedded map + form
- A 4-column light footer with newsletter, social, and links

The design language uses a **blue (`#03a4ed`) + red (`#ff695f`) on white** palette — a signature look from the original Templatemo template.

---

## 🛠 Tech Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| **Markup** | HTML5 | Semantic tags (`<header>`, `<section>`, `<article>`, `<footer>`) |
| **Styling** | Pure CSS3 | No preprocessor, no framework — single `style.css` |
| **Layout** | CSS Grid + Flexbox | Grid for 2D layout, Flexbox via grid auto-flow |
| **Typography** | Google Fonts – Poppins | Weights 100–900 loaded via `<link>` |
| **Interactivity** | None (0 JS) | Carousel, dots, arrows — all CSS |
| **Assets** | PNG / JPG / SVG | All bundled under `assets/images/` |
| **Icons** | Inline SVG | Social icons + phone/email in footer, no icon font |
| **External Scripts** | None | Zero `<script>` tags |
| **Build Tools** | None | Plain file editing |

---

## 🏗 Architecture

The codebase follows a **layered, section-by-section** architecture inside a single CSS file. The HTML is one continuous scroll with named anchors. There is **no router, no state, no event handlers** — just declarative structure and styling.

```
┌──────────────────────────────────────────────────────────┐
│                       HTML Document                       │
│                                                           │
│   <head>                                                  │
│   ├── meta tags (charset, viewport, description)         │
│   ├── favicon                                             │
│   ├── Google Fonts preconnect + stylesheet                │
│   └── style.css                                           │
│                                                           │
│   <body>                                                  │
│   ├── <header>      → .site-header / .main-nav            │
│   ├── <main>                                             │
│   │   ├── #home       → .main-banner (hero)              │
│   │   ├── #services   → .our-services                     │
│   │   ├── #about      → .about-us                         │
│   │   ├── #portfolio  → .our-portfolio / .carousel        │
│   │   ├── .pricing-tables                                │
│   │   ├── .subscribe                                      │
│   │   ├── #videos     → .our-videos                       │
│   │   └── #contact    → .contact-us                       │
│   └── <footer>      → .site-footer                        │
└──────────────────────────────────────────────────────────┘
```

### CSS File Layout (style.css)

The file is organized into clearly commented sections in this order:

```
1.  Color tokens (:root custom properties)
2.  Reset / base
3.  Layout primitives (.container)
4.  Section headings
5.  Pill buttons
6.  Header (.site-header / .main-nav / .nav)
7.  Hero (.main-banner / .hero-grid / .hero-text / .hero-image)
8.  Services (.our-services / .service-card)
9.  About (.about-us / .facts-grid)
10. Portfolio carousel (.carousel / .slides / .slide-arrow)
11. Pricing (.pricing-tables / .pricing-item)
12. Subscribe (.subscribe / .subscribe-inner)
13. Videos (.our-videos / .overlay-effect)
14. Contact (.contact-us / .contact-form / .info-block)
15. Footer (.site-footer / .footer-grid / .newsletter-form)
16. Responsive breakpoints (media queries)
```

---

## 📂 File & Folder Structure

```
templatemo_565_onix_digital/
│
├── index.html                    # Single-page document
├── style.css                     # All styling (~1200 lines)
├── prepros.config                # Optional Prepros live-reload config
│
└── assets/
    ├── fonts/                    # Original template font files (unused now)
    │   ├── Flaticon.woff
    │   ├── FontAwesome.otf
    │   ├── flexslider-icon.*
    │   ├── fontawesome-webfont.*
    │   └── slick.*
    │
    └── images/                   # All image assets
        ├── logo.png              # Brand logo (used in header + footer + favicon)
        ├── baner-dec-left.png    # Hero decoration (left side, 267×532)
        ├── banner-right-image.png # Hero illustration (819×596)
        ├── services-left-dec.png # Services watermark
        ├── services-right-dec.png
        ├── about-left-image.png  # About section image
        ├── portfolio-01..04.jpg  # Carousel slides
        ├── portfolio-left-dec.png
        ├── tables-left-dec.png   # Pricing decoration
        ├── first-plan-bg.png     # Pricing card background
        ├── second-plan-bg.png
        ├── third-plan-bg.png
        ├── subscribe-bg.png      # Subscribe section background
        ├── subscribe-dec.png     # Subscribe decoration (top-right curve)
        ├── videos-left-dec.png   # Videos decoration
        ├── videos-right-dec.png
        ├── video-thumb-01..04.png # Video thumbnail list
        ├── contact-form-bg.png   # Contact form background art
        ├── contact-left-dec.png
        ├── contact-dec.png
        ├── footer-dec.png        # Decorative wave above footer
        └── hover-bg.png          # Portfolio caption background
```

---

## 🧱 Page Sections

### 1. Header (`.site-header`)
- Absolute-positioned bar at the top, fixed height `100px`
- Logo on the left, navigation on the right
- "Contact Us Now" CTA button with red background + blue hover

### 2. Hero (`.main-banner`)
- **200px top padding** to clear the fixed header
- Left decoration (`baner-dec-left.png`) — a thin liquid shape
- Right hero illustration (`banner-right-image.png`) — absolutely positioned to overflow the right edge
- `.hero-text` carries the h6/h2/p + CTA buttons + numbered dots
- Single-column grid (`grid-template-columns: 1fr`) with `max-width: 620px` on text

### 3. Services (`.our-services`)
- 4-column grid (collapses to 2 / 1 on smaller screens)
- Each card has: h4 title → icon image → paragraph
- Decorative left/right watermark images

### 4. About (`.about-us`)
- 2-column grid: image on left, text on right
- Counter stats: **320 SEO Projects**, **640 Websites**, **120 Satisfied Clients**
- Each stat: large digit (50px) + red title + grey description

### 5. Portfolio Carousel (`.carousel`)
- 4 slides, each containing 3 portfolio thumbnails
- Pure CSS sliding via `:checked ~ .slides { transform: translateX(...) }`
- 2 navigation arrows + 4 clickable dots
- Caption overlay (`.hover-effect`) appears on each thumbnail

### 6. Pricing (`.pricing-tables`)
- 3-column grid with `transform: scale(1.05)` on the middle "featured" plan
- Each card: large price (red `$140 / $200 / $280`) + features list + CTA

### 7. Subscribe (`.subscribe`)
- Curved background image
- 2 inputs + 1 button in a single rounded form (40px radius)

### 8. Videos (`.our-videos`)
- Main video on the left (16:9 aspect ratio with red gradient overlay)
- Thumbnail list on the right (4 items)

### 9. Contact (`.contact-us`)
- 2-column grid: map + info blocks on left, form on right (negative margin overlaps)
- Google Maps iframe + 2 contact info blocks + form (3 fields + submit)
- Decorative blob bottom-right

### 10. Footer (`.site-footer`)
- 4-column grid: brand+social / Services / Community / Subscribe newsletter
- Dotted-pattern background (radial-gradient)
- Copyright bar at the bottom

---

## 🎨 Design System

### Color Tokens (defined in `:root`)

| Token | Hex | Usage |
|-------|-----|-------|
| `--blue` | `#03a4ed` | Primary accent, CTAs, links, info icons |
| `--red` | `#ff695f` | Secondary accent, prices, headings, dots |
| `--dark` | `#1e1e1e` | Rare — kept for dark text |
| `--text` | `#2a2a2a` | Default body text |
| `--muted` | `#afafaf` | Secondary / placeholder text |
| `--border` | `#eee` | Hairline borders |
| `--bg-soft` | `#fafafa` | Subtle background panels |
| `--bg-light` | `#f7f7f7` | Light alternate background |
| `--white` | `#ffffff` | Base background |

### Typography

- **Family:** Poppins (Google Fonts), weights 100–900
- **Base size:** 15px body, 30px section h2, 50px hero h2
- **Line height:** 1 (headings), 30px (paragraphs)

### Spacing

- **Section padding:** `120px 0` (default), reduces responsively
- **Container:** `max-width: 1200px`, centered, `padding: 0 24px`

### Border Radius

- Cards & sections: `20px`
- Pill buttons: `23px`
- Round buttons / icons: `50%`

---

## 📐 Responsive Breakpoints

The design uses **mobile-first-friendly max-width queries** with **0.1px decimal gaps** for pixel-perfect isolation:

| Query | Range | Adjustments |
|-------|-------|-------------|
| `min-width: 2340px` | ≥ 2340px | Ultra-wide: container 1500px, larger typography |
| Default | 992.1 – 2339px | Standard desktop |
| `max-width: 1240px` | ≤ 1240px | Hero image shrinks to 700px |
| `max-width: 991.9px` | ≤ 991.9px | Tablet portrait: nav tighter, 2-col grids |
| `max-width: 767.9px` | ≤ 767.9px | Mobile: 1-col grids, stacked nav |
| `max-width: 480px` | ≤ 480px | Small phones: smaller typography |

### Why `.9` decimal gaps?

The 0.1px gap prevents **sub-pixel rounding conflicts** that can cause flickering or unintended style application at exact breakpoint widths (e.g., a viewport reporting `991.95px` could otherwise trigger both the 992px and 991px rules).

---

## 🎠 CSS-Only Carousel

The portfolio carousel is built entirely with **radio inputs + labels + `:checked` sibling selectors**. No JavaScript required.

### How it works

```html
<input type="radio" name="slide" id="s1" checked>
<input type="radio" name="slide" id="s2">
<input type="radio" name="slide" id="s3">
<input type="radio" name="slide" id="s4">

<div class="slides">  <!-- 4 slides, each 25% wide of a 400%-wide container -->
  <div class="slide">...</div>
  <div class="slide">...</div>
  <div class="slide">...</div>
  <div class="slide">...</div>
</div>

<label for="s2" class="slide-arrow next">›</label>  <!-- 6 arrow labels total -->
...

<div class="carousel-dots">
  <label for="s1" class="dot"></label>  <!-- clickable dots -->
  ...
</div>
```

### CSS logic

```css
.slides {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  width: 400%;  /* 4 columns at 100% each */
}

/* Slide translation based on which radio is checked */
#s1:checked ~ .slides { transform: translateX(0%); }
#s2:checked ~ .slides { transform: translateX(-25%); }
#s3:checked ~ .slides { transform: translateX(-50%); }
#s4:checked ~ .slides { transform: translateX(-75%); }

/* Only show 2 arrows at a time (prev + next for active slide) */
.slide-arrow { display: none; }
#s1:checked ~ .arr-from-s1,
#s2:checked ~ .arr-from-s2-prev,
#s2:checked ~ .arr-from-s2-next,
#s3:checked ~ .arr-from-s3-prev,
#s3:checked ~ .arr-from-s3-next,
#s4:checked ~ .arr-from-s4 { display: grid; }

/* Highlight active dot */
#s1:checked ~ .carousel-dots label[for="s1"] { /* enlarge */ }
```

### Why arrows are placed outside `.slides`

Originally the arrows lived inside each `.slide` div, but on certain widths the arrows from adjacent slides could bleed into the visible area (causing 4 arrows to appear instead of 2). Moving them **outside `.slides`** as siblings of the radio inputs and using `display: none` ensures **exactly 2 arrows** are visible at any time.

---

## 🖼 Pure CSS Hero with Absolutely Positioned Artwork

The hero section uses **CSS Grid + absolute positioning** for the layered effect:

```css
.hero-grid {
  display: grid;
  grid-template-columns: 1fr;       /* Single text column */
  min-height: 600px;
}

.hero-text {
  max-width: 620px;                /* Constrains text width */
  z-index: 3;                      /* Above the hero image */
}

.hero-image {
  position: absolute;              /* Pulled out of flow */
  right: -100px;                   /* Overflows viewport by 100px */
  width: 819px;
  z-index: 1;
}
```

The hero image is placed in the DOM **outside** `.container` so it can use the full section width for its overflow effect.

---

## 🚀 Setup & Local Preview

This project has **no build step**. To run locally:

### Option 1 — Direct file open

1. Download / clone this folder
2. Double-click `index.html` — it opens in your default browser

### Option 2 — Local server (recommended)

Some browsers block `file://` requests for fonts. Use a simple server:

```bash
# Python 3
python -m http.server 5500

# Node.js (with npx)
npx serve .

# PHP
php -S localhost:5500
```

Then visit **http://localhost:5500** in your browser.

### Option 3 — VS Code Live Server

1. Install the **Live Server** extension
2. Right-click `index.html` → **Open with Live Server**

---

## 🎨 Customization Guide

### Change brand colors

Edit the `:root` block at the top of `style.css`:

```css
:root {
  --blue:    #03a4ed;   /* primary CTA */
  --red:     #ff695f;   /* accent / prices */
  --text:    #2a2a2a;   /* body text */
  /* ... */
}
```

All colors in the entire stylesheet reference these tokens — change once, update everywhere.

### Replace the logo

1. Drop a new PNG into `assets/images/`
2. Update the `src` in 3 places in `index.html`:
   - `.logo img` (header)
   - `.footer-logo img` (footer)
   - `<link rel="icon">` (favicon)

### Add a new service card

In `.our-services .services-grid`, copy any `<article class="service-card">` block and update:
- h4 (title)
- `service-icon img src`
- `<p>` (description)

Add the matching icon PNG to `assets/images/`.

### Add a new portfolio slide

1. Drop the image into `assets/images/`
2. Copy one `<div class="slide">...</div>` block in the carousel
3. Update the `img src` references
4. Add a corresponding `<input type="radio" id="s5">` and dot
5. Add CSS rules: `#s5:checked ~ .slides { transform: translateX(-80%); }`

### Change counter numbers

In `.facts-grid`, update:
- `.count-digit` text (e.g., `320`)
- `.count-title` text (e.g., `SEO Projects`)

### Update contact info

In `.contact-info .info-block` and the form's `action` attribute.

---

## 🌐 Browser Support

| Browser | Status |
|---------|--------|
| Chrome / Edge (Chromium) | ✅ Full support |
| Firefox | ✅ Full support |
| Safari (macOS / iOS) | ✅ Full support |
| Samsung Internet | ✅ Full support |
| IE 11 | ❌ Not supported (uses modern Grid + `:has()`-adjacent patterns) |

Minimum required features:
- CSS Grid Layout
- CSS Custom Properties (variables)
- `:checked` + general sibling combinator (`~`)
- `transform` + `translateX`
- `position: absolute` + relative anchoring

---

## ♿ Accessibility

- Semantic HTML5 tags (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- All decorative images have empty `alt=""` and `aria-hidden="true"`
- Functional images have descriptive `alt` text
- Form inputs all have associated `<label>` (via `aria-label` for placeholder-only fields)
- Navigation is keyboard-accessible (links + form buttons)
- Carousel dots/arrows are real `<label>` elements bound to radio inputs → **keyboard-friendly by default**
- Color contrast: red on white passes WCAG AA for body text
- Skip-targets: each section has a meaningful `id` (`#home`, `#services`, `#about`...)

---

## ⚡ Performance

- **Zero JS** — no bundle, no parse time, no event listeners
- **Zero web fonts blocking** — `preconnect` + `display=swap` minimize FOUT
- **Single CSS file** — ~50 KB unminified
- **No external dependencies** — no jQuery, no Bootstrap, no Tailwind
- **Lazy-loadable** — images use native `loading="lazy"` (where supported) and reasonable dimensions
- **Cumulative Layout Shift** — image dimensions are constrained via `max-width` so the layout stays stable

---

## 🔧 Audit & Quality Notes

The template was originally inherited and went through a comprehensive audit. The following fixes were applied:

1. ✅ Footer logo color filter removed (was rendering black)
2. ✅ Hero text positioning normalized (single-column with max-width)
3. ✅ Duplicate `<div class="videos-list">` removed in HTML
4. ✅ `var(--black)` → `var(--text)` for about-section counters
5. ✅ Carousel arrows moved outside `.slides` + `:checked` visibility logic added
6. ✅ Subscribe form grid `1px` orphan column fixed to clean `38.5% 38.5% 23%`
7. ✅ Hero-image positioning tuned per breakpoint
8. ✅ Favicon link added to `<head>`

---

## 📜 Credits & License

- **Original template:** [Templatemo 565 – Onix Digital](https://templatemo.com/tm-565-onix-digital) (free for commercial & non-commercial use)
- **Typography:** [Google Fonts – Poppins](https://fonts.google.com/specimen/Poppins) (Open Font License)
- **Icons:** Inline SVG (no external icon library)
- **Recreation:** Pure HTML + CSS rewrite — no JavaScript, no frameworks

---

## 📞 Quick Reference

| What you want to change | Where to look |
|-------------------------|---------------|
| Brand colors | `style.css` → `:root` |
| Logo | `index.html` → `.logo img` + `.footer-logo img` + favicon |
| Hero text | `index.html` → `.hero-text` |
| Service cards | `index.html` → `.services-grid` |
| About stats | `index.html` → `.facts-grid` |
| Pricing | `index.html` → `.pricing-grid` |
| Videos | `index.html` → `.videos-grid` |
| Contact info | `index.html` → `.contact-info` |
| Footer links | `index.html` → `.footer-grid` |
| Responsive behavior | `style.css` → bottom (media queries) |

---

**Built with ❤️ — pure HTML + CSS, no compromises.**
