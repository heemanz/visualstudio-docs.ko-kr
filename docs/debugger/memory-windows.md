---
title: "디버거에서 변수에 대 한 메모리를 보려면 | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.memory
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Memory window
- strings [Visual Studio], viewing
- debugger [Visual Studio], Memory window
- memory [Visual Studio], debugging
- debugging [Visual Studio], Memory window
- buffers, viewing
ms.assetid: 7f7a0439-10e4-4966-bb2d-51f04cda4fe2
caps.latest.revision: "32"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5c6f422e980a585b9cbac3c0b59ad8d981aba93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="use-the-memory-windows-in-the-visual-studio-debugger"></a>Visual Studio 디버거에서 메모리 창을 사용 하 여
**메모리** 창은 응용 프로그램에서 사용 되는 메모리 공간에 대 한 뷰를 제공 합니다. **조사식** 창 **간략 한 조사식** 대화 상자, **자동** 창 및 **지역** 창은 변수의 내용을 보여 줍니다. 메모리의 특정 위치에 저장 됩니다. 하지만 **메모리** 포괄적 창에 표시 합니다. 이 뷰는 다른 창들에는 잘 표시되지 않는 버퍼나 큰 문자열 등의 큰 데이터를 검사하는 데 편리합니다. 그러나는 **메모리** 창이 데이터의 표시에 제한 되지 않습니다. 메모리 창에는 메모리 공간의 할당되지 않은 메모리에 데이터, 코드 또는 임의 가비지 비트 중 어떤 내용이 있든 관계없이 메모리 공간의 모든 내용이 표시됩니다.  
  
 **메모리** 기간을 주소 수준 디버깅을 활성화 한 경우에 사용할 수는 **옵션** 대화 상자, **디버깅** 노드. **메모리** 기간은 메모리 개념을 인식 하지 못하는 언어인 SQL 또는 스크립트에 사용할 수 있습니다.  
  
## <a name="opening-a-memory-window"></a>메모리 창 열기  
  
#### <a name="to-open-a-memory-window"></a>메모리 창을 열려면  
  
1.  디버그 모드에 있지 않다면 디버깅을 시작합니다.  
  
2.  에 **디버그** 메뉴에서 **Windows**합니다. 가리킨 **메모리** 클릭 하 고 **메모리 1**, **메모리 2**, **메모리 3**, 또는 **메모리 4**합니다. (하위 수준 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하나 뿐 **메모리** 창. 이러한 버전 중 하나를 사용 하는 경우 클릭 하기만 **메모리**.)  
  
## <a name="paging-in-the-memory-window"></a>메모리 창의 페이징  
 **메모리** 창에는 일반적인 방식으로 작동 하는 세로 스크롤 막대입니다. 오늘날 사용되는 컴퓨터는 주소 공간이 매우 크므로 스크롤 막대의 엄지 단추를 임의의 위치로 드래그하면 현재 위치와 방향을 잃기 쉽습니다. 이러한 이유로 엄지 단추는 "스프링이 달려 있는 것처럼" 항상 스크롤 막대 중앙에 놓이게 됩니다. 네이티브 코드 응용 프로그램에서 페이지 위나 아래로는 이동할 수 있지만 자유롭게 스크롤할 수는 없습니다.  
  
 메모리 주소가 높을수록 창의 아래쪽에 나타납니다. 따라서 상위 주소를 확인하려면 위쪽이 아니라 아래쪽으로 스크롤합니다.  
  
#### <a name="to-page-up-or-down-in-memory"></a>메모리에서 페이지 위나 아래로 이동하려면  
  
1.  페이지 아래로 이동하려면(상위 메모리 주소로 이동) 세로 스크롤 막대의 엄지 단추 아래를 클릭합니다.  
  
2.  페이지 위로 이동하려면(하위 메모리 주소로 이동) 세로 스크롤 막대의 엄지 단추 위쪽을 클릭합니다.  
  
## <a name="selecting-a-memory-location"></a>메모리 위치 선택  
 메모리에서 선택한 위치로 즉시 이동 하려는 경우 그렇게 할 수 있습니다에서 값을 편집 하거나 끌어서 놓기 작업을 사용 하 여는 **주소** 상자입니다. **주소** 상자에는 사용할 숫자 값 뿐만 아니라 주소로 계산 되는 식입니다. 기본적으로는 **메모리** 창에서는 처리 하므로 **주소** 은 프로그램을 실행할 때 다시 평가 하는 라이브 식으로는 식입니다. 라이브 식을 사용하면 매우 편리합니다. 예를 들어 라이브 식을 사용하여 포인터가 있는 위치의 메모리를 확인할 수 있습니다.  
  
#### <a name="to-select-a-memory-location-by-dragging-and-dropping"></a>끌어서 놓기를 사용하여 메모리 위치를 선택하려면  
  
1.  임의의 창에서 메모리 주소가 포함된 메모리 주소 또는 포인터 변수를 선택합니다.  
  
2.  주소 또는 포인터를 끌어는 **메모리** 창.  
  
#### <a name="to-select-a-memory-location-by-editing"></a>편집하여 메모리 위치를 선택하려면  
  
1.  에 **메모리** 창의 선택 된 **주소** 상자 합니다.  
  
2.  입력 하거나 보고 한 다음 키를 눌러 하려는 주소를 붙여 넣습니다. **ENTER**합니다.  
  
## <a name="changing-the-way-the-memory-window-displays-information"></a>메모리 창의 정보 표시 방식 변경  
 방식을 사용자 지정할 수는 **메모리** 창에 메모리 내용이 표시 됩니다. 기본적으로 메모리 내용은 16진수 형식의 1바이트 정수로 표시되고 열 수는 창의 현재 너비에 따라 자동으로 지정됩니다.  
  
#### <a name="to-change-the-format-of-the-memory-contents"></a>메모리 내용의 형식을 변경하려면  
  
1.  마우스 오른쪽 단추로 클릭는 **메모리** 창.  
  
2.  원하는 형식을 선택합니다.  
  
#### <a name="to-change-the-number-of-columns-in-the-memory-window"></a>메모리 창에 표시된 열 수를 변경하려면  
  
1.  맨 위에 있는 도구 모음에는 **메모리** 창 찾습니다는 **열** 목록입니다.  
  
2.  에 **열** 목록에서 선택 표시 하거나 선택 하는 열 개수 **자동** 창의 너비에 맞게 자동으로 조정에 대 한 합니다.  
  
 내용을 않도록 하려는 경우는 **메모리** 실행 프로그램으로 변경 하는 창, 라이브 식 계산을 해제할 수 있습니다.  
  
#### <a name="to-toggle-live-evaluation"></a>라이브 계산을 설정/해제하려면  
  
1.  마우스 오른쪽 단추로 클릭는 **메모리** 창.  
  
2.  바로 가기 메뉴를 클릭 **자동으로 다시 계산**합니다.  
  
     라이브 계산이 설정되어 있는 경우 옵션이 선택된 상태이므로 옵션을 클릭하면 라이브 계산이 해제됩니다. 라이브 계산이 해제되어 있는 경우 옵션이 선택되지 않은 상태이므로 옵션을 클릭하면 라이브 계산이 설정됩니다.  
  
 맨 위에 있는 도구 모음을 표시 하거나 숨길 수 있습니다는 **메모리** 창. 도구 모음이 숨겨진 동안에는 주소 상자나 기타 도구에 액세스할 수 없습니다.  
  
#### <a name="to-toggle-the-toolbar"></a>도구 모음을 설정/해제하려면  
  
1.  마우스 오른쪽 단추로 클릭 한 **메모리** 창.  
  
2.  바로 가기 메뉴를 클릭 **도구 모음 표시**합니다.  
  
     도구 모음의 이전 상태에 따라 도구 모음이 나타나거나 없어집니다.  
  
## <a name="following-a-pointer-through-memory"></a>포인터가 가리키는 메모리 표시  
 네이티브 코드 응용 프로그램에서는 레지스터 이름을 라이브 식으로 사용할 수 있습니다. 예를 들어, 스택 포인터를 사용하여 스택을 따를 수 있습니다.  
  
#### <a name="to-follow-a-pointer-through-memory"></a>포인터가 가리키는 메모리를 표시하려면  
  
1.  에 **메모리** 창 **주소** 포인터 식을 입력 합니다. 포인터 변수는 현재 범위 안에 있어야 합니다. 사용하는 언어에 따라 포인터 변수를 역참조해야 할 수도 있습니다.  
  
2.  **ENTER** 키를 누릅니다.  
  
     이제 명령을 사용할 때 프로그램 실행와 같은 **단계**, 표시 되는 메모리 주소 포인터 변경 될 때 자동으로 변경 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)