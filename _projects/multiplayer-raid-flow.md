---
title: "Multiplayer Raid Flow"
summary: "보스 페이즈와 기믹 상태를 여러 클라이언트에서 일관되게 보여 주기 위한 동기화 흐름 예시입니다."
role: "Client Programmer"
period: "Case study template"
status: "MULTIPLAYER"
tech: [Unity, CSharp, Networking]
order: 2
---

## Goal

여러 참여자가 같은 보스 페이즈와 기믹 결과를 신뢰할 수 있게 보고, 입장·이탈·재접속 상황에서도 현재 전투 상태를 복원할 수 있도록 합니다.

## Approach

권한 주체가 최종 상태를 결정하도록 하고, 클라이언트는 입력 요청과 화면 표현을 분리했습니다. 상태 스냅샷과 일회성 이벤트를 구분해, 재접속 시에는 스냅샷만으로 현재 화면을 복구할 수 있게 구성했습니다.

## What I learned

동기화의 핵심은 전송량보다도, 각 데이터가 **명령인지 상태인지** 그리고 **누가 결정권을 갖는지**를 문서와 코드에서 같은 방식으로 표현하는 데 있었습니다.
