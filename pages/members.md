---
layout: default
title: 成员
permalink: /members/
---
{% assign members_page = site.data.page_content.members %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ members_page.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ members_page.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ members_page.masthead.intro }}</p>
    </header>

    {% assign members = site.members | sort: "order" %}
    {% if members.size > 0 %}
    <div class="team-grid team-grid--institutional">
    {% for member in members %}
      <article class="member-card member-card--institutional">
        {% if member.photo %}
        <img class="member-card__image" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
        {% else %}
        <div class="member-card__image member-card__image--placeholder">{{ members_page.list.placeholder_mark }}</div>
        {% endif %}
        <div class="member-card__body">
          <p class="card-meta">{{ member.role }}</p>
          <h2 class="card-title"><a href="{{ member.url | relative_url }}">{{ member.name }}</a></h2>
          <p>{{ member.research }}</p>
          <p><a href="mailto:{{ member.email }}">{{ member.email }}</a></p>
        </div>
      </article>
    {% endfor %}
    </div>
    {% else %}
    <p>{{ members_page.list.empty_text }}</p>
    {% endif %}
  </div>
</section>
