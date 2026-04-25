---
layout: default
title: 项目与学术成果
permalink: /projects/
---
{% assign outputs = site.data.page_content.outputs %}
{% assign projects = site.projects | sort: "order" %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ outputs.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ outputs.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ outputs.masthead.intro }}</p>
    </header>

    <section class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Projects</p>
          <h2 class="section-title section-title--left">项目</h2>
        </div>
        <p class="section-intro section-intro--narrow">当前已录入国家社科基金、教育部基金及校内项目条目，每个项目可继续下钻查看摘要。</p>
      </div>

      <div class="project-grid project-grid--institutional">
        {% for project in projects %}
        <article class="project-card project-card--institutional">
          <p class="card-meta">{{ project.period }}</p>
          <h3 class="card-title"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
          <p><strong>负责人</strong> {{ project.leader }}</p>
          <p>{{ project.summary }}</p>
        </article>
        {% endfor %}
      </div>
    </section>

    <section id="books" class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Books</p>
          <h2 class="section-title section-title--left">书籍成果</h2>
        </div>
        <p class="section-intro section-intro--narrow">书籍成果统一收纳到本页，后续可继续增加专著、编著与译著条目。</p>
      </div>

      <div class="publication-grid publication-grid--institutional publication-grid--light">
        {% for book in outputs.books %}
        <article class="publication-card publication-card--institutional publication-card--light">
          <p class="card-meta">{{ book.year }}</p>
          <h3 class="card-title">{{ book.title }}</h3>
          <p><strong>作者</strong> {{ book.authors }}</p>
          <p><strong>出版社</strong> {{ book.publisher }}</p>
          <p>{{ book.note }}</p>
        </article>
        {% endfor %}
      </div>
    </section>

    <section class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">Publications</p>
          <h2 class="section-title section-title--left">论文与学位论文入口</h2>
        </div>
        <p class="section-intro section-intro--narrow">“Publication 数据结构”已按研究方向拆成统一入口，避免在成果页重复堆叠长列表。</p>
      </div>

      <div class="publication-grid publication-grid--institutional publication-grid--light">
        {% for item in outputs.highlights %}
        <article class="publication-card publication-card--institutional publication-card--light">
          <h3 class="card-title">{{ item.title }}</h3>
          <p>{{ item.text }}</p>
        </article>
        {% endfor %}
      </div>
      <p class="section-link"><a href="{{ '/research/' | relative_url }}">前往研究领域页查看完整论文与学位论文清单</a></p>
    </section>
  </div>
</section>
