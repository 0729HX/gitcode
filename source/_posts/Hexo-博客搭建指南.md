---
title: Hexo 博客搭建指南
date: 2026-01-03 08:26:13
tags: [Hexo, 博客, 教程]
categories: [技术教程]
---

## 前言

Hexo 是一个快速、简洁且高效的博客框架，基于 Node.js。它使用 Markdown 解析文章，可以在几秒内生成静态网页。本文将详细介绍如何使用 Hexo 搭建个人博客。

## 环境准备

### 1. 安装 Node.js

Hexo 基于 Node.js，首先需要安装 Node.js。建议使用 Node.js 18 或更高版本。

```bash
# 检查 Node.js 版本
node -v
# 检查 npm 版本
npm -v
```

### 2. 安装 Git

如果还没有安装 Git，需要先安装 Git 用于版本控制。

```bash
# 检查 Git 版本
git --version
```

## 安装 Hexo

使用 npm 安装 Hexo：

```bash
npm install -g hexo-cli
```

## 初始化博客

创建一个新的博客目录并初始化：

```bash
# 创建博客目录
mkdir my-blog
cd my-blog

# 初始化 Hexo
hexo init
npm install
```

## 常用命令

### 本地开发

```bash
# 启动本地服务器
hexo server
# 或简写
hexo s
```

访问 http://localhost:4000 查看效果。

### 生成静态文件

```bash
# 生成静态文件
hexo generate
# 或简写
hexo g
```

### 部署

```bash
# 部署到服务器
hexo deploy
# 或简写
hexo d
```

### 创建新文章

```bash
# 创建新文章
hexo new "文章标题"
```

## 配置文件

### _config.yml

这是 Hexo 的主配置文件，包含博客的基本设置：

```yaml
# Site
title: 我的博客
subtitle: 记录技术成长
description: 分享技术心得
author: 你的名字
language: zh-CN
timezone: Asia/Shanghai

# URL
url: https://yourname.github.io
```

### 主题配置

NexT 是一个优秀的 Hexo 主题，功能强大且美观。

#### 安装 NexT 主题

```bash
cd themes
git clone https://github.com/next-theme/hexo-theme-next.git next
```

#### 配置主题

在 `_config.yml` 中设置主题：

```yaml
theme: next
```

在 `themes/next/_config.yml` 中配置主题选项：

```yaml
# 选择主题方案
scheme: Pisces

# 启用深色模式
darkmode: true

# 配置导航菜单
menu:
  home: / || fa fa-home
  about: /about/ || fa fa-user
  tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive
```

## 部署到 Cloudflare Pages

### 1. 创建 GitHub 仓库

将博客代码推送到 GitHub 仓库。

### 2. 连接 Cloudflare Pages

1. 登录 Cloudflare 控制台
2. 进入 Pages 页面
3. 点击 "Create a project"
4. 选择 "Connect to Git"
5. 选择你的 GitHub 仓库

### 3. 配置构建设置

在 Cloudflare Pages 中配置：

- **构建命令**: `npm run build`
- **构建输出目录**: `public`
- **环境变量**:
  - `NODE_VERSION`: `20`

### 4. 自动部署

每次推送到 GitHub，Cloudflare Pages 会自动构建和部署。

## 常用插件

### 搜索功能

安装搜索插件：

```bash
npm install hexo-generator-searchdb --save
```

在 `_config.yml` 中添加：

```yaml
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

在主题配置中启用：

```yaml
local_search:
  enable: true
```

### Sitemap

安装 sitemap 插件：

```bash
npm install hexo-generator-sitemap --save
```

在 `_config.yml` 中配置：

```yaml
sitemap:
  path: sitemap.xml
  rel: false
  tags: true
  categories: true
```

## 写作技巧

### Front-matter

每篇文章的开头需要添加 Front-matter：

```markdown
---
title: 文章标题
date: 2026-01-03 08:26:13
tags: [标签1, 标签2]
categories: 分类
---
```

### Markdown 语法

Hexo 支持 Markdown 语法，可以轻松格式化文本：

```markdown
# 一级标题
## 二级标题
**粗体**
*斜体*
[链接](https://example.com)
![图片](/images/image.png)
```

### 代码块

使用三个反引号包裹代码：

```javascript
function hello() {
  console.log("Hello, Hexo!");
}
```

## 总结

Hexo 是一个功能强大的静态博客框架，配合 NexT 主题可以快速搭建出美观的个人博客。通过 Cloudflare Pages 可以实现免费的自动化部署。希望本文能帮助你快速上手 Hexo 博客搭建！
