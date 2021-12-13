---
title: CSharpe
layout: defualt
permalink: /csharp
---

{% for post in site.posts %}
{% if post.categories contains "C#" %}
  <article>
    <h2>
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h2>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    {{ post.content }}
  </article>
{% endif %}
{% endfor %}