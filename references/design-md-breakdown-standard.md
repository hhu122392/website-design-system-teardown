# DESIGN.md-Style Website Teardown Standard

Use this standard after opening and inspecting the target website. The goal is to capture the reusable design system, not to copy one page.

## Evidence Standard

Collect enough proof to support the document:

- Visit the main URL and 2-4 representative pages when available.
- Use visual inspection for composition, imagery, density, and mood.
- Use DOM and computed styles for color, font, spacing, radius, and component measurements.
- Collect source-backed visual assets that define the system: favicon, logo, app icons, inline SVGs, CSS mask icons, product images, feature art, partner marks, brand cards, screenshots, or UI mock images.
- Check desktop and mobile behavior when practical.
- List observed pages and known gaps in the final document.
- For signature interactive components, capture source rectangles, computed styles, child layers, animation ownership, and text-fit metrics. This is required for image-artwork buttons, animated CTAs, badges, reward numbers, modal cards, bottom sheets, game boards, and share/invite surfaces.
- For any compact dynamic text, record whether the longest observed text fits inside its own visual box. Use DOM evidence such as `clientWidth`, `scrollWidth`, `white-space`, font size, and line height when possible.
- For source image buttons or decorative controls, record the layer split: outer artwork/background, inner label, icon, gesture/hand cue, and any observed offset such as `margin-top`, `top`, `bottom`, or transform.

Never write a claim as fact if it was not observed. Mark pattern-based judgments as inferred.

## Core Structure

Every language version should follow this shape:

1. YAML-style front matter
2. Overview
3. Colors
4. Typography
5. Layout
6. Elevation & Depth
7. Shapes
8. Components
9. Do's and Don'ts
10. Responsive Behavior
11. Iteration Guide
12. Known Gaps

This mirrors the getdesign.md pattern: token block first, then human-readable implementation guidance.

## Bilingual Output

Create two separate Markdown files by default:

- `<site-slug>-DESIGN.zh-CN.md`
- `<site-slug>-DESIGN.en-US.md`
- `<site-slug>-preview.html`

Use the same structure, token names, observed pages, and Known Gaps in both files. The English file is a full counterpart, not a short translation note or summary.

If the user explicitly asks for one combined bilingual document, place the Chinese version first and the English version second. Keep both full versions complete.

Always create the preview HTML unless the user explicitly says not to. The HTML preview should visualize the same tokens and rules documented in the Markdown files.

The preview HTML must be treated as visual proof, not as a decorative add-on. It should use observed source-site logo/icon/media assets when they are public and relevant. Do not replace real source assets with placeholder icons, emoji, single-letter tiles, generic initials, gray boxes, gradient boxes, or invented screenshots. If the page uses icons heavily, the preview must preserve that icon language with source-backed SVGs/images or faithful inline vectors.

## Front Matter

The front matter is the machine-friendly part. Include:

- `version`: usually `alpha`
- `name`: `<site-or-brand>-design-analysis`
- `language`: `zh-CN` or `en-US`
- `description`: one dense paragraph describing the site's visual language and best-fit use cases
- `source_url`: target URL
- `analyzed_at`: ISO-like date if available
- `observed_pages`: list of URLs inspected
- `colors`: named hex tokens with roles
- `typography`: named text styles with font family, size, weight, line height, letter spacing, and usage
- `rounded`: radius scale
- `spacing`: spacing scale
- `components`: component tokens and short usage notes

Keep token names semantic. Bad: `blue-1`. Better: `primary`, `link`, `hero-canvas`, `card-border`, `muted-text`.

## Overview

Explain the visual system in plain language:

- what the site feels like
- what creates that feel
- what the design is best suited for
- what makes it distinct from generic UI

This section should mention the main visual drivers: color contrast, type behavior, imagery, grid, density, motion, and signature motifs.

## Colors

Break colors by job, not by color family:

- Brand & Accent: primary action, links, brand marks, highlights
- Surface: page canvas, cards, elevated panels, dark/light bands
- Text: headings, body, muted text, inverse text
- Hairlines & Borders: subtle dividers, strong borders, input borders
- Semantic: success, warning, error, sale, info, state colors
- Gradients or image overlays when they are a visible system feature

For each important color, include hex and where it appears. If the exact value comes from computed style, treat it as observed. If sampled by eye, mark as approximate.

## Typography

Capture both tokens and rules:

- font family and fallback
- display, heading, body, caption, label, and monospace styles
- size, weight, line height, letter spacing
- uppercase/lowercase behavior
- numeric style if important
- where each style appears

Explain the rationale. Example: "Tight tracking makes the product feel technical" is more useful than just `letterSpacing: -0.02em`.

## Layout

Document:

- max-width/container sizes
- grid columns
- section padding
- spacing ladder
- hero height and composition
- alignment rules
- density: compact, editorial, dashboard-like, retail-like, etc.

Call out repeated layout moves such as full-bleed hero, centered narrow copy, 3-column card grids, sticky sidebars, split media/text bands, or dense product tables.

## Elevation & Depth

Describe how the site shows hierarchy:

- shadows
- borders
- translucent overlays
- blur/frosted glass
- background bands
- gradients
- image depth

If the site uses almost no shadow, say that. Absence is part of the system.

## Shapes

Document:

- border radius scale
- button shape
- card shape
- image geometry and aspect ratios
- icon shape language
- unusual cuts, masks, pills, circles, rounded panels, or square engineering style

Tie shape to usage. Example: "8px cards, pill CTAs, square media frames."

## Components

Analyze common and signature components:

- top navigation
- buttons and links
- hero sections
- cards and containers
- inputs and forms
- tabs, chips, filters, tags
- pricing or product cards
- tables or dashboards
- media blocks
- footer
- signature brand-specific components

For each component, cover structure, visual styling, states if visible, and when to use it.

For high-fidelity components, include enough implementation detail to prevent a future preview from drifting:

- Buttons and CTAs: whether the control is a real CSS button, a source artwork button, or a layered artwork button. Record label position, icon position, animation owner, and optical-centering offsets.
- Numeric displays: maximum observed text length, font-size cap, one-line/wrapping behavior, and overflow prevention.
- Modal or overlay surfaces: source viewport width, internal card width, intentional side overflow/cropping, background dimming, close control placement, and whether the component should be shown in a source-sized wrapper in the preview.
- Badges, chips, and bubbles: source asset role, text size, line height, vertical alignment, and whether the element is clickable or informational.
- Repeated components: if the same class or source asset appears in hero, fixed action, and component sample areas, document one shared rule instead of letting each instance drift.

When the source is a product, app, developer tool, AI tool, finance platform, marketplace, or media product, include domain-specific component patterns. For example: prompt composers, command palettes, terminal/code panels, model or pricing tables, usage meters, settings panels, product mock surfaces, integration cards with real icons, checkout panels, watch/player modules, trading rows, or catalog cards. Avoid reducing the preview to generic cards with explanatory text.

## Do's and Don'ts

Write implementation guardrails:

- Do: repeat the patterns that define the system.
- Don't: add generic styles that conflict with the observed system.

Make the rules direct and practical. Include common failure modes such as adding purple gradients, oversized rounded cards, heavy shadows, wrong font weight, too much decoration, or weak spacing.

## Responsive Behavior

Cover:

- breakpoints observed or inferred
- nav collapse
- grid collapse
- hero and image behavior
- touch targets
- typography scaling
- spacing reduction

If mobile was not checked, state that in Known Gaps.

For mobile-first or activity pages, explicitly document source viewport behavior. A campaign modal, game board, or invite/share card may be wider than the visible viewport and intentionally crop at the sides. Do not summarize this as "responsive card"; write the measured viewport width, internal card width, and how clipping is supposed to behave.

## Iteration Guide

Tell a future UI-building agent how to use the analysis:

- which tokens to start with
- which component pattern to build first
- how to preserve the site's character while creating new screens
- what to avoid when extending the system

## Known Gaps

Always include this section in both language versions. Examples:

- pages not inspected
- hidden menu states not opened
- forms not submitted
- logged-in surfaces unavailable
- mobile not checked
- exact brand fonts unavailable
- color values approximated
- public icon or media assets that failed to load in preview verification
- dynamic states or external actions that were not clicked, such as final share submission, checkout, purchase, recharge, send message, or social share confirmation
- text-fit or alignment values that were inferred from screenshot instead of measured from computed styles
