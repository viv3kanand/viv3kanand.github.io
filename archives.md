---
layout: page
title: Archives
permalink: /archives/
header: true
---

<p class="meta">everything &middot; <a href="/R/">R</a></p>

<ul>
{% for post in site.posts %}
  <li>
    {{ post.date | date: "%Y-%m-%d"  }} &mdash; <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
