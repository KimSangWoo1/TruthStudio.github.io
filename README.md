# TruthStudio — Jekyll Development Blog

Unity / C# / 게임 클라이언트 개발 기록을 위한 GitHub Pages + Jekyll 스타터입니다.

## 1. GitHub Pages로 배포하기

1. GitHub에서 새 저장소를 만듭니다.
   - 개인 사이트 주소를 쓰려면: `<GitHub ID>.github.io`
   - 프로젝트 사이트로 쓰려면: 원하는 저장소 이름
2. 이 폴더의 파일을 저장소 루트에 올리고 `main` 브랜치에 푸시합니다.
3. GitHub 저장소 **Settings → Pages → Build and deployment**에서 **GitHub Actions**를 선택합니다.
4. Actions 탭의 `Deploy Jekyll site to GitHub Pages` 워크플로가 완료되면 Pages 주소가 표시됩니다.

> GitHub Pages는 외부에 공개될 수 있으므로, 토큰·API 키·회사 내부 문서와 같은 민감한 정보는 저장소에 올리지 마세요.

## 2. 꼭 바꿔야 하는 값

`_config.yml`

```yml
url: "https://YOUR_GITHUB_USERNAME.github.io"
baseurl: ""
```

- 저장소가 `YOUR_GITHUB_USERNAME.github.io`라면 `baseurl`은 빈 값으로 둡니다.
- 저장소가 `truthstudio`처럼 일반 프로젝트 저장소라면 `baseurl: "/truthstudio"`로 바꿉니다.

또한 아래 파일의 `YOUR_GITHUB_USERNAME`을 본인 GitHub ID로 바꿔 주세요.

- `_includes/header.html`
- `_includes/footer.html`

## 3. 새 글 작성

`_posts` 안에 `YYYY-MM-DD-title.md` 형식의 파일을 추가합니다.

```md
---
title: "글 제목"
description: "한 줄 요약"
categories: [Unity]
tags: [CSharp, Architecture]
reading_time: "5 min"
---

본문을 작성합니다.
```

## 4. 프로젝트 아카이브 작성

`_projects` 폴더에 Markdown 파일을 추가합니다.

```md
---
title: "프로젝트 이름"
summary: "한 줄 소개"
role: "Client Programmer"
period: "2026.01 — 2026.04"
status: "IN PROGRESS"
tech: [Unity, CSharp]
order: 4
---

프로젝트의 문제, 선택, 결과를 작성합니다.
```

## 5. 로컬 실행 (선택)

Ruby와 Bundler가 설치되어 있다면 아래 명령으로 확인할 수 있습니다.

```bash
bundle install
bundle exec jekyll serve
```

브라우저에서 `http://localhost:4000`을 엽니다.
