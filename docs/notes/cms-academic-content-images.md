# Pages CMS：学术成果栏目封面图与正文插图使用说明

更新时间：2026-04-08

## 当前适用范围

Pages CMS 目前建议维护以下三类集合内容：

- `_members/`：团队成员
- `_news/`：学术成果/新闻
- `_projects/`：项目

当前不建议在 Pages CMS 中直接编辑以下固定页面：

- `pages/index.markdown`
- `pages/about.markdown`
- `pages/research.md`
- `pages/contact.md`

原因：这些页面已经带有较强的模板结构和样式挂钩，富文本编辑容易破坏版式。

## 学术成果栏目当前能力

在 Pages CMS 中维护“学术成果”时，当前目标是同时支持：

1. 封面图（front matter `cover`）
2. 正文插图（正文 `body` 内插图）
3. 常规摘要字段（`summary`）
4. 日期字段（`date`）

## 当前仓库配置要求

`.pages.yml` 中，`news` 集合应至少包含以下字段：

- `title`
- `date`
- `cover`
- `summary`
- `body`

其中：

- `cover` 用作列表页和详情页头图
- `body` 使用富文本编辑器，可插入多张正文图片
- 图片统一建议上传到 `assets/uploads/news/`

## 你在 Pages CMS 中的操作流程

1. 【需要你操作】进入 Pages CMS 项目并确认当前仓库与分支正确。
2. 【需要你操作】打开“学术成果”集合。
3. 【需要你操作】新增或编辑条目，填写：
   - `title`
   - `date`
   - `summary`
   - `cover`
4. 【需要你操作】在正文编辑器中继续录入正文。
5. 【需要你操作】如需正文插图，直接通过编辑器图片按钮上传或选择已有图片。
6. 【需要你操作】保存后回到站点检查列表页和详情页是否显示正常。

## 正文插图建议

### 图片目录

建议统一放在：

- `assets/uploads/news/`

### Markdown 写法示例

```markdown
![图 1：发掘现场](/assets/uploads/news/example-fieldwork-1.jpg)

图 1：考古发掘现场记录。

![图 2：器物细节](/assets/uploads/news/example-artifact-2.jpg)

图 2：器物局部细节。
```

### 使用建议

1. 文件名使用英文、小写、短横线。
2. 图片上传前先压缩，避免首屏和详情页加载过慢。
3. 每张图都写 alt 文本，便于检索和无障碍访问。

## 当前维护边界说明

如果你要维护的是：

- 团队成员资料：进入 `members`
- 学术成果/论文/动态：进入 `news`
- 项目资料：进入 `projects`

如果你要改的是首页分区、关于页结构、研究页模块、联系方式版式，建议仍在本地代码里修改，而不是直接在 CMS 中改。

## 发布后检查

1. 学术成果列表页可以看到新增条目。
2. 详情页能正常显示封面图。
3. 正文中的插图不溢出、不失真。
4. 移动端查看时不出现横向滚动。
5. 夜间模式下图片与文字仍可正常阅读。

## 常见问题

### 学术成果里看不到新增条目

按这个顺序检查：

1. `_news/` 下是否真的新增了 Markdown 文件。
2. 文件 front matter 是否包含 `title` 和 `date`。
3. 当前 `.pages.yml` 是否把 `news` 指向 `_news`。
4. Pages CMS 是否刷新到了最新仓库状态。

### 正文图片显示异常

按这个顺序检查：

1. 图片是否在 `assets/uploads/news/`。
2. 正文引用路径是否是 `/assets/uploads/news/文件名`。
3. 本地构建是否通过：`bundle exec jekyll build`。
4. 详情页样式是否被新改动覆盖。