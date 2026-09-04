# 贡献指南（Contributing）

感谢你对小雨田的博客（leipengic.github.io）的关注！欢迎通过以下方式参与贡献。

## 行为准则

参与本项目即表示你同意遵守我们的[行为准则](CODE_OF_CONDUCT.md)。

## 如何贡献

### 报告问题

1. 先在 [Issues](https://github.com/leipengic/leipengic.github.io/issues) 中搜索是否已有人报告相同问题。
2. 提交新 issue 时请说明：问题现象、涉及的页面/文章、浏览器环境。

### 内容投稿（文章 / 修正）

1. Fork 本仓库并克隆到本地；
2. 从 `main` 分支创建分支：`git checkout -b post/your-slug`；
3. **新增文章**：在 `_posts/` 下新建 `yyyy-mm-dd-slug.md`，front matter 使用 `layout: post`；
4. **修正错别字 / 更新链接**：直接修改对应 Markdown；
5. 本地预览无误后推送并创建 Pull Request。

### 提交代码

- 涉及主题/构建配置的改动，请先开 issue 说明意图再动手；
- 保持 Markdown 与 front matter 格式规范，勿夹带个人敏感信息。

## 开发约定

- 站点基于 Jekyll + jekyll-theme-chirpy，文章用 Markdown 写作；
- 本地预览：`bundle exec jekyll s`；
- 请勿提交无关的构建产物或大体积二进制文件。

感谢你的贡献！
