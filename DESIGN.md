# Design —— NUS 311 导师助手设计系统

<!-- impeccable:design-schema 1 -->

> 翻新日期：2026-08-22 ｜ 方法：Impeccable（audit → critique → shape → layout/typeset/colorize → polish）
> 决策背景见 [PRODUCT.md](PRODUCT.md)（产品事实）与本文件（视觉系统）。后续所有 UI 改动必须遵循本文件。

## Design World

**"深蓝学术 + 活力橙"（NUS 蓝 × 工程橙）**：深海军蓝承载信息层级与可信感（学术/学校品牌联想），橙色只用于关键行动与高亮（稀缺即力量）。整体气质：专业、清晰、有温度的高密度学术工作台。

## Color System

| Token | 值 | 角色 | 对比度 |
|---|---|---|---|
| `--blue` | `#003D7C` | 主色：标题、导航激活、信息强调 | 白字 12:1 |
| `--blue-2` | `#0B5CAD` | 链接、次级强调 | 白字 7.5:1 |
| `--blue-soft` | `#EFF5FB` | 浅蓝底（表头、tip、hover） | 深蓝字 7.2:1 |
| `--blue-line` | `#CFE0F2` | 信息边框 | — |
| `--orange` | `#EF7C00` | 行动橙（时间线节点、列表箭头） | 仅装饰/图标 |
| `--orange-deep` | `#9A4500` | 浅橙底上的文字（note、tag.warn） | 6.5:1 |
| `--orange-soft` | `#FFF3E6` | 警示底 | — |
| `--grad-blue` | `120deg #003D7C→#0B5CAD` | 头部、页签激活、按钮 | 白字 ≥7.5:1 |
| `--grad-bar` | `90deg #EF7C00→#0B5CAD` | 进度条、章节渐变条、时间线节点 | — |
| `--grad` | `135deg 蓝→蓝→橙` | 预留品牌渐变（页脚分隔） | — |
| `--bg`/`--card`/`--line` | `#F4F6F9`/`#FFFFFF`/`#E3E8EF` | 表面/卡片/分隔 | — |
| `--text`/`--muted` | `#1F2937`/`#5B6572` | 正文/次级文字 | 14.8:1 / 7.1:1 |
| `--green` | `#0E9F6E` | 成功语义 | — |

**语义块**：tip=info（浅蓝底深蓝字）、note=warn（浅橙底深橙字）、tag.ok=绿。全部满足 WCAG AA（≥4.5:1）。

**反模式（禁止）**：紫蓝渐变、纯黑/纯灰文字、灰字彩底、橙底白字（<3:1）、无目的渐变堆叠。

## Typography

- 字体栈：`-apple-system, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Noto Sans SC", sans-serif`（系统字体，零加载成本）
- 层级（7 档，按角色）：
  | 角色 | 字号/字重 |
  |---|---|
  | 页头 H1 | 26px / 800 |
  | 章节标题 h2.sec | 17px / 700 + 渐变条 |
  | 卡片标题 | 15–16px / 700（蓝） |
  | 页签 | 15px / 500（激活 700 白字渐变底） |
  | 正文 | 14px / 1.65 |
  | 表格 | 13px（表头 600） |
  | 标签/元信息 | 12px |
- 移动端：body 14px，表格 12.5px，H1 22px
- 正文行高 1.65；避免半档字号（12.5/13.5/14.5/15.5 已收敛）

## Spacing & Layout

- 基数 4px：`--s1:4 … --s6:32`；节奏 = 紧(8) 与 松(24) 交替
- 卡片：圆角 14px、细边框 `--line`、轻阴影 `0 1px 3px`；**禁止顶部 3px 强调条**（已删除）
- 唯一强调模式：章节标题左侧 4px 渐变条（h2.sec::before）+ 时间线竖线（语义用途）
- 文献大表（.lit-table）：横向滚动 + **首列冻结**（sticky left:0，表头 z-index 3）
- 页签：桌面平铺；移动端横向滑动胶囊（激活=渐变底白字圆角 999px）

## Motion

- 页签切换：fade 0.25s（进入）
- 进度条：width 0.4s cubic-bezier(0.4,0,0.2,1)
- 表格行 hover：`#F0F6FF` 高亮；任务行 hover：浅蓝底
- 按钮 hover：阴影 + 上浮 1px（0.15s）
- 全部动画尊重 `prefers-reduced-motion: reduce`（全局关闭）

## Components

- `.tip`（信息）/`.note`（警示）/`.card`/`.stat`/`.day-card`/`.task-group`（任务组+进度条）/`.timeline`/`.tag`/`.pill`（页头胶囊）/`.btn`（渐变蓝行动按钮）
- 任务勾选：原生 checkbox + accent-color 蓝，完成态删除线 + muted

## Accessibility Commitments

- 正文对比度全部 ≥4.5:1（检测器验证 0 处违规）
- 语义化标签：header/nav/main/footer/section/button/table/label/input
- 触控目标：页签高 ≥44px、checkbox 17px（label 全区域可点）
- 键盘可导航（原生 button/input）；焦点样式由浏览器默认提供（未覆盖）

## Detector Baseline（Impeccable 59 规则）

- 翻新前：59 条发现（9 对比度 + 44 side-tab + 2 圆角边框等）
- 翻新后：3 条（flat-type-hierarchy 权衡接受；em-dash ×64 与 buzzword ×2 为正文内容，保留）
- 复测命令：`node tools/impeccable/plugin/skills/impeccable/scripts/detect.mjs 导师助手.html`
