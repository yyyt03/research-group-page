---
layout: default
title: 项目
permalink: /projects/
---
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">Projects</p>
      <h1 class="section-title section-title--left">项目列表</h1>
      <p class="section-intro section-intro--wide">项目页面集中展示课题组研究计划、周期和负责人信息，与成员页和成果页使用同一套页面框架。</p>
    </header>

    {% assign projects = site.projects %}
    {% if projects.size > 0 %}
    <div class="project-grid project-grid--institutional">
    {% for project in projects %}
      <article class="project-card project-card--institutional">
        <p class="card-meta">{{ project.period }}</p>
        <h2 class="card-title"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
        <p><strong>负责人</strong> {{ project.leader }}</p>
        <p>{{ project.summary }}</p>
      </article>
    {% endfor %}
    </div>
    {% else %}
    <p>当前还没有项目内容。</p>
    {% endif %}
  </div>
</section>
