# NEON TOKYO — Style Specification

## Concept

A cyberpunk-inspired design system channeling the electric energy of Akihabara at midnight. Neon signs bleeding color into rain-slicked streets, holographic advertisements floating above crowded crossings, the buzz of CRT screens in cramped tech shops. This aesthetic fuses Japanese anime visual language with dark, high-contrast cyberpunk sensibilities — a love letter to Tokyo's digital underground.

**Emotional tone:** Electric, futuristic, bold, slightly nostalgic. Feels like stepping into a ¥500 manga cafe at 2 AM.

---

## Design Tokens

### Color Palette

| Token | Hex | Usage |
|---|---|---|
| `--nt-bg-primary` | `#0a0a0f` | Page background (void black) |
| `--nt-bg-secondary` | `#12121a` | Card/section backgrounds |
| `--nt-bg-tertiary` | `#1a1a25` | Elevated surfaces, inputs |
| `--nt-neon-pink` | `#ff2d95` | Primary CTA, accents |
| `--nt-neon-cyan` | `#00f0ff` | Secondary accents, links |
| `--nt-neon-purple` | `#b537f2` | Tertiary accent, badges |
| `--nt-neon-pink-glow` | `rgba(255, 45, 149, 0.6)` | Pink glow shadow |
| `--nt-neon-cyan-glow` | `rgba(0, 240, 255, 0.6)` | Cyan glow shadow |
| `--nt-neon-purple-glow` | `rgba(181, 55, 242, 0.6)` | Purple glow shadow |
| `--nt-text-primary` | `#ffffff` | Main text |
| `--nt-text-secondary` | `#b0b0c0` | Muted text |
| `--nt-text-dark` | `#0a0a0f` | Text on light backgrounds |
| `--nt-border` | `rgba(255, 255, 255, 0.08)` | Subtle borders |
| `--nt-border-neon` | `rgba(0, 240, 255, 0.3)` | Accent borders |

### Typography

**Headings:** `Rajdhani` (700, 600) — sharp, geometric, futuristic. Uppercase transforms for maximum impact.

**Body:** `Inter` (400, 500, 600) — clean, highly legible, modern sans-serif.

**Fallbacks:** `system-ui, -apple-system, sans-serif`

| Scale | Size | Weight | Font | Line Height |
|---|---|---|---|---|
| `--nt-text-xs` | 0.75rem | 500 | Inter | 1.5 |
| `--nt-text-sm` | 0.875rem | 500 | Inter | 1.5 |
| `--nt-text-base` | 1rem | 400 | Inter | 1.6 |
| `--nt-text-lg` | 1.125rem | 500 | Inter | 1.5 |
| `--nt-text-xl` | 1.25rem | 600 | Rajdhani | 1.3 |
| `--nt-text-2xl` | 1.5rem | 700 | Rajdhani | 1.2 |
| `--nt-text-3xl` | 2rem | 700 | Rajdhani | 1.1 |
| `--nt-text-4xl` | 2.5rem | 700 | Rajdhani | 1.0 |
| `--nt-text-5xl` | 3.5rem | 700 | Rajdhani | 0.95 |

### Spacing

`--nt-space-1` = 0.25rem → `--nt-space-16` = 4rem (scale in 0.25rem increments)

### Border Radius

| Token | Value |
|---|---|
| `--nt-radius-sm` | 4px |
| `--nt-radius-md` | 8px |
| `--nt-radius-lg` | 12px |
| `--nt-radius-xl` | 16px |

### Transitions

| Token | Value |
|---|---|
| `--nt-transition-fast` | 150ms ease |
| `--nt-transition-base` | 250ms ease |
| `--nt-transition-slow` | 400ms ease |

### Shadows / Glows

```css
--nt-glow-pink: 0 0 20px rgba(255, 45, 149, 0.6), 0 0 40px rgba(255, 45, 149, 0.3);
--nt-glow-cyan: 0 0 20px rgba(0, 240, 255, 0.6), 0 0 40px rgba(0, 240, 255, 0.3);
--nt-glow-purple: 0 0 20px rgba(181, 55, 242, 0.6), 0 0 40px rgba(181, 55, 242, 0.3);
```

---

## Component Examples

### Buttons

**Primary CTA** — Neon pink with glow. Uppercase Rajdhani text, letter-spacing 0.1em. Hover: intensified glow + slight scale(1.02). Active: scale(0.98).

**Secondary CTA** — Outlined in neon cyan. Ghost style with border. Hover: cyan glow + background fill at 10% opacity.

**Ghost Button** — No border, text only. Hover: underline glow effect.

### Cards

**Product Card** — Dark card (`--nt-bg-secondary`) with subtle border. Image container with gradient overlay at bottom. On hover: border transitions to neon cyan, card lifts (`translateY(-8px)`), glow appears beneath. Badge positioning top-right.

### Badges

- **Default:** Small pill, neon purple background
- **New:** Neon pink with glow
- **Sale:** Neon cyan with glow

### Navbar

Sticky, semi-transparent dark background with backdrop-blur. Logo on left (Rajdhani bold). Nav links with neon cyan hover state (underline grows from center). Mobile: hamburger becomes full-screen neon overlay menu.

### Footer

Dark background, neon pink accent line on top. Three-column layout. Social icons with hover glow.

### Form Elements

**Input:** Dark background (`--nt-bg-tertiary`), subtle border, focus state adds neon cyan border + glow.

**Select:** Custom styled with neon chevron.

---

## Visual Effects

- **Scanlines overlay** — Subtle CRT scanline texture over hero sections
- **Glitch text** — CSS-only glitch animation for headings on hover
- **Neon flicker** — Subtle brightness variation on neon elements (ambient)
- **Gradient text** — Linear gradient from pink → purple → cyan for hero headlines
- **Glassmorphism** — `backdrop-filter: blur(12px)` + semi-transparent bg on navbar/modals

---

## Layout

### Grid

12-column responsive grid:
- Desktop: 1200px max-width, 24px gaps
- Tablet (768px): 8 columns, 16px gaps
- Mobile (480px): 4 columns, 12px gaps

### Sections

- **Hero:** Full-viewport-height, centered content, animated background gradient
- **Product Grid:** 4-column → 2-column → 1-column responsive
- **Featured:** 2-column asymmetric layout (large image left, content right)