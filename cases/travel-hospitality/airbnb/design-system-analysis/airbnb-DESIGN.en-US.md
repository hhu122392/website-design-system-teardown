---
version: alpha
name: airbnb-design-analysis
language: "en-US"
source_url: "https://zh.airbnb.com/"
analyzed_at: "2026-06-02"
description: >
  Airbnb's public Chinese site is a travel-commerce design system built around a white canvas, Airbnb Cereal VF typography, Rausch pink-red brand action, oversized rounded search shells, image-first listing cards, and light hairline structure. It compresses lodging, experiences, services, help content, and host acquisition into scannable cards, pill searches, horizontal carousels, and a clear footer information architecture. The system fits travel marketplaces, local-service marketplaces, lifestyle commerce, booking flows, help centers, and host or seller acquisition pages.
observed_pages:
  - label: "Home / Homes"
    url: "https://zh.airbnb.com/"
    access: "public"
  - label: "Experiences"
    url: "https://zh.airbnb.com/experiences"
    access: "public"
  - label: "Services"
    url: "https://zh.airbnb.com/services"
    access: "public"
  - label: "Host homes"
    url: "https://zh.airbnb.com/host/homes"
    access: "public"
  - label: "Help"
    url: "https://zh.airbnb.com/help"
    access: "public"
  - label: "Room detail"
    url: "https://zh.airbnb.com/rooms/1446929417046820432"
    access: "public"

colors:
  primary: "#FF385C"
  primary-deep: "#E61E4D"
  primary-gradient-end: "#D70466"
  ink: "#222222"
  body: "#222222"
  muted: "#6A6A6A"
  subtle: "#717171"
  canvas: "#FFFFFF"
  surface-soft: "#F7F7F7"
  surface-chip: "#F2F2F2"
  border: "#DDDDDD"
  border-soft: "#EBEBEB"
  inverse: "#FFFFFF"
  success: "#008A05"
  star: "#222222"

typography:
  display:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "60px"
    fontWeight: 700
    lineHeight: "64px"
    letterSpacing: "normal"
    usage: "Large host-acquisition page headings; a 120px computed value appeared in a constrained reading, but the practical system uses large wrapped display headings"
  page-title:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "32px"
    fontWeight: 500
    lineHeight: "36px"
    letterSpacing: "normal"
    usage: "Experience page primary headings"
  listing-title:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "26px"
    fontWeight: 500
    lineHeight: "30px"
    letterSpacing: "normal"
    usage: "Public room detail heading"
  section-heading:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "22px"
    fontWeight: 500
    lineHeight: "26px"
    letterSpacing: "normal"
    usage: "Service page and regional section headings"
  body:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: "20.02px"
    letterSpacing: "normal"
    usage: "Global body text, listing metadata, footer links"
  label:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: "18px"
    letterSpacing: "normal"
    usage: "Search labels, button labels, and emphasized metadata"

rounded:
  none: "0px"
  sm: "4px"
  md: "12px"
  lg: "16px"
  xl: "24px"
  search-pill: "100px"
  circle: "50%"
  pill: "999px"

spacing:
  xs: "8px"
  sm: "12px"
  md: "16px"
  lg: "24px"
  xl: "32px"
  section: "48px"
  page-x: "32px desktop, 24px tablet, 16px mobile"

components:
  logo: "Rausch pink-red Airbnb mark on the left; public pages expose SVG brand marks"
  top-nav: "White top navigation with center Homes / Experiences / Services visual tabs and right-side host, locale, and circular menu controls"
  search-shell: "Large centered pill search split into Where / When / Who, with a circular pink-red search action"
  listing-card: "Around 190x181 image crop, wishlist control, Guest favorite pill, price, location, and rating metadata"
  experience-card: "Same image-card frame as listings, adapted to experience labels, hosts, titles, and local activity metadata"
  host-hero: "Minimal white marketing page with large display headings, small Rausch CTA, value sections, protection table, and FAQ"
  help-search: "Help center search uses a #F7F7F7 pill field with #DDDDDD border"
---

## Overview

Airbnb's public Chinese site is a "look first, act lightly" travel-commerce system. The core language is not decoration. It is a white canvas, clear black text, pink-red action points, circular and pill controls, scannable image cards, and a large footer information architecture.

The system fits browsing, comparing, saving, and booking. Users first read images, then check property type, location, price, rating, and Guest favorite status. Interaction density is high, but the surface stays light: little shadow, soft hairlines, large radii, and visual weight carried mostly by photography.

This teardown follows the user's instruction to avoid login. It covers public pages only. Logged-in wishlist, trips, messages, account, full booking, and host-dashboard surfaces were not inspected.

## Colors

### Brand & Accent

- `primary` `#FF385C`: Airbnb's core pink-red, visible in the mark and search action.
- `primary-deep` `#E61E4D`: A deeper pink-red used in strong action surfaces such as login/search actions.
- `primary-gradient-end` `#D70466`: The gradient endpoint for wider primary actions that need stronger brand emphasis.

### Surface

- `canvas` `#FFFFFF`: Primary page canvas, listing surfaces, and most transaction UI.
- `surface-soft` `#F7F7F7`: Footer, help-center search, and quiet section backgrounds.
- `surface-chip` `#F2F2F2`: Locale buttons, menu buttons, and light chip controls.

### Text

- `ink` `#222222`: Primary headings, body text, price, ratings, and most interface labels.
- `muted` `#6A6A6A`: Secondary descriptions, location subtitles, and helper metadata.
- `subtle` `#717171`: Low-priority metadata and footer links.
- `inverse` `#FFFFFF`: Text on pink-red or dark action surfaces.

### Hairlines & Borders

- `border` `#DDDDDD`: Help-center search border, inputs, and primary dividers.
- `border-soft` `#EBEBEB`: Section dividers, footer separators, and subtle card separation.

### Semantic

- `success` `#008A05`: Green check semantics in host protection lists.
- `star` `#222222`: Rating stars remain small black marks, not a yellow review system.

## Typography

### Font Family

Computed public-page styles show this stack:

`"Airbnb Cereal VF", Circular, -apple-system, BlinkMacSystemFont, Roboto, "Helvetica Neue", sans-serif`

The family is central to the feel. It is rounder than a plain system stack but still highly legible across prices, locations, ratings, and short card text.

### Hierarchy

- Display: `60px / 64px / 700`, used by host-acquisition page headings.
- Page title: `32px / 36px / 500`, used by experience page primary headings.
- Listing title: `26px / 30px / 500`, used by public room-detail headings.
- Section heading: `22px / 26px / 500`, used by area and service sections.
- Body: `14px / 20.02px / 400`, used by card metadata, footer, and explanatory copy.
- Label: `14px / 18px / 500`, used by search labels, input labels, and important short metadata.

### Principles

Airbnb does not rely on dramatic tracking or decorative type. It relies on compact hierarchy and clear weight roles: rounded, strong headings; small dense card text; and price/rating metadata that stays restrained.

### Note on Font Substitutes

If Airbnb Cereal VF is unavailable, use `Circular`, then `-apple-system`, `BlinkMacSystemFont`, `Roboto`, and `Helvetica Neue`. Avoid overly geometric tech fonts.

## Layout

### Spacing System

The public home page uses roughly `32px` desktop page gutters, with about `12-16px` between horizontally scrolling cards. Host pages use larger vertical gaps; help pages use a narrower centered content rhythm.

### Grid & Container

- Home / experiences: horizontal card groups, with observed cards around `190px` wide and `181px` tall image crops.
- Help center: centered content, pill search, and article/card lists.
- Host homes: centered display headings followed by vertical modules for value, protection, FAQ, and app mockups.

### Whitespace Philosophy

Airbnb uses whitespace as a pre-transaction buffer. The UI should feel browsable rather than like an operations table. The search shell is large, cards breathe, and dense footer content is contained in a soft gray band.

## Elevation & Depth

### Decorative Depth

The site uses very little shadow. Hierarchy comes from photography, radius, soft gray bands, hairlines, and overlays.

- Search and menu modals can use floating depth.
- Listing cards do not need heavy card chrome.
- Help search uses `#F7F7F7` plus a `#DDDDDD` border.
- Footer uses a full-width soft background as a closing band.

## Shapes

### Border Radius Scale

- Circle: search action, locale button, menu button, carousel arrows.
- Pill: help search, top search shell, Guest favorite labels, and primary CTAs.
- Image card: public screenshots show visually rounded listing media; use `12px-16px` for stable reproduction.
- Host CTAs can use either small radius or pill style depending on the section context.

### Media Geometry

Listing and experience cards use a near-square but slightly wide crop around `190x181`. Help-center media uses more regular square or rectangular cards.

## Components

### Top Navigation

The top nav uses the Airbnb mark on the left, Homes / Experiences / Services visual tabs in the center, and host, locale, and circular menu controls on the right. Experiences and Services carry "new" badges.

Keep the white background, the visual tab group, and the circular tool buttons. Do not reduce it to a generic SaaS navbar.

### Search Shell

The home search shell is the core component. It is centered under the nav, split into Where / When / Who segments, and ends with a circular pink-red search action. The fields are not standard bordered inputs; they are information segments inside a large pill-like shell.

The help center uses search differently: a `#F7F7F7` pill field, `#DDDDDD` border, and about a `400px` desktop width.

### Listing Cards

Listing cards combine image, wishlist action, Guest favorite pill, property type / location, price, and rating. They do not need outer borders or shadows. The image carries the card's main visual weight.

### Experience Cards

Experience cards reuse the listing-card frame but shift the content to activity names, host labels, and local experience metadata. This shows that Airbnb's card system spans lodging, experiences, and services.

### Host Marketing Sections

The host page is more marketing-led. It uses large `60px / 64px / 700` headings, wider vertical spacing, value points, AirCover protection lists, FAQs, and app mockups. It should not be turned into a dashboard.

### Help Center

The help center turns complex support content into search, user-role tabs, popular articles, illustration cards, and footer links. It uses the same font, borders, and soft surface language as the marketplace pages, but with a more content-first rhythm.

### Footer

The footer is a large information architecture block: `#F7F7F7` background, multiple link columns, locale/currency, copyright, and social actions. It is dense but quiet because color and type stay restrained.

## Do's and Don'ts

### Do

- Use a white canvas with `#222222` text.
- Reserve pink-red for brand, search, and primary actions.
- Put real photography first; keep card text to necessary metadata.
- Use pill and circular controls for search and tools.
- Use `#F7F7F7` to contain footer, help search, and secondary bands.
- Preserve consistency across homes, experiences, and services.

### Don't

- Do not add heavy shadows or thick borders to listing cards.
- Do not turn ratings into a yellow review system; observed stars are small and black.
- Do not replace Airbnb's pink-red with blue-purple tech gradients.
- Do not convert the top nav into a generic corporate header.
- Do not design the host page like an admin dashboard.

## Responsive Behavior

### Breakpoints

Full breakpoint inspection was not completed, but the observed system depends on horizontal card groups and mobile-friendly controls. Desktop uses a centered search shell and horizontal card rows. Mobile should keep the large search entry and either one-column or horizontal-scrolling cards.

### Touch Targets

Circular tool buttons are around `40px`; the search action is around `48px`. Do not shrink mobile actions below `40px`.

### Collapsing Strategy

The top tab group can compress into fewer visible labels or icon entries. Card groups should remain swipeable. Help-center article lists collapse to one column. Footer link groups stack vertically.

### Image Behavior

Images must crop into stable ratios with `object-fit: cover`. Do not let varied source image ratios distort card height.

## Iteration Guide

Start new UI with four components: top navigation, pill search, image card, and soft footer. Then extend by page type:

- Travel browse page: horizontal card rows, Guest favorite labels, wishlist, price and rating metadata.
- Detail page: image/title structure, price or booking module, and grouped content.
- Help page: pill search, role tabs, and article cards.
- Host acquisition page: display heading, value points, protection table, and FAQ.

Preserve light surfaces, real imagery, pink-red action points, and clear type hierarchy.

## Known Gaps

- The user explicitly asked not to log in; logged-in wishlist, trips, messages, account menu, full profile, and host dashboard were not inspected.
- No search, booking, wishlist, payment, login, or state-changing action was submitted.
- Only one public room-detail sample was opened, and it loaded limited content in the current environment; full gallery, booking card, reviews, and map are not treated as verified.
- The Services page did not expose many service cards in the current public access state; only the service search shell and footer structure were observed.
- The in-app Browser screenshot command timed out on the current tab at one point; final evidence relies on DOM snapshots, computed styles, public image URLs, and auxiliary Playwright screenshots.
- Airbnb Cereal VF font files were not downloaded or redistributed; the document records the computed font stack only.
