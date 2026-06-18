---
version: alpha
name: pinduoduo-special-nine-newcomer-001-design-analysis
language: "zh-CN"
source_url: "https://mobile.yangkeduo.com/sjs_special_nine.html"
analyzed_at: "2026-06-18"
description: >
  对拼多多 9 块 9页面中“新人低至 0.01 元”限时补贴模块的独立设计系统拆解。该模块用高饱和红色页面背景、白色圆角活动卡、图片化标题资产、倒计时、横向商品轨道、补贴条、超低价数字和强渐变 CTA，快速制造“新人专享、马上抢、数量有限”的零售压力感。适合用于新人补贴、限时秒杀、补贴商品横滑、低价引流入口等活动模块。
observed_pages:
  - label: "9块9特卖活动页"
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
    usage: "新人低至 0.01 元标题图层"
  timer-label:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "22.1867px"
    fontWeight: 400
    lineHeight: "25.6px"
    letterSpacing: "0"
    usage: "仅剩标签"
  timer-digit:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "20.48px"
    fontWeight: 500
    lineHeight: "29.0133px"
    letterSpacing: "0"
    usage: "倒计时数字胶囊"
  product-title:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "22.1867px"
    fontWeight: 400
    lineHeight: "32.4267px"
    letterSpacing: "0"
    usage: "商品短标题，单行可裁切"
  price:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "34.1333px"
    fontWeight: 600
    lineHeight: "34.1333px"
    letterSpacing: "0"
    usage: "补贴价主数字"
  cta:
    fontFamily: "system-ui, PingFang SC, Arial, sans-serif"
    fontSize: "29.0133px"
    fontWeight: 600
    lineHeight: "43.52px"
    letterSpacing: "0"
    usage: "立即抢购主按钮"
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
  red-campaign-band: "640px 宽红色活动带，承载白色新人卡"
  newcomer-card: "613x451 白色圆角卡，半径 13.6533px"
  title-asset-row: "左侧 31x38 图标资产 + 266x38 标题资产，右侧倒计时"
  countdown: "仅剩标签 + 29px 红橙渐变数字胶囊 + 红色分隔符"
  product-rail: "599x276 裁切视窗，内部 1934px 横向商品内容"
  subsidy-ribbon: "174x31 图片背景条，白字已补3元和小箭头资产"
  product-card: "174px 商品卡，174px 正方形图片、31px补贴条、32px标题、34px价格"
  primary-cta: "512x68 pill，90度红橙渐变、34.1333px圆角、柔红阴影"
---

## Overview

这是一个移动电商活动模块，不是普通商品列表。它把“新人价”拆成几层压力信号：顶部图片化标题强调 `0.01 元`，右侧倒计时持续刷新，中间商品横轨露出半张下一卡，底部用大 pill 按钮收口。整体目标是让用户不用思考，直接理解“限时、补贴、便宜、马上抢”。

可复用时要保留三件事：红色活动背景、白色圆角承载卡、强对比价格和 CTA。它不适合改成冷静的商城卡片，也不适合加太多说明文案。

## Colors

### Brand & Accent

- `primary` `#e63e3e`: 页面红色活动底，用来形成整块活动氛围。
- `action-start` `#ff542e` 到 `action-end` `#ff1808`: 主 CTA 渐变，方向为 90deg。
- `price-red` `#ef1407`: 价格主数字，比普通拼多多红更刺眼。
- `pdd-red` `#e02e24`: “补贴价”标签和辅助价格文案。
- `timer-red` `#ff3d34`: 倒计时分隔符和时间强调色。

### Surface

- `surface-card` `#ffffff`: 新人模块主卡、商品轨道、商品底层。
- `canvas-red` `#e63e3e`: 模块外部活动底色。

### Text

- `ink` `#151516`: 商品标题。
- `muted` `#9c9c9c`: “仅剩”等弱提示。
- `body` `#666666`: 页面默认正文色。
- `coupon-text` `#9d3a00`: CTA 内“仅限一次”的小胶囊文字。
- `on-primary` `#ffffff`: 按钮、补贴条、倒计时数字。

### Hairlines & Borders

该模块基本不用线框分割，靠白色卡、图片裁切、红色条和大圆角建立层级。商品图片之间用 10px 左右留白，而不是边框。

### Semantic

- 红色代表低价、抢购、倒计时。
- 橙红渐变代表主要行动。
- 白色代表商品和信息承载层。

## Typography

### Font Family

普通文本使用系统中文字体栈。标题“新人低至 0.01 元”不是 DOM 文本，而是两段源图片资产：31x38 的橙色小图标和 266x38 的标题字图。因此复刻时不要把它当普通 H1 文本来随意排版。

### Hierarchy

- 标题资产：视觉高度 38px，左图标 31px 宽，标题资产 266px 宽，位于白卡顶部 `x=323,y=159` 附近。
- 倒计时标签：`22.1867px / 25.6px / 400`，灰色。
- 倒计时数字：`20.48px / 29.0133px / 500`，白字，29x29 胶囊。
- 商品标题：`22.1867px / 32.4267px / 400`，黑色，卡内单行裁切，长标题 `scrollHeight` 远高于 `clientHeight`，这是刻意裁掉长文案。
- 价格主数字：整数 `34.1333px / 600`，小数 `23.8933px / 600`，通过字号差拉开视觉层级。
- CTA：`29.0133px / 43.52px / 600`，主字白色。

### Principles

模块的字不是“统一字号”，而是按转化强度分层：标题图片最大，CTA 其次，价格用大数字，商品标题只负责识别商品，不允许抢走价格和按钮注意力。

### Note on Font Substitutes

预览或复刻中可用 `system-ui, -apple-system, BlinkMacSystemFont, "PingFang SC", Arial, sans-serif`。标题建议继续使用源图片资产；若必须改文字，需要重新画同等重量的标题资产。

## Layout

### Spacing System

模块源尺寸为 640px 宽活动带，白卡为 `613x451`，卡片左侧偏移约 13px。顶部标题行高 38px，商品轨道从 `y=213` 开始，CTA 从 `y=500` 开始。商品卡宽 `174px`，相邻卡横向间距约 10px。

### Grid & Container

核心结构：

1. 红色背景带：`640x471`。
2. 白色新人卡：`613x451`，圆角 `13.6533px`。
3. 标题/倒计时行：左资产，右倒计时。
4. 横向商品轨道：视窗 `599x276`，内部内容宽 `1934px`。
5. 主 CTA：`512x68`，居中，pill。

### Whitespace Philosophy

这是高密度零售模块，留白只服务于识别和点击。商品图片区和标题区非常紧，按钮上下有足够空间，确保“立即抢购”成为视线终点。

## Elevation & Depth

### Decorative Depth

模块深度来自：

- 白卡与红底的强对比。
- CTA 的柔红阴影：`rgba(253, 99, 99, 0.3) 0px 3.41333px 17.0667px 0px`。
- 商品图片自身的内容深度。
- 补贴条图片背景和箭头图层。

没有复杂投影系统，也没有玻璃拟态。层级主要靠颜色和面积。

## Shapes

### Border Radius Scale

- 倒计时数字胶囊：`3.41333px`。
- 商品轨道底部圆角：`0 0 6.82667px 6.82667px`。
- 新人白卡：`13.6533px`。
- 主 CTA：`34.1333px`，完整 pill。

### Media Geometry

商品图为 `174x174` 正方形，裁切方式是 cover。商品标题和价格都限制在同一个 174px 宽度内。

## Components

### Top Navigation

本次拆解聚焦新人补贴模块，不把页面顶部搜索栏和分类导航作为主对象。它们只作为上下文：红色页面、白色搜索框、横向频道标签共同把模块放在 9 块 9促销场景里。

### Buttons

主按钮是 `512x68` 的红橙渐变 pill，背景为 `linear-gradient(90deg, #ff542e, #ff1808)`，半径 `34.1333px`，带柔红投影。按钮内左侧是大白字“立即抢购”，右侧是小浅色胶囊“仅限一次”。这是强转化按钮，不能改成普通矩形按钮。

“立即抢购”涉及购买/领券路径，本次未点击，以避免外部副作用。

### Cards & Containers

主容器是白色圆角卡，内部又包含商品轨道。商品轨道本身也是白底，底部有 `6.82667px` 圆角。它不是普通卡片网格，而是横向活动货架。

### Inputs & Forms

该模块内没有输入框。页面顶部搜索框不属于本模块，未作为输入组件拆解。

### Tabs / Chips / Tags

模块内的主要标签是“已补3元”补贴条，使用源图片背景 `476bf3be...png`，右侧小箭头是独立图片资产 `edecb4cb...png`。这类标签不要用纯 CSS 矩形替代，否则会丢失补贴条的活动感。

### Signature Components

#### 01 标题资产行

左侧图标和标题都是图片背景，不是文本。图标源资产为 `1a7463a2...png`，标题源资产为 `d1bfbf4e...png`。右侧倒计时与标题同行，形成“新人低价 + 剩余时间”的组合。

#### 02 倒计时

倒计时由“仅剩”标签、三个两位数字、一个一位小数和红色分隔符组成。数字块为红橙渐变背景，29px 高，圆角 3.41333px。实测 1.3 秒后从 `06:47:33.9` 变为 `06:47:32.5`，属于真实动态计时。

#### 03 商品横向轨道

外层可见视窗 `599x276`，`overflow:hidden`；内部内容宽 `1934px`，商品卡按 174px 宽横排。截图中右侧露出下一张商品卡的一部分，这是刻意制造“可继续看/还有更多”的视觉提示。

鼠标横向拖动测试没有让轨道移动；因此只能确认视觉裁切和横向内容结构，不能把“桌面鼠标可拖动”写成已验证功能。触摸滑动可能存在，但本次未确认。

#### 04 商品卡

每张卡结构固定：

1. `174x174` 商品图。
2. `174x31` 补贴条。
3. `174x32` 商品标题，长标题只露出一行。
4. `174x34` 价格行。

标题长文案被裁切是设计选择，不是排版 bug。价格行使用分段字号：币种/标签小，整数大，小数较小。

#### 05 补贴条

补贴条为图片背景，文本白色 `20.48px / 600`，文本位置大约水平居中，右侧配向下箭头图层。它表达“平台已经替你补贴”的机制，不是普通 sale badge。

#### 06 价格行

价格前缀“补贴价”为 `20.48px`，价格整数为 `34.1333px`，小数为 `23.8933px`。低价的视觉重点落在 `0` 上，`0.01` 比商品标题更抢眼。

#### 07 主 CTA

按钮位于商品轨道下方，居中，宽 512px，高 68px。主文案在按钮中心偏左，“仅限一次”是按钮内的约束标签，强调稀缺和资格限制。

#### 08 查看更多入口

商品轨道右端存在一个竖向白色小卡“查看更多”，宽约 65px，高 154px，说明横向商品集合可以导向更多商品，但本次未点击。

### Footer

模块本身没有 footer。模块下方直接进入推荐商品分类 tab 和商品瀑布流。

## Do's and Don'ts

### Do

- 使用红色活动底包住白色圆角卡。
- 标题优先使用源图片资产或同等重量的位图/矢量标题。
- 保留倒计时数字胶囊和红色分隔符。
- 商品轨道要保留右侧裁切露出，不能改成普通三列网格。
- 价格要做分段字号，整数最强，小数次之。
- 主 CTA 要使用红橙渐变、pill 圆角和柔红阴影。

### Don't

- 不要把标题“新人低至 0.01 元”改成普通 H1。
- 不要把补贴条改成普通红色矩形标签。
- 不要把商品标题全部展开，多行展开会破坏低价模块密度。
- 不要点击抢购、商品下单、购买、支付相关动作来验证设计。
- 不要把页面顶部 QR 引导当成这个模块的组成部分；那是桌面浏览器打开移动页时的外部提示。

## Responsive Behavior

### Breakpoints

源页面在桌面浏览器中仍以移动页宽度居中展示，实际活动内容宽 640px。模块内部尺寸基于这一移动活动宽度，不是桌面自适应大卡。

### Touch Targets

主 CTA 高 68px，足够大；商品卡宽 174px，商品图和卡片都可以作为入口，但本次未点击商品或抢购。

### Collapsing Strategy

复刻时应保持源宽度优先：在窄屏内按 `max-width: 640px; width: 100%` 缩放，而不是把商品卡强行变成两列或三列。商品轨道保持横向裁切。

### Image Behavior

商品图片用正方形 cover；标题和补贴条使用源图片资产，必须等比铺满自己的盒子。

## Iteration Guide

先搭红色活动带和白色主卡，再搭标题资产行、倒计时、商品轨道、补贴条和 CTA。开发时优先保证这些硬指标：白卡 613/640 的比例、商品卡 174px、CTA 512x68、轨道裁切、倒计时数字胶囊。

扩展到其他新人活动时，可以换商品图和价格，但不要改掉“标题资产 + 倒计时 + 横向货架 + 主 CTA”的结构。

## Known Gaps

- 未点击“立即抢购”，因为可能触发领券、购买或账号状态变化。
- 未点击商品卡，避免进入商品详情或产生行为记录。
- 未点击“查看更多”，避免跳转和潜在推荐记录。
- 鼠标横向拖动商品轨道未产生位移；触摸滑动未在真实手机环境中验证。
- 页面 URL 中的分享和页面参数已从最终文档中脱敏。
- 商品内容可能随用户、时间、库存变化；本拆解只记录模块结构和视觉系统。
