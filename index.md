---
title: Absorb a Concept
---

<h1>{{ page.title }}</h1>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h2>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
      {{ post.excerpt }}
      <a href="{{ post.url | relative_url }}">Read more...</a>
    </li>
  {% endfor %}
</ul>
