---
layout: default
title: Blog
description: Unity, C#, 게임 클라이언트 개발 기록
permalink: /blog/
---
<section class="page-hero">
  <div class="container">
    <p class="eyebrow">DEVELOPMENT NOTES</p>
    <h1>Blog</h1>
    <p>문제를 발견하고, 구조를 잡고, 해결한 뒤 남기는 개발 기록입니다.</p>
  </div>
</section>

<section class="section container blog-layout">
  <div class="post-list">
    {% for post in site.posts %}
    <article class="post-list-item">
      <div class="post-list-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time></div>
      <div>
        <p class="category-label">{{ post.categories | first | default: 'DEV NOTE' }}</p>
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p>{{ post.description }}</p>
        <div class="tag-list">
          {% for tag in post.tags %}<a class="tag" href="{{ '/tags/' | relative_url }}#{{ tag | slugify }}">#{{ tag }}</a>{% endfor %}
        </div>
      </div>
      <a class="list-arrow" href="{{ post.url | relative_url }}" aria-label="{{ post.title }} 읽기">↗</a>
    </article>
    {% endfor %}
  </div>

  <aside class="sidebar">
    <p class="sidebar-title">CATEGORIES</p>
    <ul>
      {% assign categories = site.categories | sort %}
      {% for category in categories %}<li><span>{{ category[0] }}</span><strong>{{ category[1].size }}</strong></li>{% endfor %}
    </ul>
  </aside>
</section>
