# Report Builder Skill

## 核心能力

根据用户输入的研究主题，自动生成多风格可视化 HTML 报告。

---

## 快速开始

### 输入格式（两种）

**纯主题输入：**
```
帮我写一份关于 [主题] 的报告
```

**带风格指令：**
```
帮我写一份 [主题] 的报告，风格是 [风格名]
```

---

## 风格列表

| 风格 | 适用场景 |
|------|---------|
| `dashboard` / 仪表盘 | 高管汇报、数据呈现 |
| `dark` / 暗黑科技 | 程序员/极客受众 |
| `magazine` / 杂志社论 | 学术、权威感 |
| `infographic` / 信息图 | 算法规则解读（**默认推荐**）|
| `minimal` / 极简白 | 简约北欧风 |
| `retro` / 复古报纸 | 老式排版质感 |
| `gradient` / 渐变现代 | 现代柔和暖色 |
| `data` / 数据优先 | 表格为主，严肃专业 |
| `playful` / 活力创意 | emoji点缀，轻松活泼 |
| `professional` / 专业蓝 | 企业信任感 |

**多风格同时生成：**
```
生成3个版本的报告：infographic、dashboard、dark
```

---

## 输出规则

### 必须遵守

1. **引用数据必须标注来源** — 每个结论模块必须有对应来源引用
2. **区分"官方声明"与"第三方推测"** — 明确标注数据来源性质
3. **每个版本必须独立完整** — 不能有任何残标
4. **生成后自检清单** — 见下方质量检查

### 来源标注规范

```html
<!-- 每个HTML文件底部必须有来源区域 -->
<div class="sources">
  <h4>📚 参考来源（点击可查看原文）</h4>
  <ul>
    <li><a href="[官方URL]" target="_blank">[来源名称]</a></li>
    ...
  </ul>
</div>

<!-- 每个模块标题旁必须有来源标签 -->
<div class="section-title">
  模块标题
  <a href="[来源URL]" target="_blank" class="src-tag">[来源]</a>
</div>
```

### 来源优先级

1. 官方文档（Meta透明度中心、官方博客）
2. 权威媒体（TechCrunch、Social Media Today）
3. 行业分析（Anchour、GrowthHQ）
4. 案例数据（需标注"样本量N="或"来源：[平台]内部数据"）

---

## HTML 质量自检清单

**生成后、部署前必须逐项检查：**

### 结构完整性
- [ ] `<!DOCTYPE>` / `<html>` / `<head>` / `<body>` 完整
- [ ] 所有 `<div>` 有对应的 `</div>`
- [ ] 无残标 `<h1>` `<h2>` `<p>` `<ul>` 等

### 可视化质量
- [ ] 有真正的可视化元素（进度条、图表、颜色编码）
- [ ] 不是纯文字堆砌
- [ ] 布局有层次感（不是从头到尾单一列）

### 内容准确性
- [ ] 数据与需求一致
- [ ] 无乱码、无错误字符
- [ ] 逻辑通顺

### 功能完整性
- [ ] 页面能正常渲染
- [ ] 外部 CDN（字体、图标）能加载
- [ ] 截图预览确认布局正常

---

## 部署流程

### 单文件 HTML
```bash
# 直接部署到 Vercel（静态托管）
vercel deploy --prod --yes --token="[VercelToken]" --archive=tgz
```

### 多文件项目（推荐）
```bash
cd [项目目录]
vercel deploy --prod --yes --token="[VercelToken]"
```

### 入口页面
```bash
# 入口索引页命名：index.html
# 多版本时用 v[N]-[风格名].html
```

---

## 高级用法

### 多版本同时生成

支持一次生成 N 个风格，命名规范：
```
v01-dashboard.html     ← 大数字编号
v02-dark.html
v03-infographic.html
```

入口页 `index.html` 展示所有版本卡片导航。

### 来源数据库（内置）

系统已内置以下来源映射，可自动匹配：

| 来源 | URL |
|------|-----|
| Meta透明度中心 | transparency.meta.com |
| Meta官方博客 | about.fb.com |
| TechCrunch | techcrunch.com |
| Anchour | anchour.com |
| Social Media Today | socialmediatoday.com |
| GrowthHQ | growthhq.io |

### 自定义风格开发

如需新增风格，在 `~/.openclaw/workspace/output/` 下创建新 HTML 文件，
参考已有风格的结构和 CSS 变量系统。

---

## Vercel Token

已配置 token 存储于 `~/.vercel/token` 或直接使用：
```
<YOUR_VERCEL_TOKEN>
```

---

## 示例对话

**用户：** 帮我写一份关于 Meta 广告算法 2026 新规的报告，用 infographic 风格

**AI 响应流程：**
1. 搜索/整理 Meta 官方最新政策文献
2. 生成 infographic 风格 HTML（内置可视化：进度条、颜色编码、流程图）
3. 每个模块添加 `[来源]` 标签
4. 底部添加完整可点击来源列表
5. 自检（结构 + 可视化 + 来源标注）
6. 部署到 Vercel
7. 返回在线链接

**用户：** 再生成一个 dashboard 版本

**AI：** 复用已有研究内容，仅切换视觉风格，10分钟内完成部署。
