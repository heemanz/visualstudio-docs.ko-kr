---
title: '워크플로 디자이너-방법: 활동 디자이너 라이브러리 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d05ddb48e88627f4b7ab4112c164b5129ddba910
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-activity-designer-library"></a>방법: 활동 디자이너 라이브러리 만들기
사용자 지정 활동 디자이너를 사용하여 표준 또는 사용자 지정 활동을 위한 사용자 인터페이스를 만들 수 있습니다. 사용자 인터페이스의 복잡성을 조절하고 한 가지 활동에 대해 두 개 이상의 활동 디자이너를 만들 수 있습니다. 이 시나리오에서는 여러 대상에 맞게 조정한 디자이너를 만들 수 있습니다.

## <a name="to-create-an-activity-designer-library"></a>활동 디자이너 라이브러리를 만들려면

1.  Visual Studio 2010을 시작합니다.

2.  에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트** 열려는 **새 프로젝트** 대화 상자.

3.  에 **프로젝트 형식** 창 선택 **워크플로** 중 하 나와 **Visual C#** 또는 **Visual Basic** 사용자 기본 설정에 따라 그룹화 언어입니다.

4.  에 **템플릿** 창 선택 **활동 디자이너 라이브러리**합니다.

5.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

6.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

7.  에 **솔루션** 상자는 솔루션에 대 한 설명이 포함 된 이름을 입력 한 다음 클릭 **확인**합니다.

    > [!NOTE]
    > 기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가 하려는 경우 Visual Studio 2010에서 해당 솔루션을 열고, 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**를 선택 하 고 **추가**, 다음 **새 프로젝트** 열려는 **새 프로젝트** 대화 상자. 그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.

8.  프로젝트 템플릿이 XAML로 활동 디자이너 정의를 만들고 코드 숨김 구현 파일을 소스 코드로 만듭니다. Windows Workflow Designer가 열리고 활동 디자이너의 캔버스가 표시 됩니다.

9. 끌어서 Windows Presentation Foundation (WPF)에서 제어는 **도구 상자** 사용자 지정 활동 디자이너에서 사용 하 여 디자인 화면에 있습니다.  사용자 지정 활동 디자이너를 구현 하는 방법의 예제를 보려면 [하는 방법: 사용자 지정 활동 디자이너를 만드는](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer)합니다.

    > [!WARNING]
    > 기본.NET Framework 4activities 구문과 사용자 지정 활동에 대 한 사용자 지정 활동 디자이너를 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

- [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)