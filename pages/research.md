---
layout: default
title: 研究方向
permalink: /research/
---
{% assign research = site.data.page_content.research %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ research.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ research.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ research.masthead.intro }}</p>
    </header>

    <div class="research-grid research-grid--institutional">
      {% for area in research.areas %}
      <article class="research-card research-card--institutional">
        <img class="research-card__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">
        <div class="research-card__body">
          <p class="card-meta">{{ area.code }}</p>
          <h2 class="card-title">{{ area.title }}</h2>
          <p>{{ area.description }}</p>
        </div>
      </article>
      {% endfor %}
    </div>
  </div>
</section>