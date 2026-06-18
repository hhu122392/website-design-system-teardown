# Final Audit Standard

Use this standard before saying a website design-system teardown is ready. The audit is a hard gate, not a short self-review. It must prove that the source evidence, DESIGN files, and preview HTML agree with each other.

Create this file for every teardown:

- `design-system-analysis/<site-slug>-AUDIT.md`

Save supporting evidence under `evidence/` and browser screenshots under `screenshots/` when screenshot capture works.

## 1. Audit Scope

Record exactly what was inspected and what was not.

```text
source surfaces inspected:
- <url or page name> - <role>

source surfaces not inspected:
- <surface> - <reason>

preview target:
- <preview file or local URL>

viewports checked:
- desktop: <width>x<height>
- mobile or narrow: <width>x<height>

comparison mode:
- design-system fidelity, not pixel-perfect clone
```

Rules:

- If an important page, state, modal, flow, or logged-in surface was not inspected, list it in Known Gaps.
- Do not imply full coverage when only one surface was checked.
- Do not use private account data as design-system evidence.

## 2. Coverage Audit

Mark each relevant area as `pass`, `missing`, or `not applicable`:

- navigation and page chrome
- first viewport, hero, header, or primary content area
- typography hierarchy
- color and surface system
- spacing and layout grid
- buttons and CTAs
- cards and repeated items
- forms and inputs
- tabs, filters, chips, or segmented controls
- menus, popovers, drawers, modals, or overlays
- empty, loading, error, disabled, selected, and active states when visible or safely reachable
- responsive behavior
- source-backed images, icons, logos, illustrations, or media
- domain-specific components that make the product or site recognizable

Generic swatches, type samples, and simple buttons are not enough.

## 3. Evidence Audit

Every important claim in the DESIGN files must have evidence.

```text
item: <token or component>
claim: <what the document says>
evidence: <screenshot path or evidence JSON path>
status: pass | P0 | P1 | P2
notes: <gap or confirmation>
```

P1 failures:

- token listed but not observed
- component described but not represented in preview
- source asset role is wrong
- inferred rule written as fact
- English file drops important details from Chinese file

## 4. Preview Audit

Open the preview in a real browser and verify:

- page is nonblank
- no horizontal overflow on desktop and mobile
- images, icons, and media load successfully
- anchor nav active state matches URL and click state
- mobile layout does not crush source-sized components
- repeated components use consistent rules
- compact text does not overflow its box
- the preview shows real product logic, not only documentation blocks
- source-backed assets are used in the same role as the source
- no invented phone frame, browser chrome, fake logo tile, placeholder icon, or unrelated image is used as a substitute

For text-bearing compact UI, check DOM metrics:

```text
selector: <selector>
clientWidth: <number>
scrollWidth: <number>
clientHeight: <number>
scrollHeight: <number>
fontSize: <value>
lineHeight: <value>
status: pass | P0 | P1 | P2
```

Gate:

- `scrollWidth > clientWidth` is P1 unless the source intentionally scrolls or clips.
- unreadable text is P1.
- broken mobile layout is P0 or P1 depending on severity.

## 5. Component-Level Audit

For each signature component family, audit repeated instances, not only one sample.

```text
component family: <name>
instances checked: <count>
source evidence: <path>
preview evidence: <path>
checks:
- size and placement
- internal spacing
- text hierarchy
- icon or image role
- border, radius, and shadow
- selected, disabled, active, or hover state when relevant
- responsive behavior
status: pass | P0 | P1 | P2
```

Signature components include whatever matters for the inspected site, such as primary actions, repeated cards, pricing/product/content/list items, badges, status labels, navigation items, form controls, overlays, floating controls, charts, counters, meters, media blocks, or other product-specific UI.

## 6. Interaction Audit

Audit only interactions that are safely reachable or explicitly authorized.

Generic interaction categories:

- navigation state
- tab, filter, or segmented-control switching
- menu or popover open and close
- modal, drawer, or bottom sheet open and close
- toggle or setting state
- hover, focus, or active state when relevant
- scroll, sticky, fixed, or go-to-position behavior
- loading or transition state
- animation or attention cue
- form validation or disabled state when safe to test

Record each interaction like this:

```text
interaction: <generic name>
source action: <what was done or observed>
source result: <measured state>
preview result: <verified state>
side effect risk: none | avoided | user-authorized
status: pass | P0 | P1 | P2
```

Rules:

- Do not click purchase, payment, order, destructive, permission, sharing, message-sending, or account-changing actions unless the user clearly authorized that exact action.
- Avoided interactions must be listed in Known Gaps.
- Do not claim an interaction was verified if it was only visually described.

## 7. Privacy And Safety Audit

Scan final documents, preview, screenshots, and evidence for:

- URL tokens and share IDs
- session, login, or API tokens
- account balances
- private names, addresses, phone numbers, emails
- private search terms
- order, payment, medical, financial, or account-specific text
- real-user ticker text not needed for design analysis
- raw API responses
- placeholders
- mojibake
- fake asset classes or one-letter logo tiles

Required result:

```text
privacy scan: pass | fixed | blocked
redactions made:
- <item>
remaining risk:
- <item or none>
```

## 8. Severity Rules

- P0: output is unsafe, blank, misleading, or unusable. Examples: missing required files, no browser verification, private data leak, fake assets presented as source assets, broken main layout, or missing core surface.
- P1: output is usable but materially wrong. Examples: unreadable text, compact text overflow, wrong source asset role, major layout mismatch, repeated component inconsistency, unsupported claim, or missing important state.
- P2: minor polish issue. Examples: tiny spacing drift, minor color drift, or small non-critical text wrap difference.

Final gate:

- No known P0 may remain.
- No known P1 may remain unless blocked and clearly reported.
- P2 may remain, but must be listed.

## 9. Repair Loop

After every visual, layout, interaction, or privacy fix:

1. rerun the failed check
2. save new evidence
3. update `<site-slug>-AUDIT.md`
4. do not reuse old screenshots as proof
5. do not claim completion until the latest evidence passes

## 10. Final Audit Summary

End the audit file with:

```text
final status: pass | blocked

passed gates:
- scope
- coverage
- evidence
- preview
- component-level checks
- interaction checks
- privacy scan

remaining P2:
- <item or none>

blocked P0/P1:
- <item or none>

checks run:
- <browser check, command, or evidence file>

files reviewed:
- <DESIGN zh-CN>
- <DESIGN en-US>
- <preview HTML>
- <evidence files>
```
