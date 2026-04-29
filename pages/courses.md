---
layout: default
title: 课程与实验
permalink: /courses/
---
{% assign courses = site.data.page_content.courses %}
{% assign course_items = site.courses | sort: "order" %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ courses.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ courses.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ courses.masthead.intro }}</p>
    </header>

    <div class="project-grid project-grid--institutional">
      {% for card in course_items %}
        <article class="project-card project-card--institutional">
          <p class="card-meta">{{ card.meta }}</p>
          <h2 class="card-title">{{ card.title }}</h2>
          <p><strong>{{ card.label }}</strong> {{ card.value }}</p>
          <p>{{ card.text }}</p>
        </article>
      {% endfor %}
    </div>
  </div>
</section>
