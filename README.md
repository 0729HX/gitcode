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

### 部署

```bash
hexo deploy
```

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
- GitHub: https://github.com/hxzjx

---

最后更新: 2026-01-03
