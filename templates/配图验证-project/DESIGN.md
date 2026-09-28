# 余烬烘焙工坊
> Category: custom

## 1. Visual Theme & Atmosphere

深夜的烘焙工坊：深棕近黑的底色，只有烘焙机与吧台是亮的。整体气质是「手作、专注、有温度但不喧闹」——大面积留白（留黑），直线条与细边框，暖琥珀色只用在真正需要被看到的地方（CTA、关键数据、曲线）。配图分两级：Hero 主视觉是照片级大图（微距咖啡豆），其余配图是内联线性插画——细线勾形 + 琥珀与奶油色描边，少量实心色块表现咖啡液、豆子与火光。不使用外链图片与图库素材。

## 2. Color Tokens

- --bg: #12100E
- --surface: #1B1815
- --surface-2: #241F1B
- --line: #332C26
- --line-field: #75655A
- --text: #F4EFE6
- --text-muted: #A79E92
- --primary: #E3A65B
- --primary-strong: #C9863A
- --primary-ink: #17130E
- --roast-light: #C79A6B
- --roast-medium: #8C5A33
- --roast-dark: #4A2E1E
- --cream: #E8DCC6

派生记号（不是新颜色，只用于照片蒙版的透明度写法）：`--bg-rgb: 18,16,14`、`--primary-rgb: 227,166,91`

## 3. Typography

- 标题：系统无衬线 600
- 正文：系统无衬线 400
- 字号刻度：12 / 14 / 16 / 20 / 22 / 34 / 52
- 行高：标题 1.15，正文 1.7
- 字距：标题 -0.02em，正文 0
- 数字与参数用 `font-variant-numeric: tabular-nums`

## 4. Spacing & Layout

- 容器 960px，间距 8 的倍数
- 间距刻度：8 / 16 / 24 / 32 / 48 / 64 / 96 / 128
- 圆角刻度：8 / 12 / 20 / 999
- 分区垂直内边距 96px，标题到正文 16px，正文到操作区 32px
- 断点 860px：多列降为单列

## 5. Components

- 主按钮：底色 `--primary`，文字 `--primary-ink`，圆角 999，高 48px
- 次按钮：透明底，1px `--line-field` 边框，文字 `--text`
- 卡片：底 `--surface`，1px `--line` 边框，圆角 20，内边距 32
- 标签：圆角 999，文字 `--primary`，1px `--primary` 半透明边框
- 数据行 / 参数行：`--text-muted` 小字标签 + `--text` 数值，1px `--line` 分隔
- 配图容器：底 `--surface-2`，圆角 20，内部 SVG 居中，四周 32 内边距
- Hero 主视觉：全出血大图（内联 SVG，`preserveAspectRatio="xMidYMid slice"` 裁切），桌面最小高度 720px；文字压在 `--bg` 蒙版不透明度 ≥ 0.9 的区域内，蒙版由 0.98 递减到 0.08

## 6. Imagery

- 全部使用内联 SVG，禁止外链图片与图库素材。
- Hero 主视觉 = 照片级大图：微距咖啡豆特写，逐层渲染体积光、接触阴影、景深虚化、暖色散景、胶片颗粒、暗角。所有 fill / stroke / stop-color 只取 token；明暗与色彩过渡由 `stop-opacity` 与图层叠加派生，不引入新色值。
- Hero 之外的配图 = 线性插画：线宽 2 / 3，端点 round；暖光用低对比径向渐变（不透明度 ≤ 0.22）。
- 三类必备视觉元素：手冲器具（V60 滤杯 / 鹅颈壶 / 注水）、烘焙设备（鼓式烘焙机 / 火候）、咖啡豆（豆形 + 中缝，按烘焙度换色）。
- 装饰性 SVG 加 `aria-hidden="true"`；主视觉与承载信息的 SVG 用 `role="img"` + `<title>` / `<desc>`。
- 配图管线：换成 AI 生成照片时，把 Hero 主视觉元素改为 `<img src="…" data-image-prompt="英文提示词">`，由运行时注入本地图片；未配置图像凭证时会被降级成灰度占位块。

## 7. Tone of Voice

- 具体、克制：只写能验证的事实（温度、克数、时间、产地、处理法）
- 禁用空词：匠心、极致、臻选、赋能
- 句子短，一句一件事；标题不超过 20 字

## 8. Anti-Patterns

- 禁止无对比度的浅色文字
- 禁止 emoji 作为装饰性图标
- 禁止大面积纯黑 `#000` 铺底
- 禁止玻璃拟态（backdrop-blur 卡片）与霓虹发光
- 禁止用 `<table>` 做布局
- 禁止超过两行的居中长段落

## 9. Accessibility

- 正文对比度 ≥ 4.5:1
- 交互控件边框与焦点环 ≥ 3:1（焦点环用 `--primary`，2px）
- 键盘可达：跳过导航链接、可见焦点态、语义化标题层级
- 尊重 `prefers-reduced-motion`
