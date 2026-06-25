# Onix Digital — Marketing & SEO Template

A pixel-perfect recreation of the **Templatemo 565 – Onix Digital** template. The page itself is built with **pure HTML + CSS** (no JS, no framework), plus **two intentionally scoped additions**:

1. A **CSS-only CRUD section** ("Manage Records") with a minimal, focused vanilla-JS layer that powers only Submit / Edit / Save / Delete.
2. **Animation libraries** — Animate.css (entry animations) and ScrollReveal.js (scroll-triggered reveals) — both with `prefers-reduced-motion` support.

Layout is powered entirely by **CSS Grid**, the portfolio carousel uses a clever **CSS-only radio + `:checked` pattern**, and the rest of the page stays 100% declarative.

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
10. [CRUD Section (JS Layer)](#-crud-section-js-layer)
11. [Animations](#-animations)
12. [Setup & Local Preview](#-setup--local-preview)
13. [Customization Guide](#-customization-guide)
14. [Browser Support](#-browser-support)
15. [Accessibility](#-accessibility)
16. [Performance](#-performance)
17. [Audit & Quality Notes](#-audit--quality-notes)
18. [Credits & License](#-credits--license)

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
- A **"Manage Records" CRUD section** — submission form + live table with Add / Edit / Save / Cancel / Delete (powered by a small vanilla-JS layer)
- Subtle **Animate.css + ScrollReveal.js** animations (hero entry, scroll reveals, with reduced-motion support)
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
| **Interactivity** | CSS-only + 1 focused JS block | Carousel/nav = pure CSS. CRUD table uses a small vanilla-JS layer (no dependencies) |
| **Animation libs** | Animate.css 4.1 + ScrollReveal 4 | Loaded via CDN; gated by `prefers-reduced-motion` |
| **Assets** | PNG / JPG / SVG | All bundled under `assets/images/` |
| **Icons** | Inline SVG | Social icons + phone/email in footer, no icon font |
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
│   ├── style.css                                           │
│   └── Animate.css CDN                                     │
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
│   │   ├── #contact    → .contact-us                       │
│   │   └── #crud-records → .crud-section (form + table)   │
│   └── <footer>      → .site-footer                        │
│                                                           │
│   <script> (end of body, before </body>)                  │
│   ├── CRUD helpers: toggleEdit, saveEdit, cancelEdit,     │
│   │                 deleteRecord, submitRecord, escapeHtml │
│   └── ScrollReveal init + reduced-motion guard            │
└──────────────────────────────────────────────────────────┘
```

### CSS File Layout (style.css)

The file is organized into clearly commented sections in this order:

```
1.  Color tokens (:root custom properties)
2.  Reset / base + prefers-reduced-motion guard
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
15. CRUD Records (.crud-section / .crud-form-card / .records-table / .edit-inline-form / decorations)
16. Footer (.site-footer / .footer-grid / .newsletter-form)
17. Responsive breakpoints (media queries)
```

---

## 📂 File & Folder Structure

```
templatemo_565_onix_digital/
│
├── index.html                    # Single-page document (now includes CRUD section + animation CDN links + 1 small <script> block)
├── style.css                     # All styling (~1500 lines, includes CRUD + decoration + reduced-motion guard + responsive overrides)
├── README.md                     # This file
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
        ├── services-left-dec.png # Services watermark + CRUD decor (left-top)
        ├── services-right-dec.png # Services watermark + CRUD decor (right-bottom)
        ├── about-left-image.png  # About section image
        ├── portfolio-01..04.jpg  # Carousel slides
        ├── portfolio-left-dec.png
        ├── tables-left-dec.png   # Pricing decoration + CRUD decor (left-mid)
        ├── first-plan-bg.png     # Pricing card background
        ├── second-plan-bg.png
        ├── third-plan-bg.png
        ├── subscribe-bg.png      # Subscribe section background
        ├── subscribe-dec.png     # Subscribe decoration + CRUD top-right corner accent
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
- 2-column grid: map + info blocks on left, form on right
- Google Maps iframe + 2 contact info blocks + form (3 fields + submit)
- Decorative blob bottom-right

### 10. Manage Records / CRUD (`.crud-section`)
- Two subsections on the same page: a submission **form card** + a **records table**
- **Form** (`#crud-form .crud-form-card`) — 3 inputs (S.No / Name / Email) styled exactly like the contact form (transparent background, blue bottom-border, Poppins 15px) wrapped in a white card with the same 20px radius and `0 0 15px rgba(0,0,0,0.1)` shadow
- **Submit button** — pill button (`.btn-blue` style), validates inputs on click and tags any empty field with `.input-error` (red bottom-border). On success, calls `submitRecord()` to append a new record + edit row to the table and clear the form
- **Records table** (`#records-tbody .records-table`) — blue `<thead>` with pill-radius first/last `<th>`, alternating zebra rows, action cell laid out via `display: grid; grid-auto-flow: column; gap: 10px`
- **Per-row actions** — Edit / Delete buttons (pill buttons; edit blue→red on hover, delete red→blue on hover)
- **Edit row** — `colspan="4"` row containing `.edit-inline-form` (grid: `80px 1fr 1fr auto auto`) with 3 pre-filled inputs and Save / Cancel buttons. Saves write back into the record row's `<td>` text content
- **Empty state** — When `data-count="0"` a single `tr.empty-state-row` shows the message *"No records yet. Fill in the form above and click Submit Record."* in muted grey. `submitRecord()` hides it on first add; `deleteRecord()` restores it when the last record is removed
- **Decorations** — 4 absolute-positioned watermarks (services-left-dec / services-right-dec / tables-left-dec / subscribe-dec) with subtle opacity 0.5–0.85. Container is elevated with `z-index: 2` so form & table always sit above
- **Responsive** — Table collapses to card-style stacked rows with `data-label` pseudo-elements under 767.9px; edit-inline-form stacks single-column; decorations are progressively hidden on smaller screens

### 11. Footer (`.site-footer`)
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

## 🧩 CRUD Section (JS Layer)

Reading typed input values, appending DOM rows, and writing edited values back into a table are **physically impossible with pure CSS** alone. To keep every other section 100% declarative, the CRUD table is driven by a **single small `<script>` block** at the end of `<body>` (just before `</body>`).

### Why a focused JS layer instead of a framework?

- The rest of the page (carousel, navigation, contact form, hero, etc.) is still pure CSS — no JS framework overhead.
- The CRUD logic is self-contained: ~120 lines of vanilla JS with zero dependencies.
- Easy to read, audit, and remove if you don't need the CRUD section.

### Functions

| Function | Purpose |
|----------|---------|
| `submitRecord()` | Reads the 3 form inputs, validates them, appends a new `<tr>` (record + paired edit row) to `#records-tbody`, increments `data-count`, hides the empty-state row, clears the form, and smooth-scrolls to the new row |
| `toggleEdit(n)` | Toggles `#edit-row-N` between `display: none` and `table-row`, flips the Edit button text to *"Editing…"* and recolors it red while editing |
| `saveEdit(n)` | Reads the 3 edit-row inputs, writes their values back into the visible record row's `<td>` cells, then closes the edit row |
| `cancelEdit(n)` | Resets the edit-row inputs back to the current displayed values and closes the edit row |
| `deleteRecord(n)` | Fades out the record row (0.3s opacity transition), removes it and its paired edit row, and restores the empty-state placeholder if no records remain |
| `escapeHtml(str)` | Sanitises user-typed input before it is injected via `innerHTML` to prevent XSS |

### Counter & empty state

```html
<tbody id="records-tbody" data-count="0">
  <tr class="empty-state-row" id="empty-state-row">
    <td colspan="4">No records yet. Fill in the form above and click Submit Record.</td>
  </tr>
</tbody>
```

`data-count` starts at `0`. Every successful `submitRecord()` increments it and assigns `id="record-row-{n}"` and `id="edit-row-{n}"`, so all subsequent Edit / Delete / Save calls work by ID.

### Validation

Empty fields trigger `.input-error` on the offending input (CSS rule `border-bottom-color: var(--red)`). `submitRecord()` returns early and shows no error toast — the red border is the only signal, matching the minimalist aesthetic.

### XSS safety

All user-typed values pass through `escapeHtml()` before being inserted via `innerHTML`, so a malicious name like `<script>alert(1)</script>` is rendered as harmless text.

---

## 🎬 Animations

Two animation libraries are loaded from CDN and gated by `prefers-reduced-motion`:

| Library | Version | Source | Role |
|---------|---------|--------|------|
| Animate.css | 4.1.1 | `cdnjs.cloudflare.com` | Entry animations on initial page load |
| ScrollReveal.js | 4.0.9 | `unpkg.com` | Scroll-triggered reveals on every section |

### Animate.css (entry animations)

Applied directly as classes in the HTML on hero/heading/CRUD/footer elements:

| Element | Classes |
|---------|---------|
| `.logo` | `animate__animated animate__fadeInLeft` |
| `.nav` | `animate__animated animate__fadeInDown` |
| `.hero-text h6, h2` | `animate__animated animate__fadeInDown` |
| `.hero-text p` | `animate__animated animate__fadeInUp` |
| `.down-buttons` | `animate__animated animate__zoomIn` |
| `.hero-image` | `animate__animated animate__fadeInRight` |
| Every `.section-heading` | `animate__animated animate__fadeInUp` |
| `.contact-form` | `animate__animated animate__fadeInUp` |
| `.crud-form-card` | `animate__animated animate__fadeInLeft` |
| `.records-wrapper` | `animate__animated animate__fadeInRight` |
| `.site-footer` | `animate__animated animate__fadeInUp` |

Only **fade / slide / zoom** are used. No bounce, flip, rotate, shake, rubberBand, heartBeat, or infinite animations.

### ScrollReveal (scroll-triggered)

A single shared instance is created at the bottom of the body:

```js
var sr = ScrollReveal({
  distance: '60px',
  duration: 1200,
  delay: 200,
  reset: false,        /* trigger once, do not loop */
  easing: 'ease'
});
```

Reveal targets by section:

| Selector | Origin | Extra |
|----------|--------|-------|
| `.hero-text h6, h2` / `.hero-text p` / `.down-buttons` / `.banner-decor-left` | `left` | |
| `.service-card` | `bottom` | `interval: 150` |
| `.about-image` | `left` | |
| `.about-text` | `right` | |
| `.pricing-item` | `bottom` | `interval: 200` |
| `.subscribe-inner` | `top` | |
| `.videos-main` | `left` | |
| `.video-item` | `right` | `interval: 150` |
| `.contact-form` / `.contact-map, .contact-info` | `bottom` | `interval: 150` |
| `.crud-form-card` | `left` | |
| `.records-wrapper` | `right` | |
| `.site-footer` | `bottom` | |

### Reduced-motion support

A guard runs at the top of the ScrollReveal init script:

```js
var prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

if (prefersReduced) {
  /* Strip all animate__* classes from the DOM */
  document.querySelectorAll('[class*="animate__"]').forEach(function (el) { /* ... */ });
  return; /* Do NOT initialise ScrollReveal */
}
```

And a CSS guard in `style.css` collapses every animation duration to ~0ms if the OS preference flips to reduce:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.001ms !important;
  }
  .animate__animated { animation: none !important; }
}
```

Users who have "reduce motion" enabled in their OS see a static page with no entry animations and no scroll reveals.

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
| IE 11 | ❌ Not supported (uses modern Grid + custom properties) |

Minimum required features:
- CSS Grid Layout
- CSS Custom Properties (variables)
- `:checked` + general sibling combinator (`~`)
- `transform` + `translateX`
- `position: absolute` + relative anchoring
- ES5+ JavaScript (uses `var`, `querySelectorAll`, `classList` — no ES6+ required for the CRUD script)
- `window.matchMedia('(prefers-reduced-motion: reduce)')` for the a11y guard

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
- **`prefers-reduced-motion: reduce`** is honoured — both Animate.css and ScrollReveal are bypassed for users with the OS preference enabled
- CRUD empty-state row uses real `<td>` content (not a placeholder image), so screen readers announce it correctly
- All CRUD action buttons are real `<button>` elements (not styled divs) → keyboard-focusable and screen-reader-friendly

---

## ⚡ Performance

- **Single CSS file** — ~70 KB unminified (includes CRUD + decoration styles + responsive overrides)
- **Tiny JS bundle** — the CRUD `<script>` block is ~3 KB unminified, vanilla JS, no dependencies
- **Zero web fonts blocking** — `preconnect` + `display=swap` minimize FOUT
- **No external JS dependencies for CRUD** — no jQuery, no Bootstrap, no framework
- **Animation libs from CDN** — Animate.css (~5 KB gzip) + ScrollReveal (~5 KB gzip), both loaded once and cached
- **`reset: false`** on ScrollReveal → animations fire exactly once per element, never re-trigger on scroll
- **Lazy-loadable** — decorative images use native `loading="lazy"`
- **Cumulative Layout Shift** — image dimensions are constrained via `max-width` so the layout stays stable
- **Animations don't block paint** — Animate.css animations are GPU-accelerated (transform/opacity) where possible

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
9. ✅ Hero decoration `.banner-decor-left` shifted to `top: -60px` so its bottom blob aligns with the dot-number row
10. ✅ Contact form `margin-left: -100px` removed → form now sits cleanly in its grid column with the standard 30px gap from the map
11. ✅ **CRUD section added** with white-card form + zebra-striped records table, pill action buttons, mobile card-style stacked rows, and 4 decorative watermarks
12. ✅ **Empty-state placeholder row** added to the CRUD table (hidden on first add, restored when last record is deleted)
13. ✅ **CRUD `<script>` block** added with `submitRecord / toggleEdit / saveEdit / cancelEdit / deleteRecord / escapeHtml` — vanilla JS, no dependencies, XSS-safe via `escapeHtml()`
14. ✅ **Animate.css 4.1.1** integrated for entry animations (hero, headings, contact form, CRUD, footer)
15. ✅ **ScrollReveal 4.0.9** integrated for scroll-triggered reveals, single shared instance, `reset: false`
16. ✅ **`prefers-reduced-motion: reduce`** fully respected — both via JS guard (strips animate classes + skips ScrollReveal init) and CSS guard (collapses all animation durations to ~0ms)

---

## 📜 Credits & License

- **Original template:** [Templatemo 565 – Onix Digital](https://templatemo.com/tm-565-onix-digital) (free for commercial & non-commercial use)
- **Typography:** [Google Fonts – Poppins](https://fonts.google.com/specimen/Poppins) (Open Font License)
- **Icons:** Inline SVG (no external icon library)
- **CRUD logic:** Original vanilla JavaScript implementation (no dependencies)
- **Animations:**
  - [Animate.css](https://animate.style/) 4.1.1 — MIT license, via cdnjs
  - [ScrollReveal.js](https://scrollrevealjs.org/) 4.0.9 — MIT license, via unpkg
- **Recreation:** HTML + CSS rewrite + focused JS layer for CRUD + animation libraries — no frameworks

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
| **CRUD form fields** | `index.html` → `#crud-form` + `<script>` → `submitRecord()` |
| **CRUD table behaviour** | `index.html` → `<script>` block at end of body |
| **CRUD styles** | `style.css` → `/* CRUD RECORDS */` block |
| **CRUD decorations** | `index.html` → `.crud-dec-*` + `style.css` → CRUD decor rules |
| Footer links | `index.html` → `.footer-grid` |
| **Entry animations** | `index.html` → `animate__*` classes on hero/heading/CRUD/footer |
| **Scroll-reveal targets** | `index.html` → ScrollReveal `<script>` block |
| **Reduced-motion behaviour** | `style.css` → `@media (prefers-reduced-motion: reduce)` |
| Responsive behaviour | `style.css` → bottom (media queries) |

---

**Built with ❤️ — pure HTML + CSS, a tiny focused JS layer for CRUD, and elegant scroll animations.**
