---
layout: page
title: Archives
permalink: /tag1/
---


<p class="meta"><a href="/archives/">everything</a> &middot; Tag1</p>
<ul>
{% for post in site.posts %}
  {% if post.tag == "food-and-drug-law" %}
  <li>
    {{ post.date | date: "%Y-%m-%d"  }} &mdash; <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endif %}
{% endfor %}
</ul>
