---
title: Visual Studio의 디버거에서 디스어셈블리 코드를 보고 | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.disassembly
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- assembly language, debugging inline assembly code
- breakpoints, Disassembly window
- Disassembly window
- machine code
ms.assetid: eaf84dd0-c82d-481b-af51-690b74e7794c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46c0ae689a9d514983aeb747bebc6cb9905c6e11
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="view-disassembly-code-in-the-visual-studio-debugger"></a>Visual Studio 디버거에서 디스어셈블리 코드 보기
이 기능은 주소 수준 디버깅을 설정한 경우에 사용할 수는 **옵션** 대화 상자, **디버깅** 노드. 스크립트 또는 SQL 디버깅에는 사용할 수 없습니다.  
  
 **디스어셈블리** 창에는 컴파일러에서 만든 명령에 해당 하는 어셈블리 코드가 표시 합니다. 관리 코드를 디버깅하는 경우 이러한 어셈블리 명령은 Visual Studio 컴파일러에서 생성한 MSIL(Microsoft Intermediate Language)이 아닌 JIT(Just-in-Time) 컴파일러에서 만든 네이티브 코드에 대응합니다.  
  
 어셈블리 지침 뿐 아니라는 **디스어셈블리** 창에는 다음과 같은 선택적 정보도 표시할 수 있습니다.  
  
-   각 명령이 있는 메모리 주소, 네이티브 응용 프로그램의 경우 실제 메모리 주소, Visual Basic, C# 또는 관리 코드의 경우 함수 시작 부분으로부터의 오프셋  
  
-   어셈블리 코드가 파생된 소스 코드  
  
-   코드 바이트(실제 컴퓨터 또는 MSIL 명령의 바이트 표시)  
  
-   메모리 주소의 기호 이름  
  
-   소스 코드에 해당하는 줄 번호  
  
 어셈블리 언어 명령은 명령 이름의 약어인 니모닉과 변수, 레지스터 및 상수를 나타내는 기호로 이루어집니다. 각 컴퓨터 언어 명령은 하나의 어셈블리 언어 니모닉으로 표시되며 그 뒤에는 보통 하나 이상의 변수, 레지스터 또는 상수가 옵니다.  
  
 어셈블리 언어를 읽을 수 없을 때 디스어셈블리 창을 최대한 활용하려면 어셈블리 언어 프로그래밍 관련 서적을 참조하십시오. 어셈블리 언어 프로그래밍은 디스어셈블리 창에 대한 이 간략한 소개의 범위를 벗어납니다.  
  
 어셈블리 코드는 프로세서 레지스터(관리 코드의 경우에는 공용 언어 런타임 레지스터)를 많이 사용하기 때문에 레지스터의 내용을 검사할 수 있는 레지스터 창과 함께 디스어셈블리 창을 사용하는 것이 좋습니다.  
  
 아마 컴퓨터 코드 명령을 어셈블리 언어가 아닌 원시 숫자 형식으로 보려는 사람은 없을 것입니다. 그러나 그렇게 하려면 용도에 따라 메모리 창을 사용하거나 디스어셈블리 창의 바로 가기 메뉴에서 코드 바이트를 선택할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-display-the-disassembly-window"></a>디스어셈블리 창을 표시하려면  
  
-   디버깅 하는 동안 선택 **디버그 > Windows** 클릭 하 고 **디스어셈블리**합니다.
  
### <a name="to-turn-optional-information-on-or-off"></a>선택적 정보 표시 여부를 선택하려면  
  
-   마우스 오른쪽 단추로 클릭는 **디스어셈블리** 창 고을 선택 하거나 바로 가기 메뉴에서 원하는 옵션의 선택을 취소 합니다.  
  
     왼쪽 여백의 노란색 화살표는 현재 실행 위치를 나타냅니다. 네이티브 코드에서는 이 화살표가 CPU의 프로그램 카운터에 해당합니다. 이 위치는 프로그램에서 다음에 실행될 명령을 나타냅니다.  
  
     자세한 내용은 참조 [페이지 위나 아래로 이동 메모리에](../debugger/how-to-page-up-or-down-in-memory.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [방법: 레지스터 창 사용](../debugger/how-to-use-the-registers-window.md)