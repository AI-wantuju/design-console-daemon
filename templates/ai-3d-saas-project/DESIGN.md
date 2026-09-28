# ai-3d-saas
> Category: custom
> Direction: Dark Tech（深色科技）

## 1. Visual Theme & Atmosphere

面向游戏、电商与工业设计团队的 AI 三维建模 SaaS。整体基调是"深夜里的三维视口"：极深的海军蓝黑底（#0B0F1A 系）压住画面，紫蓝霓虹渐变只用在需要牵引视线的地方——主标题关键词、主按钮、推荐档位描边、视口辉光。信息层以玻璃拟态卡片承载：4.5% 白色透明面 + 1px 微光描边，边缘比中心亮，模拟屏幕发光散射。点缀元素来自建模工具本身的语言：mono 字体的视口状态栏、token 消耗日志、三角面数、帧率、区域与构建号，让页面读起来像一台正在运行的工作站，而不是一张宣传海报。

三条氛围规则：
1. **霓虹是稀缺资源**——同一屏内发光元素不超过 3 处，避免整页发紫。
2. **深度靠层级不靠阴影堆叠**——背景（#070A12）→ 卡片（玻璃面）→ 高亮面（7% 玻璃面）三层足矣。
3. **数据即装饰**——不用插画和 emoji，用真实的数值、格式名、状态点填充留白。

## 2. Color Tokens

### 背景层
- `--bg-deep: #070A12`（页面最底、页脚）
- `--bg-base: #0B0F1A`（主背景）
- `--bg-elevated: #111729`（抬升面：定价卡、内嵌面板）
- `--bg-glass: rgba(255,255,255,0.045)`（玻璃卡片面）
- `--bg-glass-strong: rgba(255,255,255,0.07)`（悬停/选中态玻璃面）

### 描边层
- `--stroke-glass: rgba(255,255,255,0.10)`（卡片默认微光描边）
- `--stroke-strong: rgba(255,255,255,0.18)`（悬停描边、分隔强调）

### 强调色
- `--primary: #4C8DFF`（主蓝，唯一的功能色）
- `--neon-purple: #A855F7`（霓虹紫，与主蓝构成渐变）
- `--neon-cyan: #22D3EE`（青色，仅用于三维线框与数据点）
- `--gradient-neon: linear-gradient(120deg, #4C8DFF 0%, #A855F7 100%)`（装饰性渐变：描边、辉光、大字号标题文字）
- `--gradient-cta: linear-gradient(120deg, #2F6BE0 0%, #8B3FE0 100%)`（实心按钮底色，压暗以保证白字对比度）
- `--gradient-text: linear-gradient(100deg, #8FB8FF 0%, #C79BFF 100%)`（仅用于 ≥32px 的标题文字）

### 文字层
- `--text-primary: #EDF1FB`（标题、关键数字）
- `--text-secondary: #A9B6D4`（正文）
- `--text-muted: #7C89AC`（辅助说明、标签，对比度 5.5:1）
- `--text-on-accent: #FFFFFF`（渐变按钮与徽标上的文字）

### 语义色
- `--success: #34D399`（终端成功行、系统状态点）
- `--warning: #FBBF24`（配额告警）

### 辉光与阴影
- `--glow-blue: 0 0 32px rgba(76,141,255,0.35)`
- `--glow-purple: 0 0 48px rgba(168,85,247,0.30)`
- `--shadow-card: 0 24px 64px rgba(3,6,16,0.55)`

## 3. Typography

- `--font-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Microsoft YaHei", sans-serif`
- `--font-mono: ui-monospace, "SF Mono", "JetBrains Mono", Consolas, monospace`
- 标题字重 600，正文 400；mono 仅用于数据与终端元素，字重 500，字距 0.02em。

字号刻度（桌面 / 移动用 clamp 下限）：
- `--fs-display: clamp(40px, 5.2vw, 64px)` / 行高 1.08 / 字距 -0.02em（Hero 主标题）
- `--fs-h2: clamp(28px, 3.2vw, 40px)` / 1.18（区块标题）
- `--fs-h3: 20px` / 1.4（卡片标题、定价档名）
- `--fs-body: 16px` / 1.7（正文）
- `--fs-small: 14px` / 1.6（卡片描述、页脚链接）
- `--fs-micro: 12px` / 1.5（mono 标签、徽标）

## 4. Spacing & Layout

- 间距基数 8px：`--space-1: 8px` / `--space-2: 16px` / `--space-3: 24px` / `--space-4: 32px` / `--space-5: 48px` / `--space-6: 64px` / `--space-7: 96px` / `--space-8: 128px`
- `--container: 1200px`，左右安全边距 `--gutter: 24px`
- 区块纵向节奏：上下 `--space-8`（移动端 `--space-6`）
- 栅格：12 列；能力六宫格 3 列（<1024px 2 列，<640px 1 列）；定价 3 列（<1024px 1 列）；Hero 双栏 1.05fr / 1fr（<1024px 单栏）
- 圆角：`--radius-sm: 8px` / `--radius-md: 12px` / `--radius-lg: 20px` / `--radius-pill: 999px`

## 5. Components

- **主按钮**：`--gradient-cta` 底色 + 白字 + `--radius-md`，常态带 `--glow-blue`；hover 提升 1px 并把辉光换成 `--glow-purple`。
- **次按钮**：透明底 + `--stroke-strong` 描边 + `--text-primary` 文字；hover 面变 `--bg-glass`。
- **玻璃卡片**：`--bg-glass` 面 + 1px `--stroke-glass` 描边 + `backdrop-filter: blur(18px)` + `--radius-lg`；hover 面升为 `--bg-glass-strong`、描边升为 `--stroke-strong`。
- **推荐档位卡**：在玻璃卡基础上用 `--gradient-neon` 做 1px 渐变描边（双层背景实现，不用额外伪元素）并加 `--glow-purple`。
- **徽标 / mono 标签**：`--radius-pill`，mono 12px，前置状态点用 `--success` 或 `--primary`。
- **终端块**：`--bg-deep` 面 + mono 14px，行为前缀 `>`（`--primary`）、`✓`（`--success`）、`→`（`--neon-cyan`）。
- **FAQ 项**：原生 `<details>/<summary>`，玻璃卡承载，展开态描边转 `--primary`。
- **视口预览**：玻璃外框 + 内嵌三维线框 SVG + 悬浮 mono 数据片。

## 6. Imagery

- 不使用照片与位图插画。三维场景用**手写 SVG 线框**表达：透视地面网格（`--neon-cyan` 低透明度）、多面体网格（紫蓝渐变填充 + 亮边线）、轨道环、顶点控制点、选择框角标。
- 图标一律为 1.6px 描边的线性 SVG，尺寸 24px，颜色继承 `--primary` 或 `--text-secondary`；禁止 emoji 与彩色贴图图标。
- 允许的背景装饰只有两种：`--primary` / `--neon-purple` 的大半径径向光晕，以及 1px 的网格底纹。

## 7. Tone of Voice

- 第二人称、动词开头、给数字。写"60 秒生成带 UV 与 PBR 材质的网格模型"，不写"极速体验，畅享未来"。
- 中文为主，专有名词与技术单位保留英文原文（glTF、PBR、SSO、SLA），不强行翻译。
- 单句不超过 40 字；描述能力时先说结果再说机制。
- 禁用词：赋能、闭环、颠覆、极致、一键搞定、未来已来。

## 8. Anti-Patterns

- 禁止无对比度的浅色文字；`--text-muted` 已是对比度下限（5.5:1），不得再调暗。
- 禁止用 `--gradient-neon`（亮色渐变）直接承载白色小字；实心按钮一律用 `--gradient-cta`。
- 禁止 emoji 装饰、禁止用 `<table>` 做布局、禁止在正文使用渐变文字（仅 ≥32px 标题可用）。
- 禁止同一屏出现 3 处以上霓虹辉光。
- 禁止纯黑 `#000` 背景与纯白 `#FFF` 大色块。
- 禁止无 `aria-label` 的纯图标按钮。

## 9. Accessibility

- 正文对比度 ≥ 4.5:1，大字 ≥ 3:1；关键组合：`--text-secondary` on `--bg-base` ≈ 9.4:1，`--text-muted` ≈ 5.5:1，白字 on `--gradient-cta` ≥ 4.8:1。
- 键盘可达：全站 `:focus-visible` 用 2px `--primary` 外描边 + 2px 偏移；提供跳转到主内容的 skip link。
- 语义结构：`header/nav/main/section/footer` + 每个 section 有可读标题；纯装饰 SVG 标 `aria-hidden="true"`。
- 尊重 `prefers-reduced-motion`：关闭所有位移与脉冲动画。
- 正文最小 14px；可点击目标最小 44×44px。
