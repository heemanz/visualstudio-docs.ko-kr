---
title: 워크플로 디자이너-규칙 조건 편집기 대화 상자 (레거시)
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords:
- Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f723894f175cbf031c3a2ac61ed9eaec8e1c94f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>규칙 조건 편집기 대화 상자(레거시)

이 항목에서는 설명 방법을 사용 하 여는 **규칙 조건 편집기** 레거시 Windows 워크플로 디자이너의 대화 상자. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

만들고 사용 하 여 선언적 규칙 조건 수정 된 **규칙 조건 편집기** 대화 상자. 이러한 규칙 조건은 기본적으로 제공되는 다음과 같은 Windows Workflow Foundation 활동에 대한 속성으로 나타납니다.

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

액세스는 **규칙 조건 편집기** 를 사용 하 여 대화 상자는 [조건 선택 대화 상자 (레거시)](../workflow-designer/select-condition-dialog-box-legacy.md)합니다.

다음 표에 사용자 인터페이스 (UI) 요소는 **규칙 조건 편집기** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**조건:**|규칙 조건을 위한 식을 입력합니다.|
|**그래**|규칙 조건을 저장하려면 클릭합니다.|

## <a name="entering-condition-expressions"></a>조건식 입력

조건식은 텍스트로 입력합니다. 입력할 수 **이 있습니다.** 필드, 속성 및 워크플로에 사용 되는 메서드를 참조 하는 편집기에 IntelliSense 형식의 메뉴를 사용 하 여 합니다. 또는 워크플로 멤버 이름을 직접 입력할 수도 있습니다. AND, OR, NOT 등의 논리 연산자를 조건에 추가할 수 있습니다. 조건자를 추가할 수도 있습니다. 조건자는 이항 연산자 한 개와 피연산자 두 개로 이루어집니다. 지원 되는 이항 연산자는 **==**, **>**, **\<**, **>=**, 및 **<=** 합니다. 지원되는 피연산자는 상수 값, 산술 함수 및 범위 Public 멤버입니다.

비교 형식을 지정할 수 있습니다 및를 비교할 수 **null** 또는 빈 문자열입니다. `this.Address.State == "WA"`와 같이 복합 형식을 포함하는 변수에서 멤버에 대한 중첩 호출을 수행할 수 있습니다.

규칙 조건 편집기는 다음과 같은 연산자를 지원합니다.

-   관계형 연산자: ==, =, !=

-   비교 연산자: <, \<=, >, > =

-   산술 연산자: +,-, \*, /, MOD

-   논리 연산자: 및, & &, OR, &#124; &#124;, NOT,!

-   비트 연산자: &,&#124;

식 연산자 우선 순위는 C# 연산자 우선 순위 규칙을 따릅니다.

규칙 조건 편집기는 다음과 같은 숫자 식을 지원합니다.

this.i == 1D(1.0으로 해석됨)

this.i == 1E1(10.0으로 해석됨)

this.i == 1L(long 형식으로 해석됨)

this.i == 1M(10진수로 해석됨)

this.i == 1F(single 형식으로 해석됨)

this.i == 1U(unsigned int 형식으로 해석됨)

조건에 대 한 자세한 내용은 참조 [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)합니다.

## <a name="see-also"></a>참고자료

- [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)
- [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)
- [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)
- [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)
- [조건 선택 대화 상자(레거시)](../workflow-designer/select-condition-dialog-box-legacy.md)
- [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)
- [Windows Workflow Foundation용 레거시 디자이너 UI 도움말](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)