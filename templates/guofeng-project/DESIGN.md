# Design System: 国风·宣纸

> Category: chinese-guofeng
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

水墨国风、宣纸质感。宣纸米白底 + 墨黑文字 + 朱砂红点缀 + 黛青辅助，宋体衬线营造东方书卷气。设计意图：雅致、留白、有文化厚度。可选用极细的墨线分隔。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#B03A2E`（朱砂红，强调、印章感按钮、关键数字）
- surface: `#F7F2E7`（宣纸米白，页面背景）
- surface-alt: `#EFE7D4`（浅竹浆，卡片/分区背景）
- text-primary: `#2B2B2B`（墨黑，标题与正文）
- text-secondary: `#6B6355`（暖灰褐，次要文字）
- border: `#E3DAC8`（浅麦色，分隔线、边框）
- accent: `#3E5C57`（黛青，引注、辅助强调、印章副色）

禁止：纯黑 `#000`、纯白 `#FFF`、任何霓虹/荧光色、冷蓝紫系作为主色、大面积红。

## 3. Typography

- 字体族：标题 `"Noto Serif SC", "Songti SC", "SimSun", serif`；正文 `"Noto Serif SC", "Songti SC", "Source Han Serif SC", serif`（全文衬线，书卷气）
- 字号刻度：标题 42px/30px（serif 加粗），正文 17px，次要 14px，caption 12px
- 字重：标题 700，正文 400
- 行高：标题 1.4，正文 1.9（疏朗）

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 40 / 64 / 96 px（多用大留白）
- 页面最大宽度 860px，水平居中
- 区块间 96px，区块内 40px

## 5. Layout & Composition

- 层级：大标题（42px 衬线）→ 一句对仗式副标题（17px, text-secondary）→ 朱砂印章式按钮
- 按钮：solid primary 朱砂，白字，直角（圆角 2px，印章感），padding 14px 36px
- 卡片：surface-alt 背景，1px 麦色细线边框，圆角 6px，padding 32px，禁止 box-shadow
- 可选用细墨线（1px border）作标题与正文的分隔

## 6. Components

- 按钮 hover：朱砂加深 `#9A2F24`，150ms ease
- 链接：primary 色，hover 加下划线
- 引注块：左侧 3px accent 黛青竖线 + surface-alt 背景

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）与链接下划线浮现。禁止弹跳、缩放、轮播、辉光等动效。

## 8. Voice & Brand

- 文案克制、有文气，可引诗句或四字短语；不使用营销感叹号、夸张副词（"顶级""爆款""颠覆"一律禁止）。

## 9. Anti-patterns

- 禁止无衬线标题（标题必须 serif 宋体族）
- 禁止阴影、辉光、霓虹、荧光、渐变
- 禁止大面积朱砂红（红仅作点缀与按钮）
- 禁止 emoji 装饰
- 禁止内容超出 860px 容器
