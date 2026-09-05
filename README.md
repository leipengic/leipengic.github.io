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

## 主要第三方依赖

站点基于 Ruby 生态构建，依赖集中在 `Gemfile`。

### 站点构建与主题

| 依赖 | 在项目中做的事 | 为什么选它 |
|---|---|---|
| `jekyll` | 把 `_posts/` 的 Markdown、`_tabs/` 的导航页和 `_config.yml` 编译成静态站点 | GitHub Pages 原生支持 Jekyll，无需自建构建链；Markdown 写作 + 静态输出，维护成本最低 |
| `jekyll-theme-chirpy` | 提供整套页面布局、代码高亮、暗色/亮色切换、搜索与归档能力 | 主题成熟、文档完善，中文排版与博客所需功能开箱即用，不必从零写布局 |

### 配套服务

| 服务 | 作用 |
|---|---|
| GitHub Actions | `build_type: workflow` 模式下自动 `bundle exec jekyll b`，产物发布到 Pages |
| GitHub Pages | 站点托管，绑定 `CNAME` 中的自定义域名 hyx.leipeng.us.kg |

> 组件版本：`jekyll ~> 4.3`、`jekyll-theme-chirpy ~> 7.0`（以 `Gemfile` 为准）。

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

## 鸣谢（Acknowledgments）

感谢以下开源项目与工具（图标均取自官方站点 / CDN）：

<table>
  <tr>
    <td align="center" width="140">
      <a href="https://github.com/cotes2020">
        <img src="https://github.com/cotes2020.png?size=120" width="64" height="64" alt="cotes2020" /><br />
        <sub><b>cotes2020</b></sub>
      </a>
      <br />
      <sub><a href="https://github.com/cotes2020/jekyll-theme-chirpy">jekyll-theme-chirpy</a> 作者</sub>
    </td>
    <td align="center" width="140">
      <a href="https://jekyllrb.com/">
        <img src="https://jekyllrb.com/img/logo-2x.png" width="64" height="64" alt="Jekyll" /><br />
        <sub><b>Jekyll</b></sub>
      </a>
      <br />
      <sub>静态站点生成器</sub>
    </td>
    <td align="center" width="140">
      <a href="https://www.jetbrains.com/idea/">
        <img src="https://resources.jetbrains.com/storage/products/intellij-idea/img/meta/intellij-idea_logo_300x300.png" width="64" height="64" alt="IntelliJ IDEA" /><br />
        <sub><b>IntelliJ IDEA</b></sub>
      </a>
      <br />
      <sub>JetBrains 出品</sub>
    </td>
    <td align="center" width="140">
      <a href="https://www.jetbrains.com/pycharm/">
        <img src="https://resources.jetbrains.com/storage/products/pycharm/img/meta/pycharm_logo_300x300.png" width="64" height="64" alt="PyCharm" /><br />
        <sub><b>PyCharm</b></sub>
      </a>
      <br />
      <sub>JetBrains 出品</sub>
    </td>
  </tr>
</table>

| 项目 / 服务 | 贡献 | 许可证 / 说明 |
|---|---|---|
| [jekyll](https://github.com/jekyll/jekyll) | 站点构建引擎 | MIT |
| [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) | 主题、布局与博客功能 | MIT |
| [GitHub Pages](https://pages.github.com/) | 站点托管 | 免费服务，遵循 GitHub 服务条款 |
| [GitHub Actions](https://github.com/features/actions) | 自动构建与发布 | 免费额度内使用，遵循 GitHub 服务条款 |
| [JetBrains](https://www.jetbrains.com/) | 提供 IntelliJ IDEA / PyCharm 等开发工具 | 商业授权（开源项目可申请免费许可证） |

> 自定义域名 `hyx.leipeng.us.kg` 由 [nic.us.kg](https://nic.us.kg/) 提供。
> 文章中若引用他人内容，均在各篇 `front matter` 或正文注明出处。
