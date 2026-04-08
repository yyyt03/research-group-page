# 仓库修改说明

## 目录作用

### 站点配置

- `_config.yml`
  站点总配置。控制站点标题、域名、collections、默认 layout、插件与构建行为。
- `.pages.yml`
  Pages CMS 配置文件。当前建议只管理结构化集合内容，不直接在 CMS 中编辑固定页面模板。

### 页面源码

- `pages/`
  固定页面统一放在这里，方便维护页面结构与样式。

当前包含：

- `pages/index.markdown`（首页）
- `pages/about.markdown`（关于我们）
- `pages/research.md`（研究方向）
- `pages/contact.md`（联系方式）
- `pages/members.md`（团队成员列表）
- `pages/news.md`（学术成果列表）
- `pages/projects.md`（项目列表）
- `pages/404.html`（404 页面）

这些页面都通过 `permalink` 暴露访问路径，所以目录整理不会改变线上 URL。

### 导航与布局

- `_data/navigation.yml`
  控制主导航顺序和入口。
- `_includes/header.html`
  控制顶部导航结构、桌面与移动端导航按钮。
- `_includes/head.html`
  控制页面元信息和样式资源引用。
- `_layouts/default.html`
  全站外壳布局。
- `_layouts/page.html`
  普通页面布局。
- `_layouts/member.html`
  成员详情页布局。
- `_layouts/news-item.html`
  学术成果详情页布局。
- `_layouts/project-item.html`
  项目详情页布局。

### 样式与资源

- `assets/main.scss`
  全站样式主文件，包含首页、列表页、详情页、移动端与夜间模式样式。
- `assets/uploads/members/`
  成员照片。
- `assets/uploads/news/`
  学术成果封面与正文插图。
- `assets/uploads/projects/`
  项目图片。
- `assets/uploads/site/`
  首页与固定页面共用图片资源。

### 结构化内容

- `_members/*.md`
  成员资料。适合长期通过 Pages CMS 维护。
- `_news/*.md`
  学术成果/新闻条目。适合长期通过 Pages CMS 维护。
- `_projects/*.md`
  项目条目。适合长期通过 Pages CMS 维护。

### 模板与文档

- `templates/`
  内容模板。
- `docs/notes/`
  项目流程、部署、CMS 使用与维护记录。
- `docs/references/`
  参考页面与样式素材。

## 当前推荐的 CMS 管理边界

适合放进 Pages CMS 的内容：

- `_members/`
- `_news/`
- `_projects/`

不建议直接放进 Pages CMS 富文本编辑的内容：

- `pages/index.markdown`
- `pages/about.markdown`
- `pages/research.md`
- `pages/contact.md`

原因：这些固定页面已经包含较多模板化结构、分区 HTML 和样式挂钩字段，直接用 CMS 富文本编辑容易破坏页面结构。

## 常见修改场景

### 想改导航顺序

改 `_data/navigation.yml`。

### 想改页头/导航样式

改 `_includes/header.html` 和 `assets/main.scss`。

### 想改首页内容与结构

改 `pages/index.markdown`。

### 想改固定页面文案

改 `pages/about.markdown`、`pages/research.md`、`pages/contact.md`。

### 想改列表页结构

改 `pages/members.md`、`pages/news.md`、`pages/projects.md`。

### 想改详情页样式

- 成员详情：改 `_layouts/member.html` 和 `assets/main.scss` 中 `member-detail` 相关样式。
- 学术成果详情：改 `_layouts/news-item.html` 和 `assets/main.scss` 中 `detail-shell` 相关样式。
- 项目详情：改 `_layouts/project-item.html` 和 `assets/main.scss` 中 `detail-shell` 相关样式。

### 想新增成员

1. 在 `_members/` 复制一个现有成员文件。
2. 修改 `name`、`role`、`photo`、`research`、`email`、`order` 等字段。
3. 把图片放进 `assets/uploads/members/`。

### 想新增学术成果

1. 在 `_news/` 新建一篇 Markdown 文件。
2. 填写 `title`、`date`、`cover`、`summary`。
3. 在正文中继续写内容，正文可以插入多张图片。
4. 配图放进 `assets/uploads/news/`。

### 想新增项目

1. 在 `_projects/` 新建 Markdown 文件。
2. 填写 `title`、`period`、`leader`、`summary`、`status`。
3. 在正文中补充项目详情。

## 本地检查与发布流程

```bash
bundle exec jekyll serve --livereload
bundle exec jekyll build
git checkout main
git merge --ff-only <功能分支>
git push origin main
```

如果本地正常、线上异常，优先检查：

1. 最新改动是否已经进入 `main`。
2. Cloudflare Pages 或 GitHub Pages 是否完成重新构建。
3. 浏览器是否需要强制刷新（`Ctrl + F5`）。
4. 关键资源路径是否正常：`/assets/main.css`、`/assets/uploads/*`、集合详情页链接。