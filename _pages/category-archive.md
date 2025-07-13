---
title: "Categories"
layout: category
permalink: /categories/
author_profile: true
---
## Các trang con trong Categories

<ul>
{% assign subpages = site.pages | where_exp: "page", "page.url != '/categories/' and page.url contains '/categories/'" %}

{% for page in subpages %}
{% assign parts = page.url | split: '/' | reject: '' %}
{% comment %} parts là mảng các phần trong url, ví dụ ['categories', 'sample'] {% endcomment %}
{% if parts.size == 2 %}
<li><a href="{{ page.url }}">{{ page.title }}</a></li>
{% endif %}
{% endfor %}
</ul>
