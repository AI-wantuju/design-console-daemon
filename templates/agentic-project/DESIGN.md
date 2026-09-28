# Design System Inspired by OpenAI — 深色科技风改编

> Category: AI & LLM / Developer Platform
> 蓝本：`openai-project/DESIGN.md`。字阶、间距刻度、组件规格、圆角与动效规则**逐条保留**，只把明暗角色对调，得到一套深色科技风表面。

## 0. 与蓝本的关系（唯一的改动：明暗角色对调）

蓝本是一套「白底 + 墨黑字」的冷静编辑风。深色改编不动任何色值、不动任何刻度，只重新分配每个 token 落在哪一层。

| 蓝本角色 | 蓝本取值 | 深色改编取值 | 在新页面中的用途 |
|---|---|---|---|
| Primary background | `#ffffff` | `#0d0d0d` | 页面画布、代码块内嵌面 |
| Card surface | `#ffffff` / `#f5f5f5` | `#1a1a1a` | 卡片、控制台外框、收尾条带 |
| Ink（正文与 CTA 底色） | `#0d0d0d` | `#ffffff` | 展示级标题、主按钮底色 |
| Body text | `#3c3c3c` | `#c4c4c4` | 正文、卡片描述 |
| Secondary text | `#6e6e6e` | `#9b9b9b` | 元信息、说明、页脚链接 |
| Tertiary / decorative | `#c4c4c4` | `#6e6e6e` | **仅**装饰圆点与占位，不承载正文 |
| Hairline border | `#e5e5e5` | `#3c3c3c` | 分隔线、chip 描边、控制台内框 |
| Strong text / code | `#1a1a1a` | `#e5e5e5` | 代码正文、强调正文 |
| Brand accent | `#10a37f` | `#10a37f` | 不变：整个系统里唯一的彩色 |
| Accent hover / deep | `#0a7a5e` | `#0a7a5e` | 不变：代码高亮块底色 |
| Accent soft | `#e8f5f0` | `#e8f5f0` | 不变：只做浅底 chip 的底色 |

**色值白名单（页面里允许出现的全部十六进制颜色，共 12 个）：**
`#0d0d0d` `#1a1a1a` `#3c3c3c` `#6e6e6e` `#9b9b9b` `#c4c4c4` `#e5e5e5` `#ececec` `#ffffff` `#10a37f` `#0a7a5e` `#e8f5f0`

未在深色表面使用的蓝本 token：`#fafafa`（Mist）、`#f5f5f5`（Pearl）、`#ededed`（Border Soft）。它们在深色下没有对应层级，保留在规范中但不上色。

## 1. Visual Theme & Atmosphere

蓝本是「穿正装的研究实验室」。深色改编把它变成同一间实验室的夜间模式：画布是带轻微青调的近黑（`#0d0d0d`），卡片抬高一层到 `#1a1a1a`，两者之间靠表面明度而不是阴影分层。

科技感不来自发光和渐变，而来自三件事：**等宽字排版的结构信息**（endpoint、状态码、延迟、版本号）、**终端式的内嵌控制台**、以及**唯一的青色只出现在交互与强调的位置**。页面读起来应该像一份写得很好的 API 文档，而不是一张产品海报。

**Key Characteristics:**
- 近黑画布（`#0d0d0d`）+ 抬升一层的卡片面（`#1a1a1a`），用明度分层，不用阴影
- 头发丝分隔线 `#3c3c3c`；白底时它是「没有颜色」，深色下它是「结构」
- Söhne / Inter 400–600，权重上限 600，层级靠字号与颜色而非字重
- Signifier 衬线只出现在展示级标题与引言，产品控件全部无衬线
- 等宽字承担标签、endpoint、度量与代码——科技感的唯一来源
- 青色 `#10a37f` 是系统里唯一的彩色，只用于链接、图标、圆点与代码高亮
- 代码块用两层底色（`#1a1a1a` 卡内嵌 `#0d0d0d`），高亮块用 `#0a7a5e` 底 + 白字
- 无渐变、无发光、无重阴影、无彩色终端点；终端窗口的圆点也是灰的

## 2. Color Palette & Roles（深色角色）

### Surface（表面层级，自下而上三层）
- **Canvas**（`#0d0d0d`）：页面背景、代码块、控制台内嵌面。
- **Elevated**（`#1a1a1a`）：卡片、控制台外框、收尾条带。
- **Divider**（`#3c3c3c`）：分隔线、chip 描边、控制台内框、装饰圆点。

### Text（文字层级，自上而下四层）
- **Text 1**（`#ffffff`）：展示标题、区块标题、主按钮文字底色。
- **Text 2**（`#c4c4c4`）：正文、卡片描述、代码默认色（代码用 `#e5e5e5`）。
- **Text 3**（`#9b9b9b`）：元信息、说明、页脚链接、标签。
- **Text 4**（`#6e6e6e`）：仅装饰圆点与不可交互的占位，**对比度 3.7:1，不得承载正文**。
- **Text strong**（`#e5e5e5`）：代码正文、需要压过正文一档的强调。

### Accent（唯一彩色）
- **Teal**（`#10a37f`）：链接、图标、状态圆点、代码中的结构关键字。对 `#0d0d0d` 对比度 5.8:1。
- **Teal Deep**（`#0a7a5e`）：代码高亮块底色（配 `#ffffff`，5.3:1）、按钮按下态。
- **Teal Soft**（`#e8f5f0`）：只做浅底 chip 的底色（配 `#0d0d0d` 文字，16.9:1）。全页只用一次。

### Neutrals
- **Cloud**（`#ececec`）：主按钮 hover 底色。

## 3. Typography Rules

### Font Family
- **Display / Editorial**: `Signifier`, fallback `'Source Serif Pro', Georgia, 'Songti SC', 'Noto Serif SC', serif`
- **Body / UI**: `Söhne`, fallback `Inter, system-ui, -apple-system, 'Segoe UI', 'PingFang SC', sans-serif`
- **Code / Mono**: `Söhne Mono`, fallback `ui-monospace, 'JetBrains Mono', Menlo, Consolas, monospace`

### Hierarchy（与蓝本完全一致）

| Role | Font | Size | Weight | Line Height | Letter Spacing | Notes |
|------|------|------|--------|-------------|----------------|-------|
| Display | Signifier | 56px | 400 | 1.08 | -0.02em | Hero 标题、引言 |
| H1 | Söhne | 40px | 600 | 1.15 | -0.01em | 度量数字、价格 |
| H2 | Söhne | 28px | 600 | 1.2 | -0.005em | 区块标题 |
| H3 | Söhne | 20px | 600 | 1.3 | normal | 卡片标题 |
| Body Large | Söhne | 18px | 400 | 1.6 | normal | Lede 段落 |
| Body | Söhne | 16px | 400 | 1.65 | normal | 正文 |
| Body Small | Söhne | 14px | 400 | 1.55 | normal | 卡片正文、密集 UI |
| Caption | Söhne | 13px | 500 | 1.4 | 0.01em | 元信息、徽章 |
| Label | Söhne | 12px | 500 | 1.3 | 0.04em | Eyebrow、全大写标签 |
| Code | Söhne Mono | 14px | 400 | 1.7 | normal | 代码块、终端输出 |

### Principles
- **字重上限 600**。层级来自字号与颜色，不来自加粗。
- **衬线给灵魂，无衬线给系统**：Signifier 只出现在 Hero 标题与用户引言。
- **等宽字是科技信号的载体**：endpoint、状态码、延迟、版本号、代码。
- 展示级负字距 -0.02em；到 16px 归零。

### 代码着色规则（只用白名单内的颜色）
- 结构关键字与 JSON 键 → `#10a37f`
- 字符串与内容值 → `#c4c4c4`
- 注释与协议头 → `#9b9b9b`
- 其余 → `#e5e5e5`
- 高亮块（唯一一处强调）→ 底 `#0a7a5e`，字 `#ffffff`

## 4. Component Stylings

### Buttons
**Primary** — 底 `#ffffff`，字 `#0d0d0d`，padding 10px 18px，圆角 12px，hover 底 `#ececec`。
**Secondary** — 底透明，字 `#ffffff`，描边 1px `#3c3c3c`，padding 10px 18px，圆角 12px，hover 底 `#1a1a1a`、描边 `#6e6e6e`。
**Quiet** — 透明底，字 `#9b9b9b`，hover 字 `#ffffff`、底 `#1a1a1a`。
**Focus** — `outline: 2px solid #10a37f; outline-offset: 2px` + `box-shadow: 0 0 0 3px rgba(16,163,127,0.12)`，对所有可交互元素生效。

### Cards
底 `#1a1a1a`，无描边，圆角 16px，padding 24–32px。hover 时描边转为 `#3c3c3c`（`border:1px solid transparent` 预留位置，避免布局跳动）。蓝本的 `0 4px 16px rgba(13,13,13,0.06)` 在深色下不可见，保留但由描边承担 hover 反馈。

### Console（终端式内嵌面）
外框 `#1a1a1a`；头部与脚部 `#1a1a1a`，各配 1px `#3c3c3c` 分隔线；主体两栏为 `#0d0d0d`，中缝 1px `#3c3c3c`。终端圆点用三层灰（`#3c3c3c` / `#6e6e6e` / `#9b9b9b`），不用红黄绿。

### Pills & Tags
透明底，描边 1px `#3c3c3c`，字 `#c4c4c4`，padding 4px 10px，圆角 9999px，字号 12/500。
**Stamp（唯一浅底 chip）**：底 `#e8f5f0`，字 `#0d0d0d`，全页只用一次。

### Inputs
深色下不存在真实表单控件；需要时按蓝本规格对调：底 `#0d0d0d`，描边 `#3c3c3c`，focus 描边 `#10a37f`。

## 5. Spacing & Layout

- **Base unit**: 4px。刻度 4, 8, 12, 16, 24, 32, 48, 64, 96, 128。
- **Container**: max-width 1200px，桌面 48px、移动 24px 边距。
- **Section rhythm**: 桌面区块间 96–128px，移动 64px。
- **Grid**: 桌面 12 栏、卡片栅格 2/3/4 列，间距 24px。
- **分层而非阴影**：表面明度差承担层级，分隔线只在组件内部出现。

## 6. Motion

- **Duration**: hover 150–220ms；布局过渡 280–360ms。
- **Easing**: `cubic-bezier(0.16, 1, 0.3, 1)`。
- **Restraint**: 无视差、无滚动劫持、无循环动画、无打字机效果。只做淡入与位移。
- `prefers-reduced-motion` 下过渡降到 1ms。

## 7. Usage Guardrails

- 明暗对调是**唯一**的改动。不要顺手改字号、圆角或间距——蓝本的克制就是它的身份。
- 青色只出现在交互与强调位置（链接、图标、圆点、代码关键字、高亮块）。青色面积一旦变大，页面立刻从「实验室」变成「营销页」。
- 深色下不要用阴影表达层级，用 `#0d0d0d` 与 `#1a1a1a` 的表面差、以及 `#3c3c3c` 分隔线。
- 科技感由等宽字与终端部件提供，不要引入发光边框、网格背景、扫描线等装饰。

## 8. Anti-patterns

- 禁止渐变（含 `linear-gradient` / `radial-gradient` 做的网格、光晕、遮罩）。
- 禁止 token 之外的任何颜色；禁止用青色大面积铺底。
- 禁止 700 及以上字重。
- 禁止 emoji 装饰、彩色终端圆点、发光阴影。
- 禁止 `<table>` 布局。
- 禁止把 `#6e6e6e` 用在正文（对比度 3.7:1，未达 4.5:1）。
- 禁止循环动画、打字机效果与滚动劫持。
- 禁止把同一套字号字重铺满全页，层级必须可见。
