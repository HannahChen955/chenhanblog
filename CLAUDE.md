# 给 Claude Code 的工作说明

这是 Hannah 的个人博客。Hannah 主要用中文写作，希望博客成为她**统一的内容入口**——
所有想法都先沉淀到这里，而不是分散到公众号、即刻等平台。

她的核心目标是**持续地写**，而不是产出体系化或盈利化的内容。
所以你的工作是降低写作摩擦，不是提高写作"高度"。

## 写作工作流（最常见的请求）

Hannah 通常会这样找你：
- "我有点想法，帮我整理一下"
- "我刚才说了一堆，你帮我写成一篇文章"
- "今天想写一个关于 XX 的，但我没想清楚"

**你要做的**：

1. **倾听她说的内容**。允许她碎片化、跳跃地表达，不要打断结构。
2. **整理成 Markdown 文件**，放在 `src/content/blog/<slug>.md`。slug 用英文小写短横连字（kebab-case），简洁、不超过 5 个词。
3. **frontmatter 必填**：`title`、`description`、`pubDate`（用今天的日期 YYYY-MM-DD）。
4. **保留她的语气**。她写的是个人感悟，不要改成新闻稿、不要加套话、不要"总结升华"段。
5. **目标长度大约 800–1200 字**，但要服从内容本身——短就短，长就长。
6. **写完给她看**，用 `Read` 展示内容，让她确认或调整。
7. **她确认后** commit 并 push（如果远端已配置），Vercel 会自动部署。

## 写作风格的红线

- ❌ 不要加"总而言之"、"让我们一起"、"愿你……"这种结尾
- ❌ 不要把她口语化的表达全部改成书面语——保留一些"她说话的样子"
- ❌ 不要主动加 emoji（除非她要求）
- ❌ 不要加"作者按"、"声明"、"免责声明"
- ❌ 不要在文末加"如果你觉得有用，欢迎转发/订阅"——这不是公众号
- ✅ 段落之间留呼吸感，中文长文不要堆得太密
- ✅ 标题用 H2 (`##`)，避免一级标题（一级标题由 layout 自动渲染）

## 项目技术栈

- **Astro** v6 - 静态站点生成
- **TypeScript** strict 模式
- **MDX 支持** - 但默认用 `.md`，除非需要嵌入组件
- **托管**：Vercel（推 main 分支自动部署）

## 关键文件

- `src/content/blog/` - 所有文章
- `src/content.config.ts` - frontmatter 的 schema
- `src/consts.ts` - 站点标题、描述、作者
- `src/layouts/BlogPost.astro` - 文章页布局
- `src/pages/index.astro` - 首页（最近文章列表）
- `src/pages/blog/index.astro` - 全部文章归档（按年分组）
- `src/pages/about.astro` - 关于页
- `src/styles/global.css` - 中文排版优化的全局样式

## 部署相关

- 域名待 Hannah 申请。先用 Vercel 子域名上线。
- 当域名买好后，需要更新 `astro.config.mjs` 的 `site` 字段，并在 Vercel 项目里绑定。

## 内容备份

文章是 git 仓库里的纯文本，天然有备份。如果未来加图片，建议放 `public/images/<year>/` 下，
或用 Vercel Blob——避免把大图直接 commit 进仓库。

## 还没做但 Hannah 可能会想要的

- [ ] 评论系统（推荐 Giscus，基于 GitHub Discussions）
- [ ] 标签 / 分类
- [ ] 站内搜索（Pagefind 是最简单的方案）
- [ ] 邮件订阅（Buttondown 或 Resend）
- [ ] 暗色模式
- [ ] OG 图片自动生成

她**还没要求**这些。**不要主动加**。等她说"我想要 XX"再说。
