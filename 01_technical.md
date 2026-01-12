---
layout: page
title: Technical
permalink: /technical/
order: 1
---

{% for post in site.posts %}
  <article>
    <h2>
       <a> 
          {% if post.categories contains "Technical" %}
            <li>
              <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
            </li>
          {% endif %}
       </a>
     
    </h2>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date_to_long_string }}</time>

    {{ post.excerpt | strip_html_newlines }}

    <a href="{{ post.url | relative_url }}">Read more...</a>
  </article>
{% endfor %}
