---
layout: default
title: 成员
permalink: /members/
---
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">People</p>
      <h1 class="section-title section-title--left">团队成员</h1>
      <p class="section-intro section-intro--wide">成员页面集中展示课题组核心教师与相关成员，当前已补入李英华、韦璇、李康康、牛文渊等教师入口，后续可继续完善学生与合作成员资料。</p>
    </header>

    {% assign members = site.members | sort: "order" %}
    {% if members.size > 0 %}
    <div class="team-grid team-grid--institutional">
    {% for member in members %}
      <article class="member-card member-card--institutional">
        {% if member.photo %}
        <img class="member-card__image" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
        {% else %}
        <div class="member-card__image member-card__image--placeholder">◯</div>
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
    <p>当前还没有成员信息。</p>
    {% endif %}
  </div>
</section>
