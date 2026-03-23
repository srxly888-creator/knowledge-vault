# 🎨 玛露（Malu）6g 罐装遮瑕膏 - 高转化落地页

> **项目类型**: 营销落地页（长图海报）
> **目标**: 复用高转化结构，打造去工厂化的高端美妆品牌
> **实现方式**: AI 工具链（GLM + Claude Code CLI）

---

## 📊 项目分析

### 原图结构（小红书爆量课）

1. **头图（Hero Section）**
   - 主标题：10倍增长！小红书爆量课
   - 深色科技感背景

2. **适合学员画像**（6 个网格卡片）
   - 品牌创始人
   - 内容创作者
   - 操盘手
   - 等

3. **课程亮点**
   - AI 落地
   - 小红书实操

4. **授课导师**
   - 头像 + Title
   - 实战背景

5. **课程权限与解决的问题**
   - 徽章样式展示权益
   - 痛击业务瓶颈
   - SOP 解决方案

6. **课程大纲**
   - 树状/列表结构
   - 系统性展示

7. **数据背书**
   - 后台收益截图
   - 流量数据

8. **转化尾部**
   - 首期特惠价格（6980 元）
   - 扫码报名入口

---

## 🎯 玛露（Malu）重构策略

### 视觉重构
- ❌ **摒弃**：深蓝底色（压迫感）
- ✅ **采用**：浅色背景（米白、柔和裸色）
- ✅ **目标**：衬托美妆产品质感

### 语境重塑
- ✅ **客观专业**：去工厂化的高级品牌调性
- ✅ **拒绝宏大叙事**：不用苦难营销
- ✅ **产品实力说话**：科学配方 + 持妆数据

---

## 🛠️ 实现路径

### 方案 1: GLM（文案）+ Claude Code CLI（开发）⭐⭐⭐⭐⭐

#### 第一步：给 GLM 的文案 Prompt

```
你现在是玛露（Malu）美妆品牌的资深内容策略师。请参考经典营销单页的逻辑框架（精准人群-产品亮点-痛点解决-权威背书），为我们的核心产品'6g 罐装遮瑕膏'撰写一份单页网站文案。

要求：
* 语气必须极致专业，带有去工厂化的高端美学感。
* 拒绝任何宏大叙事或苦难营销，客观、直接地陈述产品在底妆上的技术优势。
* 产出 Markdown 格式的内容结构，包含：适用肤质图谱、产品核心亮点（遮瑕与轻薄的平衡点）、科学成分解析、以及真实消费者的持妆数据证明。

目标用户：
- 有黑眼圈、痘印、色斑困扰的女性
- 追求轻薄自然底妆的都市白领
- 对成分敏感的理性消费者

产品特性：
- 6g 罐装设计（便携、精准取量）
- 遮瑕力强但不厚重
- 持妆 12 小时
- 适合敏感肌

请按以下结构输出：

# 玛露 6g 罐装遮瑕膏

## 适用肤质图谱
[6 个网格卡片，每个描述一个肤质问题]

## 产品核心亮点
[3-5 个亮点，聚焦遮瑕与轻薄的平衡]

## 科学成分解析
[成分表 + 功效说明]

## 真实持妆数据
[用户反馈 + 持妆时长统计]

## 购买信息
[价格 + 购买方式]
```

---

#### 第二步：给 Claude Code CLI 的开发 Prompt

```
Read the generated copy.md file. As an expert frontend developer, build a responsive single-page application (SPA) using Next.js and Tailwind CSS.

Design constraints:
* Strictly use a premium light color palette (off-whites, soft beige, warm creams). Do not use dark or heavily saturated backgrounds.
* Structure the layout sequentially like a high-converting promotional poster (Hero section, Target Audience cards, Highlight features, Data proof, Pricing footer).
* Use clean, minimalist typography and subtle fade-in animations to reflect a highly professional, high-end cosmetic brand aesthetic.

Technical requirements:
* Next.js 14 (App Router)
* Tailwind CSS for styling
* Framer Motion for animations
* Mobile-first responsive design
* Optimized images (WebP format)

Sections to implement:
1. Hero Section: Product name + tagline + CTA button
2. Skin Concern Cards: 6 grid cards with icons
3. Product Highlights: 3-5 feature cards
4. Ingredient Analysis: Clean layout with scientific data
5. Data Proof: User testimonials + statistics
6. Pricing Footer: Price + purchase button

Deploy to Vercel when complete.
```

---

### 方案 2: Antigravity（自动化开发）⭐⭐⭐⭐

#### 给 Antigravity Manager 的 Prompt

```
Create a new promotional web project for the Malu cosmetics brand, specifically a landing page for our 6g jar concealer.

Requirements:
* Layout: Emulate a high-converting long-scroll poster. Include sections for User Skin Concerns (e.g., dark circles, blemishes), Product Form (6g jar specifics), Professional Formulation Highlights, and Effectiveness Data.
* UI/UX: Implement a sophisticated light-themed design system. Use CSS to create a clean, de-industrialized, professional aesthetic that avoids any 'cheap' or overly aggressive marketing visual cues.
* Agent Execution: Plan the component structure, write the React code, install necessary UI libraries for smooth scrolling, run the local server, and capture browser screenshots of the final page for my review.

Color Palette:
* Background: #F5F5F0 (Off-white)
* Accent: #D4A574 (Soft beige)
* Text: #2C2C2C (Dark gray)
* Highlight: #F8E8D6 (Warm cream)

Typography:
* Headings: Inter (sans-serif)
* Body: Inter (light weight)
* Data: JetBrains Mono (monospace)

Components:
1. Hero: Full-width hero with product image
2. Concerns: 6-card grid with icons
3. Highlights: Alternating image-text layout
4. Ingredients: Two-column layout
5. Data: Statistics cards with animations
6. Footer: Simple CTA with price
```

---

### 方案 3: Codex（OpenAI Mac 应用）⭐⭐⭐

#### 给 Codex 的 Prompt

```
Create a Next.js landing page for Malu 6g jar concealer with the following structure:

Sections:
1. Hero: "玛露 6g 罐装遮瑕膏 - 轻薄如肤，遮瑕如影"
2. Skin Concerns (6 cards):
   - 黑眼圈
   - 痘印
   - 色斑
   - 肤色不均
   - 细纹
   - 毛孔粗大
3. Product Highlights:
   - 6g 精准取量
   - 12 小时持妆
   - 遮瑕不厚重
   - 敏感肌友好
4. Ingredients:
   - 烟酰胺（提亮）
   - 透明质酸（保湿）
   - 氧化锌（控油）
5. Data Proof:
   - 92% 用户持妆 12 小时
   - 89% 用户遮瑕满意度
   - 95% 敏感肌无刺激
6. Footer:
   - 价格：¥198
   - 购买按钮

Design:
* Light color palette (off-whites, beige)
* Minimalist typography
* Subtle animations
* Mobile-first responsive

Use Tailwind CSS and Framer Motion.
```

---

## 🚀 快速实现（5 分钟）

### 步骤 1: 生成文案（GLM）

**复制粘贴到 GLM：**
```
你现在是玛露（Malu）美妆品牌的资深内容策略师。请为'6g 罐装遮瑕膏'撰写单页网站文案。

要求：
* 极致专业，去工厂化的高端美学感
* 拒绝宏大叙事，用产品实力说话
* Markdown 格式

结构：
1. 适用肤质图谱（6 个网格卡片）
2. 产品核心亮点（遮瑕与轻薄的平衡）
3. 科学成分解析
4. 真实持妆数据
5. 购买信息
```

---

### 步骤 2: 生成代码（Claude Code CLI）

**复制粘贴到 Claude Code CLI：**
```
Read copy.md. Build a Next.js landing page with Tailwind CSS.

Design:
* Light color palette (off-whites, beige)
* Minimalist typography
* Subtle animations
* Mobile-first

Sections:
1. Hero
2. 6 skin concern cards
3. Product highlights
4. Ingredients
5. Data proof
6. Pricing footer

Deploy to Vercel.
```

---

## 📊 效果预期

### 转化率优化

| 元素 | 原图 | 玛露版本 | 优化点 |
|------|------|----------|--------|
| **头图** | 深蓝科技感 | 浅色优雅 | ✅ 减少压迫感 |
| **人群定位** | 6 个学员画像 | 6 个肤质问题 | ✅ 更精准 |
| **亮点展示** | AI + 小红书 | 遮瑕 + 轻薄 | ✅ 产品导向 |
| **数据背书** | 收益截图 | 持妆数据 | ✅ 更可信 |
| **价格** | 6980 元 | 198 元 | ✅ 低门槛 |

---

## 🎯 关键成功因素

### 1. 视觉调性
- ✅ 浅色背景（米白、裸色）
- ✅ 简约字体
- ✅ 高质量产品图

### 2. 文案风格
- ✅ 客观专业
- ✅ 拒绝苦难营销
- ✅ 数据说话

### 3. 结构逻辑
- ✅ 头图（吸引注意）
- ✅ 人群定位（对号入座）
- ✅ 产品亮点（建立兴趣）
- ✅ 数据背书（建立信任）
- ✅ 转化入口（促成购买）

---

## 💡 进阶优化

### A/B 测试建议

#### 版本 A（专业版）
- 强调成分科学
- 数据图表展示
- 专业术语

#### 版本 B（情感版）
- 强调使用场景
- 用户故事
- 情感共鸣

**测试指标：**
- 页面停留时间
- 滚动深度
- 转化率

---

## 📞 获取帮助

### 工具支持
- [GLM](https://chatglm.cn/)
- [Claude Code CLI](https://claude.ai/)
- [Antigravity](https://antigravity.so/)
- [Codex](https://openai.com/codex/)

### 设计资源
- [Tailwind CSS](https://tailwindcss.com/)
- [Framer Motion](https://www.framer.com/motion/)
- [Unsplash](https://unsplash.com/)（免费图片）

---

**开始创建玛露的高转化落地页！** 🚀

**记住：5 分钟生成文案 + 5 分钟生成代码 = 10 分钟上线！**
