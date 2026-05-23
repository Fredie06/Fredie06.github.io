# Fredie 个人网站维护指南

## 网站概况

| 项目 | 说明 |
|------|------|
| 地址 | https://fredie06.github.io |
| 技术 | [Hugo](https://gohugo.io/) 静态网站生成器 |
| 主题 | [PaperMod](https://github.com/adityatelange/hugo-PaperMod) |
| 部署 | GitHub Actions 自动部署 |

---

## 快速开始

### 1. 环境准备

确保电脑上安装了 Hugo（Extended 版）：

```bash
winget install Hugo.Hugo.Extended
```

验证安装：
```bash
hugo version
```

### 2. 本地预览

在项目根目录运行：

```bash
hugo server -D
```

浏览器打开 `http://localhost:1313` 就能看到网站。你改任何文件，浏览器都会自动刷新。

### 3. 提交部署

修改满意后：

```bash
git add -A
git commit -m "描述你改了什么"
git push
```

Push 后 GitHub Actions 会自动构建和部署，30 秒左右就能在线上看到更新。

---

## 项目结构

```
personal-site/
├── hugo.yaml              ← 网站配置文件
├── assets/
│   └── images/
│       └── avatar.jpg     ← 头像图片
│   └── css/extended/
│       └── custom.css     ← 自定义样式
├── content/
│   ├── about/_index.md    ← "关于"页面
│   └── projects/_index.md ← "项目"页面
├── archetypes/default.md  ← 新文章模板
├── themes/PaperMod/       ← 主题文件（不要改这里）
└── .github/workflows/     ← 自动部署脚本
```

---

## 日常操作

### 修改个人信息

编辑 `hugo.yaml`：

- `title` — 网站标题
- `profileMode.title` / `profileMode.subtitle` — 首页标题和简介
- `profileMode.imageUrl` — 头像图片路径
- `socialIcons` — 社交链接
- `profileMode.buttons` — 首页按钮

### 更新头像

1. 把新图片放到 `assets/images/` 目录
2. 修改 `hugo.yaml` 中的 `imageUrl`

### 修改"关于"页面

编辑 `content/about/_index.md`

### 添加/修改项目

编辑 `content/projects/_index.md`

Hugo 内容文件支持 Markdown 格式：

```markdown
## 项目名称

项目描述。

- 技术点1
- 技术点2

[GitHub 仓库](链接)
```

### 添加新页面

```bash
hugo new content 新页面名称/_index.md
```

### 调整配色/样式

编辑 `assets/css/extended/custom.css`

---

## 写新文章/博客（未来可能用到）

创建新文章：

```bash
hugo new content posts/文章标题.md
```

这会生成 `content/posts/文章标题.md`，编辑它即可。

---

## 常见问题

### 本地预览和线上不一样

浏览器可能缓存了旧版本，按 `Ctrl+Shift+R` 强制刷新。

### 部署失败（Actions 红叉）

去 GitHub 仓库的 Actions 标签页，点失败的 workflow，看日志报错信息。常见原因：
- Hugo 语法错误（比如 YAML 配置缩进不对）
- Markdown 格式问题
- GitHub Pages 设置问题

### 想恢复之前的版本

```bash
git log --oneline          # 查看历史记录
git checkout 提交ID -- 文件名  # 恢复某个文件
```

---

## 有用的链接

- [Hugo 文档](https://gohugo.io/documentation/)
- [PaperMod 主题文档](https://github.com/adityatelange/hugo-PaperMod/wiki)
- [PaperMod 示例配置](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation)

---

## 一句话总结

> 改 `hugo.yaml` 调配置，改 `content/` 写内容，改 `custom.css` 调外观，最后 `git push` 就上线。
