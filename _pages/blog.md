---
layout: default
permalink: /blog/
title: blog
nav: true
nav_order: 4
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 5
  sort_field: date
  sort_reverse: true
---

<div class="post">
  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>

  <ul class="post-list">
    {% assign postlist = paginator.posts | default: site.posts %}
    {% for post in postlist %}
    {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    <li>
      <h3>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %d, %Y' }}
      </p>
      {% if post.tags %}
      <p class="post-tags">
        {% for tag in post.tags %}
        <a href="{{ tag | slugify | prepend: '/blog/tag/' | relative_url }}">
          <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>{% unless forloop.last %}&nbsp;{% endunless %}
        {% endfor %}
      </p>
      {% endif %}
    </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
  <nav class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">newer</a>
    {% endif %}
    <span class="page_number">page {{ paginator.page }} of {{ paginator.total_pages }}</span>
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">older</a>
    {% endif %}
  </nav>
  {% endif %}
</div>
