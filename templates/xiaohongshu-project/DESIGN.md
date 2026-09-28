# Design System: 小红书·种草

> Category: social-xiaohongshu
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体或间距。

## 1. Visual Theme & Atmosphere

小红书种草笔记风。暖白底 + 薯红强调 + 深灰文字，圆角卡片、大字大图、轻拟态。设计意图：亲切、种草、有生活感。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#FF2442`（薯红，CTA、标签、关键数字）
- surface: `#FFFDF9`（暖白，页面背景）
- surface-alt: `#F7F3EE`（浅米灰，卡片背景）
- text-primary: `#333333`（深灰，标题与正文）
- text-secondary: `#8A8A8A`（浅灰，辅助文字、角标）
- border: `#EDE7E0`（浅米线，卡片描边）
- accent: `#FF8A3D`（暖橙，仅用于价格、折扣标签）

禁止：纯黑 `#000`、冷淡蓝灰大面积、荧光绿、厚重阴影（只允许轻拟态微阴影）。

## 3. Typography

- 字体族：全部 `-apple-system, "PingFang SC", "Microsoft YaHei", sans-serif`（无衬线）
- 字号刻度：标题 34px/26px（加粗），正文 17px，次要 14px，caption 12px
- 字重：标题 700，正文 400
- 行高：标题 1.35，正文 1.8

## 4. Spacing & Grid

- 间距刻度：8 / 12 / 16 / 24 / 32 / 48 px
- 页面最大宽度 720px，卡片流式排布
- 区块间 32px，区块内 24px

## 5. Layout & Composition

- 层级：大字标题（34px）→ 一句种草式导语 → 大图 → 薯红胶囊 CTA
- 按钮：solid primary 薯红，白字，圆角 999px（胶囊），padding 14px 32px
- 卡片：surface-alt 背景，1px 米线描边，圆角 16px，padding 24px，允许 `box-shadow: 0 2px 8px rgba(0,0,0,.04)`（轻拟态）
- 标签：primary 红底白字小号圆角胶囊

## 6. Components

- 按钮 hover：薯红加深 `#E01F3C`，150ms ease
- 链接：primary 色，hover 加下划线
- 价格标签：accent 暖橙加粗

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）。禁止弹跳、缩放、轮播等动效。

## 8. Voice & Brand

- 文案亲切、有生活感、口语化；可用"姐妹们""亲测""绝了"等种草语（适度）；禁硬广腔。

## 9. Anti-patterns

- 禁止冷淡灰蓝大面积、荧光绿
- 禁止厚重阴影（> 0.04 不透明度即违例）
- 禁止衬线大标题
- 禁止 emoji 堆砌（每屏 ≤ 2 个）
- 禁止内容超出 720px 容器
