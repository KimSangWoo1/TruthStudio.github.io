---
layout: default
title: Projects
description: TruthStudio의 프로젝트 아카이브
permalink: /projects/
---
<section class="page-hero">
  <div class="container">
    <p class="eyebrow">PROJECT ARCHIVE</p>
    <h1>Projects</h1>
    <p>문제와 선택, 구현 과정에 집중해 정리한 프로젝트 단위의 기록입니다.</p>
  </div>
</section>

<section class="section container">
  <div class="archive-grid">
    {% assign ordered_projects = site.projects | sort: 'order' %}
    {% for project in ordered_projects %}
    <article class="archive-card">
      <div class="archive-card-number">0{{ forloop.index }}</div>
      <p class="category-label">{{ project.status | default: 'CASE STUDY' }}</p>
      <h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
      <p>{{ project.summary }}</p>
      <div class="tag-list">{% for tech in project.tech %}<span class="tag">{{ tech }}</span>{% endfor %}</div>
      <a class="text-link" href="{{ project.url | relative_url }}">Case study 보기 →</a>
    </article>
    {% endfor %}
  </div>
</section>
