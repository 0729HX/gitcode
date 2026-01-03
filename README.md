# HX的个人博客

基于Hexo框架的个人博客项目，使用Next主题。

## 项目信息

- **博客标题**: HX的个人博客
- **副标题**: 记录技术成长
- **描述**: 分享技术心得，记录学习历程
- **作者**: HX
- **邮箱**: hxzjx0729@163.com

## 技术栈

- **框架**: Hexo 5.5.3
- **主题**: Next
- **语言**: 中文 (zh-CN)
- **时区**: Asia/Shanghai

## 项目结构

```
E:\gitcode\
├── _config.yml              # Hexo主配置文件
├── source/                  # 源文件目录
│   └── _posts/             # 文章目录
├── themes/
│   └── next/               # Next主题
├── scaffolds/               # 模板目录
│   ├── draft.md           # 草稿模板
│   ├── page.md            # 页面模板
│   └── post.md            # 文章模板
├── .github/                # GitHub配置
│   └── dependabot.yml      # 依赖更新配置
├── .gitignore              # Git忽略文件
├── package.json             # 项目依赖
└── package-lock.json       # 依赖锁定文件
```

## 快速开始

### 安装依赖

```bash
npm install
```

### 创建新文章

```bash
hexo new "文章标题"
```

### 启动本地服务器

```bash
hexo server
```

访问地址: http://localhost:4000/

### 生成静态文件

```bash
hexo generate
```

## 部署

### 部署到 Cloudflare Pages

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 进入 **Workers & Pages** -> **Pages**
3. 点击 **Create a project**
4. 选择 **Connect to Git**
5. 选择您的 GitHub 仓库（0729HX/gitcode）
6. 配置构建设置：
   - **框架预设**: Hexo
   - **构建命令**: `npm run build`
   - **构建输出目录**: `public`
   - **Node.js 版本**: 24
7. 点击 **Save and Deploy**

Cloudflare Pages 会自动检测 Hexo 框架并使用正确的构建配置。每次推送代码到 GitHub 时，Cloudflare 会自动重新构建和部署。

### 部署到 GitHub Pages

```bash
hexo deploy
```

### 本地部署测试

```bash
hexo clean
hexo generate
hexo server
```

访问地址: http://localhost:4000/

## 常用命令

| 命令 | 说明 |
|------|------|
| `hexo new "title"` | 创建新文章 |
| `hexo new page "name"` | 创建新页面 |
| `hexo generate` | 生成静态文件 |
| `hexo server` | 启动本地服务器 |
| `hexo deploy` | 部署到远程服务器 |
| `hexo clean` | 清理缓存文件 |

## 主题配置

Next主题的配置文件位于: `themes/next/_config.yml`

### 主题特性

- 响应式设计
- 多种布局方案
- 丰富的主题配置
- 支持评论系统
- 支持搜索功能
- 支持代码高亮
- 支持数学公式

## 开发环境

- **Node.js**: v24.12.0
- **npm**: 11.6.2
- **Git**: 2.47.1.windows.1

## 许可证

MIT License

## 联系方式

- 邮箱: hxzjx0729@163.com
- GitHub: https://github.com/0729HX

---

最后更新: 2026-01-03
