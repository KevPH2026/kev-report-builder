# 🤖 Kev 的报告生成器 (Kev 的报告生成器)

<div align="center">

![Report Builder](https://img.shields.io/badge/Report-Builder-3B82F6?style=for-the-badge&logo=robot&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-OpenClaw-6366F1?style=for-the-badge&logo=claw&logoColor=white)
![Style](https://img.shields.io/badge/Style-10+_Templates-10B981?style=for-the-badge&logo=paintbrush&logoColor=white)
![Marketing](https://img.shields.io/badge/Marketing-Ready-DD6B20?style=for-the-badge&logo=lightbulb&logoColor=white)

### 一句话输入 → 多风格可视化报告 → 直接发文件

**无需部署环境，报告生成后直接发送，收到即可查看**

[演示案例](#-演示案例) · [快速开始](#-快速开始) · [10种风格](#-10种风格) · [部署方式](#-部署方式)

</div>

---

## 🎯 这是什么

一个 AI 驱动的**可视化报告生成器**。

你告诉 AI 要研究什么主题、想要什么风格 → AI 自动生成可查看的 HTML 报告 → 直接发给你

**完全离线可用**，不需要 Vercel、不需要任何部署环境，收到 `.html` 文件直接浏览器打开。

---

## ✨ 核心特性

| 特性 | 说明 |
|------|------|
| 🗣️ **自然语言输入** | 一句话描述需求，不用学命令 |
| 🎨 **10 种视觉风格** | 仪表盘、信息图、杂志风、暗黑科技… |
| 📊 **内置可视化** | 进度条、图表、颜色编码，非纯文字 |
| 🔗 **来源自动标注** | 每个模块带来源标签，可查证 |
| 📎 **直接发送文件** | 无需部署，收到即可查看 |
| 🔄 **多版本并行** | 一次生成 N 个风格，对比选择 |

---

## 🚀 快速开始

### 基本语法

```
报告 [主题]，[风格]
```

### 示例

```
报告 Meta 广告算法新规，信息图
报告 DTC 品牌出海，仪表盘 + 杂志风
报告 AI 工具选型，极简白
```

---

## 🎨 10 种风格

| 风格 | 预览 | 适用场景 |
|------|------|---------|
| `dashboard` | 📊 | 高管汇报、数据呈现 |
| `infographic` | 🗺️ | **算法/政策解读（默认推荐）** |
| `magazine` | 📰 | 学术、权威感 |
| `dark` | 💻 | 程序员/极客受众 |
| `minimal` | 🤍 | 简约北欧风 |
| `retro` | 🗞️ | 老式排版质感 |
| `gradient` | 🌈 | 现代柔和暖色 |
| `data` | 📈 | 表格为主，严肃专业 |
| `playful` | 🎉 | emoji 点缀，轻松活泼 |
| `professional` | 🔷 | 企业信任感 |

---

## 📋 使用模式

### 模式 A｜指定风格
```
帮我写一份关于 [主题] 的报告，风格是 [风格名]
```

### 模式 B｜让 AI 推荐
```
帮我研究 [主题]，你推荐最适合的风格
```
AI 根据主题判断最适合的风格组合。

### 模式 C｜描述感觉
```
"要一个看起来很权威的、像杂志封面的报告"
"科技感强一点，暗色系"
"活泼一点，多用 emoji"
```

### 模式 D｜一次生成多个风格
```
生成 5 个版本的报告：信息图、仪表盘、暗黑科技、极简、复古
```

---

## 📂 交付方式

### 默认：直接发送文件 ✅

生成报告后，**直接发送 HTML 文件给你**。

收到后浏览器打开 `.html` 即可，**完全离线、立即可用**。

### 可选：自己部署到 Vercel

如需自己部署获得永久在线链接：

```bash
# 1. 注册 Vercel
https://vercel.com

# 2. 安装 CLI
npm i -g vercel

# 3. 部署
cd [报告目录]
vercel login
vercel deploy --prod
```

---

## 🔍 质量标准

每份报告生成后必须通过：

- ✅ `<!DOCTYPE>` / `<html>` / `<head>` / `<body>` 完整
- ✅ 所有标签正确闭合，无残标
- ✅ 有真正的可视化元素（进度条/图表/颜色编码）
- ✅ 每个模块有来源引用
- ✅ 页面能正常渲染

> **宁可重做一个精品，不发十个垃圾。**

---

## 📚 内置来源库

| 来源 | URL |
|------|-----|
| Meta透明度中心 | transparency.meta.com |
| Meta官方博客 | about.fb.com |
| TechCrunch | techcrunch.com |
| Anchour | anchour.com |
| Social Media Today | socialmediatoday.com |
| GrowthHQ | growthhq.io |

---

## 📖 演示案例

### Meta 算法研究报告
10 个可视化版本，覆盖限流封号、算法推荐、官方政策解读
- [信息图版（默认）](https://meta-reports.vercel.app)
- [仪表盘版](https://meta-reports.vercel.app/v01-executive-dashboard.html)
- [暗黑科技版](https://meta-reports.vercel.app/v02-dark-tech.html)
- [查看全部版本](https://meta-reports.vercel.app/all-versions.html)

---

## 🔧 安装到 OpenClaw

```bash
# 克隆到本地 skills 目录
git clone https://github.com/KevPH2026/report-builder-skill.git ~/.openclaw/skills/report-builder

# 或从 clawhub 安装
npx clawhub install report-builder
```

---

## 📄 文件结构

```
report-builder-skill/
├── README.md              # 本文件
├── REPORT-BUILDER-SKILL.md # Skill 定义文件
├── SKILL.md               # 内部技能定义
└── ONBOARDING.md          # 用户引导文档
```

---

<div align="center">

**让报告生成变简单**

Made with ❤️ for OpenClaw

</div>
