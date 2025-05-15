---
layout: page # GitBook 테마 기본 레이아웃
title: 📂 카테고리
permalink: /categories/
---

{% assign sorted = site.categories | sort %}

<ul class="category-list">
{% for cat in sorted %}
  {% assign cat_name  = cat[0] %}
  {% assign posts     = cat[1] %}
  <li>
    <details>
      <summary><strong>{{ cat_name }} ({{ posts | size }})</strong></summary>
      <ul>
        {% for p in posts %}
          <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a></li>
        {% endfor %}
      </ul>
    </details>
  </li>
{% endfor %}
</ul>
