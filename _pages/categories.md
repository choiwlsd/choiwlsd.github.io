---
layout: default # GitBook 테마 기본 레이아웃
title: 📂 카테고리
permalink: /categories/
---

{% assign sorted = site.categories | sort %}

<ul class="summary">          <!-- ⭐ GitBook과 동일한 class -->
{% for cat in sorted %}
  <li class="chapter">
    <a class="title" href="#" onclick="return false;">{{ cat[0] }} ({{ cat[1] | size }})</a>
    <ul class="articles">
      {% for p in cat[1] %}
        <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a></li>
      {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>
