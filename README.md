# CDS — Classic Design Systems

A curated archive of design systems for web developers and UI designers. Each system is a complete, self-contained visual language delivered as a single interactive HTML reference — tokens, typography, components, motion, and composition examples in one file.

The goal: serve as a study resource and a starting point. Browse the systems, inspect their tokens, read the code, adapt what fits your project.

Live site: [facundouferer.github.io/designsystems](https://github.com/facundouferer/designsystems)

---

## What's inside

Four design systems, each one a full reference in a single HTML file:

| System       | Philosophy                                                   | Open                          |
| ------------ | ------------------------------------------------------------ | ----------------------------- |
| Blueprint    | Technical drawing. Cyanotype palette, monospaced grid.       | `/systems-raw/blueprint.html`  |
| Brutalist    | Raw structure. Loud neons, heavy display type, contrast.     | `/systems-raw/brutalist.html`  |
| Minimalism   | Silent interface. Muted surfaces, whitespace as component.   | `/systems-raw/minimalism.html` |
| Swiss        | International Typographic Style. Editorial grids, clarity.   | `/systems-raw/swiss.html`      |

Each file is self-contained: all tokens as CSS custom properties, all components styled inline, fonts loaded from Google Fonts. No build step needed to open and inspect them.

---

## How these systems were built

**Every design system in this archive was produced by a single AI prompt.** No hand-coding, no iteration loop — one structured prompt per system, one HTML file as the output.

This matters because it demonstrates something concrete: when the prompt is rigorously scoped (philosophy + tokens + component rules + composition example), a modern LLM can deliver a coherent, production-quality design system in a single pass. The discipline is in the prompt, not the back-and-forth.

## The prompt template

Below is the generic structure. Replace `{{STYLE_NAME}}` with the target style (Brutalist, Swiss, Memphis, Skeuomorphic, etc.) and adapt the philosophy + tokens. Keep the section scaffolding intact — it's what drives the model toward a complete, consistent output.

````markdown
Create a complete design system based on the graphic style **{{STYLE_NAME}}**
({{one-line definition of the style applied to digital interfaces}}).

Deliver it as a single self-contained HTML file with all CSS embedded,
functioning as an interactive visual reference for the system.

---

## Philosophy of the style

{{A dense paragraph on what this style *means* — not just visual traits,
but the belief system behind it. Cite historical references (movements,
studios, designers). Write 5–7 foundational principles as a bullet list.
Each principle is a rule the AI will use to resolve ambiguity later.}}

---

## Color palette

{{Table of design tokens: `--color-*` name, hex value, intended use.
Group by surface / ink / accent. State explicit rules: max number of
hues per viewport, forbidden treatments (gradients, tints, shadows of color).}}

### Accent rules
{{One or more accent options with when/where each applies.}}

### Unbreakable color rules
{{5–8 bulleted hard constraints.}}

---

## Typography

{{Primary font family (one, with 1–2 fallbacks). Full scale as a table:
token, size, weight, line-height, letter-spacing, use case. State
weight and alignment rules, forbidden patterns (centered long text,
opacity as hierarchy, etc.).}}

---

## Spacing and layout

{{Geometric spacing scale as a table: token, value, typical use.
Layout rules: max content width, column count, gutter, lateral margins,
negative space ratio.}}

---

## Elevation and depth

{{Shadow scale if the style allows shadows (or border-based depth if not).
Hard limits on how many elevation levels can coexist in a viewport.}}

---

## Borders and radius

{{Radius scale, one radius per component family. Rule against mixing radii.}}

---

## Motion and transitions

{{Duration tokens and easing curves as tables. Rules on when motion is
allowed: state change, attention guidance — never decoration.}}

---

## Iconography

{{Style (line vs fill), stroke width, allowed sizes, color inheritance,
recommended library (Lucide, Heroicons, Material Symbols).}}

---

## Components to implement

Universal rules all components must follow:
- State transition: `all var(--duration-base) var(--easing-standard)`
- Required states: rest, hover, focus, active, disabled
- Focus feedback: `outline: 2px solid var(--color-accent); outline-offset: 2px`

Then specify each component in its own numbered subsection:

### 01 — Typography (rendered scale h1–h6 + lead + caption + display number)
### 02 — Color (swatches with tokens, hex, usage)
### 03 — Buttons (primary / secondary / ghost / destructive / disabled; sm/md/lg)
### 04 — Inputs and forms (text, textarea, select, checkbox, radio, toggle)
### 05 — Cards (base, flat, elevated, interactive, stat, profile)
### 06 — Navigation (navbar, links, active state, mobile drawer)
### 07 — Tables (headers, rows, hover, action column, numeric alignment)
### 08 — Badges and tags (variants via opacity of accent, not new colors)
### 09 — Alerts (info / success / warning / error)
### 10 — Modals and overlays (backdrop, enter animation, max width)
### 11 — Menus and dropdowns (items, separators, submenus)
### 12 — Tooltips (color, arrow, delay)
### 13 — Progress and loading (bar, spinner, skeleton)
### 14 — Example page composition

---

## Example page composition

A landing-style section that integrates every component in real context:
- Hero with display number, two-line headline, subtitle, primary + ghost CTAs
- Stats section: 3 large numbers with small labels
- Card grid with horizontal separator
- Contact form with every input type
- Footer with text-small links and copyright

---

## Closing principles

Finish the document with a block of text in the system's own typography
(often ultralight weight) restating the philosophy and how a reader
should adapt the system to their own product.
````

### What makes the prompt work

- **Philosophy first, tokens second.** The model needs a belief system to resolve micro-decisions consistently.
- **Tokens as tables.** Structured data beats prose for anything that has to stay in sync.
- **Explicit "unbreakable rules."** Enumerating forbidden patterns is what prevents style drift.
- **Components numbered and scoped.** Each component is its own contract — the model finishes one before starting the next.
- **Closing composition example.** Forces the model to prove the system works as a whole, not as isolated specimens.

### Generating your own with Claude or Stitch

- **[Claude](https://claude.ai)** — paste the template with your chosen style, ask for a single HTML file. Claude Sonnet 4.6 and Opus 4.7 produce production-grade systems in one shot. Save the output as `index.html`, drop it in a browser.
- **[Stitch by Google](https://stitch.withgoogle.com)** — feed the same prompt structure. Stitch is better when you want visual iteration; Claude is better when you want a final artifact you can ship.

In both cases: **do not argue with the output.** If something's off, fix the prompt, regenerate. The prompt is the system.

---

## Local development

The site is built with Astro 6 and Tailwind CSS v4. Requires Node >= 22.12.

```sh
pnpm install
pnpm dev       # dev server at http://localhost:4321
pnpm build     # production build to ./dist
pnpm preview   # preview the production build
```

### Project structure

```
src/
├── pages/
│   └── index.astro           # single Astro route — the archive homepage
├── layouts/
│   └── Layout.astro          # HTML shell, fonts, global CSS
├── components/               # Header, Hero, CoordinateBar, SystemsGrid,
│   └── ...                   # SystemCard, Footer
├── styles/
│   └── global.css            # Tailwind v4 + @theme tokens from DESIGN.md
└── base_template/            # source HTML prototypes (pre-publish workshop)
    ├── homepage/             # DESIGN.md + code.html (the Astro homepage's spec)
    ├── Blueprint/
    ├── Brutalist/
    ├── Minimalism/
    └── Swiss/

public/
└── systems-raw/              # the 4 systems served as flat HTML
    ├── blueprint.html
    ├── brutalist.html
    ├── minimalism.html
    └── swiss.html
```

The homepage (`index.astro`) is itself a small design system called **Compiler**, generated from `src/base_template/homepage/DESIGN.md` (the archive's own spec). Its tokens live in `src/styles/global.css` inside Tailwind v4's `@theme` block.

---

## Credits

Designed and developed by **[Facundo Uferer](https://facundouferer.ar)**.

Source code: [github.com/facundouferer/designsystems](https://github.com/facundouferer/designsystems).
