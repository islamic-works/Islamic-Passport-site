---
layout: default
title: Arquivo de Publicações
seo_title: Arquivo Islamic Passport | Notícias, Lançamentos e Entidades
description: "Explore o histórico completo de notícias, lançamentos e entidades reconhecidas pelo Islamic Passport."
keywords:
  - "arquivo Islamic Passport"
  - "histórico noticias islâmicas"
  - "lançamentos Islamic Passport"
  - "entidades islamic passport"
  - "repositório comunidade islâmica"
permalink: /arquivo/
---

<section class="section archive">
  <div class="container reading">
    <header class="archive-intro">
      <h1>Arquivo de Publicações</h1>
      <p>Explore todas as notícias, lançamentos e entidades já apresentadas no Islamic Passport.</p>
    </header>

    <div class="archive-groups">
      {% assign published_news = site.news | where_exp: "item", "item.date <= site.time" | sort: 'date' | reverse %}
      <section class="archive-group">
        <h2>Notícias</h2>
        {% if published_news.size > 0 %}
          <ul class="archive-list">
            {% for item in published_news %}
              <li class="archive-item">
                <span class="archive-item-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></span>
                <span class="archive-meta">{{ item.date | date: "%d %B %Y" }}</span>
                {% if item.summary %}
                  <p class="archive-summary">{{ item.summary }}</p>
                {% endif %}
              </li>
            {% endfor %}
          </ul>
        {% else %}
          <p class="archive-empty">Nenhuma notícia publicada até o momento.</p>
        {% endif %}
      </section>

      {% assign published_releases = site.releases | sort: 'date' | reverse %}
      <section class="archive-group">
        <h2>Lançamentos</h2>
        {% if published_releases.size > 0 %}
          <ul class="archive-list">
            {% for item in published_releases %}
              <li class="archive-item">
                <span class="archive-item-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></span>
                {% if item.date %}
                  <span class="archive-meta">{{ item.date | date: "%d %B %Y" }}</span>
                {% endif %}
                {% if item.summary %}
                  <p class="archive-summary">{{ item.summary }}</p>
                {% endif %}
              </li>
            {% endfor %}
          </ul>
        {% else %}
          <p class="archive-empty">Ainda não publicamos lançamentos.</p>
        {% endif %}
      </section>

      {% assign featured_entities = site.entities | sort: 'position' %}
      <section class="archive-group">
        <h2>Entidades</h2>
        {% if featured_entities.size > 0 %}
          <ul class="archive-list">
            {% for item in featured_entities %}
              <li class="archive-item">
                <span class="archive-item-title"><a href="{{ item.url | relative_url }}">{{ item.title }}</a></span>
                {% if item.location %}
                  <span class="archive-meta">{{ item.location }}</span>
                {% endif %}
                {% if item.summary %}
                  <p class="archive-summary">{{ item.summary }}</p>
                {% endif %}
              </li>
            {% endfor %}
          </ul>
        {% else %}
          <p class="archive-empty">As entidades serão divulgadas em breve.</p>
        {% endif %}
      </section>
    </div>
  </div>
</section>
