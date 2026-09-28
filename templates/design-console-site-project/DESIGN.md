# Design System: Design Console 官网

> Category: AI-Native SaaS
> 目标：为「Design Console——对话式 AI 设计工作台」打造品牌官网，传达「一句话需求 → 可部署落地页」的产品价值，兼具科技感、可信度与转化力。

## 1. 定位与气质
- 产品气质：AI-Native、开发者友好、专业可信、克制而有张力。
- 首屏必须回答：这是什么、为谁而做、凭什么强（30 秒内可理解）。
- 语气：直接、具体、少形容词；避免「赋能」「颠覆」等空词。

## 2. 色彩（token）
- 主色 Indigo #6366F1（交互、主按钮、渐变起点）
- 强调 Violet #8B5CF6（CTA、渐变终点、数据高亮）
- 背景层级：深空 #0B0E17（Hero/深色区）→ 面板 #12162A → 卡片 #171C33
- 文字：主 #F2F4FA、次 #A6ADC2、弱 #6B7388
- 语义：成功 #22C55E、警示 #F59E0B、错误 #EF4444
- 渐变：135deg #6366F1 → #8B5CF6（按钮/关键强调，大面积不渐变）

## 3. 字体
- 标题/正文统一 Inter（system-ui 回退），数字用 tabular-nums
- 层级：Hero 56/1.05 → 章节 32/1.15 → 卡片 18/1.5 → 正文 15/1.7 → 注释 12
- 代码/指标用等宽（Cascadia Code / SF Mono / Consolas）

## 4. 布局与栅格
- 1200px 内容容器，24px 栅格感；Bento 网格卡（2/3 + 1/3 混排）
- 页面结构：Nav（吸顶模糊）→ Hero → 信任条 → 特性 Bento → 工作流 4 步 → 模板/成果 → 指标 → CTA → Footer
- 留白优先：卡片间距 16-24，章节间距 96-120

## 5. 组件规范
- 按钮：主（渐变+阴影）、次（描边、hover 提亮）、文本链接（下划线 hover）；高度 40/44
- 卡片：圆角 16、1px rgba(255,255,255,.08) 描边、hover 上浮 2px + 光晕
- 徽标：胶囊 20px 高，Indigo 15% 底 / 主色字
- 输入/表单：深底描边、focus 3px Indigo 光环（用于早鸟登记等）

## 6. 动效（低运动友好）
- 进场：fade-up 12px，400ms cubic-bezier(.22,.61,.36,1)，stagger 80ms
- 滚动：Hero 视差 0.35x/0.8x；工作流激活高亮；进度条 0-100%
- 指针：Bento 卡径向光效 + 3D 倾斜（pointer-driven，仅 transform）
- 全部动画仅 transform/opacity；hover 150-300ms；prefers-reduced-motion 下全停
- 无循环横幅、无粒子、无 emoji 作图标（SVG 图标）

## 7. 响应式
- 断点：375 / 768 / 1024 / 1440；Bento 降为单列；导航折叠为菜单
- 触控目标 ≥ 44px；正文 ≥ 14px；无 hover 依赖的核心信息

## 8. 落地页结构（landing.html 蓝图）
1. Nav：logo + 功能锚点 + CTA「开始设计」
2. Hero：产品名 + 一句话价值 + 双 CTA + 控制台截图（console.png）+ 视差
3. 信任条：20 设计系统 · 7 成品模板 · 5 语言导出 · 138 次迭代（计数动画）
4. 特性 Bento：对话生成 / 局部修改 / 多语言 / 协作评论 / 用量透明 / 一键打包（4 图卡 ikea/warm/templates）
5. 工作流：描述 → 生成 → 预览 → 交付 4 步（滚动高亮 + 连接线）
6. 模板展示：成品与规范卡片（templates.png）
7. CTA：主渐变按钮 + 副文案
8. Footer：产品 + 文档 + 版本号

## 9. 内容清单（质量门）
- 真实数字必须来自产品实测（20 系统 / 7 成品 / 5 语言 / 版本迭代数）
- 文案用中文，代码/品牌名保留英文
- QA 自测钩子：`#qa` 触发行级断言（JS/卡数/工作流/计数/指针），真实浏览器全 PASS
- reduced-motion 与键盘可达性（focus-visible 环）纳入交付检查
