# Output Template

Use this template for both final documents. Fill in every template marker with evidence-backed content. Delete sections that are truly not supported by evidence, except Known Gaps, which must remain.

Default output paths:

- `design-system-analysis/<site-slug>-DESIGN.zh-CN.md`
- `design-system-analysis/<site-slug>-DESIGN.en-US.md`
- `design-system-analysis/<site-slug>-preview.html`

The two files must keep the same structure and evidence. The English version must be a full counterpart to the Chinese version, not a shorter summary.

Create the preview HTML from `preview-html-standard.md` after both Markdown files. The HTML must use the same tokens, component rules, and Known Gaps as the documents. It must include anchor navigation, numbered sections, responsive CSS, and rich domain-specific components; a generic hero/card demo is not enough.

Preview asset requirements:

- Use source-backed logo, favicon, SVG icon, product image, feature art, brand card, partner mark, screenshot, or UI mock asset when the source site exposes them publicly.
- Do not use fake placeholder icons, emoji, single-letter tiles, generic initials, gray boxes, gradient boxes, or invented product screenshots as substitutes for observed site assets.
- If an observed icon or media asset cannot be loaded in the browser, replace it with another observed public asset or record the exact failure in Known Gaps.
- Browser-check the preview HTML on desktop and mobile. If `file://` is blocked, serve the file through a local static server and open the localhost URL.

```markdown
---
version: alpha
name: <site-slug>-design-analysis
language: "<zh-CN-or-en-US>"
source_url: "<target-url>"
analyzed_at: "<YYYY-MM-DD>"
description: >
  <One dense paragraph that explains the site's visual language, its strongest
  visual signatures, and the UI types it suits best.>

observed_pages:
  - label: "Home"
    url: "<url>"
    access: "public"
  - label: "<Page role>"
    url: "<url>"
    access: "<public-or-logged-in>"

colors:
  primary: "<hex>"
  primary-hover: "<hex-or-omit>"
  ink: "<hex>"
  body: "<hex>"
  muted: "<hex>"
  canvas: "<hex>"
  surface-card: "<hex>"
  surface-elevated: "<hex>"
  hairline: "<hex>"
  on-primary: "<hex>"
  success: "<hex-or-omit>"
  warning: "<hex-or-omit>"
  error: "<hex-or-omit>"

typography:
  display:
    fontFamily: "<font stack>"
    fontSize: "<value>"
    fontWeight: <number>
    lineHeight: <value>
    letterSpacing: "<value>"
    usage: "<where this appears>"
  heading:
    fontFamily: "<font stack>"
    fontSize: "<value>"
    fontWeight: <number>
    lineHeight: <value>
    letterSpacing: "<value>"
    usage: "<where this appears>"
  body:
    fontFamily: "<font stack>"
    fontSize: "<value>"
    fontWeight: <number>
    lineHeight: <value>
    letterSpacing: "<value>"
    usage: "<where this appears>"
  label:
    fontFamily: "<font stack>"
    fontSize: "<value>"
    fontWeight: <number>
    lineHeight: <value>
    letterSpacing: "<value>"
    usage: "<where this appears>"

rounded:
  none: "0px"
  sm: "<value>"
  md: "<value>"
  lg: "<value>"
  pill: "999px"

spacing:
  xs: "<value>"
  sm: "<value>"
  md: "<value>"
  lg: "<value>"
  xl: "<value>"
  section: "<value>"

components:
  button-primary: "<short implementation note>"
  button-secondary: "<short implementation note>"
  top-nav: "<short implementation note>"
  hero: "<short implementation note>"
  card: "<short implementation note>"
  input: "<short implementation note>"
---

## Overview

<Explain the site as a system. Say what creates the look and what kinds of UI it fits.>

## Colors

### Brand & Accent

- `<token>` `<hex>`: <where it appears and why it matters>.

### Surface

- `<token>` `<hex>`: <role>.

### Text

- `<token>` `<hex>`: <role>.

### Hairlines & Borders

- `<token>` `<hex>`: <role>.

### Semantic

- `<token>` `<hex>`: <role, if observed>.

## Typography

### Font Family

<Observed font stack, fallbacks, and confidence level.>

### Hierarchy

- Display: <rules and usage>.
- Heading: <rules and usage>.
- Body: <rules and usage>.
- Label: <rules and usage>.

### Principles

<Why the typography works and how to extend it.>

### Note on Font Substitutes

<Fallback advice if the exact font is unavailable.>

## Layout

### Spacing System

<Spacing ladder and section rhythm.>

### Grid & Container

<Container widths, columns, alignment, full-bleed behavior.>

### Whitespace Philosophy

<Dense, airy, editorial, app-like, retail-like, etc.>

## Elevation & Depth

### Decorative Depth

<Borders, shadows, gradients, overlays, blur, or deliberate flatness.>

## Shapes

### Border Radius Scale

<How radius is used by component type.>

### Media Geometry

<Image/video/card aspect ratios and cropping behavior.>

## Components

### Top Navigation

<Structure, styling, states, responsive behavior.>

### Buttons

<Primary, secondary, text links, hover/focus rules if observed.>

### Cards & Containers

<Card anatomy, borders, surfaces, image treatment.>

### Inputs & Forms

<Only write if observed; otherwise move to Known Gaps.>

### Tabs / Chips / Tags

<Only write if observed.>

### Signature Components

<Brand-specific repeated visual patterns.>

### Footer

<Footer layout and styling.>

## Do's and Don'ts

### Do

- <Practical rule>.

### Don't

- <Practical rule>.

## Responsive Behavior

### Breakpoints

<Observed or inferred. Mark inferred rules clearly.>

### Touch Targets

<Mobile controls and sizing.>

### Collapsing Strategy

<How nav, grids, media, and content collapse.>

### Image Behavior

<Cropping, aspect ratio, full-bleed behavior.>

## Iteration Guide

<How a future agent should build new UI from this system.>

## Known Gaps

- <Gap or uncertainty>.
- <If login was needed but not completed, state which logged-in surfaces were not inspected.>
```
