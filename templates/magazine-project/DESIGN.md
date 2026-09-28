# Design System: 杂志·编辑部

> Category: editorial-magazine
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

都市杂志编辑感。纯白底 + 近黑文字 + 单一国际红强调，大字号衬线标题、多栏栅格。设计意图：摩登、锐利、内容为王。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#C8102E`（国际红，强调、头条标签、CTA）
- surface: `#FFFFFF`（纯白，页面背景）
- surface-alt: `#F4F4F2`（浅暖灰，卡片/分区背景）
- text-primary: `#111111`（近黑，标题）
- text-secondary: `#555555`（中灰，正文次要）
- border: `#DCDCDC`（浅灰，分隔线、边框）
- accent: `#0057B8`（克莱因蓝，仅用于数字索引、页脚）

禁止：纯黑以外的花哨色作大面积、霓虹/荧光、渐变、厚重阴影。

## 3. Typography

- 字体族：标题 `Georgia, "Times New Roman", "Noto Serif SC", serif`；正文 `-apple-system, "Segoe UI", "Microsoft YaHei", sans-serif`
- 字号刻度：标题 56px/36px（serif 加粗），导语 20px，正文 17px，次要 14px，caption 12px
- 字重：标题 800，正文 400
- 行高：标题 1.15（紧），正文 1.75

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 40 / 64 / 96 px
- 页面最大宽度 1080px，多栏栅格（正文两栏可选）
- 区块间 80px，区块内 40px

## 5. Layout & Composition

- 层级：特大标题（56px）→ 导语（20px, text-secondary）→ 红色头条标签 → 内容
- 按钮：solid primary 国际红，白字，直角（圆角 0px，杂志印刷感），padding 14px 32px
- 卡片：surface-alt 或纯白 + 1px border，圆角 0px，padding 32px
- 头条标签：primary 红底白字小号全大写

## 6. Components

- 按钮 hover：红加深 `#A40D26`，150ms ease
- 链接：primary 色，hover 加下划线
- 数字索引：accent 克莱因蓝大号数字（如 01/02/03）

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）。禁止弹跳、缩放、轮播等动效。

## 8. Voice & Brand

- 文案利落、有观点、编辑腔；短句、强动词；可适度使用反问与断言；避免过度感叹号。

## 9. Anti-patterns

- 禁止圆角卡片（> 4px 即违例，杂志印刷应直角）
- 禁止渐变、厚重阴影、霓虹
- 禁止超过两种强调色（红/蓝仅限指定用法）
- 禁止 emoji 装饰
- 禁止内容超出 1080px 容器
