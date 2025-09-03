---
layout: default
title: Блог
show_sidebar: true
permalink: /blog/
---

<div class="posts-grid">
{% for post in site.posts %}
  <div class="post-card">
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p class="post-date">{{ post.date | date: "%d.%m.%Y" }}</p>
    <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
    <a class="read-more" href="{{ post.url | relative_url }}">Читать далее</a>
    <div class="post-tags">
      {% for tag in post.tags %}
        <span>#{{ tag }}</span>
      {% endfor %}
    </div>
  </div>
{% endfor %}
</div>
