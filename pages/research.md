---
layout: default
title: 研究领域
permalink: /research/
---
{% assign research = site.data.page_content.research %}
{% assign research_areas = site.research_areas | sort: "order" %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ research.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ research.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ research.masthead.intro }}</p>
    </header>

    <div class="research-grid research-grid--institutional">
      {% for area in research_areas %}
      <article class="research-card research-card--institutional research-card--linked">
        <a class="research-card__link" href="{{ '/research/' | append: '#' | append: area.slug | relative_url }}">
          <img class="research-card__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">
          <div class="research-card__body">
            <p class="card-meta">{{ area.code }}</p>
            <h2 class="card-title">{{ area.title }}</h2>
            <p>{{ area.description }}</p>
          </div>
        </a>
      </article>
      {% endfor %}
    </div>

    {% for area in research_areas %}
    <section id="{{ area.slug }}" class="detail-section">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">{{ area.code }}</p>
          <h2 class="section-title section-title--left">{{ area.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ area.detail_intro }}</p>
      </div>
      <img class="detail-section__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">

      {% for panel in area.panels %}
      <div class="detail-section__panel">
        <h3>{{ panel.title }}</h3>
        <ol class="detail-list">
          {% for entry in panel.entries %}
          <li>{{ entry }}</li>
          {% endfor %}
        </ol>
      </div>
      {% endfor %}
    </section>
    {% endfor %}
  </div>
</section>
