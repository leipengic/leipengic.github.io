# 小雨田的博客（leipengic.github.io）

基于 **Jekyll + jekyll-theme-chirpy** 主题构建的个人博客，部署于 GitHub Pages，绑定自定义域名 **hyx.leipeng.us.kg**。

- 主题：[jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)
- 部署：GitHub Actions（`build_type: workflow`）自动构建并发布，每次 push 到 `main` 分支即触发
- 内容：Markdown 写作，文章位于 `_posts/`，导航页位于 `_tabs/`

## 目录结构

```
leipengic.github.io/
├── .github/workflows/pages.yml   # GitHub Actions：构建 + 部署到 Pages
├── .gitignore                    # 忽略 Jekyll/Chirpy 构建产物
├── CNAME                         # 自定义域名 hyx.leipeng.us.kg
├── Gemfile                       # 依赖：jekyll + jekyll-theme-chirpy
├── _config.yml                   # 站点配置（主题、社交链接、分页、tabs 集合）
├── _posts/                       # 博客文章（Markdown，文件名 yyyy-mm-dd-slug.md）
│   └── 2026-09-01-blog-launch.md
├── _tabs/                        # 顶部导航静态页（Chirpy collection）
│   ├── about.md                  # 关于页（中文），/about/
│   └── archive.md                # 归档页，/archive/
├── assets/img/avatar.jpg         # 头像（原 stock-photo.jpg 重命名）
├── index.md                      # 首页（layout: home）
├── index-en.md                   # 关于页（英文），/index-en.html
└── README.md
```

## 本地预览

```bash
bundle install
bundle exec jekyll s -d "_site" --trace
# 浏览器打开 http://127.0.0.1:4000
```

## 常用操作

- **新增文章**：在 `_posts/` 下新建 `yyyy-mm-dd-slug.md`，开头 front matter 用 `layout: post`。
- **新增导航页**：在 `_tabs/` 下新建 `.md`，设置 `permalink` 即可出现在顶部导航。
- **修改社交链接**：编辑 `_config.yml` 的 `social.links`（B站、微信公众号等）。
- **切换主题色**：`_config.yml` 的 `theme_mode: light | dark`。

## 部署说明

仓库 Pages 的 Build source 已设为 **GitHub Actions**。推送 `main` 后，Actions 自动执行 `bundle exec jekyll b -d "_site"` 并将产物发布到 GitHub Pages。
