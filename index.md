---
layout: default
title: Home
description: TruthStudio — Unity, C#, 게임 클라이언트 개발 기록
permalink: /
---
<section class="hero">
  <div class="container hero-grid">
    <div class="hero-copy">
      <p class="eyebrow">GAME CLIENT DEVELOPMENT LOG</p>
      <h1>기록이 쌓여<br><em>더 단단한 개발</em>이 된다.</h1>
      <p class="hero-description">TruthStudio는 Unity와 C#을 중심으로, 게임 플레이 시스템·UI·멀티플레이·최적화의 시행착오를 구조화해 남기는 개발 블로그입니다.</p>
      <div class="hero-actions">
        <a class="button" href="{{ '/blog/' | relative_url }}">개발 노트 보기 <span>→</span></a>
        <a class="button button-ghost" href="{{ '/projects/' | relative_url }}">프로젝트 둘러보기</a>
      </div>
    </div>
    <div class="hero-panel" aria-label="TruthStudio 개발 원칙">
      <div class="panel-topline"><span class="status-dot"></span> SYSTEM ONLINE</div>
      <div class="code-window">
        <span class="code-comment">// TruthStudio Principle</span>
        <span><b>while</b> (building)</span>
        <span>{</span>
        <span class="indent">learn();</span>
        <span class="indent">document();</span>
        <span class="indent">ship();</span>
        <span>}</span>
      </div>
      <div class="panel-stats">
        <div><strong>Unity</strong><span>Client</span></div>
        <div><strong>C#</strong><span>Systems</span></div>
        <div><strong>∞</strong><span>Notes</span></div>
      </div>
    </div>
  </div>
</section>

<section class="section container">
  <div class="section-heading">
    <div>
      <p class="eyebrow">LATEST NOTES</p>
      <h2>최근 개발 기록</h2>
    </div>
    <a class="text-link" href="{{ '/blog/' | relative_url }}">모든 글 보기 →</a>
  </div>
  <div class="post-grid">
    {% for post in site.posts limit: 3 %}
    <article class="post-card">
      <div class="post-card-top">
        <span class="category-label">{{ post.categories | first | default: 'DEV NOTE' }}</span>
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
      </div>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p>{{ post.description }}</p>
      <div class="card-footer"><span>{{ post.reading_time | default: '3 min' }}</span><a href="{{ post.url | relative_url }}" aria-label="{{ post.title }} 읽기">↗</a></div>
    </article>
    {% endfor %}
  </div>
</section>

<section class="section section-muted">
  <div class="container">
    <div class="section-heading">
      <div>
        <p class="eyebrow">FOCUS AREAS</p>
        <h2>무엇을 기록하나요?</h2>
      </div>
    </div>
    <div class="focus-grid">
      <article class="focus-card"><span class="focus-index">01</span><h3>Game Systems</h3><p>전투, AI, 퀘스트, 스킬처럼 플레이의 핵심이 되는 시스템을 설계합니다.</p></article>
      <article class="focus-card"><span class="focus-index">02</span><h3>Client Architecture</h3><p>확장 가능한 구조와 데이터 흐름을 고민하고, 유지보수 가능한 코드로 정리합니다.</p></article>
      <article class="focus-card"><span class="focus-index">03</span><h3>Optimization</h3><p>프레임, 메모리, 로딩 시간을 관찰하고 병목을 줄이는 과정을 기록합니다.</p></article>
      <article class="focus-card"><span class="focus-index">04</span><h3>Team Workflow</h3><p>Git, 문서화, 공통화처럼 팀 생산성을 높이는 작은 개선도 놓치지 않습니다.</p></article>
    </div>
  </div>
</section>

<section class="section container project-preview">
  <div class="section-heading">
    <div>
      <p class="eyebrow">SELECTED WORK</p>
      <h2>프로젝트 아카이브</h2>
    </div>
    <a class="text-link" href="{{ '/projects/' | relative_url }}">프로젝트 전체 보기 →</a>
  </div>
  <div class="project-list">
    {% assign ordered_projects = site.projects | sort: 'order' %}
    {% for project in ordered_projects limit: 3 %}
    <a class="project-row" href="{{ project.url | relative_url }}">
      <span class="project-number">0{{ forloop.index }}</span>
      <span class="project-title">{{ project.title }}<small>{{ project.summary }}</small></span>
      <span class="project-tech">{{ project.tech | join: ' · ' }}</span>
      <span class="project-arrow">↗</span>
    </a>
    {% endfor %}
  </div>
</section>
