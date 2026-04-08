---
layout: default
title: 首页
permalink: /
---
<div class="landing-shell landing-shell--center">
  <section class="landing-hero landing-hero--institutional">
    <div class="wrapper landing-hero__content landing-hero__content--institutional">
      <p class="section-kicker section-kicker--hero">考古研究中心</p>
      <h1 class="landing-title">考古课题组与研究中心信息平台</h1>
      <p class="landing-lead">围绕石器技术研究、实验考古与微形态分析，持续建设课题组成员、项目、学术成果与合作动态的公开窗口。</p>
      <div class="hero-keywords">
        <span class="detail-chip">石器技术</span>
        <span class="detail-chip">实验考古</span>
        <span class="detail-chip">微形态分析</span>
        <span class="detail-chip">区域比较研究</span>
      </div>
      <div class="hero-actions hero-actions--institutional">
        <a class="button-primary" href="{{ '/research/' | relative_url }}">研究方向</a>
        <a class="button-secondary" href="{{ '/members/' | relative_url }}">团队成员</a>
      </div>
    </div>
  </section>

  <section class="section-block section-block--light section-block--institutional">
    <div class="wrapper">
      <div class="about-grid about-grid--institutional">
        <div>
          <p class="section-kicker">机构简介</p>
          <h2 class="section-title section-title--left">研究定位与方法</h2>
          <div class="about-accent-line"></div>
          <p class="about-copy">本站以考古课题组为核心，服务于研究中心式的信息展示需求，集中呈现研究方向、成员结构、项目进展与成果发布，形成长期维护的公开界面。</p>
          <p class="about-copy">当前建设重点包括 <strong>石器技术研究</strong>、<strong>实验考古</strong>、<strong>汉水流域及长江中游旧石器研究</strong> 与 <strong>华南及东南亚区域比较</strong> 等方向。</p>
          <p class="about-copy">课题组强调材料分析、实验复原与跨区域比较相结合，并持续推进与国内外研究机构的合作交流。</p>
        </div>

        <div class="media-stack media-stack--institutional">
          <img class="media-stack__image" src="/assets/uploads/site/index-lab.jpg" alt="研究中心空间展示图">
        </div>
      </div>
    </div>
  </section>

  <section class="section-block section-block--soft section-block--institutional research-showcase">
    <div class="wrapper">
      <div class="section-header section-header--split">
        <div>
          <p class="section-kicker">Research Areas</p>
          <h2 class="section-title section-title--left">核心研究方向</h2>
        </div>
        <p class="section-intro section-intro--narrow">研究方向页、项目页与成果页将围绕以下三条主线保持一致的学术表达与栏目组织。</p>
      </div>

      <div class="research-grid research-grid--institutional">
        <article class="research-card research-card--institutional">
          <img class="research-card__image" src="/assets/uploads/site/research-economy.png" alt="石器技术研究">
          <div class="research-card__body">
            <p class="card-meta">Area 01</p>
            <h3 class="card-title">石器技术研究</h3>
            <p>围绕旧石器时代技术体系开展类型学与工艺链分析，结合显微观察与材料比较，重建早期人类技术行为与知识传统。</p>
          </div>
        </article>

        <article class="research-card research-card--institutional">
          <img class="research-card__image" src="/assets/uploads/site/research-yangtze.jpg" alt="汉水流域与长江中游旧石器研究">
          <div class="research-card__body">
            <p class="card-meta">Area 02</p>
            <h3 class="card-title">汉水流域与长江中游旧石器研究</h3>
            <p>关注区域材料、遗址序列与技术演化问题，讨论远古人类活动、环境适应与地区间交流的长期过程。</p>
          </div>
        </article>

        <article class="research-card research-card--institutional">
          <img class="research-card__image" src="/assets/uploads/site/research-hankou.jpg" alt="华南与东南亚比较研究">
          <div class="research-card__body">
            <p class="card-meta">Area 03</p>
            <h3 class="card-title">华南与东南亚比较研究</h3>
            <p>比较华南与东南亚古代人类文化和技术关系，为跨区域考古合作、区域互动与文明交流研究提供新的证据框架。</p>
          </div>
        </article>
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
          <p class="section-kicker">Contact</p>
          <h2 class="section-title section-title--left">加入我们</h2>
        </div>
        <p class="section-intro section-intro--narrow">欢迎对考古学、科技分析与区域比较研究感兴趣的学生、研究者及合作伙伴与课题组联系。</p>
      </div>

      <div class="contact-grid contact-grid--institutional">
        <article class="contact-card">
          <strong>办公地点</strong>
          <p>武汉大学历史学院<br>研究中心相关办公与资料整理空间可继续补充。</p>
        </article>
        <article class="contact-card">
          <strong>联系邮箱</strong>
          <p>lyhfrance2005@yahoo.fr<br>合作、招生与研究咨询优先通过邮件联系。</p>
        </article>
      </div>
    </div>
  </section>
</div>
