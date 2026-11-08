---
layout: index
title: "Blog do Mosca"
---

<img src="/mosca-me.png" alt="" style="width: 200px; max-width: 30%; float: right; padding: 10px;">

<h1 class="slogan">Blog do Mosca</h1>

Olá, eu sou Filipe! Sou médico,  atualmente realizando a residência (especialização) de clínica médica. Esse é meu espaço na internet para compartilhar meus hobbies e escrever sobre a medicina.

- [Jogos de tabuleiro](/boardgames/jogos-tabuleiro)
- [Jogos de baralho](/boardgames/baralho)
- [Criador de acrônimos](https://acronimos.mosca.me) para mnemônicos
- Aprendendo a digitar mais rápido: [TypingClub](https://www.edclub.com/sportal/program-21.game)

## Todas as postagens

<ul class="posts">
  {% for post in site.posts %}
      <li>
        <span class="posts-dates">{{ post.date | date: "%d/%m/%Y" }}</span>
        <span class="post-info">
          {% if post.categories contains "medicina" %}
  <span class="tag-emoji" title="Medicina" aria-label="Medicina">{{ site.data.tags.medicina | default: "🩺" }}</span>
{% else %}
  {% for tag in post.tags %}
    {% assign chave = tag | downcase %}
    {% assign emoji = site.data.tags[chave] %}
    {% if emoji %}
    <span class="tag-emoji" title="{{ tag | capitalize }}" aria-label="{{ tag | capitalize }}">{{ emoji }}</span>
    {% else %}
    <span class="tag"><i>#{{ tag | capitalize }}</i></span>
    {% endif %}
  {% endfor %}
{% endif %}
          <a href="{{ post.url }}" class="post-title">{{ post.title }}</a>

        </span>
      </li>
  {% endfor %}
</ul>
