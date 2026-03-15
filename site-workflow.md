# 课题组网站下一步流程

## 1. 当前状态

根据当前仓库内容，你现在已经完成了 **Jekyll 起始例程**，并且可以本地生成站点。当前项目还处在非常早期的模板阶段：

- 主页还是默认的 `layout: home`
- `about.markdown` 还是 Jekyll 自带说明
- `_config.yml` 已经更新为适合 GitHub Pages 的基础站点配置
- 本地已经初始化 Git，但当前还没有连接到 GitHub 上的目标仓库

这说明你下一步最重要的事情不是继续找插件，而是先把网站的 **结构、内容类型、发布方式** 定下来。

---

## 2. 总体建议

对于课题组网站，推荐按这个顺序推进：

1. 先确定 GitHub Pages 的发布方式
2. 再设计网站栏目和内容结构
3. 然后把 Jekyll 默认模板替换成你自己的页面
4. 最后接 GitHub 仓库和自动部署

也就是说，当前阶段的关键词不是“美化”，而是“搭骨架”。

---

## 3. 第一步：确定 GitHub Pages 方案

你需要先决定网站挂载在哪种仓库上：

### 方案 A：用户 / 组织主页仓库

仓库名形如：

- `<username>.github.io`
- `<orgname>.github.io`

特点：

- 网址最干净
- `baseurl` 通常可以留空 `""`
- 很适合正式的课题组主页

### 方案 B：普通项目仓库

仓库名形如：

- `lab-website`
- `group-homepage`

访问地址通常是：

- `https://username.github.io/lab-website/`

特点：

- 创建更自由
- 但 `_config.yml` 里的 `baseurl` 需要写成仓库名，例如 `/lab-website`

### 推荐

如果这是课题组正式网站，优先考虑：

- 有 GitHub 组织就用 `<orgname>.github.io`
- 个人先代管就用 `<username>.github.io`

### 你现在要做什么

如果你准备先完成这一步，可以直接按下面做：

1. 登录 GitHub，点击右上角 `New repository`
2. `Owner` 选择你准备托管网站的账号
3. 仓库名填写成 `<你的用户名>.github.io`
4. 如果你的 GitHub 用户名里有大写字母，仓库名要改成全小写
5. 仓库可见性先选 `Public`
6. 勾选 `Add README`
7. 点击 `Create repository`

### 建仓时要特别注意

- 用户主页仓库名必须严格匹配 `<username>.github.io`
- 一个账号通常只对应一个用户主页站点
- 如果你以后是课题组正式组织站，再迁移到 `<orgname>.github.io` 也可以
- 你现在这个 Jekyll 项目之后应该推送到这个新仓库里

### 仓库建好以后，你本地要同步调整

因为你准备使用 `<username>.github.io` 这种用户主页仓库，所以后面你的 `_config.yml` 应该按这个方向配置：

- `url: https://<username>.github.io`
- `baseurl: ""`

也就是说，用户主页仓库和普通项目仓库最大的区别是：

- 用户主页仓库通常不需要写仓库名到 `baseurl`
- 访问地址会直接是 `https://<username>.github.io/`

### 这一步完成的判定标准

你可以用下面 3 条判断自己是不是已经完成第一步：

- GitHub 上已经存在 `<username>.github.io` 仓库
- 你可以正常打开这个仓库的主页
- 你已经确认后续要把当前 Jekyll 项目推送到这个仓库

---

## 4. 第二步：先定网站栏目

这一步现在已经定稿，栏目结构按下面执行。

### 固定页面

- 首页 `index`
- 课题组简介 `about`
- 研究方向 `research`
- 联系方式 `contact`

### 列表页

- 成员页 `members`
- 新闻页 `news`
- 项目页 `projects`

### 后续对应的数据目录

- 成员 `_members`
- 新闻 `_news`
- 项目 `_projects`

### 图片目录

- `assets/uploads/`

### 导航顺序

- 首页
- 课题组简介
- 研究方向
- 成员
- 新闻
- 项目
- 联系方式

### 已经落到项目里的文件

- 栏目定稿文档：`site-structure.md`
- 导航数据文件：`_data/navigation.yml`

这样做的好处是：

- 后续维护规则统一
- 新成员、新新闻都可以按模板添加
- 页面导航已经有了明确顺序
- 将来就算加 CMS，也能直接沿用这套结构

---

## 5. 第三步：定义每类内容的字段模板

这一步现在已经完成，三类内容的字段结构和模板都已经落到项目中。

### 成员条目建议字段

- `name`
- `role`
- `photo`
- `research`
- `email`
- `order`

### 新闻条目建议字段

- `title`
- `date`
- `cover`
- `summary`

### 项目条目建议字段

- `title`
- `period`
- `leader`
- `summary`
- `status`

### 已经落到项目里的文件

- 字段说明文档：`content-schema.md`
- 成员模板：`templates/member-template.md`
- 新闻模板：`templates/news-template.md`
- 项目模板：`templates/project-template.md`

你真正要做的是：让大家以后只是“填表”，而不是“写代码”。

---

## 6. 第四步：修改 `_config.yml`

这一步现在已经完成，站点基础配置已经改成适合 GitHub Pages 课题组网站继续开发的版本。

### 已经修改的内容

- `title`
- `email`
- `description`
- `url`
- `baseurl`
- `lang`
- `timezone`
- `github_username`
- `collections`
- `defaults`
- `exclude`

### 已经落到项目里的文件

- 配置文件：`_config.yml`

### 你还需要自己替换的占位值

- `title`
- `email`
- `description`
- `url` 里的 `your-username`
- `github_username`

这一步完成后，站点已经从“Jekyll 默认示例配置”进入“课题组网站基础配置”阶段。

---
## 7. 第五步：清理默认页面

建议把起始模板里的默认内容尽快替换掉。

当前最需要改的文件：

- `index.markdown`
- `about.markdown`

建议做法：

- 首页改成课题组简介 + 最新新闻 + 成员入口
- `about.markdown` 改成导师 / 团队介绍
- 新增 `research.md`
- 新增 `contact.md`

这一步的目标不是完整，而是让网站打开后不再出现 Jekyll 默认文案。

---

## 8. 第六步：建立 collections 和示例数据

这是课题组网站最核心的一步。

建议建立这些目录：

- `_members/`
- `_news/`
- `_projects/`
- `assets/uploads/`

然后每个目录先放 1 到 2 条示例数据。

例如：

- `_members/pi.md`
- `_members/student-a.md`
- `_news/2026-03-14-site-setup.md`
- `_projects/project-1.md`

有了示例数据后，你再写页面模板会容易很多，因为你已经知道数据长什么样。

---

## 9. 第七步：做第一版页面展示

这时候再做展示层最合适。

优先顺序建议如下：

1. 首页显示课题组简介
2. 首页显示最近 3 条新闻
3. 单独做一个成员页，按 `order` 排序
4. 单独做一个研究 / 项目页
5. 最后再考虑样式优化

也就是说，先保证“能看、能更新、能上线”，再追求“更漂亮”。

---

## 10. 第八步：本地预览与检查

每做完一批改动，建议本地检查一次：

```bash
bundle exec jekyll serve
```

重点检查：

- 页面链接是否正确
- 图片路径是否正确
- 中文是否正常显示
- `baseurl` 设置后是否还能正常访问
- 成员、新闻、项目页面是否能正确列出内容

---

## 11. 第九步：连接远程仓库并推送

因为你现在已经有本地 Git 仓库，也已经在 GitHub 上创建了 `<username>.github.io` 仓库，所以这一步的重点变成：连接远程并推送代码。

### 如果远程仓库还是空的

```bash
git remote add origin <你的仓库地址>
git branch -M main
git push -u origin main
```

### 如果远程仓库已经有 README 初始提交

这是你当前更可能遇到的情况。常见做法有两种：

1. 保留远程 README，把两边历史合并
2. 如果远程只有占位 README，也可以在确认无重要内容后直接覆盖远程

较稳妥的合并流程如下：

```bash
git remote add origin <你的仓库地址>
git branch -M main
git pull origin main --allow-unrelated-histories
git push -u origin main
```

如果后面 `git pull` 时出现冲突，通常就是 README 或 `.gitignore` 的初始差异，处理完再继续 push 即可。

---

## 12. 第十步：开启 GitHub Pages

推送完成后，在 GitHub 仓库里设置 Pages。

常见方式有两种：

- 从 `main` 分支部署
- 使用 GitHub Actions 自动构建 Jekyll

如果你用的是 GitHub 官方支持的 Jekyll Pages 流程，通常配置不会太复杂。

部署完成后，记得检查：

- 首页能否打开
- 内页能否打开
- 图片是否丢失
- CSS 是否正常加载

---

## 13. 后续维护建议

为了让课题组成员也能维护，建议提前约定这几条规则：

- 正文内容优先用 Markdown
- 图片统一放到 `assets/uploads/`
- 不直接改复杂模板文件
- 新增成员 / 新闻时，只复制模板文件修改内容
- 优先使用 GitHub 网页端或 `github.dev` 做简单更新

这样可以把维护门槛压得很低。

---

## 14. 你现在最应该做的三件事

如果你想按最小成本继续推进，下一步优先做这 3 件事：

1. 替换默认的 `index.markdown` 和 `about.markdown` 内容
2. 创建 `_members`、`_news`、`_projects` 和 `assets/uploads`
3. 先写 1 到 2 条成员、新闻、项目示例内容

只要这三步完成，网站就会从“基础配置完成”进入“内容骨架成型”阶段。

---
## 15. 一个适合你的推进顺序

可以直接按下面这条路线做：

1. 选定 GitHub Pages 仓库方案
2. 修改 `_config.yml`
3. 删除或替换默认页面内容
4. 建立 collections
5. 补 2 到 4 条示例内容
6. 做首页和成员页
7. 本地预览
8. 推送 GitHub
9. 开启 Pages
10. 再做样式美化

这会比一开始就纠结 CMS、主题、动画效果更稳，也更适合课题组网站这种长期维护型项目。






