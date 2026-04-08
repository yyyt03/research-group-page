---
layout: default
title: 联系方式
permalink: /contact/
---
{% assign contact = site.data.page_content.contact %}
<section class="page-shell page-shell--institutional">
  <div class="wrapper">
    <header class="page-masthead">
      <p class="section-kicker">{{ contact.masthead.kicker }}</p>
      <h1 class="section-title section-title--left">{{ contact.masthead.title }}</h1>
      <p class="section-intro section-intro--wide">{{ contact.masthead.intro }}</p>
    </header>

    <div class="contact-grid contact-grid--institutional">
      {% for card in contact.cards %}
      <article class="contact-card">
        <strong>{{ card.title }}</strong>
        <p>{{ card.text | newline_to_br }}</p>
      </article>
      {% endfor %}
    </div>
  </div>
</section>