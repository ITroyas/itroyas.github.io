---
layout: default
title: Блог
---

<div class="blog-container">
  <div class="posts-grid">
    {% for post in site.posts %}
    <article class="post-card">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <time>{{ post.date | date: "%d %b %Y" }}</time>
      <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
      <a class="read-more" href="{{ post.url }}">Читать далее</a>
      <div class="tags">
        {% for tag in post.tags %}
          <span>#{{ tag }}</span>
        {% endfor %}
      </div>
    </article>
    {% endfor %}
  </div>

  <aside class="sidebar">
    <h3>Категории</h3>
    <ul>
      {% assign alltags = site.tags | sort %}
      {% for tag in alltags %}
        <li><a href="{{ '/tags/' | relative_url }}#{{ tag[0] }}">#{{ tag[0] }}</a></li>
      {% endfor %}
    </ul>
  </aside>
</div>
