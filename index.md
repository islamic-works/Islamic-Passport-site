---
layout: default
title: Islamic Passport
seo_title: Islamic Passport | Identidade Digital Islâmica Confiável
description: "Conheça o Islamic Passport: plataforma de identidade digital islâmica com validação descentralizada, confiança mútua e governança ética alinhada à Sharīʿah."
keywords:
  - "Islamic Passport"
  - "identidade digital islâmica"
  - "blockchain islâmico"
  - "confiança mútua"
  - "ética islâmica"
---

<section class="hero">
  <div class="container">
    <div class="hero-content">
      <h1>Islamic Passport</h1>
      <p>Sistema de identificação e autenticação que fortalece a confiança entre mulçumanos e entidades islâmicas reconhecidas.</p>
      <a class="cta" href="#lancamentos">Conheça as últimas versões</a>
    </div>
    <div class="hero-illustration" aria-hidden="true">
      <div class="passport-card">
        <img src="{{ '/imgs/passport-card-640x427.png' | relative_url }}" alt="Identidade Islâmica" />
      </div>
    </div>
  </div>
</section>

<section id="noticias" class="section">
  <div class="container">
    <div class="section-heading">
      <h2>Notícias</h2>
      <p>Acompanhe novidades do ecossistema Islamic Passport.</p>
    </div>
    <div class="grid">
      {% assign published_news = site.news | where_exp: "item", "item.date <= site.time" %}
      {% assign latest_news = published_news | sort: 'date' | reverse %}
      {% for item in latest_news limit:3 %}
        <article class="card">
          <h3><a href="{{ item.url | relative_url }}">{{ item.title }}</a></h3>
          <p class="meta">{{ item.date | date: "%d %B %Y" }}</p>
          <p>{{ item.summary | default: item.excerpt }}</p>
        </article>
      {% endfor %}
      {% if latest_news.size == 0 %}
        <p class="empty">Em breve traremos comunicados oficiais.</p>
      {% endif %}
    </div>
  </div>
</section>

<section id="lancamentos" class="section section-alt">
  <div class="container">
    <div class="section-heading">
      <h2>Lançamentos</h2>
      <p>Versões oficiais do software e pacotes de atualização.</p>
    </div>
    <div class="timeline">
      {% assign releases = site.releases | sort: 'date' | reverse %}
      {% for release in releases limit:4 %}
        <div class="timeline-item">
          <div class="timeline-marker"></div>
          <div class="timeline-content">
            <h3><a href="{{ release.url | relative_url }}">{{ release.title }}</a></h3>
            <p class="meta">{{ release.date | date: "%d %B %Y" }}</p>
            <p>{{ release.summary | default: release.excerpt }}</p>
          </div>
        </div>
      {% endfor %}
      {% if releases.size == 0 %}
        <p class="empty">Ainda não publicamos versões oficiais.</p>
      {% endif %}
    </div>
  </div>
</section>

<section id="entidades" class="section">
  <div class="container">
    <div class="section-heading">
      <h2>Entidades em Destaque</h2>
      <p>Instituições parceiras que utilizam o Islamic Passport.</p>
    </div>
    <div class="grid grid-entities">
      {% assign entities = site.entities | sort: 'position' %}
      {% for entity in entities limit:6 %}
        <article class="card entity">
          <h3><a href="{{ entity.url | relative_url }}">{{ entity.title }}</a></h3>
          <p class="meta">{{ entity.location }}</p>
          <p>{{ entity.summary | default: entity.excerpt }}</p>
        </article>
      {% endfor %}
      {% if entities.size == 0 %}
        <p class="empty">Estamos convidando entidades parceiras. Aguarde novidades.</p>
      {% endif %}
    </div>
  </div>
</section>

<section class="callout">
  <div class="container">
    <h2>Fortalecendo a Ummah com confiança digital</h2>
    <p>Empreendimento Rapport entrega o Islamic Passport para conectar fiéis e organizações com legitimidade e segurança.</p>
    <a class="cta-outline" href="mailto:admin@rapport.tec.br">Fale com a equipe</a>
  </div>
</section>
