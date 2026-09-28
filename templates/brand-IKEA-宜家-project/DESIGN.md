# Design System: IKEA 宜家

> Category: retail-democratic
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

务实、明亮、大众化、家居感。浅灰白画布上，以 IKEA 蓝承载信息与价格，以 IKEA 黄承载行动（按钮、促销标签），高对比、零装饰。设计意图：像一本翻开的产品目录——价格清晰、信息直给、每个人都能看懂。

素材说明：官方站点 `https://www.ikea.com` 在本环境无法抓取（DNS 解析被沙箱拦截），本设计系统依据公开品牌资料（IKEA 官方品牌色、2019 年启用的 Noto IKEA 字体、蓝色/黄色双色视觉识别）与零售电商行业常识提炼，**非像素级实测**。各 token 的溯源见文末"溯源标注"。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#0058A3`（IKEA 蓝，导航栏、链接、标题强调、价格数字）— 实测（品牌公开色值）
- secondary: `#FFDB00`（IKEA 黄，主按钮、促销标签、焦点高亮）— 实测（品牌公开色值）
- surface: `#FFFFFF`（纯白，卡片、内容区背景）— 推断
- surface-page: `#F5F5F5`（浅灰，页面底色，区分卡片与画布）— 推断，近似
- surface-alt: `#DFE8F2`（浅蓝，信息条、选中态背景）— 推断
- text-primary: `#111111`（近黑，标题与正文）— 实测（品牌公开色值）
- text-secondary: `#484848`（中灰，次要说明、价格单位、辅助文案）— 推断，近似
- border: `#DFDFDF`（浅灰线，卡片边框、分隔线）— 推断
- primary-hover: `#004F93`（蓝加深，链接与蓝色按钮 hover）— 推断（primary 派生）
- secondary-hover: `#F5CE00`（黄加深，黄色按钮 hover）— 推断（secondary 派生）
- price-red: `#CC0008`（促销价、折扣数字；仅用于价格语义，不作装饰）— 推断

禁止：纯黑 `#000`、纯白以外的高饱和荧光色、紫色/青绿色系、任何金属色与渐变。

## 3. Typography

- 字体族：`"Noto IKEA", "Noto Sans", "Noto Sans SC", "Microsoft YaHei", -apple-system, "Segoe UI", sans-serif`
  - 品牌自有字体为 Noto IKEA（Latin/Thai）与 Noto IKEA Arabic 等定制版；本系统使用其开源母体 Noto Sans 作为等价替代，中文回落 Noto Sans SC / 微软雅黑（推断）
- 字号刻度：标题 44px / 32px（H1/H2），小节标题 22px，正文 16px，次要 14px，caption 12px
- 字重：标题 700，正文 400，按钮与价格 700
- 行高：标题 1.2，正文 1.6
- 字距：标题 0 或轻微负值，正文 0；不使用大字距（品牌规范要求标题字距不低于 0，过长标题拆行而非压缩字距）

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 32 / 48 / 64 px
- 页面最大宽度 1280px，水平居中；内容网格 12 列，列间距 24px
- 区块间 64px，区块内 32px；商品网格用 4 列（≥1024px）/ 2 列（≥640px）/ 1 列（移动端）
- 侧边留白：桌面 32px，移动端 16px

## 5. Layout & Composition

- 层级：页面顶部 IKEA 蓝导航条（白字 + 黄色 logo 块）→ 大标题（44px，text-primary）→ 一句实用副标题（16px, text-secondary）→ 黄色行动按钮 → 白色卡片网格
- 按钮：solid secondary 黄底，深色文字 `#111111`，圆角 999px（胶囊），padding 14px 32px，字重 700；次要按钮为白底 + 1px `#DFDFDF` 边框 + `#111111` 文字
- 卡片：白底，1px border，圆角 8px，padding 24px，仅允许极轻阴影 `0 1px 2px rgba(0,0,0,.08)`
- 价格排版：金额用 primary 蓝或 price-red，字号大于同级正文，货币符号与单位用 text-secondary 小字号紧随其后——价格是版面第一信息
- 允许一条 surface-alt 浅蓝信息条承载配送/会员/退货等实用信息

## 6. Components

- 按钮 hover：黄 `#F5CE00` / 蓝 `#004F93`，150ms ease；焦点态用 2px `#0058A3` 外框
- 链接：primary 蓝色，hover 加下划线并转 `#004F93`
- 商品卡：白底卡片 + 图片区（surface-page 底）+ 品名（16px, text-primary, 最多两行）+ 价格行；hover 时边框转 `#0058A3`
- 标签（badge）：促销用 secondary 黄底深色字；"新品"用 surface-alt 浅蓝底 + primary 蓝字，12px，圆角 999px
- 导航：primary 蓝色条，白字，当前项加 3px 黄色下划线

## 7. Motion & Interaction

- 仅允许 hover 颜色/边框变化与焦点外框浮现（150ms ease）。禁止弹跳、缩放、视差、自动轮播等花哨动效；图片懒加载淡入不超过 200ms 且不位移。

## 8. Voice & Brand

- 文案实用、直给、平价友好，像店员面对面说话：说清尺寸、材质、价格与配送，不夸张、不煽情。可适度使用"你""我们"，使用短句与具体数字；禁止"顶级""爆款""颠覆""震撼"等营销大词，禁止感叹号堆叠，禁止 emoji 装饰。

## 9. Anti-patterns

- 禁止引入未列出颜色/字体
- 禁止纯黑 `#000` 背景与大段纯黑文字（正文用 `#111111`）
- 禁止在黄色上叠加白色文字（对比度不足），黄底必须配 `#111111`
- 禁止渐变、霓虹、荧光色与金属质感
- 禁止衬线标题与手写体（标题必须无衬线）
- 禁止卡片重阴影、玻璃拟态、3D 倾斜
- 禁止 emoji 作为主装饰
- 禁止内容超出 1280px 容器

## 溯源标注

- 实测（品牌公开资料）：IKEA 蓝 `#0058A3`、IKEA 黄 `#FFDB00`、近黑 `#111111`、Noto IKEA 字体族（[IKEA 品牌色](https://imgcolorpicker.org/brand-colors/ikea/)、[品牌字体规范](https://brandhub.boklok.com/typography)、[Verdana→Noto IKEA 换字报道](https://www.fastcompany.com/90393259/ikea-is-quietly-changing-its-brand-again-for-a-very-good-reason)）
- 近似：surface-page、text-secondary、border、派生 hover 色
- 推断（官网不可抓取，基于行业常识）：全部间距/网格/组件细节、price-red、语气描述
