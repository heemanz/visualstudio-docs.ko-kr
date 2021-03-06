---
title: '워크플로 디자이너-방법: 정의 및 활동 대리자 사용'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 73bf61c845b0124a8350f61c161ded1cf0c80043
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-and-consume-activity-delegates-in-the-workflow-designer"></a>방법: 워크플로 디자이너에서 활동 대리자 정의 및 사용

에 대 한 새 기본 제공 디자이너를 포함 하는.NET framework 4.5는 <xref:System.Activities.Statements.InvokeDelegate> 활동입니다. 이 디자이너는 <xref:System.Activities.ActivityDelegate> 또는 <xref:System.Activities.ActivityAction> 같은 <xref:System.Activities.ActivityFunc%601>에서 파생되는 작업에 대리자를 할당하는 데 사용할 수 있습니다.

## <a name="define-an-activity-delegate"></a>작업 대리자 정의

1.  Visual Studio에서 선택 **파일**, **새로**, **프로젝트**합니다. 선택은 **워크플로** 왼쪽의 노드 및 **워크플로 콘솔 응용 프로그램** 오른쪽에 서식 파일입니다. 원하는 경우 프로젝트 이름을 지정 하 고 클릭 **확인**합니다.

2.  프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **추가**, **새 항목...** . 선택은 **워크플로** 왼쪽의 노드 및 **활동** 오른쪽에 서식 파일입니다. 새 활동 이름을 **MyForEach.xaml** 클릭 **확인**합니다. 워크플로 디자이너에서 활동이 열립니다.

3.  워크플로 디자이너에서 클릭 된 **인수** 탭 합니다.

4.  클릭 **인수 만들기**합니다. 새 인수의 이름을 **항목**합니다.

5.  에 **인수 형식이** 열에서 선택 **Array of [T]** 합니다.

6.  형식 브라우저에서 선택 **개체**합니다. Click **Ok**.

7.  클릭 **인수 만들기** 다시 합니다. 새 인수의 이름을 **본문**합니다. 에 **방향** 는 새 인수를 선택에 대 한 열 **속성**합니다.

8.  인수 형식 열에서 선택 **형식 찾아보기...**

9. 형식 브라우저에 입력 **ActivityAction** 에 **유형 이름** 필드입니다. 선택 **ActivityAction\<T >** 트리 보기에서 합니다. 선택 **개체** 유형을 할당할에 나타나는 드롭다운에 **ActivityAction\<개체 >** 인수에 있습니다.

10. 끌어서는 <xref:System.Activities.Statements.While> 활동을는 **제어 흐름** 디자이너 화면에 도구 상자의 섹션.

11. 선택 된 <xref:System.Activities.Statements.While> 활동과 선택은 **변수** 탭 합니다.

12. 선택 **변수를 만들고**합니다. 새 변수의 이름을 **인덱스**합니다.

13. 에 **변수 형식** 열에서 선택 **Int32**합니다. 둡니다는 **범위** 으로 **동안**, 및 **기본** 열은 비워 합니다.

14. 설정의 **조건** 의 속성은 <xref:System.Activities.Statements.While> 활동을 **인덱스 < Items.Length;** 합니다.

15. 끌어서는 <xref:System.Activities.Statements.InvokeDelegate> 에서 활동을는 **기본 형식** 에 도구 상자의 섹션은 **본문** 의 <xref:System.Activities.Statements.While> 활동입니다.

16. 선택 **본문** 대리자 드롭다운 목록에서 합니다.

17. 에 **속성** 에 대 한 표는 <xref:System.Activities.Statements.InvokeDelegate> 활동을 클릭는 **...**  단추는 **대리자 인수** 속성입니다.

18. 에 **값** 라는 인수의 열 **인수**, 입력 **Items [Index]** 합니다. 클릭 **확인** 를 닫으려면는 **DelegateArguments** 대화 상자.

19. <xref:System.Activities.Statements.Assign> 활동을 <xref:System.Activities.Statements.InvokeDelegate> 활동 아래의 가로선으로 끌어 놓습니다. <xref:System.Activities.Statements.Assign> 활동이 만들어져 및 <xref:System.Activities.Statements.Sequence> 활동에 두 개의 활동을 포함 하도록 자동으로 생성 됩니다는 **본문** 섹션은 **MyForEach** 활동입니다. 이후 시퀀스가 필요는 **본문** 섹션에는 단일 활동을 포함할 수 있습니다. 자동으로 새로 만드는 <xref:System.Activities.Statements.Sequence> 활동에는.NET Framework 4.5의 새로운 기능입니다.

20. 설정의 **를** 의 속성은 <xref:System.Activities.Statements.Assign> 활동을 **인덱스**합니다. 설정의 **값** 의 속성은 **할당** 활동을 **index + 1**합니다.

 사용자 지정 **MyForEach** 활동에는 임의의 활동을 통해 전달 되는 각 값에 대해 한 번씩 호출 이제는 **항목** 활동에 대 한 입력으로 컬렉션의 값을 사용 하 여 컬렉션입니다.

## <a name="use-the-custom-activity-in-a-workflow"></a>워크플로에서 사용자 지정 활동 사용

1.  키를 눌러 프로젝트를 빌드합니다 **Ctrl + Shift + B**합니다.

2.  **솔루션 탐색기**개방형 **Workflow1.xaml** 디자이너에서 합니다.

3.  끌어서는 **MyForEach** 도구 상자의 활동을 디자이너 화면입니다. 활동은 프로젝트와 같은 이름을 사용하여 도구 상자의 한 섹션에 있게 됩니다.

4.  설정의 **항목** 의 속성은 **MyForEach** 활동을 **새 Object {1, "abc"}** 합니다.

5.  끌어서는 <xref:System.Activities.Statements.WriteLine> 활동을는 **기본 형식** 에 도구 상자의 섹션은 **대리자: Body** 섹션은 **MyForEach** 활동입니다.

6.  설정의 **텍스트** 의 속성은 <xref:System.Activities.Statements.WriteLine> 활동을 **Argument.ToString()** 합니다.

워크플로가 실행 되는 콘솔에서 다음을 보여 줍니다.

**1**
**abc**