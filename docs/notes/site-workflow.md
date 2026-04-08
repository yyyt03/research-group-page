# 课题组网站流程状态（更新于 2026-04-08）

## 当前状态

项目当前已经进入“可持续维护”阶段：

- 站点已完成 Jekyll 基础搭建，并已部署到 Cloudflare Pages。
- GitHub 仓库继续作为源码主仓库，`main` 作为发布分支。
- 首页、关于页、研究页、成员页、学术成果页、项目页均已完成一轮研究中心风格统一。
- 桌面端与移动端样式已做多轮适配，夜间模式也已接入并持续修正对比度问题。
- `_members`、`_news`、`_projects` 已作为主要结构化内容源使用。
- 固定页面已开始改为“模板 + 数据”模式，准备由 Pages CMS 安全维护文案与图片。

## 当前目录规范

- 页面模板：`pages/`
- 固定页数据：`_data/page_content/`
- 结构化内容：`_members/`、`_news/`、`_projects/`
- 图片资源：`assets/uploads/`
- 过程文档：`docs/notes/`
- 参考素材：`docs/references/`

## 当前推荐维护方式

### 适合在 Pages CMS 中维护

- `_members/`
- `_news/`
- `_projects/`
- `_data/page_content/home.yml`
- `_data/page_content/about.yml`
- `_data/page_content/research.yml`
- `_data/page_content/contact.yml`

### 适合在本地直接维护

- `pages/index.markdown`
- `pages/about.markdown`
- `pages/research.md`
- `pages/contact.md`
- `assets/main.scss`
- `_layouts/*.html`
- `_includes/*.html`

原因：页面模板与布局文件已经和当前样式系统强绑定，CMS 只编辑数据层，不直接改模板结构。

## 日常维护流程

1. 新建功能分支。
2. 修改页面模板、样式或集合/数据内容。
3. 本地预览检查：

```bash
bundle exec jekyll serve --livereload
```

4. 构建验证：

```bash
bundle exec jekyll build
```

5. 提交并推送当前分支。
6. 确认 Cloudflare Pages 自动部署成功。
7. 合并到 `main` 后再次确认线上页面。

## 当前 Pages CMS 使用建议

1. 成员资料维护走 `_members/`。
2. 学术成果维护走 `_news/`，支持封面图和正文插图。
3. 项目维护走 `_projects/`。
4. 固定页面文案与图片维护走 `_data/page_content/`。
5. 固定页面模板本身不建议交给 CMS 直接编辑。

## 当前优先任务

1. 检查 Pages CMS 中固定页数据入口是否显示正常。
2. 继续检查全站夜间模式下的低对比度场景。
3. 逐步补充 SEO 基础信息与页面摘要。
4. 持续补齐真实成员资料、项目与学术成果内容。

## 发布排查清单

线上看起来异常时，按顺序检查：

1. 当前改动是否已经推送到远程正确分支。
2. Cloudflare Pages 最近一次部署是否为 `Success`。
3. 浏览器缓存是否已清理。
4. 关键资源路径是否正常：`/assets/main.css`、`/assets/uploads/*`。
5. `bundle exec jekyll build` 本地是否通过。

## 相关文档

- Cloudflare 域名维护：`docs/notes/cloudflare-domain-change.md`
- CMS 图片使用：`docs/notes/cms-academic-content-images.md`
- 固定页 CMS 方案：`docs/notes/cms-safe-fixed-pages-plan.md`
- 仓库结构说明：`docs/repository-guide.md`