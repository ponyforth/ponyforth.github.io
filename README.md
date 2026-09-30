# 我的博客

基于 **Jekyll + GitHub Pages** 的静态博客。「推代码即发布」:把 Markdown 推到仓库,由 GitHub 自动构建成网站。

## 快速开始(写文章)

在 `_posts/` 下新建文件,命名 `YYYY-MM-DD-英文slug.md`,开头带上 frontmatter:

```markdown
---
layout: post
title: "文章标题"
date:   2026-09-30
categories: 分类
tags: [标签]
---
```

写好后 `commit` + `push`,GitHub 会自动构建,几分钟后生效。

## 首次部署到 GitHub Pages

1. 在 GitHub 新建一个仓库,名字必须是 **`你的用户名.github.io`**(Public),例如 `zhangsan.github.io`。
2. 关联本地仓库并推送:

   ```bash
   git init
   git add .
   git commit -m "init blog"
   git branch -M main
   git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
   git push -u origin main
   ```

3. 进入仓库 **Settings → Pages**,右侧 **Build and deployment → Source 选「Deploy from a branch」**,Branch 选 `main`,目录选 `/ (root)`,保存。
4. 等一两分钟,访问 `https://你的用户名.github.io` 即可。

> 因为是用 GitHub 原生支持的 Jekyll,部署**不需要写任何 GitHub Actions 文件**,这就是「推代码即发布」。

## 本地预览(可选)

不装也能用(推上去交给 GitHub 构建)。但如果你想写的时候实时看效果,装一下更爽:

```bash
gem install jekyll bundler
# 首次需生成 Gemfile 后:bundle install
bundle exec jekyll serve
# 然后浏览器打开 http://localhost:4000
```

## 目录结构

```
blog/
├─ _config.yml        # 站点配置(title/主题/插件)
├─ _posts/            # ★ 所有文章放这里(YYYY-MM-DD-slug.md)
├─ index.md           # 首页
├─ about.md           # 关于页
├─ assets/            # 图片等静态资源(随文章走)
└─ README.md
```

## 自定义

- **换主题**:改 `_config.yml` 里的 `theme:`(GitHub Pages 支持 [官方主题列表](https://pages.github.com/themes/))。
- **绑定自定义域名**:日后想用自己域名,在仓库 Settings → Pages 填自定义域名并在域名商加 CNAME 即可,内容零改动。