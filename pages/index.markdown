---
layout: default
title: 首页
permalink: /
---
{% assign home = site.data.page_content.home %}
{% assign research = site.data.page_content.research %}
<div class="landing-shell landing-shell--center">
  <section class="landing-hero landing-hero--institutional">
    <div class="wrapper landing-hero__content landing-hero__content--institutional">
      <p class="section-kicker section-kicker--hero">{{ home.hero.kicker }}</p>
      <h1 class="landing-title">{{ home.hero.title }}</h1>
      <p class="landing-lead">{{ home.hero.lead }}</p>
      {% if home.hero.keywords %}
      <div class="hero-keywords">
        {% for keyword in home.hero.keywords %}
        <span class="detail-chip">{{ keyword }}</span>
        {% endfor %}
      </div>
      {% endif %}
      <div class="hero-actions hero-actions--institutional">
        <a class="button-primary" href="{{ home.hero.primary_button_link | relative_url }}">{{ home.hero.primary_button_text }}</a>
        <a class="button-secondary" href="{{ home.hero.secondary_button_link | relative_url }}">{{ home.hero.secondary_button_text }}</a>
      </div>
    </div>
  </section>

  <section class="section-block section-block--light section-block--institutional">
    <div class="wrapper">
      <div class="about-grid about-grid--institutional">
        <div>
          <p class="section-kicker">{{ home.intro.kicker }}</p>
          <h2 class="section-title section-title--left">{{ home.intro.title }}</h2>
          <div class="about-accent-line"></div>
          {% for paragraph in home.intro.paragraphs %}
          <p class="about-copy">{{ paragraph }}</p>
          {% endfor %}
        </div>

        <div class="media-stack media-stack--institutional">
          <img class="media-stack__image" src="{{ home.intro.image | relative_url }}" alt="{{ home.intro.image_alt }}">
        </div>
      </div>
    </div>
  </section>

  <section class="section-block section-block--soft section-block--institutional research-showcase">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">{{ research.section.kicker }}</p>
          <h2 class="section-title section-title--left">{{ research.section.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ research.section.intro }}</p>
      </div>

      <div class="research-grid research-grid--institutional">
        {% for area in research.areas %}
        <article class="research-card research-card--institutional research-card--linked">
          <a class="research-card__link" href="{{ area.link | relative_url }}">
            <img class="research-card__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">
            <div class="research-card__body">
              <p class="card-meta">{{ area.code }}</p>
              <h3 class="card-title">{{ area.title }}</h3>
              <p>{{ area.description }}</p>
            </div>
          </a>
        </article>
        {% endfor %}
      </div>
      <p class="section-link"><a href="{{ '/research/' | relative_url }}">查看三个研究方向的完整清单</a></p>
    </div>
  </section>

  <section class="section-block section-block--light section-block--institutional">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">{{ home.output_preview.kicker }}</p>
          <h2 class="section-title section-title--left">{{ home.output_preview.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ home.output_preview.intro }}</p>
      </div>

      <div class="publication-grid publication-grid--institutional publication-grid--light">
        {% for item in home.output_preview.cards %}
        <article class="publication-card publication-card--institutional publication-card--light">
          <p class="card-meta">{{ item.meta }}</p>
          <h3 class="card-title">{{ item.title }}</h3>
          <p>{{ item.text }}</p>
          <a class="publication-card__link publication-card__link--light" href="{{ item.link | relative_url }}">{{ item.link_text }}</a>
        </article>
        {% endfor %}
      </div>
    </div>
  </section>

  <section class="section-block section-block--light section-block--institutional">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">团队成员</p>
          <h2 class="section-title section-title--left">团队成员</h2>
        </div>
        <p class="section-intro section-intro--narrow">首页展示课题组教师与学生成员入口，完整名单与个人资料可在成员栏目中继续查看。</p>
      </div>

      {% assign members = site.members | sort: "order" %}
      {% if members.size > 0 %}
      <div class="team-grid team-grid--institutional">
        {% for member in members limit:4 %}
        <article class="member-card member-card--institutional">
          {% if member.photo %}
          <img class="member-card__image" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
          {% else %}
          <div class="member-card__image member-card__image--placeholder">TL</div>
          {% endif %}
          <div class="member-card__body">
            <p class="card-meta">{{ member.role }}</p>
            <h3 class="card-title"><a href="{{ member.url | relative_url }}">{{ member.name }}</a></h3>
            <p>{{ member.research }}</p>
          </div>
        </article>
        {% endfor %}
      </div>
      <p class="section-link"><a href="{{ '/members/' | relative_url }}">查看全部成员</a></p>
      {% endif %}
    </div>
  </section>

  <section class="section-block section-block--soft section-block--institutional">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">{{ home.contact_section.kicker }}</p>
          <h2 class="section-title section-title--left">{{ home.contact_section.title }}</h2>
        </div>
        <p class="section-intro section-intro--narrow">{{ home.contact_section.intro }}</p>
      </div>

      <div class="contact-grid contact-grid--institutional">
        {% for card in home.contact_section.cards %}
        <article class="contact-card">
          <strong>{{ card.title }}</strong>
          <p>{{ card.text | newline_to_br }}</p>
        </article>
        {% endfor %}
      </div>
    </div>
  </section>
</div>
