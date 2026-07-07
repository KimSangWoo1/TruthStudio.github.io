---
title: "TruthStudio를 시작하며: 기록을 개발 자산으로 만드는 방법"
description: "개인 개발 블로그를 시작하며, 무엇을 남기고 어떤 기준으로 글을 쓸지 정리했습니다."
date: 2026-07-07 09:00:00 +0900
categories: [Workflow]
tags: [Jekyll, GitHub-Pages, Documentation]
reading_time: "4 min"
---

개발을 하다 보면 비슷한 문제를 다시 만나는 순간이 많습니다. 그때 과거의 선택과 이유가 남아 있다면, 같은 시행착오를 반복하지 않아도 됩니다.

TruthStudio는 결과만 나열하는 공간보다 **문제 → 판단 → 구현 → 회고**의 흐름을 남기는 공간을 목표로 합니다.

## 글을 남기는 기준

- 재사용할 수 있는 해결 방법인가?
- 나중의 내가 선택 이유를 이해할 수 있는가?
- 팀원이 읽었을 때 다음 행동을 결정할 수 있는가?

## 포스트 템플릿

새 글은 `_posts` 폴더에 `YYYY-MM-DD-title.md` 형식으로 만들면 됩니다.

```yaml
---
title: "글 제목"
description: "한 줄 요약"
categories: [Unity]
tags: [CSharp, Architecture]
reading_time: "5 min"
---
```

이후에는 배경, 문제, 시도, 최종 선택, 배운 점 순서로 적어 두면 글의 맥락이 자연스럽게 이어집니다.
