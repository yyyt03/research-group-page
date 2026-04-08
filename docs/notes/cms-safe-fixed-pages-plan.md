# Pages CMS 固定页面安全编辑方案（方案 B）

更新时间：2026-04-08
分支：`feat/cms-safe-fixed-pages`

## 目标

让以下固定页面也能通过 Pages CMS 修改内容，同时尽量避免把页面结构和样式改坏：

- 首页 `pages/index.markdown`
- 关于页 `pages/about.markdown`
- 研究页 `pages/research.md`
- 联系页 `pages/contact.md`

核心原则：

1. 页面结构继续由代码控制。
2. CMS 只编辑结构化内容字段，不直接编辑整页 HTML/Markdown 结构。
3. 图片、标题、摘要、卡片文案都可以通过 CMS 修改。
4. 复杂布局、Liquid 循环、样式类名仍保留在模板里。

## 为什么不能直接把固定页作为富文本页开放

当前固定页面里已经包含：

- 多个 section 区块
- 固定 class 名
- 图片位与卡片位
- 与样式系统绑定的结构层级
- 部分页面还会读取 collection 数据

如果在 Pages CMS 中直接暴露 `body: rich-text`，编辑者很容易：

- 删除关键容器
- 改坏 class 结构
- 插入不受控样式内容
- 让首页和列表页布局失衡

所以“让 CMS 能改页面”这件事，正确做法不是开放整个页面，而是拆成“模板 + 数据”。

## 推荐实现方式

### 总体架构

新增一个专门存放固定页面可编辑内容的数据目录，例如：

- `_data/page_content/home.yml`
- `_data/page_content/about.yml`
- `_data/page_content/research.yml`
- `_data/page_content/contact.yml`

页面文件本身改为：

- 只保留 layout、permalink、少量页面标识
- 页面内容全部从 `site.data.page_content.*` 读取

这样形成两层：

1. 模板层：`pages/*.md` 中的 HTML 结构、Liquid 逻辑、布局顺序
2. 内容层：`_data/page_content/*.yml` 中的标题、段落、按钮、图片、卡片文案、联系信息

这是当前项目最稳妥的 CMS 方案。

## 各页面推荐拆分方式

### 1. 首页

首页最复杂，建议拆成以下字段块：

- `hero`
  - `kicker`
  - `title`
  - `lead`
  - `keywords`（数组）
  - `primary_button_text`
  - `primary_button_link`
  - `secondary_button_text`
  - `secondary_button_link`
- `intro`
  - `kicker`
  - `title`
  - `paragraphs`（数组）
  - `image`
  - `image_alt`
- `research_section`
  - `kicker`
  - `title`
  - `intro`
- `contact_section`
  - `kicker`
  - `title`
  - `intro`
  - `office_title`
  - `office_text`
  - `email_title`
  - `email_text`

首页中的以下内容不建议放 CMS：

- 成员列表循环
- 最新成果循环
- section 的 HTML 骨架
- 卡片 class 与图片裁切逻辑

首页研究方向卡片有两种方案：

方案 B1：仍写死在首页模板里，只允许研究页维护。
方案 B2：改为从 `research.yml` 同步读取前三条研究方向。

当前更推荐方案 B2，这样首页与研究页不会出现内容不一致。

### 2. 关于页

建议拆成：

- `masthead`
  - `kicker`
  - `title`
  - `intro`
- `content`
  - `paragraphs`（数组）
  - `image`
  - `image_alt`
- `stats`
  - 数组，每项包含：
    - `value`
    - `label`
    - `accent`（true/false）

关于页很适合先接入 CMS，因为结构较稳定、字段也容易理解。

### 3. 研究页

建议拆成：

- `masthead`
  - `kicker`
  - `title`
  - `intro`
- `areas`
  - 数组，每项包含：
    - `code`
    - `title`
    - `description`
    - `image`
    - `image_alt`

研究页接入后，首页研究方向模块可以直接复用同一份数据。

### 4. 联系页

建议拆成：

- `masthead`
  - `kicker`
  - `title`
  - `intro`
- `cards`
  - 数组，每项包含：
    - `title`
    - `text`

联系页也适合优先接入，因为字段少、风险低。

## Pages CMS 中的配置方式

固定页面不再直接指向 `pages/about.markdown` 这类模板文件，而是指向 `_data/page_content/*.yml`。

例如：

- `home_content` -> `_data/page_content/home.yml`
- `about_content` -> `_data/page_content/about.yml`
- `research_content` -> `_data/page_content/research.yml`
- `contact_content` -> `_data/page_content/contact.yml`

这样在 Pages CMS 中看到的是“首页内容”“关于页内容”“研究页内容”“联系页内容”，而不是直接编辑模板源码。

## 推荐字段类型

建议优先使用：

- `string`
- `text`
- `image`
- `number`
- `boolean`
- `object`
- `list`

尽量少用在固定页面里的：

- `rich-text`

原因：

- 固定页更适合短文案、多字段、强结构
- `rich-text` 更适合成果正文、成员详细简介这类长文本场景

## 分阶段实施顺序

### 第一阶段

先接入这两个最安全的页面：

1. 关于页
2. 联系页

原因：

- 字段少
- 结构简单
- 改造成本低
- 最容易验证 CMS 使用体验

### 第二阶段

接入研究页：

1. 研究方向卡片数据转到 `research.yml`
2. 首页研究方向模块复用同一份数据

这样可以解决首页与研究页双份文案同步的问题。

### 第三阶段

最后处理首页：

1. Hero 区块结构化
2. 机构简介区块结构化
3. 联系区块结构化
4. 成员与成果列表继续保留动态读取

首页之所以最后做，是因为它最复杂，字段设计不好会直接影响 CMS 使用体验。

## 建议新增的目录结构

```text
_data/
  page_content/
    home.yml
    about.yml
    research.yml
    contact.yml
```

## 预期收益

完成方案 B 后：

- 你可以在 Pages CMS 里安全地修改固定页面文案
- 页面结构不会因为误编辑而被破坏
- 首页与研究页能共用研究方向数据
- 后续如果要让其他老师或同学维护页面内容，成本会明显降低

## 当前结论

方案 B 是可行的，而且适合这个项目当前阶段。

最合理的下一步不是直接开放固定页 Markdown，而是：

1. 先建立 `_data/page_content/` 数据层
2. 先改造 `about` 和 `contact`
3. 再改造 `research`
4. 最后改造 `home`

这会比“直接把固定页塞进 CMS”更稳，也更适合长期维护。