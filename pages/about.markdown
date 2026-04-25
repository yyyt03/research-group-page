---
layout: default
title: 关于我们
permalink: /about/
---
{% assign about = site.data.page_content.about %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ about.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ about.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ about.masthead.intro }}</p>
    </header>

    <div class="about-grid about-grid--institutional">
      <div>
        {% for paragraph in about.content.paragraphs %}
        <p class="about-copy">{{ paragraph }}</p>
        {% endfor %}
        <div class="stats-grid stats-grid--institutional">
          {% for stat in about.stats %}
          <div class="stat-card{% if stat.accent %} stat-card--accent{% endif %}">
            <div class="stat-card__value">{{ stat.value }}</div>
            <p>{{ stat.label }}</p>
          </div>
          {% endfor %}
        </div>
      </div>

      <div class="media-stack media-stack--institutional">
        <img class="media-stack__image" src="{{ about.content.image | relative_url }}" alt="{{ about.content.image_alt }}">
      </div>
    </div>
  </div>
</section>
