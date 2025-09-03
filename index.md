---
layout: default
title: Главная
---

# Привет!
Это мой минималистичный IT-блог. Ниже — свежие статьи.

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <small>— {{ post.date | date: "%d.%m.%Y" }}</small>
    {% if post.tags %} <em>#{{ post.tags | join: " #" }}</em> {% endif %}
  </li>
{% endfor %}
</ul>
