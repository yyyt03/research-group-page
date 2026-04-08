# Pages CMS：固定页面与学术成果的推荐维护方式

更新时间：2026-04-08

## 当前适用范围

Pages CMS 目前建议维护以下内容：

- `_members/`：团队成员
- `_news/`：学术成果/新闻
- `_projects/`：项目
- `_data/page_content/home.yml`：首页文案与按钮
- `_data/page_content/about.yml`：关于页文案、图片、统计
- `_data/page_content/research.yml`：研究方向页和首页研究方向卡片
- `_data/page_content/contact.yml`：联系页卡片与说明

## 固定页面的当前原则

固定页面已经改为“模板 + 数据”模式：

- `pages/*.md` 负责页面结构、Liquid 和样式挂接
- `_data/page_content/*.yml` 负责可被 CMS 编辑的文案、图片、按钮、卡片内容

因此：

- 可以通过 CMS 修改固定页面内容
- 不需要通过 CMS 直接编辑模板文件
- 可以避免误删容器、类名或循环结构导致页面布局损坏

## 学术成果栏目当前能力

在 Pages CMS 中维护“学术成果”时，当前支持：

1. 封面图（front matter `cover`）
2. 正文插图（正文 `body` 内插图）
3. 摘要字段（`summary`）
4. 日期字段（`date`）

## 固定页面分别改什么

### 首页

编辑：`_data/page_content/home.yml`

可改内容：

- Hero 标题、副标题、关键词、按钮
- 机构简介文案与配图
- 联系区块文案与联系卡片

不会改到：

- 首页成员循环
- 首页成果循环
- 页面布局结构

### 关于页

编辑：`_data/page_content/about.yml`

可改内容：

- 页面标题与简介
- 正文段落
- 配图
- 统计数字

### 研究页

编辑：`_data/page_content/research.yml`

可改内容：

- 页面标题与说明
- 研究方向卡片标题、简介、图片

说明：

- 首页研究方向模块会复用这份数据，所以这里只改一处即可。

### 联系页

编辑：`_data/page_content/contact.yml`

可改内容：

- 页面标题与简介
- 办公地点、邮箱等联系卡片

## 学术成果操作流程

1. 【需要你操作】进入 Pages CMS 项目并确认当前仓库与分支正确。
2. 【需要你操作】打开“学术成果”集合。
3. 【需要你操作】新增或编辑条目，填写：
   - `title`
   - `date`
   - `summary`
   - `cover`
4. 【需要你操作】在正文编辑器中录入正文。
5. 【需要你操作】如需正文插图，直接通过编辑器图片按钮上传或选择已有图片。
6. 【需要你操作】保存后回到站点检查列表页和详情页是否显示正常。

## 图片目录建议

- 固定页面配图：`assets/uploads/site/`
- 学术成果配图：`assets/uploads/news/`
- 成员照片：`assets/uploads/members/`
- 项目图片：`assets/uploads/projects/`

## 发布后检查

1. 固定页面修改后，首页、关于页、研究页、联系页显示正常。
2. 学术成果列表页可以看到新增条目。
3. 学术成果详情页能正常显示封面图和正文图片。
4. 移动端查看时不出现横向滚动。
5. 夜间模式下图片与文字仍可正常阅读。

## 常见问题

### CMS 能改固定页面，但页面结构不该被改

当前方案已经通过数据层实现这个目标：

- 改的是 `_data/page_content/*.yml`
- 不是 `pages/*.md` 模板文件

### 首页研究方向和研究页内容不一致

现在两者应共用 `_data/page_content/research.yml` 中的研究方向卡片数据；如果不一致，优先检查首页模板是否已经读取该数据文件。

### 正文图片显示异常

按这个顺序检查：

1. 图片是否在 `assets/uploads/news/`。
2. 正文引用路径是否是 `/assets/uploads/news/文件名`。
3. 本地构建是否通过：`bundle exec jekyll build`。
4. 详情页样式是否被新改动覆盖。