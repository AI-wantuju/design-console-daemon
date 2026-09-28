# Design System: Warm Editorial

> Category: editorial-warm
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

温暖、人文、杂志感。奶油底色 + 深棕文字 + 珊瑚色强调，衬线标题营造编辑/出版气质。设计意图：可信、亲近、有内容温度。允许极淡的柔和阴影（杂志卡片感）。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#E2725B`（珊瑚橙，强调、按钮、链接）
- surface: `#FDF8F0`（奶油白，页面背景）
- surface-alt: `#F5EBDD`（浅杏，卡片/分区背景）
- text-primary: `#3D2C23`（深棕，标题）
- text-secondary: `#7A6657`（暖灰棕，正文次要）
- border: `#E4D5C3`（浅褐，分隔线、边框）
- accent: `#2E7D6B`（墨绿，仅用于辅助强调、引注）

禁止：纯黑 `#000`、纯白 `#FFF`、冷蓝 `#2563EB` 系、霓虹色、高饱和荧光色。

## 3. Typography

- 字体族：标题 `Georgia, "Times New Roman", "Noto Serif SC", serif`；正文 `-apple-system, "Segoe UI", "Microsoft YaHei", sans-serif`
- 字号刻度：标题 40px/28px（serif），正文 17px，次要 14px，caption 12px
- 字重：标题 700，正文 400
- 行高：标题 1.25，正文 1.75（宽松阅读）

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 32 / 48 / 64 px
- 页面最大宽度 840px，水平居中（阅读窄栏）
- 区块间 64px，区块内 32px

## 5. Layout & Composition

- 层级：大标题（40px serif）→ 一句引语式副标题（17px, text-secondary, 可斜体）→ 行动按钮（primary 珊瑚）
- 按钮：solid primary，白字，圆角 999px（胶囊），padding 14px 32px
- 卡片：surface-alt 背景，1px border，圆角 4px（克制的直角感），padding 32px，允许 `box-shadow: 0 1px 3px rgba(61,44,35,.08)`
- 可选用装饰性细线（1px border）分隔标题与正文

## 6. Components

- 按钮 hover：珊瑚加深 `#C95A44`，150ms ease
- 链接：primary 色，hover 加下划线
- 引注块：左侧 3px accent 墨绿竖线 + surface-alt 背景

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）与链接下划线浮现。禁止弹跳、缩放、轮播等花哨动效。

## 8. Voice & Brand

- 文案温暖、克制、有编辑感；可适当使用"我们"；不使用营销感叹号和夸张副词（"顶级""爆款""颠覆"等一律禁止）。

## 9. Anti-patterns

- 禁止冷色系（蓝、青、紫）作主色
- 禁止纯黑纯白背景
- 禁止霓虹、荧光、渐变
- 禁止无衬线标题（标题必须 serif）
- 禁止 emoji 装饰
- 禁止内容超出 840px 容器
