<p align="center">
  <img src="assets/bolt-new-preview.gif" alt="Bolt.new design-system preview" width="860">
</p>

<p align="center">
  Turn any website into bilingual DESIGN.md analysis, a browser-checked preview HTML, and reusable case files for Codex agents.
</p>

<p align="center">
  <a href="README.zh-CN.md">中文</a> · <strong>English</strong>
</p>

<p align="center">
  <img alt="DESIGN.md Count" src="https://img.shields.io/badge/DESIGN.md%20count-2-10b981?style=classic">
  <img alt="Preview HTML" src="https://img.shields.io/badge/preview-html-1488FC?style=classic">
  <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-skill-111827?style=classic">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-blue?style=classic">
</p>

# Website Design System Teardown

Copy a website URL into Codex, ask it to use this skill, and get a practical design-system package that another AI agent can read before building UI.

This repository is inspired by the public display style of [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md): concise DESIGN.md entries grouped by product domain, with enough visual and implementation detail to keep generated UI consistent.

## What is DESIGN.md?

[DESIGN.md](https://stitch.withgoogle.com/docs/design-md/overview/) is a plain-text design-system document for AI agents. It describes how a product should look and feel: colors, typography, layout, components, responsive rules, and design guardrails.

It sits next to agent-facing project instructions:

| File | Who reads it | What it defines |
|------|-------------|-----------------|
| `AGENTS.md` | Coding agents | How to build and work in the project |
| `DESIGN.md` | Design and coding agents | How the UI should look, feel, and behave |

This skill creates bilingual DESIGN.md-style files from real websites, then adds a visual preview HTML so the design system can be inspected before reuse.

## Case Study

### Developer Tools & IDEs

- [**Bolt.new**](cases/developer-tools-ides/bolt-new/design-system-analysis/bolt-new-DESIGN.en-US.md) - AI coding and web-app builder. Dark workbench canvas, cool-blue actions, real source-backed icons, prompt composer surfaces, model routing cards, pricing tables, integration cards, and enterprise forms.

Preview:

![Bolt.new preview](assets/bolt-new-preview.gif)

Case files:

| File | Purpose |
|------|---------|
| [`DESIGN.zh-CN.md`](cases/developer-tools-ides/bolt-new/design-system-analysis/bolt-new-DESIGN.zh-CN.md) | Chinese design-system teardown |
| [`DESIGN.en-US.md`](cases/developer-tools-ides/bolt-new/design-system-analysis/bolt-new-DESIGN.en-US.md) | English design-system teardown |
| [`preview.html`](cases/developer-tools-ides/bolt-new/design-system-analysis/bolt-new-preview.html) | Browser-checkable visual catalog |
| [`metadata.md`](cases/developer-tools-ides/bolt-new/metadata.md) | Source URL, category, access state, observed pages, and known gaps |

### Travel & Hospitality

- [**Airbnb**](cases/travel-hospitality/airbnb/design-system-analysis/airbnb-DESIGN.en-US.md) - Public travel marketplace. White canvas, Airbnb Cereal typography, Rausch pink-red actions, source-backed Homes / Experiences / Services navigation icons, pill search, image-first listing cards, host acquisition modules, help-center surfaces, and responsive card behavior.

Preview:

![Airbnb preview](assets/airbnb-preview.gif)

Case files:

| File | Purpose |
|------|---------|
| [`DESIGN.zh-CN.md`](cases/travel-hospitality/airbnb/design-system-analysis/airbnb-DESIGN.zh-CN.md) | Chinese design-system teardown |
| [`DESIGN.en-US.md`](cases/travel-hospitality/airbnb/design-system-analysis/airbnb-DESIGN.en-US.md) | English design-system teardown |
| [`preview.html`](cases/travel-hospitality/airbnb/design-system-analysis/airbnb-preview.html) | Browser-checkable visual catalog |
| [`metadata.md`](cases/travel-hospitality/airbnb/metadata.md) | Source URL, category, access state, observed pages, verification notes, and known gaps |

## What's Inside This Case Format

Every generated case follows the same shape:

| # | Section | What it captures |
|---|---------|------------------|
| 1 | Front matter | Machine-readable source URL, observed pages, tokens, typography, spacing, radius, and component notes |
| 2 | Overview | The site's visual language and where it works best |
| 3 | Colors | Semantic color names, hex values, roles, and usage rules |
| 4 | Typography | Font family, hierarchy, sizes, weights, line heights, and usage |
| 5 | Layout | Containers, grids, section rhythm, density, and alignment |
| 6 | Elevation & Depth | Borders, shadows, overlays, blur, gradients, and surface hierarchy |
| 7 | Shapes | Radius scale, media geometry, icon language, and repeated motifs |
| 8 | Components | Navigation, buttons, cards, forms, tabs, pricing, dashboards, and signature components |
| 9 | Do's and Don'ts | Practical rules for preserving the site's character |
| 10 | Responsive Behavior | Breakpoints, nav collapse, grid behavior, touch targets, and mobile changes |
| 11 | Iteration Guide | How another agent should extend the system |
| 12 | Known Gaps | Pages, states, login surfaces, assets, or interactions not verified |

Each case includes:

| File | Purpose |
|------|---------|
| `design-system-analysis/<site>-DESIGN.zh-CN.md` | Full Chinese version |
| `design-system-analysis/<site>-DESIGN.en-US.md` | Full English version |
| `design-system-analysis/<site>-preview.html` | Self-contained HTML preview with source-backed assets when available |
| `metadata.md` | Case index data and verification limits |

## Preview HTML Standard

The preview is not a decorative add-on. It is the visual proof of the analysis.

Good previews must:

- Use the same tokens and component rules as the Markdown files.
- Render a polished first viewport that feels like the analyzed site.
- Use source-backed logos, favicons, SVG icons, product images, screenshots, partner marks, or UI mock assets when the source exposes them publicly.
- Avoid fake placeholder icons, emoji, single-letter logo tiles, gray boxes, gradient boxes, and invented screenshots.
- Include domain-specific components, not only generic cards and buttons.
- Be checked in a real browser on desktop and mobile widths.

## Install for Codex

Install this repository as a global Codex skill.

PowerShell:

```powershell
$skills = "$env:USERPROFILE\.codex\skills"
New-Item -ItemType Directory -Force $skills | Out-Null
git clone https://github.com/hhu122392/website-design-system-teardown.git "$skills\website-design-system-teardown"
```

macOS / Linux:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/hhu122392/website-design-system-teardown.git ~/.codex/skills/website-design-system-teardown
```

Update later:

```powershell
git -C "$env:USERPROFILE\.codex\skills\website-design-system-teardown" pull
```

## Use with Codex

Open Codex with the Browser plugin available, then ask:

```text
Use $website-design-system-teardown with @browser to analyze https://example.com.
Create Chinese and English DESIGN.md files, create preview HTML, and save the case by category.
```

For Chinese work:

```text
使用 $website-design-system-teardown 和 @浏览器 拆解 https://example.com 的设计系统。
输出中文和英文 DESIGN.md，输出 preview.html，并按分类保存案例。
```

If the target website hides key UI behind login, Codex should ask you to log in through the browser. Do not paste passwords, cookies, tokens, or private account data into chat.

## Repository Structure

```text
website-design-system-teardown/
  SKILL.md
  README.md
  README.zh-CN.md
  agents/
  assets/
  references/
    design-md-breakdown-standard.md
    design-system-output-template.md
    preview-html-standard.md
    login-collaboration.md
  cases/
    CASE_COLLECTION.md
    developer-tools-ides/
      bolt-new/
        metadata.md
        design-system-analysis/
          bolt-new-DESIGN.zh-CN.md
          bolt-new-DESIGN.en-US.md
          bolt-new-preview.html
    travel-hospitality/
      airbnb/
        metadata.md
        design-system-analysis/
          airbnb-DESIGN.zh-CN.md
          airbnb-DESIGN.en-US.md
          airbnb-preview.html
```

## Contributing Cases

Add one website per case folder:

```text
cases/<category>/<site-slug>/
  metadata.md
  design-system-analysis/
    <site-slug>-DESIGN.zh-CN.md
    <site-slug>-DESIGN.en-US.md
    <site-slug>-preview.html
```

Keep evidence honest. Record pages not inspected, login-gated surfaces not accessed, assets that failed to load, and interactions that were not tested.

## License

MIT License. The design-system analyses are independent observations of publicly visible websites. This repository does not claim ownership of any brand identity, trademark, logo, or source-site visual asset.
