---
version: alpha
name: pinduoduo-signin-campaign-design-analysis
language: "zh-CN"
source_url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
analyzed_at: "2026-06-18"
description: >
  对拼多多移动端“签到领现金”活动页的独立设计系统拆解。这个页面用强红色活动画布、现金绿色、奶油色奖池卡、3D 数字滚轮、图片化按钮和高密度商品流制造强促销感，适合签到、抽奖、返现、任务、商品转化这类短链路活动页。

observed_pages:
  - label: "首页其他弹窗中的签到入口"
    url: "https://mobile.yangkeduo.com/index.html"
    access: "public"
  - label: "签到活动主页面"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "右上角更多菜单"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "活动规则弹窗"
    url: "https://mobile.yangkeduo.com/havana_mianfei_packet.html"
    access: "public page with personalized account display"
  - label: "医药分类选中态"
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
    usage: "现金账户大数字滚轮"
  heading:
    fontFamily: "PingFangSC-Medium, PingFang SC, sans-serif"
    fontSize: "18.72px"
    fontWeight: 500
    lineHeight: "22.88px"
    letterSpacing: "normal"
    usage: "顶部标题"
  body:
    fontFamily: "PingFang SC, system-ui, sans-serif"
    fontSize: "13.52px"
    fontWeight: 400
    lineHeight: "17.68px"
    letterSpacing: "normal"
    usage: "标签、商品辅助信息、账户标签"
  label:
    fontFamily: "PingFang SC, system-ui, sans-serif"
    fontSize: "14.56px"
    fontWeight: 400
    lineHeight: "14.56px"
    letterSpacing: "normal"
    usage: "商品按钮和菜单项"

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
  entry-modal-grid: "首页“其他”弹窗中 3 列图标入口，签到图标为黄色日历底图加红字标签。"
  top-nav: "固定移动端红色导航，标题、搜索框、更多菜单三件套；滚动后标题区替换为余额滚轮。"
  cash-account-card: "白色大卡叠在红色背景上，粉色账户标签、红色金额数字、绿色微信标识、描边胶囊按钮。"
  prize-machine: "奶油色外框、橙红内发光、3x2 奖励格、图片化主按钮和手势 APNG。"
  mission-gallery: "白底四宫格任务入口，图标来自活动资源，红色 13.52px 标签。"
  category-tabs: "横向分类菜单，选中项红色 #e02e24、700 字重。"
  product-card: "两列商品卡，193px 商品图、两行标题、灰色服务标签、红色价格、满宽红色 CTA。"
  more-popover: "右上白色浮层，活动规则、打款明细、音效开关三项。"
  rules-modal: "深遮罩上白色圆角说明卡，右上外浮关闭按钮，内容可滚动。"
---

## Overview

这是一个很典型的拼多多活动页：第一屏先给“现金账户”和“抽提现”强刺激，再用任务入口和商品流把用户继续往下带。页面不是轻量品牌页，而是强运营活动画布，视觉上尽量让每个区域都像“可领、可抽、可点”。

核心视觉驱动有四个：红色活动背景、绿色现金符号、奶油色奖池卡、图片化 CTA。现金数字不是普通文本，而是多列数字滚轮，滚动时顶栏会固定在顶部并保留搜索入口。页面下半段进入商品双列流，每个商品卡继续用红色“拼单抽提现”按钮连接活动目标。

## Colors

### Brand & Accent

- `primary` `#fe1842`: 首屏红色活动背景，负责制造紧迫感。
- `primary-action` `#e02e24`: 分类选中态、商品按钮、价格，负责转化动作。
- `cash-green` `#0cab13`: 微信现金、免费提现、奖励卡上的正向信号。
- `cash-red` `#ea3c32`: 现金账户大金额和“领更多现金”入口，强调利益。
- `warning` `#ff633d`: “奖池已更新”“剩余份数”等提示胶囊。

### Surface

- `canvas` `#f4f4f4`: 商品流背景，降低白卡之间的粘连。
- `surface-card` `#ffffff`: 账户卡、任务卡、商品卡和浮层菜单。
- `warm-panel` `#ffecd9`: 奖池主容器，和红色背景拉开层次。
- `warm-panel-light` `#fff3e6`: 奖励卡高光和抽奖区域内层。
- `surface-chip` `#ffe0e6`: “我的现金账户”粉色标签底。

### Text

- `ink` `#151516`: 分类默认文字和菜单文字。
- `body` `#666666`: 商品信息、普通说明、容器默认文字。
- `muted` `#9c9c9c`: 搜索占位、商品服务标签。
- `on-primary` `#ffffff`: 红色按钮、活动标题、提示牌文字。

### Hairlines & Borders

- `hairline` `#eeeeee`: 弹窗菜单分隔、商品卡轻分隔。
- 奖励格外框主要靠图片资源和绿色边缘完成，不是普通 CSS 边框。

### Semantic

- `cash-green` 表示能提现、微信打款、任务收益。
- `primary-action` 表示立即行动、购买、拼单抽提现。
- `warning` 表示库存、奖池更新、限量提示。

## Typography

### Font Family

页面主要使用 `PingFang SC`、`STHeiti STXihei`、`Microsoft YaHei` 等中文系统字体。金额数字使用 `PDDSansStd06-Regular`，这是数字样式的关键来源；没有该字体时，数字会失去拼多多活动页的窄高感。

### Hierarchy

- Display: 现金金额使用 41.6px、400、41.6px line-height，颜色 `#ea3c32`，每位数字独立滚轮。
- Heading: 顶部标题 18.72px、500、白色，用于“签到领现金”。
- Body: 商品信息、标签和说明多在 12.48px 到 13.52px，密度高。
- Label: 商品 CTA 14.56px、白色，按钮高 29px；主 CTA 文字 20.8px、900。

### Principles

这个页面不追求留白，而追求“马上看懂能拿什么”。金额和奖励字重更大，商品标题压缩在两行内，按钮文字短、直给。分类 tab 的选中态只用颜色和字重，不加重装饰。

### Note on Font Substitutes

预览页使用系统字体和 `Arial Black` 模拟大数字。真实实现里，金额数字应优先接入 `PDDSansStd06-Regular` 或同类窄高数字字体。

## Layout

### Spacing System

页面按 375px 移动稿渲染。实测移动视口为 390px 时，文档宽度为 375px，左右留出安全边。首屏从 77px 顶栏开始，现金账户卡在 y=79，奖池容器从 y=154 开始，任务四宫格从 y=520 开始，分类和商品流从 y=619 后进入长列表。

### Grid & Container

首屏是纵向叠层：红色背景、账户卡、奖池卡、任务入口。奖池内部是 3x2 格，奖励格约 89x82px。任务入口是 4 列，每项约 75x72px。商品流是两列，每张卡约 193x303px，图片 193x193px。

### Whitespace Philosophy

留白很少，区域之间靠背景色、图片边框、圆角和按钮区分。页面把主要空间给奖励和商品，不给长说明。

## Elevation & Depth

### Decorative Depth

深度主要来自图片素材和渐变，不来自大阴影。现金账户卡是白底圆角叠在红色背景上；奖池区使用奶油色外框、内层橙红渐变和奖励格图片边框。规则弹窗使用 `rgba(0,0,0,.72)` 左右的遮罩制造层级。

## Shapes

### Border Radius Scale

活动页以小圆角为主：商品卡约 2.08px，商品 CTA 约 4.16px，任务卡约 8.32px，现金卡和任务区约 10.4px，奖池容器顶部约 16.64px。不要把它做成大圆角卡片系统。

### Media Geometry

商品图是方图，193x193px，强裁切。任务入口图标使用活动资源，背景图按 `contain` 或 `100% 100%` 拉伸。主 CTA 是图片化按钮，不是纯 CSS 胶囊。

## Components

### Top Navigation

顶部是红色移动导航。初始态左侧返回，标题“签到领现金”，中间白底搜索框，右侧圆形更多按钮。滚动后导航固定，`position: fixed`，z-index 约 9998/10000，标题区变成小号现金余额滚轮，搜索框保持 203x31px 白底。

### Entry Modal From Home

首页“其他”弹窗为 3 列入口宫格。签到入口位于第三行第一列，黄色日历图标加红色“签到”文字。点击后进入活动页。这个入口属于全站功能聚合，不是活动页内部组件。

### Cash Account Card

账户卡白底、宽约 325px，左上粉色“我的现金账户”标签，标签圆角为 `12.48px 0 8.32px`。金额数字使用红色 3D 数字滚轮，数字列有 `transform` 过渡，`transition-duration: 0.5s`。金额旁的“领更多现金”是小描边胶囊，文字 13.52px、500、红色。

### Prize Machine

奖池容器宽 390px，高约 356px，背景 `#ffecd9`，顶部圆角 16.64px。标题条是背景图 `activityDespTitleBg.png`，左右星星和微信图标也来自资源。内层主背景是 `mainPartMachineBg.png`，奖励格使用 `lottery_reward_item.png`，券格使用 `platform_coupon.png`。奖励卡分现金、券、惊喜奖励三类，现金金额绿色，券金额棕色。

### Buttons

主 CTA“立即抽提现”是图片背景 `activityMainBtn.png`，宽约 239px、高约 67px，文本层单独放置，主字 20.8px、900、白色；右下有 `main_btn_handle_finger.apng` 手势层。商品 CTA 是纯红色矩形，宽约 177px、高 29px，圆角 4.16px，文字为“拼单抽 提现”，中间夹微信小图标。

### Mission Gallery

四个入口为“全额返”“每日领钱”“招财猫”“兑换专区”。每项约 75x72px，图标区 71x44px，标签红色 `#ff1818`、13.52px、500。图标分别来自 `a7fca165...png`、`daily_money.png`、`ManekiNekoCat.png`、`ExchangeZone.png`。

### Tabs / Chips / Tags

分类 tab 为横向滚动，包含“全部、医药、食品、手机、水果、百货、男装、运动、鞋包、电脑、电器、家具、家纺、美妆、女装、家装、内衣、车品、饰品、母婴”。默认文字 `#151516`、15.6px、400；选中态实测为 `#e02e24`、15.6px、700。点击“医药”后商品流刷新为医药商品。

### Product Cards

商品流为两列白卡。卡片约 193x303px，圆角 2.08px；商品图 193x193px；标题区两行，服务标签为灰色 12.48px，价格为红色 `#e02e24`、13.52px、700，销量文字黑色 12.48px。每张卡底部都有“拼单抽提现”按钮，按钮是该页面下半段最重复的转化入口。

### More Popover

右上更多菜单是白色浮层，宽 92px、高 119px，圆角 4.16px，含“活动规则”“打款明细”“音效”。菜单项高 40px，文字 14.56px、`#151516`。音效开关是绿色开启态，测试中可以切到关闭并恢复。

### Rules Modal

点击“活动规则”会出现深色遮罩和白色说明卡。卡片约 302px 宽，居中，顶部标题 18px 左右，正文 16px 左右，右上关闭按钮外浮在卡片边缘。内容区可滚动。

### Dynamic Interaction Effects

- 数字滚轮：金额每列使用 `matrix3d`，`transform` 过渡 0.5s，制造翻牌感。
- 分类切换：选中 tab 变红加粗，商品列表刷新。
- 吸顶导航：滚动后 fixed 顶栏出现，余额滚轮进入顶栏。
- 返回顶部：右下角按钮通过 bottom/opacity 过渡出现，点击后 scrollY 回到 0。
- Loading：底部 loading 图标使用 1s linear 旋转。
- 主 CTA：图片按钮右侧有 APNG 手势层，形成点击提示。
- 音效开关：右上菜单内切换绿色开关态，测试后已恢复开启。

### All Observed Function Entries

- 首页“其他”弹窗里的“签到”入口：已点击进入。
- 顶栏返回：返回上一页，未点击，避免离开采集状态。
- 顶栏搜索：搜索商品，未输入。
- 顶栏更多：已打开，包含活动规则、打款明细、音效。
- 活动规则：已打开并关闭。
- 打款明细：未打开，可能展示账户明细。
- 音效：已切换关闭并恢复开启。
- 领更多现金：未点击，推测进入更多现金任务。
- 奖池六个奖励格：作为奖励展示和抽奖结果预期，不单独点击。
- 立即抽提现：未点击，可能消耗抽奖机会。
- 全额返、每日领钱、招财猫、兑换专区：未点击，可能进入任务或领取页面。
- 分类 tab：已测试“医药”切换。
- 商品卡和“拼单抽提现”：未点击，可能进入购买链路。
- 返回顶部：已点击并验证回到首屏。

## Do's and Don'ts

### Do

- 保持 375px 移动活动稿逻辑，不要把首屏改成桌面营销页。
- 金额、奖励、按钮要优先使用红绿对比，强化“现金”感。
- 图片化 CTA 要保留背景层、文字层、手势层，不要改成普通居中按钮。
- 商品卡要保持两列高密度、方图、红色底部 CTA。
- 弹窗和规则说明要用深遮罩加白色卡片。

### Don't

- 不要用大面积紫色、蓝色渐变或品牌无关插画替代红色活动画布。
- 不要把奖励卡做成普通白卡，原页面依赖图片边框和高饱和绿色。
- 不要把“拼单抽提现”拆成弱文本链接，它是商品流里的主行动。
- 不要在文档或预览里写完整分享参数、账号余额或私密打款明细。

## Responsive Behavior

### Breakpoints

实测 390px 视口下页面文档宽 375px，高约 3771px 到 6839px，取决于商品流加载状态。页面是移动优先画布，在宽屏中居中呈现，不做桌面重排。

### Touch Targets

顶部搜索框 203x31px，更多按钮约 20x20px 视觉图标；任务入口 75x72px；商品 CTA 177x29px；返回顶部 44x44px。部分按钮视觉尺寸偏小，但通过整块容器承接点击。

### Collapsing Strategy

没有观察到桌面版断点。活动主画布固定 375px 逻辑，宽屏时页面不扩展。商品流始终两列；分类 tab 横向滚动。

### Image Behavior

活动资源使用背景图 `100% 100%` 或 `contain`。商品图是方形裁切，瀑布流懒加载，底部加载更多后文档高度会增长。

## Iteration Guide

先搭 375px 移动活动壳，再搭固定顶栏、现金账户卡、奖池、任务四宫格和商品流。金额数字要单独做滚轮组件；主 CTA 要按“背景图 + 文字层 + 手势层”实现。新入口要放进任务四宫格或商品卡，不要增加新的大卡片样式。新增活动状态时，优先复用红色提示胶囊、绿色现金文字、奶油奖池面板。

## Known Gaps

- 未点击“立即抽提现”，因为可能消耗抽奖机会。
- 未打开“打款明细”，因为可能展示个人账户明细。
- 未点击“领更多现金”“全额返”“每日领钱”“招财猫”“兑换专区”和商品购买链路，因为可能产生账户或交易状态变化。
- 商品流内容是个性化推荐，后续账号、时间、分类或滚动深度变化都会改变商品。
- 账户余额和完整分享参数已脱敏，不作为设计系统内容。
- 精确字体文件未下载；数字字体仅从 computed style 记录到 `PDDSansStd06-Regular`。
