---
layout: default
title: 新闻
permalink: /news/
---
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">Publications & Updates</p>
      <h1 class="section-title section-title--left">学术成果</h1>
      <p class="section-intro section-intro--wide">当前页面以成果条目与研究更新为主，保持统一摘要卡片结构，后续如有需要可再独立拆分 publications 数据结构。</p>
    </header>

    {% assign news_list = site.news | sort: "date" | reverse %}
    {% if news_list.size > 0 %}
    <div class="publication-grid publication-grid--institutional">
    {% for item in news_list %}
      <article class="publication-card publication-card--institutional">
        <p class="publication-card__journal">{{ item.date | date: "%Y-%m-%d" }}</p>
        <h2 class="card-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h2>
        <p>{{ item.summary }}</p>
        <a class="publication-card__link" href="{{ item.url | relative_url }}">查看详情</a>
      </article>
    {% endfor %}
    </div>
    {% else %}
    <p>当前还没有学术成果内容。</p>
    {% endif %}
  </div>
</section>
