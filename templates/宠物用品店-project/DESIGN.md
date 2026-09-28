# 宠物用品店
> Category: custom

## 1. Visual Theme & Atmosphere

暖色温馨：以奶油米底 + 陶土橙为主，靠色块分层而不是投影，边缘一律 1px 暖砂描边。气质是"邻居家的靠谱宠物店"——安静、有温度、信息直白，不做花哨动效。

## 2. Color Tokens

- --primary: #B85C2E（陶土橙，主按钮与价格）
- --primary-dark: #94441F（按钮 hover、小字强调，白底对比 6.76:1）
- --primary-soft: #F7E3D6（徽标底色）
- --accent: #9A6212（评分星，白底对比 5.08:1）
- --bg: #FFFFFF（卡片底、产品区白带）
- --bg-warm: #FDF6EF（页面底色）
- --surface-warm: #FBEDE1（图标底、商品图区）
- --border: #E7D9CB（1px 描边）
- --text: #1A1B1C
- --text-muted: #6B5B4E（奶油底对比 6.06:1）

说明：原 token 表的 `--primary: #4C8DFF` 为系统占位值。本页按"整体暖色温馨"要求改锚为陶土橙，冷蓝保留为 `--accent-blue: #4C8DFF` 备用，本页未使用。

## 3. Typography

- 标题：系统无衬线 600
- 正文：系统无衬线 400
- 字阶：12 / 14 / 16 / 18 / 24 / 32 / 44
- 行高：标题 1.25，正文 1.7；正文不小于 16px

## 4. Spacing & Layout

- 容器 960px，间距 8 的倍数
- 间距刻度：8 / 16 / 24 / 32 / 40 / 48 / 64 / 80
- 区块纵向内边距 80px，栅格 3 列、列间距 24px，≤720px 塌为单列

## 5. Components

- 圆角：8 / 12 / 16 / 999
- 按钮：胶囊形，主按钮陶土橙底白字，次按钮透明底 + 1px 描边；focus-visible 2px 描边 + 2px 偏移
- 卡片：白底 + 1px 描边 + 16px 圆角 + 24px 内边距，无阴影
- 商品卡：图区用 --surface-warm 色块，价格 24px/600 用 --primary，购买按钮通栏
- 图标：48×48 色块内嵌 28px 线性 SVG，线宽 1.8，currentColor

## 6. Imagery

不使用实拍图与外链图片，全部用内联线性 SVG（碗、包、牵引绳、叶、心、货车）配合暖色块表达，保证离线可渲染。

## 7. Tone of Voice

- 第二人称"你"，讲具体事实（克重、时长、检测项），不喊口号
- 不用"最/第一/绝对"这类绝对化用语，不用感叹号堆叠
- 按钮用动词短语：立即选购 / 加入购物车

## 8. Anti-Patterns

- 禁止渐变（linear-gradient / radial-gradient）
- 禁止 box-shadow 与彩色投影，层次只用描边和色块
- 禁止 emoji 当图标，禁止外链图片
- 禁止玻璃拟态 / backdrop-filter 模糊
- 禁止 table 布局，禁止裸色词（颜色必须绑定 token 名）
- 禁止无对比度的浅色文字，禁止装饰性跳动动画

## 9. Accessibility

- 正文对比度 ≥ 4.5:1（--text-muted 于奶油底 6.06:1）
- 图形与图标对比度 ≥ 3:1
- 按钮与链接有 :focus-visible 可见焦点环
- 尊重 prefers-reduced-motion，关闭过渡与平滑滚动
- 装饰性 SVG 加 aria-hidden，语义用 header/main/section/footer + 单 h1
