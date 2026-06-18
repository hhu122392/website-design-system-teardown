---
version: alpha
name: pinduoduo-special-nine-newcomer-001-design-analysis
language: "en-US"
source_url: "https://mobile.yangkeduo.com/sjs_special_nine.html"
analyzed_at: "2026-06-18"
description: >
  Independent design-system teardown of the “new users from 0.01 yuan” subsidy module on Pinduoduo's 9.9 sale page. The module combines a saturated red activity canvas, a white rounded campaign card, image-backed headline assets, a live countdown, a horizontally clipped product rail, subsidy ribbons, ultra-low price numerals, and a strong gradient CTA to create an immediate retail pressure pattern. It is best suited for newcomer subsidies, limited-time offers, low-price acquisition slots, and compact promotional product rails.
observed_pages:
  - label: "9.9 sale activity page"
    url: "https://mobile.yangkeduo.com/sjs_special_nine.html"
    access: "public visible page, query tokens redacted"
colors:
  primary: "#e63e3e"
  action-start: "#ff542e"
  action-end: "#ff1808"
  price-red: "#ef1407"
  pdd-red: "#e02e24"
  timer-red: "#ff3d34"
  orange: "#ff6310"
  canvas-red: "#e63e3e"
  surface-card: "#ffffff"
  ink: "#151516"
  muted: "#9c9c9c"
  body: "#666666"
  coupon-text: "#9d3a00"
  on-primary: "#ffffff"
  rail-border: "#ffffff"
typography:
  title-asset:
    fontFamily: "source image asset"
    fontSize: "38px visual asset height"
    fontWeight: "image-backed"
    lineHeight: "38px"
    letterSpacing: "0"
    usage: "newcomer headline asset"
  timer-label:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "22.1867px"
    fontWeight: 400
    lineHeight: "25.6px"
    letterSpacing: "0"
    usage: "remaining-time label"
  timer-digit:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "20.48px"
    fontWeight: 500
    lineHeight: "29.0133px"
    letterSpacing: "0"
    usage: "countdown digit capsules"
  product-title:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "22.1867px"
    fontWeight: 400
    lineHeight: "32.4267px"
    letterSpacing: "0"
    usage: "single-line clipped product title"
  price:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "34.1333px"
    fontWeight: 600
    lineHeight: "34.1333px"
    letterSpacing: "0"
    usage: "subsidized price numeral"
  cta:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "29.0133px"
    fontWeight: 600
    lineHeight: "43.52px"
    letterSpacing: "0"
    usage: "primary grab-now CTA"
rounded:
  sm: "3.41333px"
  md: "6.82667px"
  lg: "13.6533px"
  pill: "34.1333px"
spacing:
  xs: "6.82667px"
  sm: "13.6533px"
  md: "20.48px"
  lg: "34.1333px"
  section: "68px"
components:
  red-campaign-band: "640px-wide red activity band containing the white newcomer card"
  newcomer-card: "613x451 white rounded card with 13.6533px radius"
  title-asset-row: "31x38 icon asset plus 266x38 headline asset on the left, countdown on the right"
  countdown: "remaining label, 29px red-orange digit capsules, and red separators"
  product-rail: "599x276 clipped viewport with 1934px of horizontal product content"
  subsidy-ribbon: "174x31 image-backed ribbon with white subsidy text and arrow asset"
  product-card: "174px card: square image, 31px subsidy ribbon, 32px title, 34px price row"
  primary-cta: "512x68 pill CTA with red-orange gradient, 34.1333px radius, and soft red shadow"
---

## Overview

This is a mobile retail campaign module, not a normal product grid. It stacks pressure signals: an image-backed newcomer headline highlights `0.01 yuan`, a live countdown keeps urgency moving, the product rail exposes part of the next card, and the large pill CTA closes the flow. The intended reading is immediate: newcomer deal, active subsidy, very low price, act now.

The reusable core is the red activity canvas, white rounded campaign card, high-contrast price system, and strong CTA. It should not be turned into a calm marketplace list or expanded with heavy explanatory copy.

## Colors

### Brand & Accent

- `primary` `#e63e3e`: the red activity background.
- `action-start` `#ff542e` to `action-end` `#ff1808`: the 90-degree CTA gradient.
- `price-red` `#ef1407`: the main price numeral, more aggressive than regular brand red.
- `pdd-red` `#e02e24`: supporting red for price-label text.
- `timer-red` `#ff3d34`: countdown separators and time accents.

### Surface

- `surface-card` `#ffffff`: the newcomer card, product rail, and product content surface.
- `canvas-red` `#e63e3e`: the activity background around the card.

### Text

- `ink` `#151516`: product names.
- `muted` `#9c9c9c`: weak prompt text such as the remaining-time label.
- `body` `#666666`: default page body text.
- `coupon-text` `#9d3a00`: the small “one time only” tag inside the CTA.
- `on-primary` `#ffffff`: countdown digits, CTA text, and subsidy ribbon text.

### Hairlines & Borders

The module does not rely on hairlines. Hierarchy comes from card surfaces, clipped image blocks, red ribbon art, and large rounded actions. Product cards are separated by spacing rather than borders.

### Semantic

- Red means low price, urgency, and sale action.
- Orange-red gradients mean primary conversion.
- White means product and information surface.

## Typography

### Font Family

Ordinary text uses a system Chinese font stack. The headline “new users from 0.01 yuan” is not DOM text; it is built from two source image assets: a 31x38 orange icon and a 266x38 wordmark. Rebuilding it as normal text would change the module's visual weight.

### Hierarchy

- Headline asset: 38px visual height, 31px icon width, 266px headline width.
- Countdown label: `22.1867px / 25.6px / 400`, gray.
- Countdown digits: `20.48px / 29.0133px / 500`, white text inside 29x29 capsules.
- Product title: `22.1867px / 32.4267px / 400`, dark text, clipped to one line.
- Main price numeral: integer at `34.1333px / 600`, decimal at `23.8933px / 600`.
- CTA: `29.0133px / 43.52px / 600`, white.

### Principles

The type system is conversion-weighted, not uniform. The headline asset owns the module, the CTA is the next strongest, the price numerals dominate product cards, and product titles only provide recognition.

### Note on Font Substitutes

Use `system-ui, -apple-system, BlinkMacSystemFont, "PingFang SC", Arial, sans-serif` for ordinary text. Keep the source headline assets when possible; if the title copy changes, redraw a matching title asset.

## Layout

### Spacing System

The observed activity band is 640px wide. The white card is `613x451` with a roughly 13px side inset. The title row is 38px high, the product rail starts at `y=213`, and the CTA starts at `y=500`. Product cards are 174px wide with roughly 10px horizontal spacing.

### Grid & Container

Core structure:

1. Red background band: `640x471`.
2. White newcomer card: `613x451`, radius `13.6533px`.
3. Headline/countdown row: image assets on the left, countdown on the right.
4. Product rail: visible viewport `599x276`, inner content width `1934px`.
5. Primary CTA: `512x68`, centered pill.

### Whitespace Philosophy

This is a dense retail module. Whitespace is used only to keep recognition and tapping clear. The product area is tight; the CTA receives the strongest breathing room.

## Elevation & Depth

### Decorative Depth

Depth comes from:

- the white card against the red activity canvas
- the CTA shadow: `rgba(253, 99, 99, 0.3) 0px 3.41333px 17.0667px 0px`
- product imagery
- image-backed subsidy ribbons and arrow layers

There is no complex shadow or glass system. Hierarchy is mostly color, surface area, and image density.

## Shapes

### Border Radius Scale

- Countdown digit capsule: `3.41333px`.
- Product rail bottom corners: `0 0 6.82667px 6.82667px`.
- Newcomer card: `13.6533px`.
- Primary CTA: `34.1333px`, a true pill.

### Media Geometry

Product images are `174x174` square images with cover-style cropping. Product titles and prices stay within the same 174px card width.

## Components

### Top Navigation

This teardown focuses on the newcomer subsidy module. The search bar and category tabs provide context for the 9.9 sale page but are not part of the target module.

### Buttons

The primary button is a `512x68` red-orange gradient pill using `linear-gradient(90deg, #ff542e, #ff1808)`, a `34.1333px` radius, and a soft red shadow. It contains a large white “grab now” label and a small light tag for the “one time only” constraint. It should not be replaced by a generic rectangular button.

The CTA was not clicked because it may trigger claiming, purchase, or account-state changes.

### Cards & Containers

The main container is a white rounded card, and the product rail is another white surface inside it. The rail is not a normal grid; it is a horizontal activity shelf.

### Inputs & Forms

No input is part of this module. The page search field above it was not analyzed as a module input.

### Tabs / Chips / Tags

The main tag is the “subsidized by 3 yuan” ribbon. It uses the source image-backed ribbon asset `476bf3be...png`, with a separate arrow asset `edecb4cb...png`. Replacing it with a plain CSS rectangle would lose the promotional texture.

### Signature Components

#### 01 Headline Asset Row

The left icon and headline are background-image assets, not text. The icon asset is `1a7463a2...png`; the title asset is `d1bfbf4e...png`. The countdown sits on the same row to tie low-price messaging to urgency.

#### 02 Countdown

The countdown consists of a remaining-time label, three two-digit capsules, one one-digit decimal capsule, and red separators. A 1.3-second check changed the value from `06:47:33.9` to `06:47:32.5`, so this is a real dynamic state.

#### 03 Product Rail

The visible viewport is `599x276` with `overflow:hidden`; the inner content is `1934px` wide. A partial card on the right creates a “more content” affordance.

Mouse dragging did not move the rail in this browser session, so this audit verifies clipping and horizontal structure, not desktop mouse dragging. Touch swiping may exist but was not confirmed.

#### 04 Product Card

Each card has:

1. a `174x174` product image
2. a `174x31` subsidy ribbon
3. a `174x32` product title, clipped to one line
4. a `174x34` price row

The clipped long title is intentional; it preserves the module's density.

#### 05 Subsidy Ribbon

The ribbon uses an image background with white `20.48px / 600` text and a small arrow asset on the right. It communicates a subsidy mechanism, not a generic sale badge.

#### 06 Price Row

The “subsidy price” label is `20.48px`, the integer numeral is `34.1333px`, and the decimal is `23.8933px`. The visual emphasis lands on the large `0`.

#### 07 Primary CTA

The CTA is centered under the product rail. It is 512px wide and 68px tall. The main label is centered-left, while the “one time only” tag acts as a constraint badge inside the same pill.

#### 08 View More Entry

At the rail's far right there is a small vertical white “view more” card, about 65px wide and 154px tall. It implies a deeper product set, but it was not clicked.

### Footer

The module has no footer. It flows directly into category tabs and the broader product feed below.

## Do's and Don'ts

### Do

- Use a red campaign band around the white card.
- Preserve the source headline assets or redraw an equally weighted title.
- Keep countdown digit capsules and red separators.
- Preserve the right-side rail clipping instead of turning the products into a grid.
- Use segmented price typography.
- Use the red-orange pill CTA with the observed shadow.

### Don't

- Do not rebuild the image-backed headline as a plain H1.
- Do not replace the subsidy ribbon with a flat red rectangle.
- Do not expand product titles into multiple full lines.
- Do not click claim, purchase, payment, or order paths for design verification.
- Do not treat the desktop QR app-open prompt as part of this module.

## Responsive Behavior

### Breakpoints

In desktop browser context the mobile page stays centered with a mobile page width. The activity module is based on a 640px mobile activity width, not a desktop-resizing card.

### Touch Targets

The CTA is 68px high and large enough for touch. Product cards are 174px wide and likely act as product entries, but they were not clicked.

### Collapsing Strategy

Rebuilds should preserve the source width model: use `max-width: 640px; width: 100%` and scale down, rather than converting the rail into a desktop grid.

### Image Behavior

Product images use square cover geometry. Headline and subsidy visual layers should use source-backed image assets that fill their boxes.

## Iteration Guide

Start with the red activity band and white card, then build the headline asset row, countdown, product rail, subsidy ribbon, and CTA. Preserve the hard proportions: card-to-band ratio, 174px product cards, 512x68 CTA, rail clipping, and digit capsules.

When extending this to other newcomer offers, change products and prices but keep the structure: headline asset, countdown, horizontal shelf, and primary CTA.

## Known Gaps

- The “grab now” CTA was not clicked because it may claim a subsidy, initiate purchase, or modify account state.
- Product cards were not clicked to avoid entering product detail pages or creating behavior signals.
- The “view more” entry was not clicked to avoid navigation and recommendation-side effects.
- Mouse dragging the product rail did not move it; touch swiping was not verified on a real phone.
- Share and page query parameters were redacted from final documents.
- Product content may change by user, time, and inventory; this teardown records the module's structure and visual system.
