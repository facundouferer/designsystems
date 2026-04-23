---
name: The Modernist Compiler
colors:
  surface: '#f8f9fa'
  surface-dim: '#d9dadb'
  surface-bright: '#f8f9fa'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f4f5'
  surface-container: '#edeeef'
  surface-container-high: '#e7e8e9'
  surface-container-highest: '#e1e3e4'
  on-surface: '#191c1d'
  on-surface-variant: '#4c4546'
  inverse-surface: '#2e3132'
  inverse-on-surface: '#f0f1f2'
  outline: '#7e7576'
  outline-variant: '#cfc4c5'
  surface-tint: '#5e5e5e'
  primary: '#000000'
  on-primary: '#ffffff'
  primary-container: '#1b1b1b'
  on-primary-container: '#848484'
  inverse-primary: '#c6c6c6'
  secondary: '#b7102a'
  on-secondary: '#ffffff'
  secondary-container: '#db313f'
  on-secondary-container: '#fffbff'
  tertiary: '#000000'
  on-tertiary: '#ffffff'
  tertiary-container: '#001b3c'
  on-tertiary-container: '#6e85ab'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e2e2e2'
  primary-fixed-dim: '#c6c6c6'
  on-primary-fixed: '#1b1b1b'
  on-primary-fixed-variant: '#474747'
  secondary-fixed: '#ffdad8'
  secondary-fixed-dim: '#ffb3b1'
  on-secondary-fixed: '#410007'
  on-secondary-fixed-variant: '#92001c'
  tertiary-fixed: '#d5e3ff'
  tertiary-fixed-dim: '#b0c7f1'
  on-tertiary-fixed: '#001b3c'
  on-tertiary-fixed-variant: '#30476a'
  background: '#f8f9fa'
  on-background: '#191c1d'
  surface-variant: '#e1e3e4'
typography:
  headline-xl:
    fontFamily: Space Grotesk
    fontSize: 64px
    fontWeight: '700'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Space Grotesk
    fontSize: 48px
    fontWeight: '600'
    lineHeight: '1.2'
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Space Grotesk
    fontSize: 32px
    fontWeight: '500'
    lineHeight: '1.3'
    letterSpacing: '0'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
    letterSpacing: '0'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.5'
    letterSpacing: '0'
  label-caps:
    fontFamily: Space Grotesk
    fontSize: 12px
    fontWeight: '700'
    lineHeight: '1.0'
    letterSpacing: 0.1em
  mono-data:
    fontFamily: Space Grotesk
    fontSize: 14px
    fontWeight: '400'
    lineHeight: '1.4'
    letterSpacing: '0'
spacing:
  baseline: 8px
  gutter: 24px
  margin: 48px
  stack-xs: 4px
  stack-sm: 12px
  stack-md: 24px
  stack-lg: 48px
  stack-xl: 96px
---

## Brand & Style

This design system is an exercise in functional reductionism, heavily influenced by the Bauhaus and Swiss Design movements. It prioritizes clarity, objective information delivery, and a rigorous adherence to mathematical harmony. The brand personality is intellectual, authoritative, and timeless, evoking the feeling of a prestige design archive or a high-end architectural portfolio.

The design style is **Minimalism** blended with **International Typographic Style**. It rejects decorative ornamentation in favor of structural integrity. Users should experience a sense of "ordered calm," where every element has a logical placement within a visible or perceived grid. The UI acts as a silent, efficient vessel for content, using whitespace not just as a gap, but as a primary structural component to guide the eye and denote importance.

## Colors

The palette is rooted in a "Paper and Ink" philosophy. The background is a slightly off-white neutral to reduce digital glare and evoke physical media, while the primary color is a deep, absolute black for maximum typographic contrast.

Following Bauhaus traditions, the system utilizes a "Primary Accent" strategy. A vivid red is the secondary color for critical actions and errors; a deep blue (tertiary) and a warm yellow (quaternary) are used sparingly for categorization or highlighting specific data points. These pops of color must be used with extreme restraint—representing less than 5% of the total UI surface area—to maintain the minimalist aesthetic.

## Typography

Typography is the core engine of this design system. We utilize **Space Grotesk** for headlines and labels to capture a technical, Swiss-inspired geometric edge. For long-form reading and interface utility, **Inter** provides a neutral, highly legible contrast.

Alignment is strictly flush-left (ragged right), reflecting Modernist rejection of justified text. Type hierarchies are extreme; headers are significantly larger and bolder than body text to create a clear visual path. Labels should frequently use uppercase with increased tracking to differentiate functional UI elements from narrative content.

## Layout & Spacing

This design system employs a **Fixed Grid** model based on a 12-column architecture. The layout is inspired by editorial design, using generous margins (48px+) to frame content. 

The spacing rhythm follows an 8px baseline grid. "Whitespace as a separator" is the primary rule; rather than using lines or boxes to group items, we use varying scales of vertical stack spacing. Large sections are separated by `stack-xl` (96px) to signify a complete shift in context, while related items use `stack-sm` (12px).

## Elevation & Depth

Depth is conveyed through **Bold Borders** and **Tonal Layers** rather than shadows. In keeping with the "Flat" philosophy of Modernism, we avoid realistic light sources. 

- **Level 0 (Base):** The neutral background.
- **Level 1 (Containers):** Defined by 1px solid black borders. No shadow.
- **Level 2 (Interactive):** Elements may shift to a primary color fill (Black or Red) or gain a slightly thicker 2px border on hover.

Avoid all blurs, gradients, and transparency. If an element must feel "above" another (like a modal), use a high-contrast solid border and a stark, solid-color "drop block" (a 100% opacity offset rectangle) to mimic depth without using soft shadows.

## Shapes

The shape language is strictly **Sharp (0px)**. Every element—buttons, input fields, cards, and images—must have 90-degree corners. This reinforces the architectural and grid-based nature of the design system. Circles are permitted only for specific functional indicators (like status dots or radio buttons) to provide a stark geometric contrast to the otherwise rectangular environment.

## Components

### Buttons
Primary buttons are solid black rectangles with white, uppercase text. Secondary buttons use a 1px black border with no fill. All hover states should be immediate with no transition easing, reflecting a "mechanical" responsiveness.

### Input Fields
Fields consist of a bottom border only (2px black) with the label positioned in `label-caps` directly above the line. Error states replace the black line with a red line.

### Cards & Containers
Cards are simple boxes defined by a 1px black border. They should not have shadows. Headers within cards should be separated by a horizontal 1px line that spans the full width of the container.

### Chips & Tags
Tags are small, rectangular boxes with solid fills in secondary or tertiary colors, using white text. They never have rounded corners.

### Lists
Lists are separated by thin 1px lines. Every list item must align perfectly with the vertical grid lines of the main layout.

### Additional Components
- **The Ruler:** A horizontal or vertical persistent line used to denote scale or separate major layout sections, mimicking a technical drawing.
- **Grid Indices:** Small, functional coordinate numbers (e.g., "01", "02") placed in the top-left of sections to assist with information wayfinding.