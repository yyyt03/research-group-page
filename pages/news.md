---
layout: default
title: 新闻
permalink: /news/
---
{% assign news_page = site.data.page_content.news %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ news_page.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ news_page.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ news_page.masthead.intro }}</p>
    </header>

    {% assign news_list = site.news | sort: "date" | reverse %}
    {% if news_list.size > 0 %}
    <div class="publication-grid publication-grid--institutional">
    {% for item in news_list %}
      <article class="publication-card publication-card--institutional">
        <p class="publication-card__journal">{{ item.date | date: "%Y-%m-%d" }}</p>
        <h2 class="card-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h2>
        <p>{{ item.summary }}</p>
        <a class="publication-card__link" href="{{ item.url | relative_url }}">{{ news_page.list.detail_link_text }}</a>
      </article>
    {% endfor %}
    </div>
    {% else %}
    <p>{{ news_page.list.empty_text }}</p>
    {% endif %}
  </div>
</section>
