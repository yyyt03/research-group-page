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
        {% for area in research.areas limit:3 %}
        <article class="research-card research-card--institutional">
          <img class="research-card__image" src="{{ area.image | relative_url }}" alt="{{ area.image_alt }}">
          <div class="research-card__body">
            <p class="card-meta">{{ area.code }}</p>
            <h3 class="card-title">{{ area.title }}</h3>
            <p>{{ area.description }}</p>
          </div>
        </article>
        {% endfor %}
      </div>
    </div>
  </section>

  <section class="section-block section-block--light section-block--institutional">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">Research Team</p>
          <h2 class="section-title section-title--left">核心成员</h2>
        </div>
        <p class="section-intro section-intro--narrow">首页仅展示核心成员入口，完整名单与个人资料可在成员栏目中继续查看。</p>
      </div>

      {% assign members = site.members | sort: "order" %}
      {% if members.size > 0 %}
      <div class="team-grid team-grid--institutional">
        {% for member in members limit:3 %}
        <article class="member-card member-card--institutional">
          {% if member.photo %}
          <img class="member-card__image" src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
          {% else %}
          <div class="member-card__image member-card__image--placeholder">◯</div>
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

  <section class="section-block section-block--light section-block--institutional section-block--archive">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">Academic Output</p>
          <h2 class="section-title section-title--left">最新学术成果</h2>
        </div>
        <p class="section-intro section-intro--narrow">当前成果展示由 `news` collection 承接，以条目摘要方式集中呈现近期研究更新。</p>
      </div>

      {% assign latest_news = site.news | sort: "date" | reverse %}
      {% if latest_news.size > 0 %}
      <div class="publication-grid publication-grid--institutional">
        {% for item in latest_news limit:3 %}
        <article class="publication-card publication-card--institutional">
          <p class="publication-card__journal">{{ item.date | date: "%Y-%m-%d" }}</p>
          <h3 class="card-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h3>
          <p>{{ item.summary }}</p>
          <a class="publication-card__link" href="{{ item.url | relative_url }}">查看详情</a>
        </article>
        {% endfor %}
      </div>
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