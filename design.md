# PPTX Swarm 实现方式详解 - 视觉设计文档

## 1. Profile 基线声明

- **Profile 选择**：`profiles/general.md`
- **选择理由**：这是一个技术架构讲解类的演示文稿，面向开发者和技术管理者，属于"通用演示场景"，不完全匹配任何特定垂直场景（如学术、品牌推广等）
- **参考维度**：信息密度（中高）、内容表达技巧（图表+SmartArt）、叙事风格（逻辑清晰）、装饰禁忌
- **偏离说明**：
  - 色彩方案偏离：general 推荐浅色，本 PPT 采用深色主题以体现技术深度和系统架构的严谨感
  - 风格定位偏离：从"专业商务"升级为"科技工业风"，参考瑞士国际主义的理性网格

## 2. 风格基线声明

- **风格锚点 1：Swiss International Style（瑞士国际主义）**
  - 参考维度：网格系统的理性布局、无衬线字体的层级对比、留白与信息密度的平衡
  - 瑞士国际主义的数学化构图非常适合展示技术架构的严谨逻辑

- **风格锚点 2：Stripe 开发者文档**
  - 参考维度：深色背景下的信息层次、代码/数据展示的清晰度、克制而精致的视觉细节
  - Stripe 的深色科技风格为技术内容提供了最佳的阅读体验

## 3. 风格细节

### 3.1 色彩设计
- **整体色彩倾向**：保守稳重偏科技，以深灰蓝为基底，克制地使用强调色
- **色温**：冷色调，矿物质感
- **Primary（主色）**：`#3B6BFF` — 偏灰的明亮蓝，技术感强但不刺眼，用于标题、关键数据、图标
- **Background（背景色）**：`#0F1923` — 深蓝灰，深邃有层次，非纯黑
- **Surface（表面色）**：`#1A2633` — 稍浅的蓝灰，用于卡片背景、容器
- **Text（主文本色）**：`#E8ECF1` — 柔和白，降低对比度疲劳
- **Secondary（次要色）**：`#7A8B9F` — 蓝灰色，用于辅助文本、注释、分隔线
- **Accent（强调色）**：`#00D4AA` — 青绿色，仅用于关键数据高亮和状态指示，极度克制使用

### 3.2 字体使用
- **中文标题**：`alimamashuheiti` — 几何无衬线，商业科技感，结构感强
- **中文正文**：`MiSans` — 清晰现代，屏幕渲染优秀
- **英文标题/正文**：`Liter` — 现代新怪诞风格，低对比，理性干净
- **字号层级**：
  - 封面标题：44px
  - 页面标题：28px
  - 副标题/章节标题：22px
  - 正文：18-20px
  - 辅助文本/注释：13-14px
  - KPI 大数字：48-56px

### 3.3 容器与装饰风格
- **内容分离**：优先使用留白+字号差异建立层次，其次使用细线分隔
- **卡片样式**：直角矩形，无边框，使用 surface 色（`#1A2633`）填充
- **装饰元素**：
  - 细线分隔（1px，`#7A8B9F` 30%透明度）
  - 左侧色带标记（4px宽，primary色）用于重点内容块
  - 网格背景纹理（极淡的点阵或细线，增加科技感）

### 3.4 图像风格
- **图标**：使用 solid 风格图标（`fas:`），克制使用，仅在辅助理解时出现
- **表格**：极简风格，深色背景下的三线表变体，header 使用 primary 色背景
- **图表**：极简风格，系列色使用 primary + accent + secondary 的组合
- **插图**：不使用装饰性插图，所有视觉元素服务于信息传达

## 4. 布局系统

### 4.1 全局布局特征
- **页面尺寸**：1280 x 720（16:9）
- **页面边距**：左右 60px，上 50px，下 40px
- **统一页面元素**：
  - 底部右侧：页码（13px，secondary色）
  - 底部左侧：PPTX Swarm 标识（13px，secondary色）
  - 无固定导航栏/侧边栏，最大化内容区域
- **网格对齐**：所有元素严格遵循网格对齐，左右布局时底部对齐

### 4.2 特殊页面布局
- **封面**：左侧 55% 文字区域（标题+副标题+日期）+ 右侧 45% 视觉区域（由几何形状和连接线组成的抽象网络/Swarm 示意图），深色背景
- **目录页**：左侧 1/3 放置大标题 "CONTENTS"，右侧 2/3 使用网格布局放置章节卡片（每个卡片带编号和章节名）
- **章节过渡页**：左侧大面积 primary 色块（占40%宽度）+ 章节编号（大号半透明数字）+ 右侧章节标题和简介
- **结束页**：居中大标题 + 下方总结语，简洁有力

### 4.3 内容页布局模式
- **左右分栏**：55:45 或 60:40，左侧文字/列表，右侧图表/示意图
- **全宽内容**：标题 + 全宽表格或流程图
- **卡片网格**：2x2 或 3 列等宽卡片，每个卡片包含图标+标题+描述
- **KPI + 详情**：上方横向排列 3-4 个 KPI 大数字，下方详细说明
- **上下分区**：上方标题区 + 下方内容区（可再分左右）

## 5. 风格使用规则

- **textStyles**:
  - `title`: 封面标题、章节页标题
  - `pageTitle`: 内容页顶部标题
  - `subtitle`: 副标题、章节描述
  - `body`: 正文内容
  - `caption`: 辅助文本、注释、页码
  - `kpi`: KPI 大数字
- **colors**:
  - `primary`: 标题文字、图标填充、强调色带、关键数据
  - `secondary`: 辅助文字、分隔线、次要信息
  - `accent`: 仅用于关键状态指示（如"必须修复"标签）
  - `background`: 页面背景
  - `surface`: 卡片背景、容器填充
  - `text`: 正文文字
- **tableStyles**:
  - `default`: 深色主题表格，header 使用 primary 色，数据行交替使用 background 和 surface 色

## 6. 风险禁忌

- [ ] **禁止使用蓝紫渐变或高饱和背景色** — 保持深色背景的纯粹性
- [ ] **禁止正文字号低于 18px** — 确保投影和屏幕阅读的清晰度
- [ ] **禁止圆角矩形** — 使用直角矩形保持瑞士国际主义的锐利感
- [ ] **禁止装饰性图标泛滥** — 图标仅在辅助理解时使用
- [ ] **禁止左右布局底部不对齐** — 严格遵循网格系统
- [ ] **禁止纯白背景** — 保持深色主题的沉浸感
- [ ] **禁止廉价蓝色（如 #0A97C0, #2C80FD）** — 使用偏灰的 primary 蓝
- [ ] **禁止上下布局时横向元素不居中** — 保持视觉平衡

## 7. Theme 定义

```yaml
theme:
  colors:
    primary: "#3B6BFF"
    secondary: "#7A8B9F"
    accent: "#00D4AA"
    background: "#0F1923"
    surface: "#1A2633"
    text: "#E8ECF1"
    textMuted: "#7A8B9F"
  textStyles:
    title:
      fontSize: 44
      color: "$text"
      fontFamily: "Liter, alimamashuheiti"
    pageTitle:
      fontSize: 28
      color: "$text"
      fontFamily: "Liter, alimamashuheiti"
    subtitle:
      fontSize: 22
      color: "$secondary"
      fontFamily: "Liter, MiSans"
    body:
      fontSize: 18
      color: "$text"
      fontFamily: "Liter, MiSans"
      lineHeight: 1.6
    caption:
      fontSize: 13
      color: "$secondary"
      fontFamily: "Liter, MiSans"
    kpi:
      fontSize: 48
      color: "$primary"
      fontFamily: "Liter, alimamashuheiti"
  tableStyles:
    default:
      fontSize: 16
      fontFamily: "Liter, MiSans"
      headerFill: "$primary"
      headerColor: "#FFFFFF"
      headerBold: true
      bodyFill: ["$background", "$surface"]
      bodyColor: "$text"
      border:
        style: solid
        width: 1
        color: "#2A3A4A"
```
