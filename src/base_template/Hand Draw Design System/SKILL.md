---
name: hand-draw-design
description: Use this skill to generate well-branded interfaces and assets for the Hand Draw Design System — a UI framework built around hand-drawn illustration, sketch art, and analog stationery aesthetics. Contains essential design guidelines, colors, type, SVG filter techniques, and UI kit components.
user-invocable: true
---

Read the README.md file within this skill, and explore the other available files.

If creating visual artifacts (slides, mocks, throwaway prototypes, etc), copy assets out and create static HTML files for the user to view. If working on production code, read the rules here to become an expert in designing with the Hand Draw aesthetic.

If the user invokes this skill without any other guidance, ask them what they want to build or design, ask some questions, and act as an expert designer who outputs HTML artifacts _or_ production code, depending on the need.

Key design rules to follow:
- Background is always #F7F3E9 (paper cream), never pure white
- Borders are SVG strokes with feTurbulence distortion, never CSS border
- Typography: Caveat (display), Lora (body), Patrick Hand (UI/labels)
- Colors are desaturated "marker" tones — never vibrant digital hues
- Animations draw in (stroke-dashoffset) rather than fade in
- Cards rotate ±0.3°–1.5° to simulate hand placement
- Shadows use warm rgba(28,25,23,...) tint, never cool gray
- No gradients — opacity transitions of paper only
