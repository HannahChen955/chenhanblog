# Hannah 的博客

一个个人写作空间，记录想法、感悟与值得留下的思考。

基于 [Astro](https://astro.build) 搭建，部署在 [Vercel](https://vercel.com)。

## 本地开发

```bash
npm install
npm run dev
```

打开 http://localhost:4321 查看。

## 写作流程

文章是 `src/content/blog/` 目录下的 Markdown 文件。新增一篇：

```bash
# 创建一个新文件，例如：
src/content/blog/some-slug.md
```

frontmatter 模板：

```yaml
---
title: '标题'
description: '一句话简介'
pubDate: '2026-04-27'
---

正文内容……
```

提交后 Vercel 自动部署。

## 项目结构

详见 [`CLAUDE.md`](./CLAUDE.md)，里面包含与 Claude Code 协作写作的工作流说明。

## 命令一览

| 命令 | 作用 |
|------|------|
| `npm run dev` | 启动本地开发服务器 |
| `npm run build` | 构建生产版本 |
| `npm run preview` | 预览构建结果 |
