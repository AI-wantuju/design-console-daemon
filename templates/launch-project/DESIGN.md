# Design System: 发布会·暗场

> Category: event-launch
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

产品发布会暗场感。深空黑底 + 霓虹青/品红双强调 + 大字号极简标题，允许轻微辉光。设计意图：科技、隆重、一眼吸睛。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#22D3EE`（霓虹青，主 CTA、关键强调）
- surface: `#0A0A12`（深空黑，页面背景）
- surface-alt: `#12121E`（深蓝黑，卡片/分区背景）
- text-primary: `#F5F5F7`（近白，标题与正文）
- text-secondary: `#9CA3AF`（冷灰，次要文字）
- border: `#26263A`（深紫灰，分隔线、边框）
- accent: `#E879F9`（品红，辅助强调、标签）

禁止：纯白背景、黑色以外的浅色大面积、霓虹之外的荧光、渐变（仅允许同色系低透明度叠加）、厚重阴影。

## 3. Typography

- 字体族：标题 `-apple-system, "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif`；可选等宽点缀 `"JetBrains Mono", "Consolas", monospace`
- 字号刻度：标题 64px/40px（加粗，可瘦体字重 800），正文 19px，次要 15px，caption 13px
- 字重：标题 800，正文 400
- 行高：标题 1.1（紧），正文 1.7

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 48 / 80 / 128 px（舞台式大留白）
- 页面最大宽度 1100px，居中
- 区块间 128px，区块内 48px

## 5. Layout & Composition

- 层级：巨型标题（64px）→ 一句宣言式副标题（19px, text-secondary）→ 霓虹青主按钮
- 按钮：solid primary 霓虹青，深色字（#0A0A12），圆角 999px，padding 16px 40px
- 卡片：surface-alt 背景，1px border，圆角 12px，padding 40px，允许轻微辉光（0 0 24px rgba(34,211,238,.08)）
- 标签：accent 品红描边透明底

## 6. Components

- 按钮 hover：青提亮 `#67E8F9`，150ms ease
- 链接：primary 色，hover 加下划线
- 关键数字：accent 品红或 primary 青，加粗大号

## 7. Motion & Interaction

- 允许 hover 颜色变化与轻微辉光浮现（150ms ease）。禁止弹跳、轮播、频繁闪烁。

## 8. Voice & Brand

- 文案简短、宣言式、有冲击力；多短句；可适当使用"重新定义""此刻"等发布会话术；禁冗长说明。

## 9. Anti-patterns

- 禁止浅色背景（必须深色舞台）
- 禁止渐变（允许同色系低透明度叠加，如 rgba(34,211,238,.08)）
- 禁止霓虹色（青/品红）之外的彩色
- 禁止 emoji 装饰
- 禁止内容超出 1100px 容器
