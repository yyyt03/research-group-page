---
layout: default
title: 课程与实验
permalink: /courses/
---
{% assign courses = site.data.page_content.courses %}
{% assign course_items = site.courses | sort: "order" %}
<section class="page-shell page-shell--institutional page-shell--courses">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ courses.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ courses.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ courses.masthead.intro }}</p>
    </header>

    <div class="course-grid course-grid--institutional">
      {% for card in course_items %}
        <article class="member-card member-card--institutional course-card">
          {% if card.image %}
          <img class="member-card__image course-card__image" src="{{ card.image | relative_url }}" alt="{{ card.image_alt | default: card.title }}">
          {% endif %}
          <div class="member-card__body">
          <p class="card-meta">{{ card.meta }}</p>
          <h2 class="card-title">
            {% if card.href %}
            <a href="{{ card.href }}" target="_blank" rel="noopener noreferrer">{{ card.title }}</a>
            {% else %}
            {{ card.title }}
            {% endif %}
          </h2>
          {% if card.certification %}<p class="course-card__badge">{{ card.certification }}</p>{% endif %}
          <p class="course-card__facts"><span class="course-card__facts-label">{{ card.label }}：</span>{{ card.value }}</p>
          {% if card.institution %}<p class="course-card__facts"><span class="course-card__facts-label">建设单位：</span>{{ card.institution }}</p>{% endif %}
          {% if card.instructor %}<p class="course-card__facts"><span class="course-card__facts-label">负责人：</span>{{ card.instructor }}</p>{% endif %}
          <p class="course-card__summary">{{ card.text }}</p>
          {% if card.href %}
          <p class="course-card__action"><a href="{{ card.href }}" target="_blank" rel="noopener noreferrer">查看课程页面</a></p>
          {% endif %}
          </div>
        </article>
      {% endfor %}
    </div>
  </div>
</section>
