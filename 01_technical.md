---
layout: page
title: Technical
permalink: /technical/
---
  {% for post in site.posts %}
  
    {% if post.category contains "Technical" %}
    <article>
     <h2>
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h2>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date_to_long_string }}</time>

    {{ post.excerpt | strip_html_newlines }}

    <a href="{{ post.url | relative_url }}">Read more...</a>
    </article>  
    {% endif %}
  
  {% endfor %}
