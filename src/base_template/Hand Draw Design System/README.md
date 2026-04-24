# Hand Draw Design System — v1.0

## Overview

The **Hand Draw Design System** is a complete UI framework built around the aesthetic of hand-drawn illustration, sketch art, and analog stationery. It celebrates imperfection as intention: irregular borders, variable-weight strokes, paper textures, and typography that feels written rather than typeset.

**Visual reference**: the uploaded reference image (`uploads/Screenshot 2026-04-24 at 1.17.14 AM.png`) shows the core spirit — bold black outlines, sketchy doodle fills, chaotic-yet-intentional composition on a warm coral ground, handwritten lettering with varying weight and scale.

---

## Sources

- **Reference image**: `uploads/Screenshot 2026-04-24 at 1.17.14 AM.png` — hand-drawn doodle composition (COVID awareness illustration), showing the Hand Draw visual language at its most expressive
- **Design spec**: `CLAUDE.md`-equivalent design brief (pasted inline at project creation)

No Figma file or codebase was provided. All design decisions are based on the design brief and the reference image.

---

## File Map

```
README.md                     ← This file
SKILL.md                      ← Agent skill descriptor
colors_and_type.css           ← All CSS tokens (colors, type, spacing, shadow, motion)
assets/                       ← Logos, textures, illustrations
preview/                      ← Design System tab cards
  colors-base.html
  colors-ink.html
  colors-markers.html
  colors-washes.html
  colors-surfaces.html
  type-scale.html
  type-specimens.html
  type-decorative.html
  spacing-tokens.html
  shadow-elevation.html
  motion-tokens.html
  decorative-arrows.html
  decorative-underlines.html
  decorative-stamps.html
  comp-buttons.html
  comp-forms.html
  comp-cards.html
  comp-badges.html
  comp-alerts.html
  comp-tooltips.html
  comp-progress.html
  comp-nav.html
  comp-tables.html
ui_kits/
  hand_draw/
    index.html                ← Full interactive demo (landing page)
    README.md
```

---

## CONTENT FUNDAMENTALS

### Voice & Tone
- **Warm, personal, human** — writes like a real person with a pencil, not a brand department
- **Sentence case everywhere** — even headings; UPPERCASE only on stamps and seals
- **First-person friendly** — "Nothing here yet..." not "No content found"
- **Short sentences** — like notes in the margin, not long paragraphs
- **Casual punctuation** — ellipses, em-dashes; avoid exclamation mark overuse
- **No emoji** — the hand-drawn illustrations carry all the expressive weight

### Examples
- ✅ "Add your first note here..."
- ✅ "Something went wrong — try again?"
- ✅ "Looks good to me."
- ❌ "No records found." (too clinical)
- ❌ "SUCCESS! 🎉" (too digital)

---

## VISUAL FOUNDATIONS

### Color
- **Background**: always `#F7F3E9` (paper cream) — never pure white `#FFFFFF`
- **Text**: `#1C1917` (ink black) — warm near-black, never pure `#000000`
- **Accent colors**: desaturated marker palette — red, yellow, green, blue, purple, orange
- **Washes**: extremely diluted versions of markers for backgrounds/fills
- **No gradients** — opacity transitions only; color transitions are analog, not digital

### Typography
- **Display**: `Caveat` (Google Fonts, 400/600/700) — casual calligraphic, variable stroke
- **Body**: `Lora` (Google Fonts, 400/italic/700) — humanist serif, warm texture
- **UI / Labels**: `Patrick Hand` (Google Fonts, 400) — consistent, hand-feel at small sizes
- **Never UPPERCASE on display text** — mixed case with natural ascenders/descenders
- **Letter-spacing**: 0.02em body, 0.01em titles — slightly open

### Borders
- **Never CSS `border`** — always SVG strokes with `feTurbulence`/`feDisplacementMap` distortion
- Stroke weight varies: 1.5–3px along same path (thicker at curves, thinner at ends)
- Corners **overshoot** slightly — the line passes through the corner as in fast hand drawing
- Four distortion levels: subtle (0.8), base (1.5), expressive (2.5), sketchy (4.0)

### Backgrounds / Surfaces
- Paper textures via CSS `background-image` + SVG noise
- Five variants: plain, lined, grid, dotted, craft
- Cards have subtle rotation (±0.3°–1.5°) to simulate hand-placement
- `--shadow-stacked` (offset solid shadows) simulates layered paper sheets

### Animations
- Organic timing: 100ms–500ms range, nothing instant
- `draw-on`: SVG `stroke-dashoffset` → 0 (traces outlines as they appear)
- `wiggle`: ±2° rotation loop at 3s (stamps, stickers)
- `paper-lift`: hover state raises card 3px + increases shadow
- `ink-appear`: opacity 0→1 + blur 2px→0 (tooltip/dropdown reveal)
- `scribble-in`: checkbox/toggle fill with bounce scale from center

### Shadows / Elevation
- All shadows use `rgba(28,25,23,...)` — warm ink tint, never cool gray
- `--shadow-stacked`: solid offset double shadow — signature paper-pile effect
- Hover: `--shadow-lifted` (12px spread); rest: `--shadow-paper` (4px)

### Cards
- Rotated ±0.3°–0.8° at rest, via `nth-child` variation
- `--shadow-paper` at rest → `--shadow-lifted` on hover with `translateY(-3px)`
- Sticky-note variant: `--color-wash-yellow` bg, heavier top stroke
- Stacked variant: `--shadow-stacked` for layered-pages effect

### Corner Radii
- **Not used** — irregularity comes from SVG paths, not CSS `border-radius`
- SVG rect paths have hand-drawn overshoot at corners

### Imagery
- Warm color grade — coral, cream, ochre tones
- High-contrast black outlines dominant
- Doodle / illustration style; no photography
- Reference: the uploaded doodle composition shows the target visual register

### Hover / Press States
- Hover: color shift + paper-lift (cards) or draw-on underline (links)
- Press: slight scale-down (0.97) with `--easing-organic`
- Focus: SVG circle/rect draw-on outline (300ms)
- Disabled: opacity 0.4, `not-allowed` cursor

### Iconography
See ICONOGRAPHY section below.

---

## ICONOGRAPHY

- **Style**: hand-drawn SVG line illustrations — variable stroke weight, open paths, organic curves
- **No icon font / no external icon library** — all icons drawn inline SVG
- **Stroke weight**: 2–3px, `round` linecap/linejoin
- **Fill**: rare; mostly stroked; when filled, use wash colors
- **Size scale**: 16px (inline), 24px (standard), 32px (feature), 48px (hero)
- **Alert icons**: drawn as individual SVGs (✓, ✗, !, △) — not Unicode or emoji
- **No emoji** used as icons

---

## Google Fonts Note

Fonts loaded from Google Fonts CDN:
- `Caveat` — weights 400, 600, 700
- `Lora` — weights 400 (regular + italic), 700
- `Patrick Hand` — weight 400

If offline use is needed, download from fonts.google.com and place in `fonts/`.
