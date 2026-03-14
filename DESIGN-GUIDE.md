# FORMA Agency — Design Guide

**Version:** 1.0
**Date:** March 2026

---

## 1. Brand Essence

FORMA is built on three pillars: **authority**, **restraint**, and **precision**. Every design decision should feel considered, never decorative. The aesthetic language is editorial — drawing from luxury print, museum catalogues, and high-fashion lookbooks.

> "The most powerful brands are not companies — they are people who chose to be seen with absolute intentionality."

---

## 2. Color Palette

### Primary Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--paper` | `#EDE5D4` | Primary background — warm parchment |
| `--paper-2` | `#E4DAC6` | Secondary background (showcase, CTA sections) |
| `--paper-3` | `#D9CEBC` | Tertiary background (proof strip) |
| `--ink` | `#1E1A14` | Primary text, headings, dark sections |
| `--ink-2` | `#3A3020` | Secondary text, pull quotes |
| `--ink-3` | `#6B5C48` | Tertiary text, labels, captions, muted UI |
| `--rust` | `#C05B3A` | Accent — primary brand color |
| `--rust-lt` | `#D97A58` | Accent light — hover states on dark backgrounds |
| `--rust-dk` | `#8C3E24` | Accent dark — hover states on light backgrounds |
| `--border` | `rgba(30,26,20,0.11)` | Dividers, input borders, grid lines |

### Color Principles
- **Paper tones** create warmth and exclusivity — never use pure white
- **Rust** is used sparingly for maximum impact: labels, CTAs, italic text, accents
- **Ink** on paper is the dominant pairing — maximize contrast without harshness
- Dark sections (`--ink` background) use `rgba(237,229,212, x)` for text at varying opacities

---

## 3. Typography

### Type System

| Role | Font | Weight | Size Token | Usage |
|------|------|--------|------------|-------|
| Headlines | Playfair Display | 700, 900 | `--t-d1`, `--t-d2`, `--t-d3` | Hero H1, section titles, CTA headlines |
| Pull Quotes | Playfair Display | 400 italic | `--t-d2`, `--t-d3` | Philosophy quote, About blockquote |
| Labels / UI | IBM Plex Mono | 400, 500 | `--t-ui`, `--t-tag`, `--t-cap` | Nav, buttons, tags, stats, captions, KPIs |
| Body / Descriptions | Epilogue | 300, 400, 500 | `--t-ui` | Body copy, descriptions, footer links |

### Type Scale

| Token | Value | Use |
|-------|-------|-----|
| `--t-d1` | `clamp(3.6rem, 6.5vw, 6.5rem)` | Hero headline |
| `--t-d2` | `clamp(2rem, 3.4vw, 3.4rem)` | Section titles, philosophy quote |
| `--t-d3` | `clamp(1.35rem, 1.8vw, 1.8rem)` | Sub-headings, KPI values, stat numbers |
| `--t-ui` | `0.88rem` | Standard body copy and UI text |
| `--t-tag` | `0.62rem` | Tags, nav logo, footer logo |
| `--t-cap` | `0.50rem` | Micro-labels, captions, fine print |

### Font Rules (Strict)

**Playfair Display** — headlines and pull quotes ONLY
- Never use for body copy or UI elements
- Always pair with `letter-spacing: -0.02em` at display sizes
- Italic variant used for emphasis words and the rust-colored word in headlines

**IBM Plex Mono** — labels, tags, nav, buttons, captions, stats
- Always uppercase with wide letter-spacing (0.14em – 0.40em)
- Used for all quantitative displays (numbers, KPIs, stats)
- Never use for long-form reading

**Epilogue** — body copy, descriptions, footer links
- Default weight: 300 (light)
- Medium (500) for names and important UI labels
- Line height: 1.7–1.85 for comfortable reading

---

## 4. Spacing System

| Token | Value | Usage |
|-------|-------|-------|
| `--sp-xs` | `0.5rem` | Tight gaps between inline elements |
| `--sp-sm` | `1rem` | Standard component spacing |
| `--sp-md` | `1.75rem` | Between related sections within a block |
| `--sp-lg` | `3rem` | Between distinct content groups |
| `--sp-xl` | `5.5rem` | Large section gaps |
| `--sp-sec` | `7rem` | Section vertical padding |
| `--sp-h` | `3.5rem` | Horizontal page margin (responsive) |

---

## 5. Layout

### Grid Philosophy
- Layouts are asymmetric by design — unequal column ratios signal editorial confidence
- Hero: `1fr 1fr` (image-content split)
- About: `1.1fr 0.9fr` (content-heavier left)
- CTA: `1fr 1fr`
- Team: `repeat(4, 1fr)`
- Proof: `repeat(4, 1fr)`
- Footer: `1.4fr 1fr 1fr 1fr`

### Horizontal Margins
- Default: `3.5rem`
- Mobile (≤ 768px): `1.5rem`
- Large screens (≥ 1600px): `5.5rem`

---

## 6. Component Patterns

### Labels
All section labels follow this pattern:
- Font: IBM Plex Mono, 0.62rem
- Color: `--rust`
- Transform: uppercase, 0.28em letter-spacing
- Prefix: 16px rust horizontal rule (`::before`)
- Margin bottom: `--sp-sm`

```css
.label {
  font-family: var(--f-mono);
  font-size: var(--t-tag);
  letter-spacing: .28em;
  text-transform: uppercase;
  color: var(--rust);
}
.label::before { content:''; width:16px; height:1px; background:var(--rust); }
```

### Section Titles
- Font: Playfair Display, 700
- Size: `--t-d2`
- Line height: 1.05
- Letter spacing: -0.02em
- Italic rust words for emphasis: `<em>` tags

### Buttons

**Primary (Solid):**
- Background: `--rust` → `--rust-dk` on hover
- Text: `--paper`, Mono, uppercase, 0.2em tracking
- Padding: 0.75rem 1.75rem
- No border radius — sharp corners only

**Secondary (Text):**
- Color: `--ink-3` → `--ink` on hover
- Border-bottom underline only (no background)
- Same mono font treatment

**Nav Pill:**
- Same as solid button, smaller padding (0.5rem 1.25rem)

### Cards (Showcase)
- No border or drop shadow on the card itself
- Photo with aspect-ratio lock: `3/4` standard, `4/5` wide
- Hover: photo scales to 1.05, card lifts `-5px` Y
- Category in rust mono, name in Epilogue 500, description in Epilogue 300

### Input Fields
- Full-width, no border-radius
- Border: `1px solid var(--border)`
- Focus: border transitions to `--rust`
- Font: Epilogue body size
- Placeholder: `--ink-3`

---

## 7. Motion & Animation

### Easing
All transitions use a custom ease: `cubic-bezier(0.16, 1, 0.3, 1)` — fast out, slight overshoot feel.

### Scroll Reveal
Three reveal classes with staggered delays:

| Class | Direction | Transform |
|-------|-----------|-----------|
| `.rv` | Vertical | `translateY(24px)` → none |
| `.rvl` | Left | `translateX(-28px)` → none |
| `.rvr` | Right | `translateX(28px)` → none |

- Duration: 0.8s
- Triggered once via IntersectionObserver (10% threshold, -36px bottom margin)
- Delay modifiers: `.d1` (0.1s) → `.d4` (0.48s)

### Keyframe Animations

| Name | Usage | Duration |
|------|-------|----------|
| `fup` | Hero entrance (opacity 0 → 1, no transform) | 0.8–1s |
| `float` | Hero floating card (±7px Y sine) | 4s infinite |
| `mqs` | Marquee scroll (translateX 0 → -50%) | 28s linear infinite |

### Hover Transitions
- Standard: `0.25s` (color, border-color, text)
- Photos: `0.6–0.7s` (scale)
- Ring cursor expansion: `0.4s`
- Proof stat underline: `0.4s scaleX`
- Nav background: `0.5s`

---

## 8. Custom Cursor

Desktop only — hides native cursor (`cursor: none` on body):

- **Dot:** 6px filled circle, `--ink` color, snaps directly to mouse position
- **Ring:** 32px circle, `1.5px solid var(--rust)`, follows with 10% lerp lag
- **Hover state:** Ring expands to 50px on `a:hover` and `button:hover`

---

## 9. Photography & Imagery

### Placeholder Treatment
Until real photography is available, all image slots use:
- Warm gradient backgrounds within the paper/linen palette
- Faint italic Playfair letter glyph (6% ink opacity) centered as a watermark
- Caption overlay: Mono micro-text on semi-transparent paper background

### Real Photo Guidelines (when implemented)
- All portraits: editorial quality, desaturated or warm-toned to match palette
- No high-contrast or cool-toned photography
- Consistent aspect ratios per section (3:4 for portraits, 4:5 for wide cards)
- Hover zoom (scale 1.04–1.05) must be smooth — use `overflow: hidden` on parent

---

## 10. Dark Section Treatment

Used in: Philosophy section, Footer

- Background: `--ink` (#1E1A14)
- Headings / primary text: `rgba(237,229,212, 0.9)` (near-full paper)
- Secondary text: `rgba(237,229,212, 0.28–0.36)`
- Muted text: `rgba(237,229,212, 0.15–0.22)`
- Accent: `--rust-lt` (#D97A58) — lighter variant for legibility on dark
- Borders: `rgba(237,229,212, 0.08)`

---

## 11. Do's and Don'ts

### Do
- Use sharp corners everywhere — no border-radius except on the cursor circle
- Keep Playfair strictly for display text and quotes
- Use rust sparingly — it should command attention when it appears
- Maintain uppercase mono for all UI chrome (nav, buttons, labels, stats)
- Let whitespace breathe — generous padding signals confidence

### Don't
- Don't use pure white or pure black — always use paper/ink tokens
- Don't mix font roles (e.g., no Playfair for body text, no Epilogue for labels)
- Don't add border-radius to buttons or cards
- Don't over-animate — only elements that need attention should move
- Don't use cool-toned or saturated colors outside the defined palette
- Don't add drop shadows to cards or components (nav shadow on scroll is the only exception)
