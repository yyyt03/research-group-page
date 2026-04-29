---
layout: default
title: 项目与学术成果
permalink: /projects/
---
{% assign outputs = site.data.page_content.outputs %}
{% assign projects = site.projects | sort: "order" %}
{% assign books = site.books | sort: "order" %}
{% assign output_highlights = site.output_highlights | sort: "order" %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ outputs.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ outputs.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ outputs.masthead.intro }}</p>
    </header>

    <section class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">{{ outputs.sections.projects.kicker }}</p>
          <h2 class="section-title section-title--left">{{ outputs.sections.projects.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ outputs.sections.projects.intro }}</p>
      </div>

      <div class="project-grid project-grid--institutional">
        {% for project in projects %}
        <article class="project-card project-card--institutional">
          <p class="card-meta">{{ project.period }}</p>
          <h3 class="card-title"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
          <p><strong>{{ outputs.sections.projects.leader_label }}</strong> {{ project.leader }}</p>
          <p>{{ project.summary }}</p>
        </article>
        {% endfor %}
      </div>
    </section>

    <section id="books" class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">{{ outputs.sections.books.kicker }}</p>
          <h2 class="section-title section-title--left">{{ outputs.sections.books.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ outputs.sections.books.intro }}</p>
      </div>

      <div class="publication-grid publication-grid--institutional publication-grid--light">
        {% for book in books %}
        <article class="publication-card publication-card--institutional publication-card--light">
          <p class="card-meta">{{ book.year }}</p>
          <h3 class="card-title">{{ book.title }}</h3>
          <p><strong>{{ outputs.sections.books.authors_label }}</strong> {{ book.authors }}</p>
          <p><strong>{{ outputs.sections.books.publisher_label }}</strong> {{ book.publisher }}</p>
          <p>{{ book.note }}</p>
        </article>
        {% endfor %}
      </div>
    </section>

    <section class="detail-section detail-section--compact">
      <div class="detail-section__header">
        <div>
          <p class="section-kicker">{{ outputs.sections.publications.kicker }}</p>
          <h2 class="section-title section-title--left">{{ outputs.sections.publications.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ outputs.sections.publications.intro }}</p>
      </div>

      <div class="publication-grid publication-grid--institutional publication-grid--light">
        {% for item in output_highlights %}
        <article class="publication-card publication-card--institutional publication-card--light">
          <h3 class="card-title">{{ item.title }}</h3>
          <p>{{ item.text }}</p>
        </article>
        {% endfor %}
      </div>
      <p class="section-link"><a href="{{ outputs.sections.publications.link_url | relative_url }}">{{ outputs.sections.publications.link_text }}</a></p>
    </section>
  </div>
</section>
