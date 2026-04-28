# lezhi-medical-figma-mcp-product-design

一个面向 Codex 的产品设计 Skill，用于基于丽滋高端医疗 UI 规范，调用 Pencil MCP 或 Figma MCP 进行前端产品界面设计、页面样式优化和高保真产出。

## 功能特色

- 基于 `design-md.md` 执行丽滋高端医疗 UI 规范，统一品牌气质、色彩、排版、卡片体系和组件风格。
- 基于 `layout-md.md` 优化页面结构与排版节奏，适合后台、工作台、列表页、详情页、驾驶舱和智能屏类场景。
- 同时支持 `Pencil MCP` 与 `Figma MCP` 两条设计路径：
  - `Pencil MCP` 适合原型、结构、流程和后台产品快速搭建。
  - `Figma MCP` 适合视觉强化、组件化页面、设计稿交付和高保真输出。
- 内置丽滋风格约束，避免在新业务场景下漂移成营销风、媒体风、黑金奢华风或娱乐化大屏风格。
- 内置 Figma 防压叠工作流，要求单页面 wrapper、分区 auto layout、逐段生成和逐段校验，减少模块重叠、文字裁切和层级错挂。
- 适用于用户需求到页面方案的直接转换，可用于生成智能屏、服务页、首页概览、推荐页、表单页和业务管理页面。

## 适用场景

- 高端医疗后台产品设计
- 会员服务、推荐页、智能屏和欢迎屏设计
- 工作台、Dashboard、列表页、详情页、表单页设计
- 基于既有设计规范进行 Figma 或 Pencil 的页面落地
- 需要在固定 UI 规范下进行产品设计和样式优化的场景

## 工作流程

1. 加载 `Pencil MCP` 或 `Figma MCP`
2. 读取 `references/design-md.md`
3. 读取 `references/layout-md.md`
4. 根据用户需求映射页面壳层、模块、组件和交互层级
5. 使用 MCP 工具生成或修改设计结果
6. 对结果进行结构、风格和压叠风险校验

## 安装方式

如果你使用支持 `npx skill add` 的环境，可直接通过 GitHub 仓库安装：

```bash
npx skill add https://github.com/levinskyfarrelly-create/lezhi-medical-figma-mcp-product-design
```

如果你的环境要求手动安装，也可以直接克隆仓库后放入本地 skills 目录。

## 使用说明

### 1. 触发方式

在 Codex 中显式调用这个 skill，例如：

```text
[$lezhi-medical-figma-mcp-product-design] 设计一个会员服务首页
```

或直接描述符合 skill 的任务场景，例如：

```text
设计一个 1280*800 的横屏智能屏界面，内容包含推荐轮播、热销榜和限时权益卡片
```

### 2. 推荐输入内容

为了让输出更稳定，建议在需求中明确以下信息：

- 页面类型：工作台、列表页、详情页、智能屏、推荐页等
- 设计工具：Pencil 或 Figma
- 目标尺寸：例如 `1440x900`、`1280x800`
- 核心模块：例如卡片、榜单、轮播、表单、表格、侧栏
- 是否要求遵守丽滋既有 UI 规范

### 3. Figma 使用建议

当输出目标是 Figma 时，skill 会优先按以下规则组织页面：

- 先创建整页 wrapper，再逐段插入内容
- 每个 major section 单独生成
- 使用 auto layout 控制区块流式排列
- 背景装饰层与正文层分离
- 每段完成后进行截图或结构校验

这套流程适合减少：

- 模块压叠
- 文本裁切
- 两列区错位
- 组件挂错父级
- 样式漂移

### 4. Pencil 使用建议

当输出目标是 Pencil 时，skill 更适合：

- 快速搭建后台结构
- 生成原型和流程页面
- 先完成页面壳层、再补业务模块
- 在低中保真阶段统一信息架构和布局关系

## 示例

### 示例 1：智能屏推荐页

```text
[$lezhi-medical-figma-mcp-product-design] 设计一个 1280*800 的横屏电话智能屏界面，内容为云商城推荐，包含热门推荐轮播、热销榜单、限时秒杀三个板块
```

### 示例 2：后台工作台

```text
[$lezhi-medical-figma-mcp-product-design] 用 Figma 设计一个高端医疗会员运营工作台，包含欢迎区、KPI 卡片、待办事项、预约概览和会员提醒
```

### 示例 3：后台列表页

```text
[$lezhi-medical-figma-mcp-product-design] 用 Pencil 生成一个客户档案列表页，包含搜索筛选区、数据表格、批量操作栏和分页器
```

## 仓库结构

```text
.
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── design-md.md
    └── layout-md.md
```

## 说明

- `SKILL.md` 是主入口说明。
- `references/design-md.md` 是丽滋高端医疗 UI 规范。
- `references/layout-md.md` 是页面结构和版式优化参考。
- `agents/openai.yaml` 用于相关代理配置。
