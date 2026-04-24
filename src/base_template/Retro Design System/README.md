# Retro Design System — Facundo Uferer

**Version:** 1.0  
**Designer:** Facundo Uferer  
**Studio:** Retro Design  
**Primary Era:** ERA D — Neon 80s (Synthwave / Outrun)

---

## About

Retro Design is a visual design studio by Facundo Uferer dedicated to interfaces, posters, and brand assets rooted in the visual vocabulary of 1950–1990. The work is not nostalgic in an accidental way — it is a deliberate editorial decision to invoke a specific era's visual language and generate an immediate emotional response in the viewer.

**Sources provided:**
- `uploads/Screenshot 2026-04-24 at 1.39.41 AM.png` — Vintage text effects (50s-60s Americana style)
- `uploads/Screenshot 2026-04-24 at 1.39.54 AM.png` — VHS cassette packaging (Sakura Chroma T-70), rainbow diagonal stripe motif
- `uploads/Screenshot 2026-04-24 at 1.40.33 AM.png` — 70s color palettes for retro-inspired design
- `uploads/Screenshot 2026-04-24 at 1.40.51 AM.png` — Retro 70s Pantone color chart
- `uploads/Screenshot 2026-04-24 at 1.41.06 AM.png` — Flat cassette tape illustrations in 6 colorways
- `uploads/Screenshot 2026-04-24 at 1.41.23 AM.png` — Brand poster series (Google, Dunkin, Instagram, Apple) in retro poster style

---

## Design Eras

| Era | Period | Status |
|-----|--------|--------|
| **ERA D — Neon 80s** | Synthwave, arcade, Miami Vice | **Primary (full system)** |
| ERA A — Americana 50s/60s | Googie, diner, aerolíneas | Documented as variant |
| ERA C — Groovy 70s | Terracotta, avocado, macramé | Documented as variant |
| ERA E — Pixel 90s | Windows 95, GeoCities, zine | Documented as variant |

---

## Content Fundamentals

### Voice & Tone
- **All caps is structural, not aggressive.** Headlines in Orbitron always uppercase — it's typographic law for the era, not for emphasis.
- **Terse, technical, declarative.** Copy reads like a terminal printout, a product label, or an arcade attract screen. No marketing fluff.
- **Numbers are visual elements.** Large numerals in Orbitron function as both data and decoration.
- **Spanish/English bilingual**: Facundo writes in both languages. Interface copy defaults to English; documentation may be Spanish.

### Copywriting Rules
- Short. Each line earns its place.
- Avoid soft qualifiers ("maybe", "perhaps", "could be").
- Brand names and era labels in ALL CAPS.
- Dates and versions in Share Tech Mono style: `v1.0`, `1984`, `80s`.
- No emoji — ever. Unicode symbols like `★`, `►`, `█` are acceptable as decorative glyphs.

### Examples of voice
- `> SYSTEM BOOT — RETRO DESIGN SYSTEM v1.0`
- `LOADING PRINCIPLES...`
- `★ NEON 80s ★ SYNTHWAVE ★ OUTRUN ★`
- `T-70 SUPERCASSETTE`

---

## Visual Foundations

### Color
The system centers on **ERA D — Neon 80s**:
- Deep navy/black backgrounds (`#0A0A1A`)
- Neon triumvirate: pink (`#FF2D78`), cyan (`#00F0FF`), purple (`#BF00FF`)
- Sunset gradient: orange → pink → purple
- Chrome/metallic accents in cold silver (`#C0C0D8`)
- See `colors_and_type.css` for all tokens

Secondary palettes (ERA A, C, E) available as documented variants.

### Typography
- **Display**: Orbitron — geométrica futurista, pesos 400/700/900, siempre MAYÚSCULAS
- **UI/Sub**: Exo 2 — angular sans, weights 400/500/700
- **Data/Mono**: Share Tech Mono — terminal aesthetic, all numeric data
- **Accent**: Audiowide — for select emphasis elements
- **Era variants**: Press Start 2P (90s pixel), Barlow Condensed (50s/60s), Playfair Display (70s)

### Backgrounds
- Always dark (`#0A0A1A`) with scanline CRT overlay (pointer-events: none)
- Outrun perspective grid as hero background
- Sunset gradient (`#0A0A1A → #8B00FF → #FF2A6D → #FF6B1A → #FFE600`)
- Star field static pattern
- Checkerboard in neon pink + black

### Animation
- Phosphor text reveal (blur → sharp), phosphor-on keyframes
- Neon flicker (subtle intensity fluctuation)
- VHS glitch (rare, every 8–12s, very brief)
- Outrun grid scroll toward viewer (infinite loop)
- Arcade blink (binary, steps(), cursors)
- Ticker (horizontal scroll, marquee-style)

### Cards
- `background: #0F0F2E` (bg-surface)
- `border: 1px solid #00F0FF` with box-shadow glow
- Hover: intensified glow + `translateY(-4px)`
- Scanlines overlay inside
- Padding: `var(--space-5)` (32px)

### Hover / Press States
- Hover: glow intensification + subtle lift (`translateY(-2px)`)
- Press (Arcade buttons): sombra offset compresses from 4px → 1px
- Ghost/outline: background wash at 10% opacity

### Borders & Radius
- Primary border: 1px neon color with glow
- Radius: 0px for ERA D (sharp/technical), 4px for containers
- ERA E bevel: 2px white/gray/gray/white

### Shadows
- Exclusively via `box-shadow` glow effects — no traditional drop shadows in ERA D
- Multicapa glow: `0 0 4px color, 0 0 12px color66, inset 0 0 4px color33`

### Imagery
- Flat illustration only — no photography in ERA D
- Cassette, VHS, palm trees, synthwave sun as canonical motifs
- Grid/geometric SVG patterns
- Grain texture overlay at low opacity

### Corner Radii
- **ERA D**: `border-radius: 2px` (near-sharp, technical aesthetic)
- **ERA A**: `border-radius: 8px` (organic, friendly)
- **ERA E**: `border-radius: 0px` (strict system UI)

---

## Iconography

No proprietary icon font. The system uses:
- **Unicode geometric glyphs**: `★ ► ◄ █ ▓ ░ ✦ ◆ ▲ ▼`
- **SVG inline illustrations**: Retro sun, cassette, CRT frame, outrun grid, palm tree silhouette — all hand-crafted as inline SVG within the design system
- **No emoji** in any context
- ERA E uses Windows 95-era standard icons (reconstructed in SVG/CSS)

---

## File Index

| File | Description |
|------|-------------|
| `README.md` | This file — overview and guidelines |
| `colors_and_type.css` | All CSS custom properties (tokens) |
| `SKILL.md` | Agent skill definition |
| `Retro Design System.html` | **Main design system reference** — all components |
| `preview/` | Design System tab cards (colors, type, components) |
| `ui_kits/retro/` | UI kit with interactive prototype |
| `assets/` | Logos, SVG illustrations, textures |

---

## Key Design Principles

1. **Every era has its own visual law. Learn it. Follow it. Don't mix.**
2. **Technical constraints are aesthetic decisions. Embrace the limitation.**
3. **The glow is not decoration. The glow IS the interface.**
4. **Typography places you in time. Choose your era. Choose your font.**
5. **Texture is memory. Grain, scanlines, and noise carry emotional weight.**
6. **Animation is cultural. Each decade moved differently. Honor that.**
7. **Nostalgia without irony. Inhabit the era. Don't mock it.**
