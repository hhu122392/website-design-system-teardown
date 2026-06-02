---
version: alpha
name: bolt-new-design-analysis
language: "zh-CN"
source_url: "https://bolt.new/"
analyzed_at: "2026-06-02"
description: >
  Bolt.new 的公开站点是一套深色 AI 开发工具视觉系统：近黑工作台画布、Inter / Inter Display 字体、冷蓝主行动按钮、低透明白色文字层级、细边框卡片、提示词输入框和产品能力表格一起构成“马上开始构建”的感觉。它适合 AI builder、开发者工具、定价页、企业销售页、模型能力说明页和设计系统导入功能展示。

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
    usage: "首页主标题 What will you build today?"
  enterprise-display:
    fontFamily: "Inter, sans-serif"
    fontSize: "66px"
    fontWeight: 500
    lineHeight: "72.6px"
    letterSpacing: "normal"
    usage: "Enterprise 页首屏标题 Prototype to Production"
  heading:
    fontFamily: "Inter, sans-serif"
    fontSize: "52px"
    fontWeight: 500
    lineHeight: "62.4px"
    letterSpacing: "-1px"
    usage: "企业页和设计系统展示区的大段标题"
  page-title:
    fontFamily: "Inter, sans-serif"
    fontSize: "36px"
    fontWeight: 600
    lineHeight: "40px"
    letterSpacing: "normal"
    usage: "Pricing 页标题"
  body:
    fontFamily: "Inter, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: "24px"
    letterSpacing: "normal"
    usage: "正文、卡片说明、页面基础字体"
  label:
    fontFamily: "Inter, sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: "20px"
    letterSpacing: "normal"
    usage: "导航、按钮、价格卡动作"
  caption:
    fontFamily: "Inter, sans-serif"
    fontSize: "12px"
    fontWeight: 400
    lineHeight: "16px"
    letterSpacing: "normal"
    usage: "Plan 按钮、Figma/GitHub 导入 chip"
  mono:
    fontFamily: "ui-monospace, \"Fira Code\", Menlo, Monaco, Consolas, \"Liberation Mono\", \"Courier New\", monospace"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: "20px"
    letterSpacing: "normal"
    usage: "代码、终端、模型或 token 类信息；来自页面根变量 --bolt-font-monospace"

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
  top-nav: "49px 高的公开站点导航；14px/500 链接；移动端收起为 36px 菜单按钮并保留社交 icon"
  button-primary: "#1488FC 背景、6px 圆角、14px/500；用于 Get started、定价卡主行动"
  button-hero: "#2BA6FF 背景、9999px 胶囊；用于提示框里的 Build now / Send message"
  button-secondary: "透明或深色底、#FFFFFF1A 边框、6px 圆角；用于 Sign in、Learn more、Ask for a quote"
  prompt-composer: "80px 高的 Tiptap/ProseMirror 输入面板，20px 内边距，底部动作区含圆形 add-context、Plan 胶囊和 Build now 胶囊"
  import-chip: "#101010 背景、#FFFFFF1A 边框、9999px 圆角、12px 字体；用于 Figma/GitHub 导入"
  pricing-card: "#1E1E21 背景、#FFFFFF1A 边框、8px 圆角、18px 内边距；移动端单列 343px 宽"
  agent-comparison: "#111114 区块中放模型能力卡、表格和错误减少指标；强调技术可信感"
  enterprise-form: "企业页使用硬边输入和像素化提交按钮；Submit 按钮 #0F6FD0，右侧小 2px 圆角"
  feature-card: "深色无重阴影卡片，用细线、居中标题和产品能力图形表现数据库、安全、鉴权、SEO、托管等能力"
---

## Overview

Bolt.new 公开站点的核心不是“营销海报”，而是“深色产品工作台”。页面用近黑背景、强对比白字、冷蓝行动按钮和提示词输入框，把用户直接带到 AI 构建动作上。首页第一屏就是一个可输入的 builder prompt，后面再展示设计系统导入、模型路由、定价和企业能力。

这套系统最明显的特征有四个：

- 深色画布统一全站，`#1E1E21` 是主要页面底，`#111114` 和 `#000000` 用在更深的产品展示区。
- 主要动作只有一个冷蓝色，公开站点按钮常用 `#1488FC`，提示框发送动作使用更亮的 `#2BA6FF`。
- 字体克制但技术感强，首页标题用 `Inter Display` 大号紧凑排版，企业页标题用 66px/500 的更工程化大标题。
- 组件更像产品 UI，不像普通官网：提示词输入框、导入 chip、模型能力表、价格卡、企业线索表单和 FAQ 都是可复用的产品组件。

这套设计最适合 AI 开发工具、代码生成器、在线 IDE、自动化 builder、设计系统平台和企业 SaaS 的技术型落地页。

## Colors

### Brand & Accent

- `primary` `#1488FC`: 顶部 Get started、价格卡 Get started、设计系统导入按钮。它是站点的主行动色。
- `primary-hover` `#2BA6FF`: 页面根变量 `--bolt-ds-brandHover`，也出现在首页 prompt 的 Build now / Send message 按钮。
- `link` `#1488FC`: 页面根变量 `--bolt-ds-textLink`，适合文内链接、计费切换选中态和次级高亮信息。

### Surface

- `canvas` `#1E1E21`: 首页、Pricing 页 body 背景和价格卡背景。
- `canvas-deep` `#000000`: Enterprise 页外围画布和部分展示区深背景。
- `surface-elevated` `#111114`: 首页模型能力区、企业页 hero 区和深层产品展示区。
- `surface-soft` `#2C2C30`: Plan 胶囊和部分浅一层的工具按钮。
- `surface-chip` `#101010`: Figma / GitHub 导入 chip。

### Text

- `ink` `#FFFEFF`: 主要标题、按钮文字和高优先级文字。
- `body` `#FFFFFFBF`: 导航链接和正文弱一级文本，约 75% 白。
- `muted` `#FFFFFF99`: 说明文字、页脚链接、Plan 按钮等低优先级内容，约 60% 白。

### Hairlines & Borders

- `hairline` `#FFFFFF1A`: 公开站点最常见边框，价格卡、按钮、chip、圆形图标按钮都在用。
- `divider` `#FFFFFF26`: 稍强的分隔线，适合表格分行、模块分隔和深色区块内的边界。
- `border-active` `#2BA6FF`: 页面根变量中出现，用于输入聚焦或选中态。

### Semantic

- `success` `#22C55E`: 根变量中出现，用于成功状态或正向提醒。
- `warning` `#F97316`: 根变量中出现，用于警告或搜索匹配类提示。
- `error` `#EF4444`: 根变量中出现，用于危险/错误状态。

## Typography

### Font Family

公开页面实际计算样式显示，主要字体是 `Inter`，首页主标题使用 `"Inter Display", sans-serif`。代码和终端相关变量使用 `ui-monospace, "Fira Code", Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace`。

### Hierarchy

- Display: 首页主标题 `48px / 48px / 700 / -1.2px`，在桌面和 390px 移动端都保持 48px，但移动端会自动换成两到三行。
- Enterprise display: 企业页首屏 `66px / 72.6px / 500`，更宽、更平，适合强业务主张。
- Heading: 设计系统展示区、企业能力区使用 `52px / 62.4px / 500 / -1px`。
- Page title: Pricing 页使用 `36px / 40px / 600`，比营销标题小，适合工具页。
- Body: 基础正文 `16px / 24px / 400`。
- Label: 导航和按钮多为 `14px / 20px / 500`。
- Caption: 小 chip、Plan、辅助标签多为 `12px / 16px / 400`。

### Principles

标题不依赖花哨字体，而靠紧凑行高、深色背景和强对比建立技术感。正文不要太轻，导航和按钮要保持 500 字重，避免在深色背景上显得发灰。大标题可以有轻微负字距，但正文和按钮不要加负字距。

### Note on Font Substitutes

没有 `Inter Display` 时，用 `Inter`、`ui-sans-serif` 或系统无衬线字体替代。不要换成圆润、装饰性或几何感过强的字体，否则会削弱开发工具的冷静感。

## Layout

### Spacing System

公开站点使用比较清楚的间距阶梯：8-12px 用在导航和 chip，18-20px 用在卡片和输入框内边距，24px 用在组间距，90px 级别用在价格页首屏上边距，109px 左右用在企业页展示大区块。

### Grid & Container

- 导航高度：主页约 49px；Enterprise 页导航约 56px。
- Pricing 页主容器：最大宽度约 1280px，桌面价格卡四列，每张约 296px 宽。
- 移动端价格卡：单列堆叠，卡片约 343px 宽，左右留 16px。
- 首页 hero：居中排版，prompt composer 桌面约 614px 宽，移动端约 339px 宽。
- 企业页：首屏全高 dark hero，后续大区块使用 1120px 左右的展示容器。

### Whitespace Philosophy

它不是非常稀疏的品牌站，也不是高密度后台。首屏留白比较大，用来突出 prompt；定价页和企业页则明显提高信息密度，用细边框卡片、FAQ 列表和能力块承载更多内容。

## Elevation & Depth

### Decorative Depth

Bolt.new 几乎不用厚重阴影。层级主要靠以下方式建立：

- 深浅不同的黑色表面：`#1E1E21`、`#111114`、`#000000`。
- 低透明白色边框：`#FFFFFF1A`。
- 蓝色容器高亮：如 `#2BA6FF1A` 用于 Help Center 类提示。
- 局部发光或渐变背景是辅助，不是主系统。

不要用大投影、玻璃拟态或彩色渐变卡片替代这些细线和深色表面。

## Shapes

### Border Radius Scale

- `0px`: 企业页像素化表单和部分展示组件，强调工程感。
- `4px`: 企业设计系统 slider 容器等更硬的展示区。
- `6px`: 公开导航按钮、主 CTA、计费切换、普通按钮。
- `8px`: Pricing 价格卡。
- `9999px`: prompt 内的 Build now、Plan、导入 chip、圆形 icon 按钮。

### Media Geometry

公开页面更多使用产品 UI mock、卡片、表格和图形组件，而不是大幅摄影。组件矩形比例稳定，价格卡纵向较高，prompt 输入框固定 80px 高，移动端保持可点按高度。

## Components

### Top Navigation

桌面导航是 49px 高的黑色横条，Logo 在左，中间是 14px/500 的链接，右侧是社交 icon、Sign in 和 Get started。链接颜色为 `rgba(255,255,255,.75)`，hover 目标是主白色。移动端导航隐藏主链接，保留 Logo、社交 icon 和 36px 的 Open menu 按钮。

### Buttons

主按钮用 `#1488FC`、6px 圆角、14px/500，适合站点级动作。Prompt 内的发送按钮用 `#2BA6FF` 和胶囊圆角，强调“执行”而不是“跳转”。透明次级按钮用 `#FFFFFF1A` 边框和白色文字，适合 Sign in、Learn more、Ask for a quote。企业页 Submit 按钮是更硬的像素化形态，背景 `#0F6FD0`，右侧约 2px 圆角。

### Cards & Containers

价格卡是最稳定的卡片样式：`#1E1E21` 背景、`#FFFFFF1A` 边框、8px 圆角、18px 内边距，无明显阴影。模型能力区和企业展示区使用更深的 `#111114` 背景，配合表格、指标和 feature tab。卡片文字不要过亮，正文优先用 75% 或 60% 白。

### Inputs & Forms

首页 prompt composer 是核心组件。它是一个 `role="textbox"` 的 Tiptap/ProseMirror 输入面，80px 高、20px 内边距、深色背景，底部动作区包含 add-context 圆形按钮、Plan 胶囊和 Build now / Send message 胶囊。企业页 email input 是硬边输入，52px 高、18px 左右内边距，和像素化 Submit 按钮连在一起。

### Tabs / Chips / Tags

Pricing 页 Monthly / Yearly 是 6px 圆角的分段按钮，选中态用蓝色文字。Figma / GitHub 导入 chip 使用 `#101010` 背景、`#FFFFFF1A` 边框、9999px 圆角、12px 字体。Teams 的 POPULAR 标签是小型状态标签，用来突出推荐卡。

### Signature Components

- Prompt composer: 站点第一视觉入口，必须优先还原。
- Design-system rail: Porsche、Material UI、Chakra、Shadcn、Washington Post 这类品牌/系统卡片横向展示，用于表达“接入现有设计系统”。
- Agent comparison: Bolt Agent、Standard、Max、Pro only、Speed、Intelligence、Token cost 组成产品能力表。
- Pricing cards: Free / Pro / Teams / Enterprise 四列，移动端单列堆叠。
- Enterprise lead form: 深色首屏里的 work email + Submit，偏硬边像素风。
- Feature grid: 数据库、安全、鉴权、SEO、托管等能力卡。

### Footer

Footer 继续使用深色画布。链接使用 14px/400、`#FFFFFF99`，分组为 Resources、Company、Social 等，移动端变成两列链接网格。

## Do's and Don'ts

### Do

- 用深色表面和细边框建立层级，不要依赖大阴影。
- 把主行动限制在冷蓝色，避免多种 CTA 颜色竞争。
- 先搭 prompt composer，再扩展其他页面；这是 Bolt 公开站点最有识别度的组件。
- 在价格页和功能页使用 6px/8px 圆角卡片，保持产品工具感。
- 移动端保持 16px 左右安全边距，卡片单列堆叠。

### Don't

- 不要加入紫色大渐变、玻璃卡片或厚重投影。
- 不要把所有按钮都做成大胶囊；站点 CTA 是 6px，prompt 动作才是胶囊。
- 不要把正文颜色写成纯白，长文本应使用 75% 或 60% 白。
- 不要把设计做成普通 SaaS 落地页；需要保留 prompt、agent、token、design-system import 这些产品特征。
- 不要声称这是 Bolt 官方设计规范；这是基于公开页面的独立分析。

## Responsive Behavior

### Breakpoints

已在 390px 宽移动视口检查首页和 Pricing 页。移动端没有水平溢出：`scrollWidth` 与 viewport 宽度一致。导航收起为 Logo + 社交 icon + Open menu；桌面主导航链接不直接显示。

### Touch Targets

Open menu 为 36px 方形按钮，prompt 中 add-context 为 32px，发送按钮高 36px，价格卡按钮高 40px。移动端价格卡宽约 343px，左右留 16px。

### Collapsing Strategy

首页 hero 仍保留 48px Display 标题，但自动换行。Prompt composer 从桌面约 614px 宽变为约 339px 宽。Pricing 四列价格卡变为单列：Free、Pro、Teams、Enterprise 顺序堆叠。页脚链接在移动端变为两列。

### Image Behavior

公开页面主要是 UI mock 和产品图形，不是摄影图。移动端会裁切或横向滑动部分设计系统 rail，但整体页面不产生横向滚动。

## Iteration Guide

新页面应先建立这些基础：

1. 画布用 `#1E1E21`，需要更深产品展示时用 `#111114` 或 `#000000`。
2. 文本层级用 `#FFFEFF`、`#FFFFFFBF`、`#FFFFFF99` 三档，不要随意加灰色。
3. 主 CTA 用 `#1488FC` + 6px；执行型 prompt 动作用 `#2BA6FF` + 9999px。
4. 优先复用 prompt composer、pricing card、agent comparison、feature card、import chip。
5. 布局使用 1280px 左右主容器，移动端 16px 内边距，复杂网格直接单列。

扩展新功能页时，最稳的方向是“深色产品说明 + 可操作组件 + 能力表格”，不要只做宣传文案。

## Known Gaps

- 登录后的 Builder / workspace / 项目编辑器没有检查；本文件只覆盖公开营销、价格和企业页面。
- Resources 下拉菜单尝试展开时浏览器点击等待超时，未把菜单内容作为已验证证据。
- 没有提交 prompt、邮箱表单、登录、购买、升级或任何会改变账户/站点状态的操作。
- 字体文件列表没有从 `document.fonts` 读到可用条目；字体结论来自页面计算样式。
- 动画、hover 过渡和部分产品 mock 的精确细节没有逐帧拆解。
