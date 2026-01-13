---
layout: page
title: Technical
permalink: /technical/
---


  <article>
 
  {% for post in site.posts %}
          {% if post.category contains "Technical" %}
            <li>
              {{ post.excerpt | strip_html_newlines }}
              <a href="{{ post.url | relative_url }}">Read more...</a> 
             <!-- <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date_to_long_string }}</time> -->
            </li>
          {% endif %}
  {% endfor %}
       

    
  </article>

