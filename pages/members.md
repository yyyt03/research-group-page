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
      <p class="section-intro section-intro--wide">成员页面集中展示课题组核心教师与学生成员，当前保留李英华教师主页，并以 mock 学生资料补齐其余展示位，后续可继续替换为真实学生与合作成员信息。</p>
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
