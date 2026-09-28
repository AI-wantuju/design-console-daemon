# Design System: 见山茶事（新中式茶馆 · Contemporary Chinese Teahouse）

> Category: new-chinese-teahouse
> 本文件是设计唯一权威。任何生成的页面必须只使用以下 token，禁止引入未列出的颜色、字体、字号或间距。
> 本文件取代 `DESIGN-guochao-dianxin.md`（国潮点心铺，深红鎏金，已归档；归档件冻结，不得据其生成页面）。
> 同目录 `DESIGN-warm-editorial.md`、`brief.md`、`brief-canvas-bag.md`、`brief-guochao-dianxin.md` 均为旧系统历史留档，不受本文件约束；本次改版简报见 `brief-jianshan-chashi.md`。

## 1. Visual Theme & Atmosphere

墨绿为墙、米白为纸、青瓷为线。墨绿取自茶室墙面与老青砖的暗调，米白是宣纸与茶巾的颜色，青瓷色只在墨绿底上以 1px 线与小字露面；茶汤琥珀是唯一暖色，只出现在浅底的序号与竖线上，像茶渍一样少。

气质：一间白天开窗、晚上留灯的当代茶室。安静、干净、有分寸——器物摆在明面上，水温和时辰写在明面上，不做旧、不喧哗、不促销。允许留白大于内容：区块之间靠底色差与 1px 线分开，不靠阴影与卡片堆叠。主视觉由 CSS 几何、汉字与平涂 SVG 图版构成，不引入位图。

## 2. Color

只允许以下颜色（十六进制严格一致）：

- primary: `#1E3A32`（墨绿，hero 与预约区底色、浅底强调与链接）
- primary-deep: `#14261F`（深墨绿，字牌底、图版底、实心按钮 hover）
- moss: `#35604F`（苔绿，**仅**图版内部图形用；不作文字、不作任何 UI 底色）
- celadon: `#9CB8A6`（青瓷，墨绿底上的 1px 线、小字、图版线条；浅底上只作 1px 线）
- amber: `#8C5E26`（茶汤琥珀，`--color-surface` 上的序号文字、1px/3px 线）
- surface: `#F4F1E8`（米白，页面底色、卡片底、墨绿底上的文字）
- surface-alt: `#E9E5D8`（浅米，通栏备用底色、引注块底）
- text-primary: `#1B2A25`（墨，浅底标题与正文）
- text-secondary: `#57675E`（灰绿，浅底次要正文）
- border: `#D4D0C1`（浅米灰，浅底描边与分隔线）

四条硬规则：

1. 墨绿底（`--color-primary` / `--color-primary-deep`）上的文字只允许 `--color-surface` 与 `--color-celadon`；层级靠字号与字重区分。禁止在墨绿底上使用 `--color-text-secondary`（2.18:1）与 `--color-amber`（2.65:1）。
2. `--color-celadon` 在浅底上一律只作 1px 线与图版内部元素，不作文字（`#9CB8A6` on `#F4F1E8` = 1.89:1）。
3. `--color-amber` 只作 `--color-surface` 上的序号文字与 1px/3px 线；在 `--color-surface-alt` 上只作线（4.45:1 < 4.5，不作文字）；墨绿底上禁用。
4. `--color-moss` 只用于图版内部的图形块，不作文本、不作底色。

### 2.1 对比度实测（WCAG 2.1，页面验收时逐条核对）

| 前景 on 背景 | 比值 | 允许用途 |
| --- | --- | --- |
| `#F4F1E8` on `#1E3A32` | 10.90:1 | 墨绿底上任意字号正文（≥4.5 AA） |
| `#F4F1E8` on `#14261F` | 14.01:1 | 深墨绿底（字牌、图版注）上任意字号正文 |
| `#9CB8A6` on `#1E3A32` | 5.75:1 | 墨绿底上的 14px 标签、时序条目、1px 线 |
| `#9CB8A6` on `#14261F` | 7.40:1 | 深墨绿底上的字牌与图版注文字 |
| `#1B2A25` on `#F4F1E8` | 13.24:1 | 米白底标题与正文 |
| `#1B2A25` on `#E9E5D8` | 11.86:1 | 浅米底标题与正文 |
| `#57675E` on `#F4F1E8` | 5.30:1 | 米白底次要正文、卡片规格标签 |
| `#57675E` on `#E9E5D8` | 4.75:1 | 浅米底次要正文（≥4.5 AA） |
| `#1E3A32` on `#F4F1E8` | 10.90:1 | 浅底强调文字、小标签、链接 |
| `#1E3A32` on `#E9E5D8` | 9.77:1 | 浅米底区块标题 |
| `#8C5E26` on `#F4F1E8` | 4.97:1 | 米白底序号文字（14px，AA） |
| `#1E3A32` on `#9CB8A6` | 5.75:1 | 反白按钮 hover 态（青瓷底 + 墨绿字） |
| `#8C5E26` on `#E9E5D8` | 4.45:1 | 仅 ≥24px 常规或 ≥18.66px 加粗；本系统改作 1px/3px 线 |
| `#9CB8A6` on `#F4F1E8` | 1.89:1 | **禁止**（青瓷不作浅底文字） |
| `#8C5E26` on `#1E3A32` | 2.65:1 | **禁止**（琥珀不作墨绿底文字） |
| `#57675E` on `#1E3A32` | 2.18:1 | **禁止**（墨绿底不用灰绿） |

### 2.2 禁止

纯黑 `#000`、纯白 `#FFF`、暖色系作主色（红/橙/黄/棕，琥珀除外且仅限 §2 规则 3）、冷色系（蓝/紫）、霓虹荧光、渐变（含任何线性/径向渐变与光晕）、位图（外链图片、图库占位图、emoji）。

## 3. Typography

- 字体族：标题 `Georgia, "Times New Roman", "Noto Serif SC", "Songti SC", serif`；正文 `-apple-system, "Segoe UI", "Microsoft YaHei", sans-serif`
- 字号刻度：40px（页面主标题、字牌汉字，serif）、28px（区块标题，serif）、20px（卡片标题，serif）、17px（正文；事实值 serif 700）、14px（次要、标签、规格）、12px（caption、图版注、页脚）
- 字重：标题 700，正文 400
- 行高：标题 1.25，正文 1.75
- 字距：浅底小标签（eyebrow）与墨绿底标签用 `letter-spacing: .2em`；竖排字牌用 `.12em`；其余位置不额外加字距
- 中文标点用全角；数字与西文不额外加空格

## 4. Spacing & Grid

- 间距刻度：8 / 16 / 24 / 32 / 48 / 64 px；页面内所有尺寸取 8 的整数倍
- 内容容器 `max-width: 1040px` 水平居中；通栏区块背景满宽，其内容仍受 1040px 与页面左右 24px 内边距约束
- 区块间 64px，区块内 32px；通栏区块自身内边距 64px；卡片间距 24px；图版间 24px；图文两栏间距 48px

## 5. Layout & Composition

页面自上而下：

1. 顶栏（`--color-surface`，1px `--color-border` 下边线）：方形字标（40px 方块，`--color-primary` 底 + 米白单字）+ 品牌名（17px serif 700）+ 右侧门店事实（14px `--color-text-secondary`）
2. Hero（墨绿通栏）：左栏 14px 标签 → 40px serif 主标题 → 64px 宽 1px 青瓷细线 → 引语式副标题（17px 斜体）→ 预约按钮 → 14px 注脚；右栏竖排字牌（200×320，`--color-primary-deep` 底 + 1px 青瓷描边 + `writing-mode: vertical-rl` 四字 40px serif 青瓷 + 12px 青瓷落款）。Hero 底部为三格时序条（`dl`：1px 青瓷上边线 + 14px 青瓷标签 + 17px serif 米白值）
3. 茶品三款（`--color-surface-alt` 通栏）：区块头（14px 标签 + 28px serif 标题 + 14px 说明 + 1px `--color-border` 下边线）→ 三张卡片（`--color-surface` 底 + 1px border + 直角 + `padding: 32px`）：琥珀序号 壹/贰/叁 → 20px serif 卡片标题 → 14px 正文 → 1px 分隔 + 两格规格（12px 标签 + 14px 值）
4. 空间照片故事（`--color-surface` 通栏）：区块头 → 图文两栏（左：16:10 图版；右：两段 17px 正文 + 引注块）→ 双图版行（两张 4:3 图版）→ 三条事实（`dl`：1px 上边线 + 14px 标签 + 17px serif 值）
5. 预约 CTA（墨绿通栏，居中）：28px serif 标题 + 17px 说明 + 预约按钮 + 14px 注脚
6. 页脚（`--color-surface`，1px 上边线）：12px caption 一行

组件约定：

- 按钮：直角（圆角 2px），`padding: 14px 32px`；墨绿底上用反白按钮（米白底 + `--color-primary` 字 + 1px 青瓷描边），浅底上用实心按钮（`--color-primary` 底 + 米白字，10.90:1）
- 卡片：`--color-surface` 底、1px `--color-border`、圆角 0、`padding: 32px`；**全页无阴影**，层次一律靠 1px 线与底色差
- 引注块：左侧 3px `--color-amber` 竖线 + `--color-surface-alt` 底 + `padding: 24px`
- 图版（plate）：`figure` + 平涂 SVG（`role="img"` + `aria-label`）+ 内嵌图注；外框 1px `--color-border`，SVG 底 `--color-primary-deep`，图注 `padding: 24px`、上边线 1px 青瓷、12px 青瓷文字 + serif 米白图版号。**照片位规则**：每个图版即一个照片位（`data-photo-slot`），上线时把 `<svg>` 换成同尺寸 `<img>`，保留外框、图注与 `figcaption` 结构；占位图版只用本系统 token 平涂，禁止外链图片与图库占位图
- 全页只有一个转化动作（预约一席）：hero 与预约区各出现一次，hero 那次指向 `#reserve` 锚点，预约区那次是终点动作（`tel:`）；两处文案一致，不并列第二个动作（无「查看茶单」「立即购买」）
- 顶栏导航：不设导航链接（单页仅一个动作），只放门店事实

## 6. Components

- 按钮 hover：反白按钮 → `--color-celadon` 底（文字仍 `--color-primary`，5.75:1）；实心按钮 → `--color-primary-deep` 底（文字仍 `--color-surface`，14.01:1），150ms ease
- 焦点态：`:focus-visible` 2px 实线 outline，墨绿底上用 `--color-celadon`，浅底上用 `--color-primary`，`outline-offset: 2px`
- 链接：`--color-primary`，hover 加下划线
- 序号（壹/贰/叁）：14px serif，`--color-amber`（仅限米白卡片底）
- 图版注标签（`图版一`）：12px serif，`--color-surface`，与后接说明文字间留 8px

## 7. Motion & Interaction

- 仅 hover 颜色变化（150ms ease）与链接下划线浮现。禁止弹跳、缩放、位移、轮播、渐变过渡、视差、滚动动画、自动播放

## 8. Voice & Brand

- 茶室的口吻：具体、克制、可核对（水温、克数、焙火次数、时辰、席数、年份）；可用「我们」；不使用营销感叹号与夸张副词（「顶级」「爆款」「臻选」「匠心之作」等一律禁止）；不写英文口号，不用 emoji
- 品牌名、地址、电话、价格为占位事实（简报中标「假定」），上线前须替换为真实信息

## 9. Anti-patterns

- 禁止暖色（红/橙/黄/棕）作主色；禁止冷色系（蓝、紫）作主色
- 禁止纯黑纯白背景；禁止渐变（含金属、光晕、纱罩）；禁止位图与外链图片
- 禁止无衬线标题（标题、卡片标题、字牌、图版号必须 serif）
- 禁止 emoji
- 禁止琥珀作墨绿底文字、青瓷作浅底文字、灰绿作墨绿底文字
- 禁止阴影（含卡片投影与光晕）；禁止圆角超过 2px 的按钮与卡片（无胶囊按钮）
- 禁止内容超出 1040px 容器；禁止表格布局；禁止 transform/缩放类动效
- 禁止第二个转化动作与顶栏导航链接
