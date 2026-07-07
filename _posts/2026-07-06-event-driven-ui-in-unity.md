---
title: "Unity UI를 이벤트 중심으로 정리할 때 확인할 세 가지"
description: "UI가 데이터 변경을 직접 추적하지 않도록 분리하고, 갱신 비용과 생명주기를 관리하는 기준을 정리합니다."
date: 2026-07-06 21:00:00 +0900
categories: [Unity]
tags: [Unity, CSharp, UI, Architecture]
reading_time: "6 min"
---

UI가 게임 모델을 직접 참조해 매 프레임 값을 확인하기 시작하면, 화면은 빨리 만들 수 있어도 수정 지점이 늘어납니다. 이때 UI는 **변경 사실을 받는 역할**에 집중하고, 모델은 **상태를 보관하는 역할**을 유지하는 편이 관리하기 쉽습니다.

## 1. UI가 소유하지 않는 상태를 수정하지 않는다

UI는 입력을 전달하고 결과를 표시합니다. HP, 재화, 퀘스트 상태처럼 게임 규칙에 속하는 값은 모델 또는 시스템 계층에서 바꾸고, UI는 변경 이벤트를 받아 그리기만 합니다.

```csharp
public sealed class PlayerWallet
{
    public event Action<int> OnGoldChanged;

    public int Gold { get; private set; }

    public void AddGold(int amount)
    {
        if (amount <= 0)
            return;

        Gold += amount;
        OnGoldChanged?.Invoke(Gold);
    }
}
```

## 2. 구독과 해제를 같은 생명주기에 둔다

`OnEnable`에서 구독했다면 `OnDisable`에서 해제합니다. 오브젝트 풀을 사용하는 UI라면 특히 중요합니다. 비활성 상태의 위젯이 이벤트를 받아 갱신되거나, 이미 반환된 객체가 콜백을 유지하는 문제를 막을 수 있습니다.

```csharp
private void OnEnable()
{
    _wallet.OnGoldChanged += Refresh;
    Refresh(_wallet.Gold);
}

private void OnDisable()
{
    _wallet.OnGoldChanged -= Refresh;
}
```

## 3. 이벤트도 비용이 든다

짧은 시간에 많은 변경이 발생할 수 있는 값은 매번 즉시 화면을 갱신하는 대신, 마지막 값만 반영하도록 묶는 전략이 더 적합할 수 있습니다. UI의 중요도와 변경 빈도를 기준으로 갱신 정책을 다르게 가져가면 됩니다.

> 핵심은 "이벤트를 쓰는가"보다 **어떤 상태 변화가 어떤 UI 갱신으로 이어지는지 추적 가능한가**입니다.
