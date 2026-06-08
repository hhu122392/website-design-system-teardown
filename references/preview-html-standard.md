# Preview HTML Standard

Create one synchronized preview HTML file for every teardown unless the user explicitly says not to.

Default path:

- `design-system-analysis/<site-slug>-preview.html`

## Purpose

The preview HTML is the visual proof of the design-system analysis. It should feel like the analyzed site has been reduced into a working mini design-system page. It is not a marketing landing page, not a screenshot copy, and not a generic demo.

The quality target is the getdesign.md preview pattern: a standalone HTML page with a nav, hero, color system, typography system, rich component examples, responsive behavior, and known gaps.

The preview must feel like a real product surface built from the source site's design system. It should not feel like a documentation page that only explains tokens.

## Hard Rules

- Write a complete standalone HTML document with `<!doctype html>`, `<html>`, `<head>`, and `<body>`.
- Keep CSS inline in a `<style>` block.
- Do not require a build step, package install, framework, or local asset folder.
- Avoid external dependencies by default. If using a web font link, it must be optional and the fallback stack must still work.
- Public source-site assets are allowed and preferred when they are part of the observed visual system: favicon, logo, SVG mask icons, social icons, product mock images, feature art, partner logos, brand cards, screenshots, or app UI images. These are not generic dependencies; they are evidence-backed design material.
- Use CSS variables for all major tokens: color, font, spacing, radius, border, shadow, and motion.
- Use the same token names and values as the Markdown documents.
- Include responsive CSS. The preview must work at desktop and mobile widths.
- Include a top anchor nav with at least `Colors`, `Typography`, `Components`, and `Responsive`.
- Use numbered section labels such as `01 - Color Palette`, `02 - Typography Scale`, and `03 - Component System`.
- Include enough real component samples to prove the system. Do not stop at one hero, one button, and one card.
- Do not include copied website text beyond short labels needed for realistic components.
- Do not use generic demo styling that conflicts with the analyzed site.
- Do not use placeholder icons or fake logo tiles. Forbidden substitutes include emoji icons, single-letter tiles, generic initials such as `D`, `X`, `P`, `M`, `DB`, `SS`, `AU`, abstract colored squares, or “icon placeholder” blocks. Use observed source-site icons, inline SVG paths extracted from the source page, or omit the icon.
- Do not use placeholder images, gray boxes, gradient boxes, or invented mock screenshots when public source images or product UI assets are available.
- Do not use a real source asset in the wrong role. A card photo, article thumbnail, hero image, or product screenshot is not an acceptable replacement for a top-nav icon, tab icon, social icon, integration icon, or tool icon.
- Do not invent device frames, phone shells, browser chrome, fake product screenshots, or mock app windows unless the source site visibly uses that exact type of frame. Responsive behavior should be demonstrated by real components collapsing, stacking, resizing, or becoming swipeable.
- Do not hard-code active nav/tab states when links can change the current section. Selected underlines, active pills, and `aria-current` values must match the current hash and update after click.
- Do not place mobile-only overlays, bottom sheets, modal invite cards, game boards, or share surfaces inside a generic padded documentation card if that changes their width, clipping, or source viewport behavior. Give those components a source-sized viewport wrapper first, then place that wrapper in the preview.
- Do not place text directly on image-artwork CTAs when the source uses a separate label layer. Preserve the outer artwork layer and the inner label/icon layer, including observed offsets such as `margin-top`, `top`, `bottom`, transforms, line height, and animation ownership.
- Do not assume `align-items: center` is enough for visual centering. Source artwork may have a visual center that differs from the element's geometric center because of highlights, shadows, empty transparent pixels, or decorative borders.

## Source Asset Rules

During site inspection, collect visual assets that define the system:

- `<link rel="icon">`, favicon, app icons
- logo images and SVGs
- inline `<svg>` elements
- CSS mask icons from computed styles
- social icons and integration icons
- product screenshots, feature images, UI mockups, brand cards, partner marks
- top navigation and product-mode tab assets, including image posters used by videos or animated icons

Use them in the preview when they make the page more faithful. Acceptable approaches:

- direct public source URL: `https://target-site/.../logo.svg`
- inline SVG copied from a visible source SVG or decoded CSS mask
- `<img>` using public source product/feature/brand assets

After using source assets, browser-check that they load. If an asset fails, replace it with another observed public asset or record the failure in Known Gaps.

Asset role matching:

- Brand mark -> observed logo, wordmark, favicon, or inline SVG.
- Product-mode or top-nav icon -> observed nav/tab icon asset from that same nav/tab component.
- Social or integration icon -> observed social/integration SVG, image, CSS mask, or faithful inline vector.
- Content card media -> observed content-card media only inside content cards, galleries, heroes, or media tiles.
- Responsive examples -> the same observed components in a narrower layout, not a fabricated device screenshot.

## Source-to-Preview Fidelity Ledger

Before writing or finalizing the preview, create a small evidence ledger for every signature component that can easily drift:

- `sourceRect`: x, y, width, height, and viewport size.
- `previewRect`: x, y, width, height, and viewport size after implementation.
- `sourceComputed`: font size, line height, weight, color, background image, background size, display, alignment, position, top/bottom/margins, transform, animation name, duration, and timing.
- `previewComputed`: the same values for the preview.
- `textFit`: `clientWidth`, `scrollWidth`, `white-space`, and whether long dynamic text fits.
- `layers`: outer artwork/background layer, text label layer, icon layer, gesture layer, motion layer, and which layer owns each style.
- `intentionalOverflow`: whether the source intentionally lets a card, hand gesture, modal, or art asset overflow/crop at mobile width.

Use this ledger for campaign CTAs, action buttons, badges, reward amounts, animated bubbles, tab controls, modal sheets, game cards, and invite/share surfaces. A screenshot can support the ledger, but it cannot replace measured evidence.

## Text and Optical Alignment Rules

Run these checks on every text-bearing component that looks like a control or compact data display:

- Buttons and CTAs: if the source uses image artwork, recreate the label as a child layer. Match the observed child-layer offset instead of centering the outer element by habit.
- Numeric rewards and balances: check the longest observed sample. If the source keeps it on one line, use `clamp()`, max width, or a measured font-size cap so `scrollWidth <= clientWidth`.
- Pills, chips, bubbles, tabs, and counters: verify the text does not overflow, wrap unexpectedly, or sit too high/low inside the visual shape.
- Icon + label buttons: verify the icon center and text layer center match the source. If the source icon is a child of the label layer, do not position it as a separate unrelated overlay.
- Artwork controls: compare visual center, not only geometric center. Record source offsets such as `margin-top: -12px` or `top: 37%` when they exist.

When fixing one control, search for all repeated instances of the same class or source asset and update them together.

## Required Page Structure

The preview must include these blocks, in this order:

1. Preview shell and nav
   - A top navigation/header that follows the analyzed site's navigation style.
   - A brand/title mark or source-backed logo/icon treatment.
   - Anchor links: `Colors`, `Typography`, `Components`, `Responsive`.
   - A primary CTA using the site's primary button style.
   - If the nav has product-mode tabs or selected states, direct links such as `#components`, `#experiences`, or `#services` must show the correct active item. A user click must update the active item.

2. Hero system sample
   - A headline that demonstrates the observed display style.
   - Short body copy that describes the analyzed visual system.
   - Primary and secondary CTAs.
   - One right-side or lower signature component that fits the site's domain.
   - The first viewport must feel designed. If the source is a product/tool site, render a product surface such as a prompt composer, command palette, dashboard, model table, settings panel, media player, checkout panel, or other real domain pattern. Do not make the hero a plain text-and-card explainer.

3. Color palette
   - Group swatches by role: Brand, Surface, Text, Border, Semantic.
   - Show token name and hex value.
   - Include alternate canvas tokens when the site uses both light and dark surfaces.

4. Typography scale
   - Display, heading, body, label, caption, and monospace/numeric samples when observed.
   - Show the usage rule, not only the font style.
   - If exact fonts are unavailable, state the preview fallback inside the page.

5. Button and action variants
   - Primary, secondary, text/link, disabled, and any special action variant observed.
   - If the site uses semantic action colors such as buy/sell, success/error, sale, warning, or info, show those separately.

6. Domain-specific component system
   - Include at least 6 component sections when enough evidence exists.
   - Each section needs a numbered label, heading, short intro, and a rendered component.
   - Choose components from the analyzed site's domain, not from a generic SaaS template.
   - At least one component should use source-backed visual assets when the source site has meaningful icons or media.
   - Product and feature examples should look like mini working UI surfaces, not just paragraphs inside cards.

7. Alternate surface or mode
   - If the site has dark/light modes, marketing/product vs transactional surfaces, editorial vs app surfaces, or another clear surface split, render both.
   - If no alternate mode was observed, include a compact note in Known Gaps instead of inventing one.

8. Responsive behavior
   - Demonstrate the grid collapse, nav collapse, touch targets, and mobile spacing rules.
   - Include a short text note describing the main breakpoint behavior.
   - Use real preview components at mobile size. Do not wrap them in an invented phone shell or fake browser frame unless the source site itself uses that visual device.

9. Known gaps
   - Mirror the important uncertainty from the Markdown documents.

## Component Selection Guide

Pick components that match the site. Examples:

- Finance / crypto / trading: market table, price ticker, buy/sell controls, stat badge, trust band, QR/app promo, FAQ rows, light transaction card.
- Ecommerce / retail: product card, category chips, price/sale treatment, product grid, filter bar, cart/checkout card, editorial campaign tile.
- Developer tools / SaaS: command palette, dashboard panel, integration card, pricing card, code block, metric strip, docs card, status pill.
- Media / editorial: full-bleed media block, article card, pull quote, issue grid, author row, newsletter form, tag chips.
- Automotive / luxury: full-bleed hero, model/spec card, configurator tile, gallery strip, stat row, dealer/contact CTA.
- AI / productivity: prompt/input surface, assistant response card, workflow stepper, feature grid, usage metric, settings panel.

For developer tools / AI builders, avoid generic “dashboard cards only.” Prefer prompt composer, model routing table, code/terminal panel, import chips, integration cards with real icons, pricing cards, project/workspace cards, generated preview frame, agent status, usage meter, and settings controls.

If the evidence supports fewer than 6 component sections, render all observed components and explain the gap. Do not invent fake patterns just to hit a number.

## Dual-Canvas and Mode Rules

Treat alternate surfaces as mandatory when observed:

- If the site uses both light and dark surfaces, preview both.
- If marketing is dark and transactional screens are light, render both.
- If the site has color-coded semantic modes, such as trading up/down, buy/sell, danger/success, show them as real components.
- If the site only has one canvas, do not force a theme toggle.

Use a light/dark toggle only when the site clearly has dual-theme behavior. Otherwise use static bands or side-by-side sections.

## Minimum Richness Bar

The preview is not acceptable if it only contains:

- nav + hero + color swatches + one card
- a generic SaaS dashboard unrelated to the target site
- text descriptions without rendered components
- CSS variables that do not match the Markdown tokens
- only one desktop layout with no mobile behavior
- placeholder icons, single-letter logo boxes, or emoji standing in for observed site icons
- fake product imagery when public source-site visual assets were available
- a page that visually reads like documentation rather than a target-site-derived preview

The preview is acceptable when it can answer: "What would a small page built from this design system look like?"

## Local Browser Verification

Use the Browser plugin to open the preview after writing it.

If direct `file://` opening is blocked by browser policy, start a local static server from the workspace and open the page through localhost:

```powershell
python -m http.server 8787 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8787/design-system-analysis/<site-slug>-preview.html
```

Do not report the preview as ready until browser verification is done or until a real blocker is reported clearly.

Verification checks:

- Page is nonblank.
- Desktop has no horizontal overflow.
- Mobile width around 390px has no horizontal overflow.
- Nav collapses or adapts on mobile.
- Source images/icons load when used; failed image count should be zero.
- Source assets are used in the correct role; nav icons are not replaced by content images.
- At least 6 component sections are present when evidence supports them.
- Placeholder icon classes or fake one-letter assets are absent.
- Invented device-frame classes or visuals are absent unless supported by source evidence.
- Active nav/tab state is tested on a direct hash URL and after at least one real click when the preview includes selected states.
- Any screenshot or GIF used in README or case documentation is regenerated after the final preview edit.
- The first viewport visually resembles a polished mini product preview, not a documentation page.
- Every repeated CTA/button class is audited globally, not just the one visible in the latest screenshot.
- For all compact text-bearing controls and numeric displays, `scrollWidth <= clientWidth` unless the source intentionally scrolls or clips the content.
- For source-artwork buttons, the preview includes the same layer split as the source: outer artwork, inner label, optional icon, optional gesture, and correct animation owner.
- For mobile overlays and modal cards, the preview wrapper matches the source mobile viewport and preserves intentional side overflow/cropping. A desktop documentation container must not squeeze the component.
- Screenshot evidence includes the intended target component. If a screenshot is captured after scrolling, record the target `getBoundingClientRect()` in the same browser state.

Screenshot checks are useful but not the only proof. If screenshot capture times out, still run DOM/layout/image-load checks and report that screenshot capture failed.

## HTML Skeleton

Use this skeleton as a starting shape. Replace every token, label, and component with the analyzed site's system.

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Design System Analysis Preview</title>
  <style>
    :root {
      --primary: #000000;
      --primary-active: #222222;
      --canvas: #ffffff;
      --canvas-alt: #f6f6f6;
      --surface: #ffffff;
      --surface-elevated: #f2f2f2;
      --ink: #111111;
      --body: #444444;
      --muted: #777777;
      --hairline: #e5e5e5;
      --success: #0a8f5a;
      --danger: #d92d20;
      --on-primary: #ffffff;
      --radius-sm: 6px;
      --radius-md: 10px;
      --radius-lg: 16px;
      --space-sm: 12px;
      --space-md: 24px;
      --space-lg: 48px;
      --section: 80px;
      --font-sans: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      --font-mono: "SFMono-Regular", Consolas, monospace;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      font-family: var(--font-sans);
      background: var(--canvas);
      color: var(--ink);
      line-height: 1.5;
    }
    .container {
      width: min(1180px, calc(100% - 32px));
      margin: 0 auto;
    }
    .nav {
      position: sticky;
      top: 0;
      z-index: 10;
      background: color-mix(in srgb, var(--canvas) 92%, transparent);
      border-bottom: 1px solid var(--hairline);
      backdrop-filter: blur(12px);
    }
    .nav-inner {
      min-height: 64px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: var(--space-md);
    }
    .nav-links {
      display: flex;
      align-items: center;
      gap: 24px;
    }
    .nav-links a {
      color: var(--body);
      text-decoration: none;
      font-weight: 600;
      font-size: 14px;
    }
    .button-primary,
    .button-secondary {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: var(--radius-sm);
      padding: 12px 18px;
      font-weight: 700;
      text-decoration: none;
      border: 1px solid transparent;
    }
    .button-primary {
      background: var(--primary);
      color: var(--on-primary);
    }
    .button-secondary {
      background: var(--surface-elevated);
      color: var(--ink);
      border-color: var(--hairline);
    }
    .hero {
      border-bottom: 1px solid var(--hairline);
      padding: var(--section) 0;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.05fr) minmax(320px, 0.95fr);
      gap: var(--space-lg);
      align-items: center;
    }
    .section {
      padding: var(--section) 0;
      border-bottom: 1px solid var(--hairline);
    }
    .section-label {
      font-family: var(--font-mono);
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.12em;
      font-size: 12px;
      margin-bottom: 16px;
    }
    .section-heading {
      font-size: clamp(28px, 4vw, 48px);
      line-height: 1.05;
      margin: 0 0 16px;
    }
    .section-intro {
      color: var(--body);
      max-width: 760px;
      margin: 0 0 32px;
    }
    .grid-4 {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: var(--space-md);
    }
    .grid-2 {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: var(--space-md);
    }
    .card {
      border: 1px solid var(--hairline);
      border-radius: var(--radius-md);
      background: var(--surface);
      padding: var(--space-md);
    }
    .swatch {
      border: 1px solid var(--hairline);
      border-radius: var(--radius-md);
      overflow: hidden;
      background: var(--surface);
    }
    .swatch-color {
      height: 72px;
      background: var(--primary);
    }
    .swatch-meta {
      padding: 12px;
      font-family: var(--font-mono);
      font-size: 12px;
      color: var(--body);
    }
    .responsive-demo {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: var(--space-md);
    }
    .component-section {
      margin-top: var(--space-md);
    }
    @media (max-width: 820px) {
      .nav-inner {
        align-items: flex-start;
        flex-direction: column;
        padding: 16px 0;
      }
      .nav-links {
        width: 100%;
        overflow-x: auto;
        gap: 16px;
      }
      .hero-grid,
      .grid-4,
      .grid-2,
      .responsive-demo {
        grid-template-columns: 1fr;
      }
      .hero,
      .section {
        padding: 48px 0;
      }
    }
  </style>
</head>
<body>
  <nav class="nav">
    <div class="container nav-inner">
      <strong>Design System Preview</strong>
      <div class="nav-links">
        <a href="#colors">Colors</a>
        <a href="#typography">Typography</a>
        <a href="#components">Components</a>
        <a href="#responsive">Responsive</a>
      </div>
      <a class="button-primary" href="#">Primary Action</a>
    </div>
  </nav>

  <header class="hero">
    <div class="container hero-grid">
      <div>
        <div class="section-label">00 - System Preview</div>
        <h1>Observed Display Style</h1>
        <p>Summarize the analyzed visual system in one short product-facing line.</p>
        <a class="button-primary" href="#">Primary</a>
        <a class="button-secondary" href="#">Secondary</a>
      </div>
      <div class="card">Render a site-specific signature component from observed evidence.</div>
    </div>
  </header>

  <section class="section" id="colors">
    <div class="container">
      <div class="section-label">01 - Color Palette</div>
      <h2 class="section-heading">Color System Headline</h2>
      <p class="section-intro">Explain how color roles work.</p>
      <div class="grid-4">Render observed color swatches.</div>
    </div>
  </section>

  <section class="section" id="typography">
    <div class="container">
      <div class="section-label">02 - Typography Scale</div>
      <h2 class="section-heading">Type System Headline</h2>
      <div class="grid-2">Render observed type samples.</div>
    </div>
  </section>

  <section class="section" id="components">
    <div class="container">
      <div class="section-label">03 - Component System</div>
      <h2 class="section-heading">Component System Headline</h2>
      <div class="component-section">
        <div class="section-label">03A - Action Variants</div>
        <div class="grid-2">Render observed button and action variants.</div>
      </div>
      <div class="component-section">
        <div class="section-label">03B - Domain Component 1</div>
        <div class="card">Render an observed domain-specific component.</div>
      </div>
      <div class="component-section">
        <div class="section-label">03C - Domain Component 2</div>
        <div class="card">Render another observed component.</div>
      </div>
      <div class="component-section">
        <div class="section-label">03D - Alternate Surface</div>
        <div class="card">Render alternate canvas or mode when observed.</div>
      </div>
    </div>
  </section>

  <section class="section" id="responsive">
    <div class="container">
      <div class="section-label">09 - Responsive Behavior</div>
      <h2 class="section-heading">Responsive Behavior Headline</h2>
      <div class="responsive-demo">Show grid collapse and mobile behavior.</div>
    </div>
  </section>

  <section class="section" id="known-gaps">
    <div class="container">
      <div class="section-label">10 - Known Gaps</div>
      <h2 class="section-heading">Known gaps</h2>
      <div class="card">Mirror important uncertainty from the Markdown documents.</div>
    </div>
  </section>
</body>
</html>
```

## Browser Verification Checklist

Before reporting completion:

- File exists at `design-system-analysis/<site-slug>-preview.html`.
- The file opens as a standalone HTML page.
- Browser inspection confirms the page is nonblank.
- Desktop width shows the hero, anchor nav, color palette, typography, and at least the first component section without overlap.
- Mobile width shows nav, hero, swatches, and component sections stacked without horizontal overflow.
- The CSS uses extracted design tokens.
- The preview includes color palette, typography, component system, responsive behavior, and Known Gaps.
- The preview contains at least 6 observed component sections when enough evidence exists.
- The preview reflects the analyzed site rather than a generic template.
- Source-backed icons/media are used when the source site exposes them.
- There are no placeholder icons, fake letter tiles, or generic image substitutes.
