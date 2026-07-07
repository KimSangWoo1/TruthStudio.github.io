---
title: "Gameplay System Foundation"
summary: "전투·스킬·상태 효과가 서로 강하게 얽히지 않도록 데이터와 실행 책임을 정리한 시스템 설계 예시입니다."
role: "Client Programmer"
period: "Case study template"
status: "SYSTEM DESIGN"
tech: [Unity, CSharp, ScriptableObject]
order: 1
---

> 이 페이지는 프로젝트 아카이브를 작성할 때 사용할 수 있는 예시입니다. 실제 프로젝트의 내부 정보 대신, 공개 가능한 맥락과 본인의 기여를 중심으로 교체해 주세요.

## Problem

초기 구현에서는 스킬, 버프, UI가 서로의 구체적인 타입을 직접 참조하고 있었습니다. 기능 하나를 추가할 때마다 수정 범위가 넓어지고, 테스트 가능한 단위도 작아졌습니다.

## Decision

- 데이터 정의와 런타임 실행 객체를 분리했습니다.
- 상태 효과는 공통 인터페이스를 통해 적용·해제하도록 정리했습니다.
- UI는 전투 상태를 직접 변경하지 않고, 이벤트를 통해 표시만 담당하게 했습니다.

## Result

새 스킬을 추가할 때 수정해야 하는 경로가 줄고, 데이터 검증과 런타임 로직을 나눠 테스트하기 쉬운 구조가 되었습니다.
