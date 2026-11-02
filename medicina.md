---
title: Medicina das Ruas
layout: index
---

<img src="/dr-mosca.png" alt="" style="width: 200px; max-width: 30%; float: right; padding: 10px;">

<h1 class="slogan">Medicina das Ruas</h1>

Blog de um clínico para clínicos e estudantes. Escrito por Filipe Mosca, clínico em formação. Esse blog não pretensão de servir como aconselhamento à população geral. O objetivo aqui é contribuir para a educação médica.

<ul class="posts">
  {% for post in site.categories.medicina %}
      {% assign post_time = post.date | date: '%s' %}
      {% assign now = 'now' | date: '%s' %}
      {% assign diff = now | minus: post_time %}
      <li>
        <span class="posts-dates">{{ post.date | date: "%d/%m/%Y" }}</span>
        <span class="post-info">
          <a href="{{ post.url }}" class="post-title">{{ post.title }}</a>
          {% for tag in post.tags %}
          <span class="tag"><i>#{{ tag | capitalize }}</i></span>
          {% endfor %}
          {% if diff < 2592000 %}
          <span class="novo-badge"><i>Novo!</i></span>
          {% endif %}
        </span>
      </li>
  {% endfor %}
</ul>