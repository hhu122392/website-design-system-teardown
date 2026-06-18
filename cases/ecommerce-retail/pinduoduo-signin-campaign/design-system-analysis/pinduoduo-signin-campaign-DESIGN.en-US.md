---
version: alpha
name: pinduoduo-signin-campaign-design-analysis
language: "en-US"
source_url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
analyzed_at: "2026-06-18"
description: >
  Independent design-system teardown of Pinduoduo's mobile "Sign in for cash" campaign page. The page uses a saturated red campaign canvas, cash green, warm cream prize panels, 3D rolling numbers, artwork-based CTAs, and a dense product feed. It is best suited for sign-in, lottery, cashback, mission, and commerce conversion pages.

observed_pages:
  - label: "Sign-in entry inside the home Other modal"
    url: "https://mobile.yangkeduo.com/index.html"
    access: "public"
  - label: "Sign-in campaign main page"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "Top more popover"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "Activity rules modal"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "Medical category selected state"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized feed"

colors:
  primary: "#fe1842"
  primary-action: "#e02e24"
  primary-gradient-end: "#f62f30"
  cash-green: "#0cab13"
  prize-green: "#12b63b"
  cash-red: "#ea3c32"
  warm-panel: "#ffecd9"
  warm-panel-light: "#fff3e6"
  canvas: "#f4f4f4"
  surface-card: "#ffffff"
  surface-chip: "#ffe0e6"
  ink: "#151516"
  body: "#666666"
  muted: "#9c9c9c"
  hairline: "#eeeeee"
  on-primary: "#ffffff"
  warning: "#ff633d"
  overlay: "rgba(0,0,0,.72)"

typography:
  display:
    fontFamily: "PDDSansStd06-Regular, PingFang SC, system-ui, sans-serif"
    fontSize: "41.6px"
    fontWeight: 400
    lineHeight: "41.6px"
    letterSpacing: "normal"
    usage: "Large cash-account rolling number"
  heading:
    fontFamily: "PingFangSC-Medium, PingFang SC, sans-serif"
    fontSize: "18.72px"
    fontWeight: 500
    lineHeight: "22.88px"
    letterSpacing: "normal"
    usage: "Top navigation title"
  body:
    fontFamily: "PingFang SC, system-ui, sans-serif"
    fontSize: "13.52px"
    fontWeight: 400
    lineHeight: "17.68px"
    letterSpacing: "normal"
    usage: "Tags, product metadata, account label"
  label:
    fontFamily: "PingFang SC, system-ui, sans-serif"
    fontSize: "14.56px"
    fontWeight: 400
    lineHeight: "14.56px"
    letterSpacing: "normal"
    usage: "Product buttons and popover rows"

rounded:
  none: "0px"
  xs: "2.08px"
  sm: "4.16px"
  md: "8.32px"
  lg: "10.4px"
  xl: "16.64px"
  pill: "999px"

spacing:
  xxs: "4.16px"
  xs: "8.32px"
  sm: "10.4px"
  md: "15.6px"
  lg: "20.8px"
  xl: "31.2px"
  section: "42px"

components:
  entry-modal-grid: "Three-column icon grid in the home Other modal; the sign-in entry uses a yellow calendar icon and red label."
  top-nav: "Fixed mobile red navigation with title, search box, and more menu; after scrolling, the title area becomes the balance roller."
  cash-account-card: "White large account card layered over red, with a pink account chip, red money number, green WeChat mark, and outlined pill action."
  prize-machine: "Warm cream frame, orange-red inner glow, 3x2 reward grid, artwork CTA, and APNG hand cue."
  mission-gallery: "White four-item task strip using campaign assets and red 13.52px labels."
  category-tabs: "Horizontal category tabs; selected item is #e02e24 and 700 weight."
  product-card: "Two-column product cards with 193px images, two-line title, gray service tags, red price, and full-width red CTA."
  more-popover: "White top-right popover with Rules, Payout details, and Sound toggle."
  rules-modal: "Dark overlay with centered white rounded rule card and floating close control."
---

## Overview

This is a high-pressure Pinduoduo campaign page. The first viewport sells the promise of cash through an account card and a draw-to-withdraw prize machine, then keeps the user moving through task entries and a product feed. It is not a light brand page; it is an operations-heavy activity canvas where almost every visible block looks claimable, drawable, or tappable.

The visual system is driven by four parts: a red campaign background, green cash signals, warm cream prize panels, and artwork-based CTAs. The cash amount is not plain text; it is a multi-column number roller. When the page scrolls, the top navigation sticks and carries the balance/search pattern forward. The lower page becomes a two-column product feed, where every product card repeats a red "group order to draw cash" action.

## Colors

### Brand & Accent

- `primary` `#fe1842`: First-screen red campaign field, used for urgency.
- `primary-action` `#e02e24`: Category selected state, product action button, and price treatment.
- `cash-green` `#0cab13`: WeChat cash, withdrawal, and positive reward cues.
- `cash-red` `#ea3c32`: Large account amount and "get more cash" action.
- `warning` `#ff633d`: Prize pool update and remaining-quantity chips.

### Surface

- `canvas` `#f4f4f4`: Product feed background, separating white cards.
- `surface-card` `#ffffff`: Account card, task cards, product cards, and popover.
- `warm-panel` `#ffecd9`: Main prize-machine container.
- `warm-panel-light` `#fff3e6`: Reward-card highlight and inner prize surface.
- `surface-chip` `#ffe0e6`: "My cash account" label background.

### Text

- `ink` `#151516`: Default category and popover text.
- `body` `#666666`: Product metadata, standard copy, and container defaults.
- `muted` `#9c9c9c`: Search placeholder and product service labels.
- `on-primary` `#ffffff`: Red buttons, campaign title, and warning-chip text.

### Hairlines & Borders

- `hairline` `#eeeeee`: Light menu separators and product-card separation.
- Reward-cell edges mostly come from source image assets and green artwork borders, not plain CSS borders.

### Semantic

- `cash-green` means withdrawable, WeChat payout, or task earning.
- `primary-action` means act now, buy, or group order for a cash draw.
- `warning` means updated pool, remaining quantity, or limited availability.

## Typography

### Font Family

The page primarily uses `PingFang SC`, `STHeiti STXihei`, `Microsoft YaHei`, and Chinese system fallbacks. Money numerals use `PDDSansStd06-Regular`, which is important for the tall, narrow campaign number style. Without this font, the cash display will feel less like the source page.

### Hierarchy

- Display: Cash amount uses 41.6px, 400 weight, 41.6px line-height, and `#ea3c32`; each digit is a separate roller.
- Heading: Top title uses 18.72px, 500 weight, white.
- Body: Product metadata, chips, and helper labels mostly sit between 12.48px and 13.52px.
- Label: Product CTA uses 14.56px white text in a 29px-tall button; main CTA text uses 20.8px and 900 weight.

### Principles

The page is built for immediate comprehension, not spacious reading. Rewards and money are large, product titles are compressed into two lines, and action text is short. Category selected state relies only on color and weight.

### Note on Font Substitutes

The preview uses system fonts and `Arial Black` to approximate the number display. A real implementation should use `PDDSansStd06-Regular` or a similar tall numeric font for the money roller.

## Layout

### Spacing System

The page renders as a 375px mobile artboard. In a 390px viewport, the document width was 375px. The top nav starts at 77px high; the cash account card begins around y=79; the prize panel starts at y=154; the four-task strip starts at y=520; categories and product feed start after y=619.

### Grid & Container

The first screen is a vertical stack: red background, account card, prize card, task entries. The prize area uses a 3x2 grid, with reward cells around 89x82px. The task strip uses four columns, each about 75x72px. The product feed uses two columns, with cards around 193x303px and 193x193px images.

### Whitespace Philosophy

Whitespace is intentionally tight. Hierarchy comes from surface color, artwork borders, rounded corners, and buttons rather than large empty areas. The page gives space to rewards and products, not long explanation.

## Elevation & Depth

### Decorative Depth

Depth comes from artwork and gradients rather than heavy CSS shadows. The white account card sits over the red background; the prize module uses a cream outer frame, orange-red inner glow, and image-backed reward cells. The rules modal uses a dark overlay around `rgba(0,0,0,.72)`.

## Shapes

### Border Radius Scale

The radius language is small: product cards around 2.08px, product CTAs around 4.16px, task cards around 8.32px, account/task blocks around 10.4px, and prize panel top corners around 16.64px. Do not turn this into a large-rounded-card system.

### Media Geometry

Product media is square and strongly cropped. Task icons use source campaign assets with `contain` or `100% 100%` sizing. The main CTA is an artwork button, not a pure CSS pill.

## Components

### Top Navigation

The top nav is a red mobile bar. Initial state: back arrow, "Sign in for cash" title, white search box, and circular more control. After scrolling, the nav becomes fixed with z-index around 9998/10000, and the title area becomes a compact balance roller while search remains a 203x31px white box.

### Entry Modal From Home

The home "Other" modal is a three-column entry grid. The sign-in entry appears in the third row, first column, using a yellow calendar icon and a red label. It belongs to the global entry system, not the activity page itself.

### Cash Account Card

The account card is a white rounded card around 325px wide. It has a pink "My cash account" label with `12.48px 0 8.32px` corner treatment. The amount uses a red 3D number roller with `transform` transitions at `0.5s`. The "get more cash" action is a small outlined pill with 13.52px, 500-weight red text.

### Prize Machine

The prize module is 390px wide and about 356px tall, with `#ffecd9` background and 16.64px top radius. Its title strip uses `activityDespTitleBg.png`; stars and the WeChat icon are also source assets. The inner frame uses `mainPartMachineBg.png`; reward cells use `lottery_reward_item.png`; coupon cells use `platform_coupon.png`. Reward cards cover cash, coupon, and surprise reward types.

### Buttons

The main "draw withdrawal now" CTA uses the image background `activityMainBtn.png`, around 239x67px. The text layer is separate, with 20.8px, 900-weight white text; an APNG hand cue sits at the right. Product CTAs are pure red rectangles, around 177x29px, radius 4.16px, with split text and a small WeChat mark.

### Mission Gallery

The four observed entries are cashback, daily money, lucky cat, and exchange zone. Each item is around 75x72px, with a 71x44px icon area and a red `#ff1818` label at 13.52px and 500 weight. Icons come from `a7fca165...png`, `daily_money.png`, `ManekiNekoCat.png`, and `ExchangeZone.png`.

### Tabs / Chips / Tags

The horizontal category menu includes All, Medicine, Food, Phone, Fruit, Department Store, Menswear, Sports, Shoes/Bags, Computer, Appliances, Furniture, Home Textile, Beauty, Womenswear, Home Improvement, Underwear, Auto, Accessories, and Mother/Baby. Default text is `#151516`, 15.6px, 400; selected state is `#e02e24`, 15.6px, 700. Tapping Medicine changed the feed content.

### Product Cards

The product feed uses two white-card columns. Cards are around 193x303px with 2.08px radius; images are 193x193px. Titles are two-line dense text; service tags are gray 12.48px; price is `#e02e24`, 13.52px, 700; sales text is black 12.48px. Every card repeats the red campaign CTA at the bottom.

### More Popover

The top-right popover is a white 92x119px panel with 4.16px radius. It includes Rules, Payout details, and Sound. Rows are 40px high, text is 14.56px and `#151516`. The sound switch shows a green enabled state; it was tested off and restored on.

### Rules Modal

The Rules entry opens a dark overlay and centered white instruction card. The card is around 302px wide, with an 18px-ish title, 16px-ish body text, and a floating close button outside the card edge. The content area can scroll.

### Dynamic Interaction Effects

- Number roller: each money digit uses `matrix3d` transforms and a 0.5s transform transition.
- Category switch: the selected tab turns red and bold, and the product list refreshes.
- Sticky nav: scrolling makes the nav fixed and moves the balance roller into the top bar.
- Go to top: the bottom-right button appears through bottom/opacity transitions and returns scrollY to 0.
- Loading: bottom loading icon uses a 1s linear spin.
- Main CTA: the artwork button has a separate APNG hand gesture layer.
- Sound toggle: the more-menu switch changes state and was restored to enabled after testing.

### All Observed Function Entries

- Sign-in entry inside the home Other modal: clicked and opened.
- Top back control: not clicked to avoid leaving the inspection state.
- Top search: observed, not typed into.
- Top more control: opened; contains Rules, Payout details, and Sound.
- Rules: opened and closed.
- Payout details: not opened because it may expose account detail.
- Sound: toggled off and restored on.
- Get more cash: not clicked; likely enters more cash tasks.
- Six prize cells: observed as reward/result expectation surfaces, not individually clicked.
- Draw withdrawal now: not clicked because it may consume draw chances.
- Cashback, daily money, lucky cat, exchange zone: not clicked because they may enter account/task states.
- Category tabs: Medicine switch tested.
- Product cards and campaign product CTAs: not clicked because they may enter purchase flow.
- Go to top: clicked and verified.

## Do's and Don'ts

### Do

- Preserve the 375px mobile campaign artboard logic instead of turning the first screen into a desktop landing page.
- Use red-green contrast for money, rewards, and action clarity.
- Keep artwork CTAs as layered background, label, and gesture elements.
- Keep product cards dense, two-column, square-image, and red-CTA heavy.
- Use dark overlay plus a white card for rules and explanation modals.

### Don't

- Do not replace the red campaign canvas with unrelated purple/blue gradients or generic illustrations.
- Do not convert reward cells into plain white cards; the original relies on artwork borders and saturated green.
- Do not weaken "group order to draw cash" into a text link; it is the main product-feed action.
- Do not include full share parameters, exact account balance, or private payout data in deliverables.

## Responsive Behavior

### Breakpoints

At a 390px viewport, the document width was 375px and document height ranged from about 3771px to 6839px depending on product-feed loading. The page is mobile-first and centers on wider screens instead of becoming a desktop layout.

### Touch Targets

The search box is 203x31px, the visual more icon is around 20x20px, task entries are 75x72px, product CTAs are 177x29px, and the go-top control is 44x44px. Some visual controls are small, but larger containers carry the touch target.

### Collapsing Strategy

No desktop breakpoint was observed. The activity canvas keeps its 375px logic, and wide screens do not expand it. Product feed remains two columns; category tabs scroll horizontally.

### Image Behavior

Campaign assets use `100% 100%` or `contain`. Product imagery is square-cropped. Product feed lazy-loads, and the document height grows as more items load.

## Iteration Guide

Start with the 375px mobile activity shell, then build the fixed nav, cash account card, prize machine, mission strip, and product feed. The money display should be a separate number roller component. The main CTA should follow the source layer split: background artwork, label layer, gesture layer. New entries should be added to the mission strip or product card system instead of introducing unrelated large-card styles.

## Known Gaps

- The "draw withdrawal now" action was not clicked because it may consume draw chances.
- Payout details were not opened because they may expose personal account information.
- "Get more cash", cashback, daily money, lucky cat, exchange zone, and product purchase entries were not clicked because they may change account or commerce state.
- Product feed content is personalized and can change by account, time, category, and scroll depth.
- Account balance and full share/query parameters are redacted and not treated as design-system content.
- The exact font file was not downloaded; `PDDSansStd06-Regular` was recorded from computed styles only.
