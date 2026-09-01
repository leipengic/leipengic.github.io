---
layout: page
title: 文章归档
permalink: /archive/
---

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
## {{ year.name }} 年
<ul>
  {% for post in year.items %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <small>（{{ post.date | date: "%m-%d" }}）</small>
  </li>
  {% endfor %}
</ul>
{% endfor %}
