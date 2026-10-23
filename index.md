---
layout: index
title: "Blog do Mosca"
---

<img src="/blog-do-mosca.png" alt="" style="max-width: 500px;">

Olá, eu sou Filipe! Sou médico,  atualmente realizando a residência (especialização) de clínica médica. Esse é meu espaço na internet para compartilhar meus hobbies e escrever sobre a medicina.


- [Jogos de tabuleiro](/boardgames/jogos-tabuleiro)
- [Jogos de baralho](/boardgames/baralho)
- [Criado de acrônimos](https://acronimos.mosca.net.br) para mnemônicos
- Aprendendo a digitar mais rápido: [TypingClub](https://www.edclub.com/sportal/program-21.game)

## Todas as postagens

<ul class="feed">
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
</ul>