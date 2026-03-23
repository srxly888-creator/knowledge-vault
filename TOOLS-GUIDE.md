# 🛠️ 工具选择指南

> **目标**: 帮助非技术人员选择最合适的工具
> **原则**: 工具优先，简单易用

---

## 📊 工具对比

### AI 编程助手

| 工具 | 难度 | 时间 | 成本 | 推荐指数 |
|------|------|------|------|----------|
| **Claude Code CLI** | ⭐⭐ | 5 分钟 | 免费（有限额） | ⭐⭐⭐⭐⭐ |
| **Codex** | ⭐⭐⭐ | 10 分钟 | 付费 | ⭐⭐⭐⭐ |
| **Antigravity** | ⭐ | 15 分钟 | 免费（开源） | ⭐⭐⭐ |
| **Cursor** | ⭐⭐ | 8 分钟 | 免费（有限额） | ⭐⭐⭐⭐ |
| **GitHub Copilot** | ⭐⭐⭐ | 10 分钟 | 付费 | ⭐⭐⭐ |

---

## 🏆 推荐方案

### 方案 1: Claude Code CLI + GLM（最佳）

**适合人群**: 完全零基础，想快速见效

**优势**:
- ✅ 自然语言交互（中文友好）
- ✅ 自动生成代码
- ✅ 自动调试和修复
- ✅ 集成开发环境
- ✅ 免费（有限额）

**劣势**:
- ❌ 需要安装 Node.js
- ❌ 网络要求（需要科学上网）

**成本**: 免费（每天 100 次对话）

**时间**: 5 分钟上手

---

### 方案 2: Codex + GPT-4o-mini（性价比）

**适合人群**: 懂一点编程，追求性价比

**优势**:
- ✅ OpenAI 官方工具
- ✅ 代码质量高
- ✅ 性价比好（GPT-4o-mini）

**劣势**:
- ❌ 需要付费（$0.15/1M tokens）
- ❌ 需要懂基础命令

**成本**: $1-5/月

**时间**: 10 分钟上手

---

### 方案 3: Antigravity（开源免费）

**适合人群**: 喜欢开源，不介意复杂

**优势**:
- ✅ 完全免费
- ✅ 开源可控
- ✅ 可视化界面

**劣势**:
- ❌ 配置复杂
- ❌ 需要懂技术
- ❌ 社区支持少

**成本**: 免费

**时间**: 15 分钟上手

---

## 🎯 选择建议

### 根据技术水平

#### 完全零基础
**推荐**: Claude Code CLI + GLM
**原因**: 自然语言交互，无需编程知识

#### 有一点编程基础
**推荐**: Codex + GPT-4o-mini
**原因**: 性价比高，代码质量好

#### 技术爱好者
**推荐**: Antigravity
**原因**: 免费开源，可自定义

---

### 根据预算

#### 预算充足（$10-20/月）
**推荐**: Codex + GPT-4o
**原因**: 性能最佳，无限制

#### 预算有限（$1-5/月）
**推荐**: Codex + GPT-4o-mini
**原因**: 性价比高，够用

#### 零预算
**推荐**: Claude Code CLI
**原因**: 免费（有限额）

---

### 根据使用场景

#### 日常数据分析
**推荐**: Claude Code CLI + GLM
**原因**: 快速生成分析代码，可视化友好

#### 复杂编程任务
**推荐**: Codex + GPT-4o
**原因**: 推理能力强，代码质量高

#### 学习编程
**推荐**: Claude Code CLI
**原因**: 代码有详细注释，易于理解

---

## 💡 使用技巧

### Claude Code CLI 技巧

#### 1. 清晰描述需求
**✅ 好的描述：**
```
我有一个 CSV 文件（data.csv），包含 3 列：
- 年龄（18-80）
- 收入（1000-100000）
- 消费金额（100-50000）

请用 GMM 聚类，分成 3 个群体，可视化结果
```

**❌ 差的描述：**
```
帮我分析数据
```

---

#### 2. 分步执行
**不要一次性描述复杂任务，而是：**

**步骤 1：**
```
请读取 data.csv 文件，显示前 5 行
```

**步骤 2：**
```
数据看起来不错，请用 GMM 聚类
```

**步骤 3：**
```
请可视化聚类结果
```

---

#### 3. 提供上下文
**✅ 好的描述：**
```
我是一个市场分析师，需要分析客户数据。
我有一个 CSV 文件（customers.csv），包含：
- 客户 ID
- 年龄
- 年收入
- 消费金额

请帮我分群，并提供营销建议
```

---

### Codex 技巧

#### 1. 明确任务类型
```
请用 Python 实现以下任务：
[任务描述]

要求：
- 使用 pandas 读取数据
- 使用 sklearn 进行聚类
- 使用 matplotlib 可视化
```

---

#### 2. 提供示例数据
```
示例数据（前 5 行）：
age,income,spending
25,50000,2000
30,60000,2500
...

请基于这个数据结构实现
```

---

#### 3. 指定输出格式
```
输出要求：
1. Python 代码
2. 可视化图表（PNG 格式）
3. 分析报告（Markdown 格式）
```

---

## 🔧 安装指南

### Claude Code CLI

#### macOS
```bash
# 1. 安装 Homebrew（如果没有）
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2. 安装 Node.js
brew install node

# 3. 安装 Claude Code CLI
npm install -g @anthropic/claude-code-cli

# 4. 启动
claude-code
```

#### Windows
```bash
# 1. 下载 Node.js
# https://nodejs.org/

# 2. 安装 Claude Code CLI
npm install -g @anthropic/claude-code-cli

# 3. 启动
claude-code
```

---

### Codex

#### 安装
```bash
# 安装 OpenAI CLI
pip install openai

# 设置 API Key
export OPENAI_API_KEY='your-api-key'
```

#### 使用
```python
import openai

response = openai.Completion.create(
    engine="code-davinci-002",
    prompt="# Python code to implement GMM clustering\n",
    max_tokens=1000
)

print(response.choices[0].text)
```

---

### Antigravity

#### 安装
```bash
# 克隆仓库
git clone https://github.com/antigravity/antigravity.git

# 安装依赖
cd antigravity
npm install

# 启动
npm start
```

---

## 📊 成本对比

| 工具 | 免费额度 | 付费价格 | 适用场景 |
|------|----------|----------|----------|
| **Claude Code CLI** | 100 次/天 | $20/月（无限） | 日常使用 |
| **Codex** | 无 | $0.15/1M tokens | 专业开发 |
| **Antigravity** | 完全免费 | 免费 | 学习研究 |
| **Cursor** | 100 次/天 | $20/月 | 日常开发 |
| **GitHub Copilot** | 无 | $10/月 | 代码补全 |

---

## 🎯 总结

### 最佳组合

#### 组合 1: 完全零基础
- **工具**: Claude Code CLI + GLM
- **成本**: 免费
- **时间**: 5 分钟上手

#### 组合 2: 追求性能
- **工具**: Codex + GPT-4o
- **成本**: $10-20/月
- **时间**: 10 分钟上手

#### 组合 3: 学习研究
- **工具**: Antigravity
- **成本**: 免费
- **时间**: 15 分钟上手

---

## 📞 获取帮助

### 官方文档
- [Claude 官网](https://claude.ai/)
- [OpenAI Codex](https://openai.com/codex/)
- [Antigravity GitHub](https://github.com/antigravity/antigravity)

### 社区支持
- [Stack Overflow](https://stackoverflow.com/)
- [GitHub Discussions](https://github.com/discussions)
- [Reddit](https://www.reddit.com/)

---

**选择最适合你的工具，开始你的 AI 编程之旅！** 🚀
