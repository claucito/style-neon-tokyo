# NEON TOKYO — Design System

> A cyberpunk-inspired CSS design system for anime and clothing ecommerce. Electric Akihabara vibes, neon glow effects, and anime-inspired UI components.

![Version](https://img.shields.io/badge/version-1.0.0-ff2d95?style=for-the-badge)
![License](https://img.shields.io/badge/license-MIT-b537f2?style=for-the-badge)

---

## Concept

Neon Tokyo is a visual design language rooted in the electric energy of cyberpunk Tokyo — think rain-slicked Shinjuku streets, holographic advertisements flickering above crowded crossings, and the buzzing glow of neon signs in cramped Akihabara arcades. This is streetwear meets anime: bold, futuristic, and dripping with personality.

The aesthetic fuses Japanese anime visual language with high-contrast dark-mode cyberpunk sensibilities. Every element feels like it belongs in a ¥500 manga cafe at 2 AM or a limited-edition drop outside a Harajuku boutique at midnight.

---

## Color Palette

| Token | Hex | Usage |
|---|---|---|
| `--nt-bg-primary` | `#0a0a0f` | Page background — deep void black |
| `--nt-bg-secondary` | `#12121a` | Card and section backgrounds |
| `--nt-bg-tertiary` | `#1a1a25` | Inputs, elevated surfaces |
| `--nt-neon-pink` | `#ff2d95` | Primary CTA, key accents |
| `--nt-neon-cyan` | `#00f0ff` | Secondary accents, links, borders |
| `--nt-neon-purple` | `#b537f2` | Tertiary accent, badges |
| `--nt-text-primary` | `#ffffff` | Main text |
| `--nt-text-secondary` | `#b0b0c0` | Body copy, descriptions |

### Glow Effects

Each neon color has paired glow shadow tokens:

```css
--nt-glow-pink-sm   /* Small: 8px blur */
--nt-glow-pink      /* Medium: 20px + 40px + 80px cascade */
--nt-glow-pink-lg   /* Large: 30px + 60px + 100px cascade */
```

---

## Typography

**Headings:** `Rajdhani` (700, 600) — geometric, sharp, futuristic sans-serif with Japanese influence. Always uppercase with wide letter-spacing for maximum impact.

**Body:** `Inter` (400, 500, 600) — clean, highly legible, modern. Perfect contrast to the aggressive Rajdhani headings.

```css
/* Load from Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700&family=Inter:wght@400;500;600&display=swap');

/* CSS variables */
--nt-font-heading: 'Rajdhani', system-ui, -apple-system, sans-serif;
--nt-font-body: 'Inter', system-ui, -apple-system, sans-serif;

/* Type scale (rem) */
--nt-text-xs:   0.75rem   /* Labels, captions */
--nt-text-sm:   0.875rem  /* Small body, hints */
--nt-text-base: 1rem      /* Body copy */
--nt-text-lg:   1.125rem /* Large body */
--nt-text-xl:   1.25rem   /* Card titles */
--nt-text-2xl:  1.5rem   /* Section headings */
--nt-text-3xl:  2rem      /* H3 */
--nt-text-4xl:  2.5rem    /* H2 */
--nt-text-5xl:  3.5rem    /* H1 */
--nt-text-6xl:  5rem      /* Hero display */
```

### Gradient Text

Apply to hero headlines for maximum visual impact:

```html
<h1 class="nt-heading nt-text-gradient">Neon Tokyo</h1>
```

---

## Quick Start

### 1. Include the CSS

Add the stylesheet to your HTML:

```html
<link rel="stylesheet" href="styles.css">
```

Or import in your CSS/SCSS:

```css
@import 'styles.css';
```

### 2. Load Fonts

The CSS file includes the Google Fonts import, but you can also add manually:

```html
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
```

### 3. Start Using Components

**Navbar:**
```html
<nav class="nt-nav">
  <div class="nt-nav-inner">
    <a href="#" class="nt-nav-logo"><span>Neon</span> Tokyo</a>
    <div class="nt-nav-links">
      <a href="#" class="nt-nav-link active">Home</a>
      <a href="#" class="nt-nav-link">Shop</a>
    </div>
    <div class="nt-nav-actions">
      <button class="nt-nav-icon-btn">🔍</button>
      <button class="nt-nav-icon-btn">🛒</button>
    </div>
  </div>
</nav>
```

**Primary CTA Button:**
```html
<button class="nt-btn nt-btn-primary nt-btn-lg">Shop Now</button>
```

**Product Card:**
```html
<article class="nt-card">
  <div class="nt-card-image">
    <img src="product.jpg" alt="Product">
    <div class="nt-card-badge">
      <span class="nt-badge nt-badge-new">New</span>
    </div>
  </div>
  <div class="nt-card-body">
    <div class="nt-card-category">Outerwear</div>
    <h4 class="nt-card-title">Cyber Jacket</h4>
    <div class="nt-card-price">¥28,800</div>
  </div>
  <div class="nt-card-footer">
    <button class="nt-btn nt-btn-primary nt-btn-sm nt-btn-full">Add to Cart</button>
  </div>
</article>
```

**Badge variants:**
```html
<span class="nt-badge nt-badge-default">Default</span>
<span class="nt-badge nt-badge-new">New</span>
<span class="nt-badge nt-badge-sale">−20%</span>
<span class="nt-badge nt-badge-hot">Hot</span>
<span class="nt-badge nt-badge-preorder">Pre-order</span>
```

---

## Components

### Buttons (`.nt-btn`)

| Class | Description |
|---|---|
| `.nt-btn-primary` | Neon pink CTA with glow — use for main actions |
| `.nt-btn-secondary` | Outlined cyan — use for secondary actions |
| `.nt-btn-tertiary` | Outlined purple — use for tertiary options |
| `.nt-btn-ghost` | Text-only with underline animation |
| `.nt-btn-sm` / `.nt-btn-lg` | Size variants |
| `.nt-btn-full` | Full-width button |
| `.nt-btn-icon` | Square icon button |

All buttons have hover glow effects and press states.

### Cards (`.nt-card`)

Product cards with image, badge, category, title, price, and CTA. On hover:
- Border transitions to neon cyan
- Card lifts `8px` with spring easing
- Glow shadow appears beneath
- Image scales to `1.08x`

Featured asymmetric card (`.nt-card-featured`) for spotlighting hero products.

### Badges (`.nt-badge`)

| Class | Color |
|---|---|
| `.nt-badge-default` | Purple |
| `.nt-badge-new` | Pink (glowing) |
| `.nt-badge-sale` | Cyan (glowing) |
| `.nt-badge-hot` | Pink/purple gradient |
| `.nt-badge-preorder` | Yellow/gold |

### Form Elements

All inputs use `.nt-input`. Supported variants:
- `.nt-input-error` — pink border + glow for validation errors
- `.nt-textarea` — resizable textarea
- `.nt-select` — custom styled select with neon chevron

### Navbar (`.nt-nav`)

Sticky with `backdrop-filter: blur(16px)`. Scroll-triggered style change adds neon cyan bottom border and stronger shadow.

### Footer (`.nt-footer`)

Three-column layout with neon gradient top-border accent. Includes social links with hover glow.

### Grid System

Responsive 4-column grid with automatic column reduction:
- Desktop: 4 columns
- Tablet (≤768px): 2 columns
- Mobile (≤480px): 1 column

Use `nt-grid-cols-2`, `nt-grid-cols-3` for specific layouts.

---

## Design Tokens

All values are defined as CSS custom properties on `:root`. Override any token to customize the theme.

```css
:root {
  /* Colors */
  --nt-bg-primary: #0a0a0f;
  --nt-neon-pink: #ff2d95;
  --nt-neon-cyan: #00f0ff;
  --nt-neon-purple: #b537f2;

  /* Spacing: --nt-space-1 (0.25rem) through --nt-space-16 (4rem) */
  /* Radius: --nt-radius-sm (4px) through --nt-radius-2xl (24px) */
  /* Transitions: --nt-transition-fast (150ms), --nt-transition-base (250ms), --nt-transition-slow (400ms) */
}
```

---

## Visual Effects

### Glitch Text

Add `.nt-glitch` to headings for a CSS-only glitch animation on hover:

```html
<h1 class="nt-heading nt-text-gradient nt-glitch">Neon Tokyo</h1>
```

### Neon Flicker

For hero headlines, apply inline animation:

```html
<h1 style="animation: neonFlicker 4s ease-in-out infinite;">
```

### Scanlines Overlay

Applied to hero sections for CRT texture. See `.nt-hero-scanlines` in `styles.css`.

### Floating Elements

```html
<div class="nt-animate-float">Floating content</div>
```

---

## File Structure

```
style-neon-tokyo/
├── SPEC.md        # Full design specification
├── styles.css     # Complete design system CSS
├── index.html     # Showcase/demo page
└── README.md      # This file
```

---

## Browser Support

Modern browsers with CSS custom properties support. Tested on:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

Requires `backdrop-filter` for glassmorphism effects (progressive enhancement recommended).

---

## License

MIT — use freely for personal and commercial projects. Attribution appreciated but not required.

---

> *「東京は眠らない — Tokyo never sleeps」*