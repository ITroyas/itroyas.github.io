<div class="post-card">
  {% if post.image %}
    <img src="{{ post.image }}" alt="{{ post.title }}">
  {% endif %}
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p>{{ post.content | strip_html | truncatewords:50 }}</p>
  <a class="read-more" href="{{ post.url | relative_url }}">Читать далее</a>
  {% if post.tags %}
    <div class="post-tags">
      {% for tag in post.tags %}
        <a href="{{ '/tags/' | relative_url }}#{{ tag }}">{{ tag }}</a>
      {% endfor %}
      <span class="post-date">{{ post.date | date: "%d.%m.%Y" }}</span>
    </div>
  {% endif %}
</div>
