# Design System: 政务·庄重

> Category: civic-formal
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

政务机构、正式严肃。政务蓝 + 白底 + 深灰文字，规整栅格，高对比度无障碍优先。设计意图：可信、规范、一目了然。禁止装饰性元素与花哨排版。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#1B4F8A`（政务蓝，主按钮、标题强调、链接）
- surface: `#FFFFFF`（纯白，页面背景）
- surface-alt: `#F3F6FA`（极浅蓝灰，表格/分区背景）
- text-primary: `#1F2937`（深蓝灰，标题与正文）
- text-secondary: `#4B5563`（中灰，次要文字）
- border: `#D1D9E4`（浅灰蓝，边框、分隔线）
- danger: `#B42318`（警示红，仅用于错误提示、警示标注）

禁止：纯黑 `#000` 作大面积、霓虹/荧光色、渐变、阴影、装饰图案。

## 3. Typography

- 字体族：全部 `-apple-system, "Segoe UI", "Microsoft YaHei", "PingFang SC", sans-serif`（无衬线，正文规整）
- 字号刻度：标题 32px/24px（无衬线加粗），正文 18px，次要 15px，caption 13px
- 字重：标题 700，正文 400
- 行高：标题 1.4，正文 1.8

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 32 / 48 / 64 px
- 页面最大宽度 960px，水平居中
- 区块间 48px，区块内 24px

## 5. Layout & Composition

- 层级：标题（32px）→ 导语（18px, text-secondary）→ 主按钮（solid primary）
- 按钮：solid primary 政务蓝，白字，圆角 4px，padding 12px 28px
- 卡片：surface-alt 背景，1px border，圆角 4px，padding 24px，无阴影
- 表格样式：border 细线、表头 surface-alt、行 hover 极浅蓝

## 6. Components

- 按钮 hover：政务蓝加深 `#143F73`，150ms ease
- 链接：primary 色，hover 加下划线
- 提示条：danger 红边框 + surface-alt 背景，用于警示文案

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）。禁止弹跳、缩放、轮播等动效。

## 8. Voice & Brand

- 文案正式、准确、简洁；避免口语化与营销话术；数字、日期、机构名务必准确。

## 9. Anti-patterns

- 禁止装饰图案、渐变、阴影、圆角过大（> 8px）
- 禁止口语化、感叹号堆叠、营销词汇
- 禁止低对比文字（正文必须 ≥ #4B5563 明度）
- 禁止 emoji 装饰
- 禁止内容超出 960px 容器
