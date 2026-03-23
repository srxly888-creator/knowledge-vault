# 🛠️ Codex Mac 应用 - 快速上手指南

> **更新**: OpenAI 推出 Codex Mac 应用
> **优势**: 原生 macOS 体验，更流畅的 AI 编程

---

## 📊 Codex Mac 应用特点

### 核心优势
- ✅ **原生 macOS 体验**：无需终端，图形界面
- ✅ **实时预览**：代码修改即时显示
- ✅ **智能补全**：AI 辅助代码补全
- ✅ **一键部署**：集成部署功能

### 适用场景
- ✅ 快速原型开发
- ✅ 单页网站搭建
- ✅ API 接口开发
- ✅ 自动化脚本

---

## 🚀 安装和使用

### 安装步骤

#### 方法 1: 官网下载
```bash
# 1. 访问官网
https://openai.com/codex

# 2. 下载 Mac 版本
# 3. 拖拽到 Applications 文件夹
```

#### 方法 2: Homebrew
```bash
brew install --cask openai-codex
```

---

### 首次使用

#### 1. 登录 OpenAI 账号
- 打开 Codex 应用
- 输入 API Key
- 或使用 OAuth 登录

#### 2. 创建项目
- 点击 "New Project"
- 选择模板（Next.js、React、Python 等）
- 输入项目名称

#### 3. 开始编程
- 在对话框中描述需求
- Codex 自动生成代码
- 实时预览效果

---

## 🎯 玛露落地页实战（Codex 版）

### Prompt 模板

```
创建一个玛露（Malu）6g 罐装遮瑕膏的营销落地页：

## 项目信息
- 产品：玛露 6g 罐装遮瑕膏
- 目标：高转化营销单页
- 风格：去工厂化的高端美妆品牌

## 设计要求
- 颜色：浅色背景（米白 #F5F5F0、柔和裸色 #D4A574）
- 字体：Inter（简洁现代）
- 动画：淡入效果（Framer Motion）
- 布局：移动优先响应式

## 页面结构
1. **Hero Section**
   - 标题："玛露 6g 罐装遮瑕膏"
   - 副标题："轻薄如肤，遮瑕如影"
   - CTA 按钮："立即购买 ¥198"

2. **适用肤质图谱**（6 个网格卡片）
   - 黑眼圈
   - 痘印
   - 色斑
   - 肤色不均
   - 细纹
   - 毛孔粗大

3. **产品核心亮点**
   - 6g 精准取量
   - 12 小时持妆
   - 遮瑕不厚重
   - 敏感肌友好

4. **科学成分解析**
   - 烟酰胺（提亮）
   - 透明质酸（保湿）
   - 氧化锌（控油）

5. **真实持妆数据**
   - 92% 用户持妆 12 小时
   - 89% 用户遮瑕满意度
   - 95% 敏感肌无刺激

6. **转化尾部**
   - 价格：¥198
   - 购买按钮
   - 联系方式

## 技术栈
- Next.js 14（App Router）
- Tailwind CSS
- Framer Motion
- TypeScript

## 部署
- 一键部署到 Vercel
```

---

## 📊 Codex vs Claude Code CLI vs Antigravity

| 维度 | Codex Mac | Claude Code CLI | Antigravity |
|------|-----------|-----------------|-------------|
| **界面** | ✅ 图形界面 | ❌ 终端 | ✅ 图形界面 |
| **难度** | ⭐⭐ | ⭐⭐ | ⭐ |
| **成本** | $0.15/1M tokens | 免费（有限额） | 免费（开源） |
| **实时预览** | ✅ 有 | ❌ 无 | ✅ 有 |
| **中文支持** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| **部署** | ✅ 一键 | ✅ 一键 | ❌ 手动 |
| **推荐指数** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |

---

## 💡 使用技巧

### 1. 描述清晰的需求

**✅ 好的描述：**
```
创建一个玛露遮瑕膏的营销落地页：
- 使用 Next.js + Tailwind CSS
- 浅色背景（米白、裸色）
- 包含 6 个肤质问题卡片
- 部署到 Vercel
```

**❌ 差的描述：**
```
帮我做一个网站
```

---

### 2. 分步执行

**步骤 1：创建项目**
```
创建 Next.js 项目，使用 Tailwind CSS
```

**步骤 2：添加 Hero Section**
```
添加 Hero Section，包含：
- 产品名称
- 副标题
- CTA 按钮
```

**步骤 3：添加其他 Section**
```
添加适用肤质图谱、产品亮点等 Section
```

---

### 3. 实时预览和调试

- ✅ 使用内置浏览器预览
- ✅ 实时查看代码修改效果
- ✅ 自动保存和版本控制

---

## 🎯 快速开始（5 分钟）

### 步骤 1: 打开 Codex Mac 应用
```bash
open /Applications/Codex.app
```

### 步骤 2: 创建新项目
- 点击 "New Project"
- 选择 "Next.js + Tailwind CSS"
- 项目名称：malu-landing-page

### 步骤 3: 输入 Prompt

**直接复制粘贴：**
```
创建玛露 6g 罐装遮瑕膏的营销落地页：

设计：
- 浅色背景（米白、裸色）
- 简约字体（Inter）
- 淡入动画

结构：
1. Hero Section（产品名称 + CTA）
2. 6 个肤质问题卡片
3. 产品亮点
4. 成分解析
5. 持妆数据
6. 购买 Footer

技术：
- Next.js 14
- Tailwind CSS
- Framer Motion

部署到 Vercel
```

### 步骤 4: 查看预览
- Codex 自动生成代码
- 实时预览效果
- 一键部署

---

## 🔧 高级功能

### 1. 自定义组件
```typescript
// 创建可复用组件
components/
├── Hero.tsx
├── SkinConcernCard.tsx
├── ProductHighlight.tsx
└── DataProof.tsx
```

### 2. 动画配置
```typescript
// Framer Motion 配置
const fadeIn = {
  initial: { opacity: 0, y: 20 },
  animate: { opacity: 1, y: 0 },
  transition: { duration: 0.6 }
}
```

### 3. 响应式设计
```typescript
// Tailwind CSS 响应式类
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {/* 6 个肤质卡片 */}
</div>
```

---

## 📊 性能优化

### 1. 图片优化
```typescript
// 使用 Next.js Image 组件
import Image from 'next/image'

<Image
  src="/product.jpg"
  alt="玛露遮瑕膏"
  width={500}
  height={500}
  priority
/>
```

### 2. 代码分割
```typescript
// 动态导入组件
const DataProof = dynamic(() => import('./DataProof'), {
  loading: () => <p>Loading...</p>
})
```

### 3. 性能监控
- 使用 Lighthouse 评分
- 优化 Core Web Vitals
- 压缩静态资源

---

## 🚀 部署流程

### Vercel 一键部署

**步骤 1: 连接 GitHub**
```
在 Codex 中：
Settings → Git → Connect GitHub
```

**步骤 2: 推送代码**
```
Git → Push to GitHub
```

**步骤 3: 部署到 Vercel**
```
Deploy → Vercel → Deploy
```

**完成！** 🎉

---

## 💡 常见问题

### Q1: Codex Mac 应用收费吗？
**A:** 使用 OpenAI API，按 tokens 计费（$0.15/1M tokens）

### Q2: 中文支持如何？
**A:** 支持，但不如 Claude Code CLI 流畅

### Q3: 能否离线使用？
**A:** 不能，需要网络连接 OpenAI API

### Q4: 如何获取 API Key？
**A:** 访问 https://platform.openai.com/api-keys

---

## 📞 获取帮助

### 官方资源
- [Codex 官网](https://openai.com/codex/)
- [OpenAI 文档](https://platform.openai.com/docs/)
- [GitHub Issues](https://github.com/openai/codex)

### 社区支持
- [Stack Overflow](https://stackoverflow.com/)
- [Reddit](https://www.reddit.com/r/OpenAI/)
- [Discord](https://discord.gg/openai)

---

**开始使用 Codex Mac 应用！** 🚀

**5 分钟创建玛露落地页！**
