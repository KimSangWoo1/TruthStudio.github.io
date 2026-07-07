---
title: "Client Workflow Improvement"
summary: "반복되는 UI·이벤트 작업을 공통화하고, 문서화와 검증 흐름을 정리한 생산성 개선 사례 예시입니다."
role: "Client Programmer"
period: "Case study template"
status: "WORKFLOW"
tech: [Unity, Git, Documentation]
order: 3
---

## Context

같은 형태의 팝업과 보상 처리, 이벤트 진입 로직이 여러 기능에 반복되면서 화면마다 예외 처리가 늘어나는 문제가 있었습니다.

## Improvement

공통 진입점과 데이터 기반 설정을 도입하고, 기능을 추가할 때 확인해야 할 체크리스트를 문서화했습니다. 반복되는 작업은 공통 컴포넌트로 묶되, 콘텐츠별 차이는 데이터로 분리했습니다.

## Outcome

새 콘텐츠를 연결할 때의 준비 작업이 단순해지고, 리뷰 시에도 변경된 책임 범위를 빠르게 확인할 수 있게 되었습니다.
