---
layout: page
title: Archives
permalink: /R/
---


<p class="meta"><a href="/archives/">everything</a> &middot; R</p>
<ul>
{% for post in site.posts %}
  {% if post.tag == "R" %}
  <li>
    {{ post.date | date: "%Y-%m-%d"  }} &mdash; <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endif %}
{% endfor %}
</ul>
