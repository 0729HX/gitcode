---
title: Cloudflare Pages 部署指南
date: 2026-01-03 08:28:00
tags: [Cloudflare, 部署, 教程]
categories: [技术教程]
---

## 前言

Cloudflare Pages 是一个免费的静态网站托管平台，提供全球 CDN 加速、自动 HTTPS 和持续集成功能。本文将详细介绍如何使用 Cloudflare Pages 部署 Hexo 博客。

## 准备工作

### 1. 注册 Cloudflare 账号

访问 [Cloudflare](https://dash.cloudflare.com/sign-up) 注册账号。

### 2. 准备 GitHub 仓库

确保你的 Hexo 博客代码已经推送到 GitHub 仓库。

## 创建 Pages 项目

### 步骤 1：进入 Pages 页面

登录 Cloudflare 控制台，点击左侧菜单的 "Workers & Pages"，然后点击 "Create application"。

### 步骤 2：选择创建方式

选择 "Pages" 标签页，然后点击 "Connect to Git"。

### 步骤 3：连接 GitHub 仓库

1. 点击 "Connect to Git" 按钮
2. 选择你的 GitHub 仓库
3. 如果是第一次连接，需要授权 Cloudflare 访问你的 GitHub 账号

### 步骤 4：配置构建设置

在 "Build settings" 部分配置：

- **Project name**: 输入项目名称（例如：my-blog）
- **Production branch**: 选择主分支（通常是 main 或 master）
- **Framework preset**: 选择 "None"
- **Build command**: `npm run build`
- **Build output directory**: `public`

### 步骤 5：配置环境变量

在 "Environment variables" 部分添加：

- **Key**: `NODE_VERSION`
- **Value**: `20`

这个设置很重要，因为 Hexo 8.1.1 需要 Node.js 18 或更高版本。

### 步骤 6：部署

点击 "Save and Deploy" 开始部署。Cloudflare Pages 会自动：
1. 克隆你的 GitHub 仓库
2. 安装依赖
3. 运行构建命令
4. 部署到全球 CDN

## 自定义域名

### 添加自定义域名

1. 在项目页面点击 "Custom domains"
2. 点击 "Set up a custom domain"
3. 输入你的域名（例如：blog.example.com）
4. 点击 "Continue"

### 配置 DNS

Cloudflare 会自动为你配置 DNS 记录。如果你的域名也在 Cloudflare 管理，DNS 记录会自动添加。

### 启用 HTTPS

Cloudflare Pages 会自动为你的网站提供免费的 SSL 证书，无需额外配置。

## 自动部署

### 触发部署

Cloudflare Pages 会在以下情况自动触发部署：

1. 推送代码到配置的分支
2. 创建 Pull Request
3. 合并 Pull Request

### 部署预览

每次创建 Pull Request 时，Cloudflare Pages 会创建一个预览部署，方便你查看更改效果。

### 部署历史

在项目页面可以查看所有部署历史，包括：
- 部署状态
- 部署时间
- 提交信息
- 部署日志

## 高级配置

### 自定义构建命令

如果你的项目需要特殊的构建命令，可以在 "Build command" 中指定：

```bash
# 使用 npm
npm run build

# 使用 yarn
yarn build

# 使用 pnpm
pnpm build
```

### 环境变量

除了 `NODE_VERSION`，你还可以添加其他环境变量：

- `HEXO_ENV`: 设置 Hexo 环境（production/development）
- `GIT_USER`: Git 用户名
- 自定义 API 密钥等

### 重定向规则

在项目设置中可以配置重定向规则：

```yaml
# 重定向旧链接到新链接
https://old.example.com/* -> https://new.example.com/:splat
```

### 头部设置

可以添加自定义 HTTP 头部：

```yaml
# 安全头部
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
```

## 性能优化

### CDN 加速

Cloudflare Pages 提供全球 CDN 加速，你的网站会自动分发到全球各地的边缘节点。

### 图片优化

Cloudflare 会自动优化图片，包括：
- 自动格式转换（WebP、AVIF）
- 自适应大小
- 懒加载

### 缓存策略

Cloudflare Pages 提供智能缓存策略：
- 静态资源长期缓存
- HTML 页面短时间缓存
- 支持缓存清除

## 监控和分析

### 访问统计

Cloudflare Pages 提供详细的访问统计：
- 访问量
- 独立访客
- 地理分布
- 设备类型

### 性能监控

可以查看网站性能指标：
- 加载时间
- 首字节时间（TTFB）
- 资源加载时间

### 错误日志

查看部署和运行时错误日志，方便调试问题。

## 故障排除

### 构建失败

如果构建失败，检查以下几点：

1. **Node.js 版本**: 确保设置了正确的 `NODE_VERSION`
2. **依赖问题**: 检查 `package.json` 中的依赖是否正确
3. **构建命令**: 确认构建命令是否正确
4. **查看日志**: 在部署日志中查看详细错误信息

### 部署后无法访问

1. 检查 DNS 配置是否正确
2. 确认域名 DNS 记录已生效
3. 查看防火墙设置
4. 检查 Cloudflare Pages 项目状态

### 环境变量不生效

1. 确认环境变量名称拼写正确
2. 检查环境变量是否在正确的环境中设置
3. 重新触发部署

## 最佳实践

### 1. 使用持续集成

- 利用 Cloudflare Pages 的自动部署功能
- 为 Pull Request 创建预览部署
- 在合并前预览更改

### 2. 优化构建速度

- 使用 `.npmrc` 配置 npm 镜像
- 缓存依赖
- 并行构建

### 3. 监控性能

- 定期查看访问统计
- 优化加载速度
- 使用 Cloudflare 的性能工具

### 4. 备份策略

- 定期备份 GitHub 仓库
- 使用 Cloudflare 的版本控制功能
- 保留重要配置的副本

## 总结

Cloudflare Pages 是一个强大且免费的静态网站托管平台，特别适合部署 Hexo 博客。通过本文的指南，你应该能够：

1. 成功部署 Hexo 博客到 Cloudflare Pages
2. 配置自定义域名和 HTTPS
3. 利用自动部署功能
4. 优化网站性能
5. 解决常见问题

开始使用 Cloudflare Pages，享受快速、稳定、免费的静态网站托管服务吧！
