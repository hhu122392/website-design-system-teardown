---
version: alpha
name: airbnb-design-analysis
language: "zh-CN"
source_url: "https://zh.airbnb.com/"
analyzed_at: "2026-06-02"
description: >
  Airbnb 中文公开站点是一套以白色画布、Airbnb Cereal VF 字体、Rausch 红粉品牌色、超大圆角搜索壳、图片优先的房源卡片和轻量边线为核心的旅行交易设计系统。它把复杂的住宿、体验、服务、帮助和房东招募流程压缩成可扫描的卡片、胶囊搜索、横向轮播和清晰 footer 信息架构，适合旅行平台、本地服务市场、生活方式电商、预订流程、内容型帮助中心和房东/卖家招募页。
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
    usage: "房东页大段标题；公开检查到移动/窄容器时可出现更大 120px 计算值，但实际首屏以可折行大标题为主"
  page-title:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "32px"
    fontWeight: 500
    lineHeight: "36px"
    letterSpacing: "normal"
    usage: "体验页主标题"
  listing-title:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "26px"
    fontWeight: 500
    lineHeight: "30px"
    letterSpacing: "normal"
    usage: "公开房源详情页标题"
  section-heading:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "22px"
    fontWeight: 500
    lineHeight: "26px"
    letterSpacing: "normal"
    usage: "服务页和区域标题"
  body:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: "20.02px"
    letterSpacing: "normal"
    usage: "全站正文、房源卡元信息、页脚链接"
  label:
    fontFamily: "\"Airbnb Cereal VF\", Circular, -apple-system, BlinkMacSystemFont, Roboto, \"Helvetica Neue\", sans-serif"
    fontSize: "14px"
    fontWeight: 500
    lineHeight: "18px"
    letterSpacing: "normal"
    usage: "搜索输入标签、按钮标签和强调元信息"

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
  logo: "左上角使用 Rausch 红粉 Airbnb 标志；公开页面中 SVG 直接作为品牌识别"
  top-nav: "白底顶部导航，中心为房源/体验/服务图文 tab，右侧是成为房东、语言/币种和圆形菜单"
  search-shell: "大号居中胶囊搜索条，按地点/时间/人数分段，右侧圆形红粉搜索按钮"
  listing-card: "图片 190x181 左右、圆角裁切、心愿单按钮、房客推荐胶囊、价格和评分元信息"
  experience-card: "与房源卡相同的图片卡骨架，但用限定/达人/体验标签和更内容化的标题"
  host-hero: "白色极简大标题 + 小型 Rausch CTA + 收入估算/保障/FAQ 分段"
  help-search: "帮助中心使用 F7F7F7 胶囊搜索框，边线为 #DDDDDD"
---

## Overview

Airbnb 的公开中文站点把旅行交易做成“先看图，再轻操作”的系统。核心不是复杂装饰，而是白色画布、清晰黑字、品牌红粉动作点、圆形或胶囊形控件、可横向扫描的图片卡片，以及非常稳的页脚信息架构。

这套系统适合高频浏览、对比、收藏和预订。用户首先被图片吸引，然后通过房源类型、地理位置、价格、评分和“房客推荐”标签快速判断。页面的交互密度不低，但表面非常轻：阴影少，边线淡，控件有大圆角，视觉负担主要由照片承担。

本次按用户要求不登录，只拆公开页面。登录后愿望单、订单、消息、个人账号、完整预订流程和房东后台没有检查。

## Colors

### Brand & Accent

- `primary` `#FF385C`: Airbnb 标志和搜索 CTA 的核心红粉色。用于把白色页面里的关键动作拉出来。
- `primary-deep` `#E61E4D`: 搜索/登录主按钮上可见的更深红粉，常和渐变端色搭配。
- `primary-gradient-end` `#D70466`: 主按钮渐变端色，适合用于宽 CTA 或需要更强品牌感的行动面。

### Surface

- `canvas` `#FFFFFF`: 主页面画布、卡片背景和大部分交易界面。
- `surface-soft` `#F7F7F7`: 页脚、帮助中心搜索框和轻分区背景。
- `surface-chip` `#F2F2F2`: 语言/币种按钮、菜单按钮、浅底胶囊控件。

### Text

- `ink` `#222222`: 主标题、正文、价格、评分和大部分 UI 文案。
- `muted` `#6A6A6A`: 次级说明、地点副标题、辅助信息。
- `subtle` `#717171`: 低优先级元信息和 footer 链接。
- `inverse` `#FFFFFF`: 红粉 CTA 或深色按钮上的文字。

### Hairlines & Borders

- `border` `#DDDDDD`: 帮助中心搜索框、输入边界和主要分隔线。
- `border-soft` `#EBEBEB`: 页面分段、footer 上边线、卡片之间的轻分隔。

### Semantic

- `success` `#008A05`: 房东保障表格中的绿色勾选语义。
- `star` `#222222`: 评分星标和价格文本保持黑色，而不是使用黄色评分体系。

## Typography

### Font Family

公开页面计算样式显示主字体为：

`"Airbnb Cereal VF", Circular, -apple-system, BlinkMacSystemFont, Roboto, "Helvetica Neue", sans-serif`

这是系统气质的关键。它比普通系统字体更圆润，但仍然非常清晰，适合价格、地名、评分和大量短文本。

### Hierarchy

- Display: `60px / 64px / 700`，用于房东页大标题。它让招募页更接近品牌营销，而不是普通列表。
- Page title: `32px / 36px / 500`，用于体验页等内容页主标题。
- Listing title: `26px / 30px / 500`，用于公开房源详情页标题。
- Section heading: `22px / 26px / 500`，用于区域标题和服务页模块。
- Body: `14px / 20.02px / 400`，用于卡片元信息、footer、说明文字。
- Label: `14px / 18px / 500`，用于搜索框标签、输入名和重要短标签。

### Principles

Airbnb 不靠夸张字距或复杂字体效果取胜。它靠紧凑层级和明确字重分工：标题圆润厚实，卡片正文小而密，价格和评分不单独炫技。这样图片卡可以高密度排列，文字仍然可读。

### Note on Font Substitutes

如果拿不到 Airbnb Cereal VF，优先使用 `Circular`，再落到 `-apple-system`、`BlinkMacSystemFont`、`Roboto`、`Helvetica Neue`。不要换成几何感过强或科技感过重的字体。

## Layout

### Spacing System

公开首页在桌面宽度使用大约 `32px` 页面横向安全区，房源卡横向轮播之间间距约 `12-16px`。房东页使用更大的垂直分段，帮助中心使用居中的窄内容区。

### Grid & Container

- 首页/体验页：横向滚动卡片组，单卡宽度约 `190px`，图片高度约 `181px`。
- 帮助中心：居中内容区 + 胶囊搜索框 + 文章列表/卡片。
- 房东页：大标题居中，后续模块垂直叠放，保障/FAQ 使用窄栏阅读节奏。

### Whitespace Philosophy

Airbnb 的空白是“交易前缓冲”。它不让页面看起来像后台表格，而像一个可慢慢浏览的旅行目录。顶部搜索条很大，卡片之间保留足够空隙，footer 信息密集但放在浅灰背景里。

## Elevation & Depth

### Decorative Depth

页面整体阴影很少。层级主要由照片、圆角、浅灰背景、边线和浮层实现。

- 顶部搜索和菜单弹窗可出现浮层感。
- 首页卡片自身几乎无阴影，依靠图片和文字层级。
- 帮助中心搜索框使用 `#F7F7F7` 背景加 `#DDDDDD` 边框。
- Footer 使用整块浅灰背景形成页面收束。

## Shapes

### Border Radius Scale

- 圆形：搜索按钮、语言按钮、菜单按钮、轮播箭头。
- 胶囊：帮助中心搜索框、顶部搜索壳、房客推荐标签、主 CTA。
- 卡片图片：公开截图中图片实际元素本身没有总能读到圆角，但视觉上房源卡图片为大圆角裁切，建议使用 `12px-16px`。
- 房东页 CTA 可使用小半径或胶囊，依页面上下文决定。

### Media Geometry

房源和体验卡使用接近 `190x181` 的图片比例，略接近方形但更宽，适合快速横向扫描。帮助中心卡图是更规则的方块/矩形，强调内容分类。

## Components

### Top Navigation

顶部导航左侧是 Airbnb 标志，中间为房源、体验、服务三个图文 tab。体验和服务 tab 带“全新”小标签。右侧依次是“成为房东”、语言/币种圆形按钮和主导航菜单圆形按钮。

实现时要保留三个特征：白底、中心 tab 的图文组合、右侧圆形工具按钮。不要把它改成普通 SaaS 左侧 logo + 右侧纯文字 nav。

### Search Shell

首页搜索条是 Airbnb 的核心组件。它居中放在导航下方，横向分成地点、时间、人员三段，右侧是红粉圆形搜索按钮。输入项不是传统表单边框，而是分段信息块。

帮助中心也使用搜索，但形态不同：`#F7F7F7` 胶囊背景、`#DDDDDD` 边线、宽约 `400px`，更像内容检索。

### Listing Cards

房源卡由图片、心愿单按钮、房客推荐胶囊、房源类型/地点、价格和评分组成。卡片不需要外框或阴影，图片承担主体视觉。评分星标和文字保持黑色，小尺寸即可。

### Experience Cards

体验页沿用房源卡骨架，但内容更偏活动：限定标签、达人/体验标题、地点和价格信息。它证明 Airbnb 的卡片系统可跨住宿、体验和服务复用。

### Host Marketing Sections

房东页使用更营销化的大标题：`60px / 64px / 700`，页面空白明显更大。模块包括收入估算、三点价值、AirCover 保障表、FAQ 和 App/手机 mock。这里同样少用装饰，靠大标题和模块间距建立品牌感。

### Help Center

帮助中心把复杂支持内容拆成搜索框、用户身份 tab、热门文章、插图卡片和 footer。视觉比首页更克制，适合信息查找。它使用同一套字体、边线和浅灰表面，但组件更内容化。

### Footer

Footer 是大型信息架构区，浅灰背景 `#F7F7F7`，三列或多列链接组，底部放语言、币种、版权和社交入口。它密集但不吵，因为颜色和字号都保持低对比。

## Do's and Don'ts

### Do

- 使用白色主画布和 `#222222` 文字，不要做厚重背景。
- 把品牌红粉色留给搜索、主按钮和标志。
- 卡片优先展示真实图片，文字只放必要元信息。
- 搜索和工具按钮使用胶囊/圆形，保证触控友好。
- 用浅灰 `#F7F7F7` 收纳 footer、帮助搜索和次级区域。
- 保留房源/体验/服务三类产品在卡片系统上的一致性。

### Don't

- 不要给每张房源卡加重阴影或重边框。
- 不要把评分做成黄色星星体系；公开页面里评分星标是黑色小图标。
- 不要用科技感蓝紫渐变替代 Airbnb 红粉品牌色。
- 不要让顶部导航变成普通企业官网导航。
- 不要把房东页做成 dashboard，它是品牌营销和招募页。

## Responsive Behavior

### Breakpoints

公开页面没有完整逐断点检查，但 Airbnb 的结构明显依赖横向卡片组和移动端折叠。桌面宽度下顶部搜索条居中，卡片横向排列。移动端应保留大搜索入口和单列/横滑卡片。

### Touch Targets

圆形按钮约 `40px`，搜索按钮约 `48px`。移动端不要缩小到低于 `40px`。

### Collapsing Strategy

顶部 tab 可以压缩为更少文字或图标入口；卡片组保持横向滑动；帮助中心文章列表转单列；footer 链接组纵向堆叠。

### Image Behavior

图片必须裁切到稳定比例，优先 `object-fit: cover`。不要让房源图因为原始比例不同而撑乱卡片。

## Iteration Guide

新页面先从四个核心组件开始：顶部导航、胶囊搜索、图片卡片、浅灰 footer。然后按页面类型扩展：

- 旅行浏览页：横向卡片组 + 房客推荐 + 心愿单 + 价格评分。
- 详情页：大图/标题 + 价格/预订浮层 + 信息分组。
- 帮助页：胶囊搜索 + 用户身份 tab + 文章卡。
- 房东招募页：大标题 + 价值点 + 保障表 + FAQ。

扩展时保持轻表面、真实图片、红粉动作点和清晰文字层级。

## Known Gaps

- 用户明确要求不登录；登录后的愿望单、订单、消息、账号菜单、完整个人资料和房东后台没有检查。
- 没有提交搜索、预订、收藏、支付、登录或任何会改变账号/站点状态的操作。
- 公开房源详情页只打开了一个样本，并且该详情页在当前环境中只加载到有限内容；完整相册、预订卡、评价和地图没有作为已验证证据。
- `services` 页面在当前公开访问环境中没有加载到大量服务卡图，只观察到服务搜索壳和 footer 结构。
- 截图命令在 in-app Browser 上曾对当前 tab 超时；最终以 DOM、计算样式、公开图片 URL 和 Playwright CLI 辅助截图进行验证。
- Airbnb Cereal VF 的字体文件本身没有下载或再分发；文档只记录页面计算样式里的字体栈。
