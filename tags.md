---
layout: default
title: Tags
description: 주제별 개발 기록
permalink: /tags/
---
<section class="page-hero">
  <div class="container">
    <p class="eyebrow">TOPIC INDEX</p>
    <h1>Tags</h1>
    <p>관심 있는 주제부터 빠르게 찾아볼 수 있도록 모았습니다.</p>
  </div>
</section>

<section class="section container tag-index">
  {% assign tags = site.tags | sort %}
  {% for tag in tags %}
  <section id="{{ tag[0] | slugify }}" class="tag-section">
    <h2>#{{ tag[0] }} <span>{{ tag[1].size }}</span></h2>
    <ul>
      {% for post in tag[1] %}
      <li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
  </section>
  {% endfor %}
</section>
