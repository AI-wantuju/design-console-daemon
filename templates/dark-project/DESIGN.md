# Design System: Dark Futuristic

> Category: dark-futuristic
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

深色、未来感、高对比。深蓝黑底 + 青色/品红双强调色，等宽字体点缀营造"终端/科技仪表盘"气质。设计意图：科技、锐利、AI 原生。允许轻微辉光（glow）用于强调元素。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#22D3EE`（青色，主强调、按钮、链接）
- secondary: `#E879F9`（品红，次要强调、标签、图表点缀）
- surface: `#0B1220`（深蓝黑，页面背景）
- surface-alt: `#111A2E`（深蓝，卡片/分区背景）
- surface-raised: `#1A2540`（更亮一档，悬浮/输入框）
- text-primary: `#E6EDF7`（近白，标题）
- text-secondary: `#94A3B8`（灰蓝，正文次要）
- border: `#263449`（深蓝灰，分隔线、边框）
- success: `#34D399`（仅用于成功状态）

禁止：浅色背景（任何亮度高于 `#3A4A6B` 的底色）、纯白 `#FFF` 大面积使用、棕色/土色系、渐变（纯色或单色透明度除外）。

## 3. Typography

- 字体族：`-apple-system, "Segoe UI", "Microsoft YaHei", sans-serif`；强调数字/标签可用 `"Cascadia Code", "Consolas", monospace`
- 字号刻度：标题 36px/24px，正文 16px，次要 14px，caption 12px
- 字重：标题 600，正文 400；强调标签可用 500
- 行高：标题 1.25，正文 1.6

## 4. Spacing & Grid

- 间距刻度：4 / 8 / 16 / 24 / 32 / 48 px
- 页面最大宽度 1100px，水平居中
- 区块间 48px，区块内 24px

## 5. Layout & Composition

- 层级：大标题（36px）→ 一句副标题（16px, text-secondary）→ 行动按钮（primary 青色）
- 按钮：solid primary，深色文字 `#0B1220`，圆角 8px，padding 12px 28px；hover 时允许 `box-shadow: 0 0 16px rgba(34,211,238,.35)` 辉光
- 卡片：surface-alt 背景，1px border，圆角 12px，padding 24px；标题行可加品红小标签（uppercase 12px monospace）
- 可选：顶部一行 monospace 面包屑/状态栏（如 `~/workspace` 风格），强化终端感

## 6. Components

- 按钮 hover：辉光浮现 + 背景微亮 `#3BD8F0`，150ms ease
- 链接：primary 色；hover 下加下划线或辉光
- 标签（badge）：secondary 品红 12px monospace uppercase，表面 `rgba(232,121,249,.12)` 底

## 7. Motion & Interaction

- 允许 hover 辉光过渡（150ms ease）。禁止弹跳、缩放、旋转、轮播。

## 8. Voice & Brand

- 文案简洁、确定、科技向；可含英文技术词（AI、batch、pipeline）；不使用夸张感叹词；不使用营销大词。

## 9. Anti-patterns

- 禁止浅色/白色背景
- 禁止棕色土色系
- 禁止全彩渐变（background-image 渐变仅限单色到透明的辉光）
- 禁止圆角胶囊按钮（按钮必须 8px 直角感）
- 禁止 emoji 作为主装饰
- 禁止内容超出 1100px 容器
