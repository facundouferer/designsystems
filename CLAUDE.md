# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

Package manager: **pnpm** (see `pnpm-lock.yaml`). Node **>= 22.12.0** is required (`package.json` `engines`).

- `pnpm install` — install dependencies
- `pnpm dev` — dev server at `localhost:4321`
- `pnpm build` — production build to `./dist/`
- `pnpm preview` — preview the production build
- `pnpm astro check` — run Astro's type + diagnostics check (there is no separate `lint` or `test` script configured yet)

## Architecture

This is an **Astro 6** project scaffolded from the `basics` starter. The live app today is just the default Astro welcome screen (`src/pages/index.astro` → `src/layouts/Layout.astro` → `src/components/Welcome.astro`), with strict TypeScript via `astro/tsconfigs/strict`.

The real intent of the repo lives in `src/base_template/homepage/`, which is a **design-system spec + reference prototype** that future work is meant to implement as Astro components:

- `src/base_template/homepage/DESIGN.md` — the canonical design system (**"The Modernist Compiler"**, Bauhaus / Swiss / International Typographic Style). Its YAML frontmatter is the **source of truth for design tokens**: the full Material-style color role palette (`surface`, `on-surface`, `primary`, `secondary`, `tertiary`, `*-container`, `*-fixed`, `outline`, `error`, …), typography scale (Space Grotesk for headlines/labels, Inter for body), and spacing rhythm (8px baseline, `gutter` 24px, `margin` 48px, `stack-xs`…`stack-xl`). Non-negotiable style rules: 0px border-radius, depth via 1–2px solid borders (never shadows/gradients/blurs), flush-left text, accent colors <5% of surface area.
- `src/base_template/homepage/code.html` — a standalone reference implementation of the homepage using Tailwind via CDN. Its `tailwind.config` block mirrors the DESIGN.md frontmatter (same token names) and is the template for how those tokens should be wired into whatever styling layer gets added to Astro (Tailwind config, CSS variables, etc.). Treat it as a visual target, not as code to import.

When implementing or extending the system, keep DESIGN.md and `code.html` in sync — tokens added/renamed in one must land in the other, and in any Astro-side config that consumes them.

### Astro conventions in play

- File-based routing under `src/pages/` (`.astro` files become routes).
- Layouts wrap pages via `<slot />` (see `Layout.astro`); components live in `src/components/`.
- `src/assets/` is for imported/optimized assets; `public/` is for files served as-is (e.g. `favicon.ico`).
- `.astro/` is generated (types) and gitignored — don't edit by hand.
