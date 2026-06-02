---
name: website-design-system-teardown
description: Analyze a live website with the Browser plugin and produce bilingual Chinese and English DESIGN.md-style design system documents plus a self-contained HTML preview. Use when the user gives a website URL and asks to break down a design system, analyze visual language, extract colors/typography/components/layout rules, create DESIGN.md, output preview HTML, save a completed case, collect cases by category, or create new design-system documents based on a site.
---

# Website Design System Teardown

## Goal

Turn a real website into practical Chinese and English DESIGN.md-style reference files plus a preview HTML that another agent can use before building UI. Do not only describe screenshots. Extract the system behind the site: tokens, rules, component behavior, and the reason each rule matters.

## Required References

Read these only when this skill is used:

- `references/design-md-breakdown-standard.md` for the teardown standard.
- `references/design-system-output-template.md` before writing the final document.
- `references/preview-html-standard.md` before writing the HTML preview.
- `references/login-collaboration.md` when the target site hides important UI behind login.
- `cases/CASE_COLLECTION.md` when saving or organizing completed cases.

## Workflow

1. Open the target URL with the Browser plugin. If the Browser plugin is unavailable, say that clearly and use the best available browser-capable fallback.
2. Inspect public pages first. If important UI is hidden behind login, paywall, invite, account workspace, or checkout state, read `references/login-collaboration.md` and ask the user whether they can assist with login before continuing. Never ask the user to send credentials in chat.
3. Inspect the site visually and through DOM/computed styles. Use at least the landing page. If the site exposes clear product, pricing, docs, app, blog, or checkout pages, inspect 2-4 representative pages. If the user logs in, inspect the logged-in surfaces that are relevant to design, not private content.
4. Collect evidence before writing claims:
   - page URLs and page roles
   - dominant backgrounds, surfaces, borders, text colors, accent colors
   - actual font families, sizes, weights, line heights, and letter spacing from computed styles
   - spacing and container patterns
   - nav, button, card, form, tab, chip, hero, footer, and signature components
   - enough domain-specific UI patterns to build a rich preview, not only generic buttons and cards
   - logo, favicon, icon SVGs, CSS mask icons, product images, UI mock images, screenshots, brand tiles, partner marks, and other public visual assets that define the source site's look
   - component-specific icon assets, especially top navigation, tab, menu, social, integration, and tool icons; do not reuse unrelated content images as icons
   - responsive changes on desktop and mobile when practical
5. Separate facts from inference. Write "inferred" or "likely" when a rule is inferred from repeated patterns rather than directly measurable.
6. Write two Markdown documents by default:
   - `design-system-analysis/<site-slug>-DESIGN.zh-CN.md`
   - `design-system-analysis/<site-slug>-DESIGN.en-US.md`
7. Write one synchronized preview HTML file by default:
   - `design-system-analysis/<site-slug>-preview.html`
8. Keep both language versions structurally identical. The English version must be a faithful counterpart to the Chinese version, not a shorter summary.
9. Make the preview HTML reflect the same tokens and component rules documented in the Markdown files. It must include anchor navigation, sectioned preview blocks, domain-specific components, and source-backed visual assets. It is not a generic demo page and not a prose documentation page.
10. Include a short "Known Gaps" section in both documents for pages not visited, hidden states not tested, missing fonts, blocked assets, login-gated surfaces not accessed, or anything uncertain.
11. If the user asks to collect the case for the skill repository, save it under the matching `cases/<category>/<site-slug>/` folder using `cases/CASE_COLLECTION.md`.

## Output Rules

- Output Chinese and English versions unless the user explicitly asks for only one language.
- Output a preview HTML file unless the user explicitly says not to.
- Use Simplified Chinese for `zh-CN` and clear product-design English for `en-US`.
- Keep the two versions in separate files by default. Create one combined bilingual file only when the user explicitly asks for a single file.
- Keep the preview HTML self-contained: inline CSS, optional tiny inline JavaScript only for preview interactions, no build step, no framework dependency, and no required local assets.
- The preview may use public source-site asset URLs when those assets are part of the observed design system, such as favicon, logo, SVG masks, product mock images, feature art, brand cards, partner marks, or app screenshots. Prefer these over placeholder drawings. If remote assets are used, verify they load in the browser and record failures in Known Gaps.
- Keep the document useful for UI implementation. Prefer exact values and usage rules over vague adjectives.
- Preserve the DESIGN.md shape: YAML-style front matter first, prose sections after.
- Do not claim brand ownership, affiliation, or official guideline status unless the website itself proves it. Use wording like "independent analysis of publicly visible pages."
- Do not collect, quote, or expose private account data from logged-in pages. Use logged-in pages only to observe design patterns, and anonymize or ignore private text.
- Do not invent tokens to make the file look complete. If a value is not observed, omit it or mark it as inferred.
- Avoid copying large chunks of website text. The output is a design-system analysis, not a content scrape.
- Never use fake placeholder icons, single-letter logo tiles, emoji, generic colored squares, or labels like `D`, `X`, `P`, `M`, `DB`, `SS`, or `AU` as substitutes for observed icons. Use the source website's public icon asset, an inline SVG extracted from the source page's CSS mask/SVG, or a faithful simple vector matching the observed icon family. If no icon evidence exists, omit the icon instead of inventing one.
- Match source assets to their original component role. A navigation tab icon must use the observed navigation/tab icon asset, not a listing image, article image, feature image, or any other unrelated source asset.
- Do not invent device frames, phone shells, browser chrome, product screenshots, or mock app windows unless that kind of frame was observed on the source site. For responsive behavior, show the real components compressed, stacked, or made swipeable instead of putting them inside an artificial device mockup.
- If the preview has anchor tabs, top-nav modes, toggles, or other visible selected states, the selected state must change correctly on click and on direct hash links. Do not leave a hard-coded `active` underline that contradicts the current URL.
- The preview must feel like a small product page built from the analyzed system. A page that reads like documentation with only color swatches, type samples, buttons, and simple cards is not acceptable.
- If screenshots are included, use them as evidence only; the main output must still be a text design system.

## Preview Quality Bar

Before writing the HTML, compare against the getdesign.md preview pattern:

- Strong first viewport with the target site's visual identity, not a generic centered explainer.
- Real source-backed logo/icon/media treatment.
- At least 6 rendered, domain-specific component sections when public evidence supports them.
- Dense enough UI examples to answer: "What would a small page built from this design system look like?"
- Visual assets are concrete and inspected, not decorative placeholders.
- The preview shows the target site's product logic: for AI tools this can be prompt composer, assistant response, workflow stepper, model table, pricing cards, integrations, command palette, settings panel, usage metrics, or product mock surfaces.

If the preview does not meet this bar, revise it before final verification.

## Verification

Before saying the skill output is ready:

1. Check both stated Markdown output files and the stated preview HTML file exist.
2. Re-read both documents for placeholders, unsupported claims, and missing Known Gaps.
3. Confirm both front matter blocks include at least `version`, `name`, `language`, `description`, `colors`, `typography`, `rounded`, `spacing`, and `components`.
4. Confirm both prose bodies include Overview, Colors, Typography, Layout, Elevation & Depth, Shapes, Components, Do's and Don'ts, Responsive Behavior, Iteration Guide, and Known Gaps.
5. Confirm the English document is not a shortened summary of the Chinese document.
6. Confirm the preview HTML has a full HTML document, inline CSS variables, responsive CSS, top anchor navigation, color swatches, type samples, source-backed icons/media when observed, and at least 6 representative component sections when enough evidence exists.
7. Search the preview HTML for placeholders and fake icon patterns before opening it:
   - forbidden output strings/classes include `Replace with`, `placeholder image`, `social-dot`, `tile-logo`, `feature-icon`, and fake one-letter icon text used as a logo.
   - also search for invented mockup wrappers such as unobserved `phone-frame`, fake browser frames, and unrelated content assets used as icons.
   - a source-backed preview should show real `<svg>`, `<img>`, source-site asset URLs, or inline vector paths for icons/media when the target site uses them.
8. Open the preview HTML in the Browser plugin and check desktop and mobile widths. If `file://` is blocked, start a local static server in the workspace and open the preview through `http://127.0.0.1:<port>/...`; do not skip browser verification because local file URLs are blocked.
9. In browser verification, confirm:
   - the page is nonblank
   - no horizontal overflow on desktop or mobile (`scrollWidth` must not exceed viewport width)
   - source images/icons load successfully when used
   - component sections are visible
   - mobile nav/grid collapse works
   - interactive selected states, such as nav tab underlines, match the current hash/URL and update after a real click
   - the preview does not look like a generic documentation page
10. After any visual or interaction fix, rerun image-load, overflow, active-state, and mobile checks. Do not reuse an older screenshot or GIF in the README after changing the preview.
11. If screenshots fail because the browser screenshot command times out, still run DOM/layout/image-load checks and say exactly what was and was not verified. Do not claim screenshot verification passed unless it did.
12. If login assistance was needed, confirm the Known Gaps accurately say which logged-in surfaces were or were not inspected.
