---
version: alpha
name: bolt-new-design-analysis
language: "en-US"
source_url: "https://bolt.new/"
analyzed_at: "2026-06-02"
description: >
  Bolt.new's public website is a dark AI developer-tool system: a near-black workbench canvas, Inter / Inter Display typography, cool-blue primary actions, translucent white text tiers, hairline cards, prompt input surfaces, and product capability tables all point toward an immediate "start building" workflow. The system fits AI builders, developer tools, pricing pages, enterprise sales pages, model capability explainers, and design-system import experiences.

observed_pages:
  - label: "Home"
    url: "https://bolt.new/"
    access: "public"
  - label: "Pricing"
    url: "https://bolt.new/pricing"
    access: "public"
  - label: "Enterprise"
    url: "https://bolt.new/enterprise/"
    access: "public"

colors:
  primary: "#1488FC"
  primary-hover: "#2BA6FF"
  link: "#1488FC"
  ink: "#FFFEFF"
  body: "#FFFFFFBF"
  muted: "#FFFFFF99"
  canvas: "#1E1E21"
  canvas-deep: "#000000"
  surface-card: "#1E1E21"
  surface-elevated: "#111114"
  surface-soft: "#2C2C30"
  surface-chip: "#101010"
  hairline: "#FFFFFF1A"
  divider: "#FFFFFF26"
  on-primary: "#F3F0F5"
  success: "#22C55E"
  warning: "#F97316"
  error: "#EF4444"

typography:
  display:
    fontFamily: "\"Inter Display\", Inter, sans-serif"
    fontSize: "48px"
    fontWeight: 700
    lineHeight: "48px"
    letterSpacing: "-1.2px"
    usage: "Home hero headline: What will you build today?"
  enterprise-display:
    fontFamily: "Inter, sans-serif"
    fontSize: "66px"
    fontWeight: 500
    lineHeight: "72.6px"
    letterSpacing: "normal"
    usage: "Enterprise hero headline: Prototype to Production"
  heading:
    fontFamily: "Inter, sans-serif"
    fontSize: "52px"
    fontWeight: 500
    lineHeight: "62.4px"
    letterSpacing: "-1px"
    usage: "Enterprise sections and design-system showcase headings"
  page-title:
    fontFamily: "Inter, sans-serif"
    fontSize: "36px"
    fontWeight: 600
    lineHeight: "40px"
    letterSpacing: "normal"
    usage: "Pricing page title"
  body:
    fontFamily: "Inter, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: "24px"
    letterSpacing: "normal"
    usage: "Body copy, card copy, default page text"
  label:
    fontFamily: "Inter, sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: "20px"
    letterSpacing: "normal"
    usage: "Navigation, buttons, pricing actions"
  caption:
    fontFamily: "Inter, sans-serif"
    fontSize: "12px"
    fontWeight: 400
    lineHeight: "16px"
    letterSpacing: "normal"
    usage: "Plan button, Figma/GitHub import chips"
  mono:
    fontFamily: "ui-monospace, \"Fira Code\", Menlo, Monaco, Consolas, \"Liberation Mono\", \"Courier New\", monospace"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: "20px"
    letterSpacing: "normal"
    usage: "Code, terminal, model, and token information; observed as root variable --bolt-font-monospace"

rounded:
  none: "0px"
  sm: "4px"
  md: "6px"
  lg: "8px"
  pill: "9999px"

spacing:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "18px"
  xl: "24px"
  section: "90px"
  section-large: "109px"

components:
  top-nav: "49px public-site navigation; 14px/500 links; mobile collapses to a 36px menu button while keeping social icons"
  button-primary: "#1488FC background, 6px radius, 14px/500; used by Get started and pricing card actions"
  button-hero: "#2BA6FF background, 9999px pill radius; used by prompt Build now / Send message"
  button-secondary: "Transparent or dark surface, #FFFFFF1A border, 6px radius; used by Sign in, Learn more, Ask for a quote"
  prompt-composer: "80px Tiptap/ProseMirror input panel with 20px padding and a bottom action row containing a round add-context control, Plan pill, and Build now pill"
  import-chip: "#101010 background, #FFFFFF1A border, 9999px radius, 12px text; used by Figma/GitHub import"
  pricing-card: "#1E1E21 background, #FFFFFF1A border, 8px radius, 18px padding; stacks to a 343px-wide single column on mobile"
  agent-comparison: "#111114 section containing model capability cards, tables, and error-reduction metrics; used to create technical trust"
  enterprise-form: "Enterprise page uses hard-edged email input and pixel-like submit button; Submit uses #0F6FD0 with a small 2px right-side radius"
  feature-card: "Dark cards with hairlines, centered headings, and product capability graphics for database, security, auth, SEO, hosting, and related features"
---

## Overview

Bolt.new's public site is not a conventional marketing poster. It behaves like a dark product workbench. The first screen centers a builder prompt, and the following sections explain design-system import, model routing, pricing, and enterprise capabilities.

The system has four strong drivers:

- A dark canvas unifies the site. `#1E1E21` is the main page base, while `#111114` and `#000000` create deeper product showcase zones.
- The primary action palette is narrow and cool. Public-site CTAs use `#1488FC`; prompt execution uses the brighter `#2BA6FF`.
- Typography is restrained but technical. The home headline uses compact `Inter Display`; the enterprise headline uses a wider 66px/500 treatment.
- Components feel like product UI, not generic landing-page blocks: prompt composer, import chips, model capability table, pricing cards, enterprise lead form, and FAQ rows.

This system is best suited for AI developer tools, code-generation products, online IDEs, automation builders, design-system platforms, and technical enterprise SaaS landing pages.

## Colors

### Brand & Accent

- `primary` `#1488FC`: Used for top Get started, pricing-card Get started, and the design-system import button. It is the site-level primary action color.
- `primary-hover` `#2BA6FF`: Observed as root variable `--bolt-ds-brandHover` and as the prompt Build now / Send message action.
- `link` `#1488FC`: Observed as root variable `--bolt-ds-textLink`; suitable for inline links, billing-toggle selection, and secondary highlights.

### Surface

- `canvas` `#1E1E21`: Body background on Home and Pricing, and pricing-card background.
- `canvas-deep` `#000000`: Outer canvas on Enterprise and some deeper showcase areas.
- `surface-elevated` `#111114`: Home model-capability zone, Enterprise hero, and deeper product sections.
- `surface-soft` `#2C2C30`: Plan pill and some tool controls.
- `surface-chip` `#101010`: Figma / GitHub import chips.

### Text

- `ink` `#FFFEFF`: Primary headings, button copy, and high-priority text.
- `body` `#FFFFFFBF`: Navigation links and one-level-lower body text, around 75% white.
- `muted` `#FFFFFF99`: Helper copy, footer links, Plan button, and low-priority information, around 60% white.

### Hairlines & Borders

- `hairline` `#FFFFFF1A`: The most common public-site border, used on pricing cards, buttons, chips, and round icon buttons.
- `divider` `#FFFFFF26`: A stronger separator for table rows, module boundaries, and dark-section dividers.
- `border-active` `#2BA6FF`: Observed in root variables for focused inputs or selected states.

### Semantic

- `success` `#22C55E`: Observed in root variables for success states or positive notices.
- `warning` `#F97316`: Observed in root variables for warning or search-match states.
- `error` `#EF4444`: Observed in root variables for danger/error states.

## Typography

### Font Family

Computed styles on public pages show `Inter` as the main family, with `"Inter Display", sans-serif` on the home hero headline. Code and terminal-related variables use `ui-monospace, "Fira Code", Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace`.

### Hierarchy

- Display: Home hero uses `48px / 48px / 700 / -1.2px`. It remains 48px at the checked 390px mobile width and wraps across lines.
- Enterprise display: Enterprise hero uses `66px / 72.6px / 500`, a wider and calmer business headline style.
- Heading: Design-system and enterprise sections use `52px / 62.4px / 500 / -1px`.
- Page title: Pricing uses `36px / 40px / 600`, smaller and more tool-like than the marketing headlines.
- Body: Default copy uses `16px / 24px / 400`.
- Label: Navigation and buttons mostly use `14px / 20px / 500`.
- Caption: Chips, Plan, and helper labels use `12px / 16px / 400`.

### Principles

The type does not rely on decorative fonts. It creates technical confidence through tight line height, dark contrast, and clean weight. Body text should not be too light; navigation and buttons need 500 weight to stay legible on dark surfaces. Large headings may use slight negative tracking, but body text and buttons should not.

### Note on Font Substitutes

If `Inter Display` is unavailable, use `Inter`, `ui-sans-serif`, or the system sans stack. Avoid rounded, decorative, or strongly geometric fonts because they weaken the calm developer-tool tone.

## Layout

### Spacing System

The public site follows a clear spacing ladder: 8-12px for navigation and chips, 18-20px for card and input padding, 24px for group spacing, around 90px for the Pricing page top section, and around 109px for large Enterprise showcase blocks.

### Grid & Container

- Navigation height: about 49px on Home; about 56px on Enterprise.
- Pricing main container: about 1280px max width; desktop pricing cards are four columns around 296px each.
- Mobile pricing cards: single-column stack, about 343px wide with 16px page gutters.
- Home hero: centered composition; prompt composer is about 614px wide on desktop and 339px on mobile.
- Enterprise: full-height dark hero followed by large 1120px-scale showcase containers.

### Whitespace Philosophy

This is neither an ultra-airy brand site nor a dense admin screen. The first screen uses generous space to focus the prompt. Pricing and Enterprise pages increase information density through hairline cards, FAQ rows, and capability blocks.

## Elevation & Depth

### Decorative Depth

Bolt.new uses almost no heavy shadow. Hierarchy is built through:

- Dark surface steps: `#1E1E21`, `#111114`, and `#000000`.
- Low-opacity white borders: `#FFFFFF1A`.
- Blue highlight containers such as `#2BA6FF1A` for Help Center style notices.
- Local glow or gradient effects as support, not the main system.

Do not replace this system with large shadows, glassmorphism, or colorful gradient cards.

## Shapes

### Border Radius Scale

- `0px`: Enterprise pixel-like forms and some hard product showcase components.
- `4px`: Hard showcase containers such as the enterprise design-system slider.
- `6px`: Public navigation buttons, primary CTAs, billing toggle, and standard buttons.
- `8px`: Pricing cards.
- `9999px`: Prompt Build now, Plan, import chips, and round icon buttons.

### Media Geometry

The public site leans on UI mockups, cards, tables, and product graphics rather than photography. Component proportions are stable: pricing cards are tall, prompt input stays 80px high, and mobile controls keep practical touch height.

## Components

### Top Navigation

Desktop navigation is a 49px black bar. The logo sits left, 14px/500 links sit center, and social icons plus Sign in and Get started sit right. Link color is `rgba(255,255,255,.75)` with a primary-white hover target. Mobile navigation hides the main links and keeps logo, social icons, and a 36px Open menu button.

### Buttons

Primary buttons use `#1488FC`, 6px radius, and 14px/500 text for site-level actions. Prompt execution uses `#2BA6FF` and pill radius to feel like an immediate action. Transparent secondary buttons use a `#FFFFFF1A` border and white text for Sign in, Learn more, and Ask for a quote. Enterprise Submit uses a harder pixel-like style with `#0F6FD0` and a small 2px right-side radius.

### Cards & Containers

Pricing cards are the most stable card style: `#1E1E21` background, `#FFFFFF1A` border, 8px radius, 18px padding, and no obvious shadow. Model capability and enterprise showcase areas use deeper `#111114` backgrounds with tables, metrics, and feature tabs. Card copy should not be pure white; use 75% or 60% white for long text.

### Inputs & Forms

The home prompt composer is the signature component. It is a `role="textbox"` Tiptap/ProseMirror input surface, 80px high with 20px padding, and a bottom action row with a round add-context button, Plan pill, and Build now / Send message pill. The Enterprise email input is hard-edged, 52px high, uses 18px horizontal padding, and connects visually to a pixel-like Submit button.

### Tabs / Chips / Tags

Pricing's Monthly / Yearly control is a 6px segmented action with blue selected text. Figma / GitHub import chips use `#101010` background, `#FFFFFF1A` border, 9999px radius, and 12px text. The Teams POPULAR label is a small status tag that highlights the recommended plan.

### Signature Components

- Prompt composer: The strongest public-site identity marker and the first component to reproduce.
- Design-system rail: Porsche, Material UI, Chakra, Shadcn, and Washington Post style cards express existing design-system import.
- Agent comparison: Bolt Agent, Standard, Max, Pro only, Speed, Intelligence, and Token cost form the product-capability table.
- Pricing cards: Free / Pro / Teams / Enterprise four-column desktop grid, single-column mobile stack.
- Enterprise lead form: Work email + Submit inside a dark hero, with a harder pixel-like form style.
- Feature grid: Database, security, auth, SEO, hosting, and related capability cards.

### Footer

The footer stays on the dark canvas. Links use 14px/400 and `#FFFFFF99`, grouped as Resources, Company, Social, and related clusters. On mobile, links become a two-column grid.

## Do's and Don'ts

### Do

- Use dark surfaces and hairline borders for hierarchy instead of heavy shadows.
- Keep primary actions in the cool-blue family so CTAs do not compete.
- Build the prompt composer first; it is Bolt's strongest public-site component.
- Use 6px/8px cards on pricing and feature pages to preserve product-tool restraint.
- Keep 16px mobile gutters and collapse complex grids to one column.

### Don't

- Do not add large purple gradients, glass cards, or thick shadows.
- Do not make every button a large pill; public-site CTAs are 6px, while prompt actions are pills.
- Do not set long body copy to pure white; use 75% or 60% white.
- Do not turn the system into a generic SaaS landing page; preserve prompt, agent, token, and design-system import patterns.
- Do not claim this is Bolt's official design guideline; it is an independent analysis of publicly visible pages.

## Responsive Behavior

### Breakpoints

Home and Pricing were checked at a 390px mobile viewport. No horizontal overflow was observed: document `scrollWidth` matched the viewport width. Navigation collapses to logo + social icons + Open menu; desktop main links are not shown directly.

### Touch Targets

Open menu is a 36px square button, prompt add-context is 32px, prompt send is 36px high, and pricing card actions are 40px high. Mobile pricing cards are about 343px wide with 16px gutters.

### Collapsing Strategy

The home hero keeps its 48px display headline and wraps across lines. The prompt composer shrinks from about 614px on desktop to about 339px on mobile. Pricing's four cards stack as Free, Pro, Teams, Enterprise. Footer links become a two-column grid.

### Image Behavior

The public site relies mostly on UI mocks and product graphics rather than photography. On mobile, some design-system rail content is clipped or slides horizontally, but the overall page does not create horizontal scrolling.

## Iteration Guide

Start new screens with these rules:

1. Use `#1E1E21` as the canvas; use `#111114` or `#000000` for deeper product showcase zones.
2. Use the three text tiers `#FFFEFF`, `#FFFFFFBF`, and `#FFFFFF99`; do not introduce random grays.
3. Use `#1488FC` + 6px radius for site CTAs; use `#2BA6FF` + 9999px radius for prompt execution.
4. Reuse prompt composer, pricing card, agent comparison, feature card, and import chip before inventing new components.
5. Use an about-1280px main container, 16px mobile gutters, and one-column collapse for complex grids.

The safest extension pattern is "dark product explanation + operable component + capability table", not pure marketing copy.

## Known Gaps

- Logged-in Builder / workspace / project editor surfaces were not inspected; this document covers public marketing, pricing, and enterprise pages only.
- The Resources dropdown was attempted, but the browser click wait timed out; dropdown contents are not treated as verified evidence.
- No prompt, email form, login, purchase, upgrade, or account-changing action was submitted.
- `document.fonts` did not expose loaded font entries; font conclusions come from computed styles.
- Animations, hover transitions, and some product mock details were not broken down frame by frame.
