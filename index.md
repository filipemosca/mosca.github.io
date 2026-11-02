---
layout: index
title: "Blog do Mosca"
---

<img src="/mosca-net-logo.png" alt="" style="width: 200px; max-width: 30%; float: right; padding: 10px;">

<h1 class="slogan">Blog do Mosca</h1>

Olá, eu sou Filipe! Sou médico,  atualmente realizando a residência (especialização) de clínica médica. Esse é meu espaço na internet para compartilhar meus hobbies e escrever sobre a medicina.

- [Jogos de tabuleiro](/boardgames/jogos-tabuleiro)
- [Jogos de baralho](/boardgames/baralho)
- [Criador de acrônimos](https://acronimos.mosca.net.br) para mnemônicos
- Aprendendo a digitar mais rápido: [TypingClub](https://www.edclub.com/sportal/program-21.game)

## Todas as postagens

<ul class="posts">
  {% for post in site.posts %}
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

<!-- <ul class="posts">
  {% for post in site.posts %}
      {% assign post_time = post.date | date: '%s' %}
      {% assign now = 'now' | date: '%s' %}
      {% assign diff = now | minus: post_time %}
      <li>
        <span class="posts-dates">{{ post.date | date: "%d/%m/%Y" }}</span> <span class="break"></span>
        <a href="{{ post.url }}" class="post-title">{{ post.title }}</a>
        {% for tag in post.tags %}
        <span class="tag"><i>#{{ tag | capitalize }}</i></span>
        {% endfor %}
        {% if diff < 2592000 %}
          <span class="novo-badge"><i>Novo!</i></span>
        {% endif %}
      </li>
  {% endfor %}
</ul> -->


<!-- <ul class="feed">
  {% for post in site.posts %}
      <li>
        <span class="data">{{ post.date | date: "%d/%m/%Y" }}</span>
        {% if post.categories.size > 0 %}
        {% for category in post.categories %}
        <span class="categoria">#{{ category | capitalize }}</span>
        {% endfor %}
        {% endif %} 
        {% for tag in post.tags %}
        <span class="tag">#{{ tag | capitalize  }}</span>
         {% endfor %}
        <br> 
        <a href="{{ post.url }}">{{ post.title }}</a>
      </li>
  {% endfor %}
</ul> -->