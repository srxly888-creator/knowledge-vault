# 🚀 MAS Factory + AI 助手编排 - 玛露落地页实现路径

> **目标**: 用 MAS Factory 的 Vibe Graphing 实现玛露落地页
> **优势**: 自然语言生成工作流，成本暴砍 95%，可视化调试
> **创建时间**: 2026-03-24 00:04

---

## 📊 MAS Factory 核心优势

### 对比其他框架

| 特性 | MAS Factory | CrewAI | LangGraph | OpenClaw |
|------|-------------|--------|-----------|----------|
| **Vibe Graphing** | ✅ 自然语言生成工作流 | ❌ 手动定义 | ❌ 手动定义 | ✅ 对话式 |
| **成本优化** | ✅ 双模型（暴砍 95%） | ❌ 单模型 | ❌ 单模型 | ✅ 灵活配置 |
| **可视化** | ✅ 图结构可视化 | ⚠️ 有限 | ✅ 图可视化 | ✅ 仪表板 |
| **学习曲线** | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ |
| **中文支持** | ✅ GLM 原生 | ⚠️ 有限 | ⚠️ 有限 | ✅ 完善 |

---

## 🎯 玛露落地页实现方案

### 方案 1: Vibe Graphing（自然语言生成工作流）⭐⭐⭐⭐⭐

#### 核心概念

**Vibe Graphing** 是 MAS Factory 的核心特性：
- **输入**: 自然语言描述（"设计一个玛露落地页开发流程"）
- **处理**: GLM-5 生成图结构设计 → JSON Blueprint → 编译成可执行工作流
- **输出**: 可运行的多智能体协作工作流

#### 实现步骤

##### 步骤 1: 安装和配置

```bash
# 安装 MAS Factory
pip install masfactory

# 配置 API Key
export GLM_API_KEY="your-api-key"

# 或使用配置文件
# ~/.openclaw/workspace/masfactory_config.py
```

##### 步骤 2: 创建配置文件

```python
# masfactory_config.py
from masfactory import OpenAIModel

# 规划模型（GLM-5）
build_model = OpenAIModel(
    model="glm-5",
    api_key="your-api-key",
    temperature=0.7
)

# 执行模型（GLM-4-Air，成本优化）
invoke_model = OpenAIModel(
    model="glm-4-air",
    api_key="your-api-key",
    temperature=0.3
)
```

##### 步骤 3: 使用 Vibe Graphing 生成工作流

```python
# malu_landing_vibe.py
from masfactory import RootGraph, VibeGraph
from masfactory_config import build_model, invoke_model

# 创建根图
g = RootGraph(name="malu_landing_page")

# 创建 Vibe Graph
vibe = g.create_node(
    VibeGraph,
    name="vibe_graph",
    invoke_model=invoke_model,  # 执行模型（便宜）
    build_model=build_model,    # 规划模型（贵）
    build_instructions="""
    设计一个玛露 6g 罐装遮瑕膏的营销落地页开发工作流：

    1. 文案撰写阶段（Copywriting Phase）
       - Agent: 资深美妆文案策略师
       - 任务: 撰写高端、专业的营销文案
       - 输出: Markdown 格式文案

    2. 设计系统阶段（Design System Phase）
       - Agent: 高级 UI/UX 设计师
       - 任务: 设计去工厂化的视觉系统
       - 输出: 颜色系统 + 字体配置

    3. 前端开发阶段（Frontend Development Phase）
       - Agent: 资深前端工程师
       - 任务: 使用 Next.js + Tailwind CSS 开发落地页
       - 输出: 完整项目代码

    4. 部署阶段（Deployment Phase）
       - Agent: DevOps 工程师
       - 任务: 部署到 Vercel
       - 输出: 部署 URL

    要求：
    - 每个阶段有明确的输入和输出
    - 支持人工审核和修改
    - 成本优化（双模型策略）
    """,
)

# 连接入口和出口
g.edge_from_entry(receiver=vibe, keys={})
g.edge_to_exit(sender=vibe, keys={})

# 构建图
g.build()

# 执行工作流
result = g.invoke(input={}, attributes={})

print("✅ 玛露落地页生成完成！")
print(result)
```

##### 步骤 4: 运行和查看结果

```bash
# 运行 Vibe Graphing
python malu_landing_vibe.py

# 查看生成的图结构
# MAS Factory 会自动生成 graph_design.json

# 查看执行日志
# MAS Factory 会记录每个阶段的输入输出
```

#### 成本优化

**双模型策略**（成本暴砍 95%）：

| 模型 | 用途 | 调用次数 | 成本 |
|------|------|----------|------|
| **GLM-5** | 规划（build_model） | 1 次 | 高 |
| **GLM-4-Air** | 执行（invoke_model） | 100+ 次 | 低 |

**总成本**: $0.26（vs $6.08 单模型）

---

### 方案 2: 手动定义工作流（更可控）⭐⭐⭐⭐

#### 实现步骤

##### 步骤 1: 定义 Agent

```python
# malu_landing_manual.py
from masfactory import RootGraph, Agent, NodeTemplate
from masfactory_config import invoke_model

BaseAgent = NodeTemplate(Agent, model=invoke_model)

# 创建根图
g = RootGraph(
    name="malu_landing_manual",
    nodes=[
        # 文案撰写 Agent
        ("copywriter", BaseAgent(
            instructions="你是玛露美妆品牌的资深文案策略师。",
            prompt_template="""
            为玛露 6g 罐装遮瑕膏撰写单页网站文案。

            目标受众：{target_audience}
            设计风格：{design_style}

            要求：极致专业，去工厂化的高端美学感。
            """
        )),

        # 设计系统 Agent
        ("designer", BaseAgent(
            instructions="你是专注于美妆品牌的 UI/UX 设计师。",
            prompt_template="""
            基于以下文案，设计视觉系统。

            文案：{copy}

            设计风格：浅色优雅，去工厂化。
            """
        )),

        # 前端开发 Agent
        ("developer", BaseAgent(
            instructions="你是资深前端工程师，精通 Next.js 和 Tailwind CSS。",
            prompt_template="""
            基于以下文案和设计规范，开发玛露落地页。

            文案：{copy}
            设计系统：{design_system}

            技术栈：Next.js 14 + Tailwind CSS + Framer Motion
            """
        )),

        # DevOps Agent
        ("devops", BaseAgent(
            instructions="你是 DevOps 工程师，精通 Vercel 部署。",
            prompt_template="""
            部署以下项目到 Vercel。

            项目代码：{code}

            要求：一键部署，自动 HTTPS。
            """
        )),
    ],
    edges=[
        # 文案撰写
        ("entry", "copywriter", {
            "target_audience": "追求轻薄自然底妆的都市白领",
            "design_style": "浅色优雅，去工厂化"
        }),

        # 设计系统
        ("copywriter", "designer", {
            "copy": "文案内容"
        }),

        # 前端开发
        ("designer", "developer", {
            "copy": "文案内容",
            "design_system": "设计系统"
        }),

        # 部署
        ("developer", "devops", {
            "code": "项目代码"
        }),

        # 输出
        ("devops", "exit", {
            "deployment_url": "部署 URL"
        }),
    ],
)

# 构建图
g.build()

# 执行工作流
out, _ = g.invoke({
    "target_audience": "追求轻薄自然底妆的都市白领",
    "design_style": "浅色优雅，去工厂化"
})

print("✅ 玛露落地页生成完成！")
print(f"部署 URL: {out['deployment_url']}")
```

---

### 方案 3: 集成 ChatDev Lite（软件开发流程）⭐⭐⭐⭐

#### ChatDev Lite 结构

MAS Factory 提供了 **ChatDev Lite** 示例，完整的软件开发流程：

1. **demand_analysis_phase** - 需求分析
2. **language_choose_phase** - 语言选择
3. **coding_phase** - 编码
4. **test_loop** - 测试循环（最多 3 次）
5. **test_error_summary_phase** - 错误总结
6. **test_modification_phase** - 修复代码

#### 玛露落地页改编

```python
# malu_chatdev.py
from masfactory import RootGraph, Agent, NodeTemplate, Loop
from masfactory_config import invoke_model

BaseAgent = NodeTemplate(Agent, model=invoke_model)

g = RootGraph(
    name="malu_chatdev",
    nodes=[
        # 需求分析阶段
        ("demand_analysis", BaseAgent(
            instructions="CEO（指导） + CPO（执行）",
            prompt_template="分析用户需求：{task}"
        )),

        # 技术选型阶段
        ("tech_choose", BaseAgent(
            instructions="CEO（指导） + CTO（执行）",
            prompt_template="选择技术栈：{task}, {modality}"
        )),

        # 设计阶段
        ("design_phase", BaseAgent(
            instructions="CTO（指导） + 设计师（执行）",
            prompt_template="设计视觉系统：{task}, {tech_stack}"
        )),

        # 开发阶段
        ("coding_phase", BaseAgent(
            instructions="CTO（指导） + 程序员（执行）",
            prompt_template="开发落地页：{task}, {design_system}",
            tools=["codes_check_and_processing_tool", "check_code_completeness_tool"]
        )),

        # 测试循环（最多 3 次）
        ("test_loop", Loop(
            nodes=[
                ("test_error_summary", BaseAgent(
                    instructions="测试工程师（指导） + 程序员（执行）",
                    tools=["run_tests_tool"]
                )),
                ("test_modification", BaseAgent(
                    instructions="测试工程师（指导） + 程序员（执行）",
                    tools=["codes_check_and_processing_tool"]
                )),
            ],
            max_iterations=3,
            terminate_conditions=[
                "error_summary 包含 'No errors found'",
                "exist_bugs_flag 为 False",
            ]
        )),
    ],
    edges=[
        ("entry", "demand_analysis", {"task": "玛露 6g 罐装遮瑕膏落地页"}),
        ("demand_analysis", "tech_choose", {"modality": "营销单页"}),
        ("tech_choose", "design_phase", {"tech_stack": "Next.js + Tailwind"}),
        ("design_phase", "coding_phase", {"design_system": "设计系统"}),
        ("coding_phase", "test_loop", {"codes": "代码文件"}),
        ("test_loop", "exit", {"deployment_url": "部署 URL"}),
    ],
)

g.build()
out, _ = g.invoke({"task": "玛露 6g 罐装遮瑕膏落地页"})
```

---

## 🔧 MAS Factory 核心组件

### 1. Agent（执行单元）

```python
Agent(
    instructions="角色说明",
    prompt_template="提示词模板",
    tools=["工具列表"],
    model="GLM-4-Air"
)
```

### 2. Graph（子图）

```python
Graph(
    name="子图名称",
    nodes=[...],
    edges=[...]
)
```

### 3. Loop（循环执行）

```python
Loop(
    nodes=[...],
    max_iterations=3,
    terminate_conditions=["条件 1", "条件 2"]
)
```

### 4. Switch（分支判断）

```python
Switch(
    cases={
        "case_1": node_1,
        "case_2": node_2,
    },
    default=default_node
)
```

### 5. Human（人工介入）

```python
Human(
    prompt="请审核代码",
    timeout=300  # 5 分钟
)
```

---

## 💡 学习路径

### 第 1 天（1 小时）

- ✅ 安装 MAS Factory
- ✅ 配置 API Key
- ✅ 运行测试脚本
- ✅ 学习基础示例（两阶段问答）

### 第 1 周（每天 2-3 小时）

- **周一**: 学习 Agent 和 Graph 组件
- **周二**: 学习 Loop 和 Switch 组件
- **周三**: Vibe Graphing 基础
- **周四**: Vibe Graphing 进阶
- **周五**: ChatDev Lite 实战
- **周末**: 设计玛露落地页工作流

### 第 2 周

- 集成到 OpenClaw
- 优化成本和性能
- 开发实用工作流

---

## 📚 学习资源

### 官方资源

- **在线文档**: https://bupt-gamma.github.io/MASFactory/
- **论文**: http://arxiv.org/abs/2603.06007
- **GitHub**: https://github.com/BUPT-GAMMA/MASFactory
- **视频**:
  - Vibe Graphing: https://www.youtube.com/watch?v=QFlQuX_cddk
  - Demo: https://www.youtube.com/watch?v=ANynzVfY32k

### 本地资源

- **仓库**: `~/.openclaw/workspace/MASFactory`
- **配置**: `~/.openclaw/workspace/masfactory_config.py`
- **测试**: `~/.openclaw/workspace/test_masfactory.py`
- **深度解析**: `ai-agent-learning-hub/MASFACTORY_DEEP_DIVE.md`

### 示例代码

- **VibeGraph Demo**: `applications/vibegraph_demo/`
- **ChatDev Lite**: `applications/chatdev_lite/`
- **CAMEL**: `applications/camel/`

---

## 🎯 总结

### MAS Factory 核心优势

1. **Vibe Graphing** - 自然语言生成工作流
2. **双模型策略** - 成本暴砍 95%
3. **可视化调试** - 图结构清晰
4. **中文原生支持** - GLM 模型

### 推荐路径

| 场景 | 推荐方案 | 时间 |
|------|----------|------|
| **快速原型** | Vibe Graphing | 30 分钟 |
| **生产环境** | 手动定义工作流 | 2-4 小时 |
| **软件开发** | ChatDev Lite | 1 天 |
| **学习研究** | 全部方案 | 1 周 |

### 对比其他框架

- **vs CrewAI**: MAS Factory 有 Vibe Graphing，成本更低
- **vs LangGraph**: MAS Factory 更易用，中文支持更好
- **vs OpenClaw**: MAS Factory 更专注于工作流编排

---

**大佬，MAS Factory 的完整路径已整理完毕！选择 Vibe Graphing 开始火力全开吧！** 🚀
