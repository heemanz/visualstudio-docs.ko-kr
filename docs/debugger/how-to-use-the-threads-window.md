---
title: 다중 스레드 응용 프로그램 디버깅
description: 스레드 창 및 디버그 위치 도구 모음을 사용 하 여 Visual Studio에서 디버깅
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: adfbe002-3d7b-42a9-b42a-5ac0903dfc25
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 37a9161011031c53ed16a9ab0918eb498f5fa270
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-debug-a-multithreaded-application-in-visual-studio-using-the-threads-window"></a>연습: 스레드 창을 사용 하 여 Visual Studio에서 다중 스레드 응용 프로그램 디버깅
Visual Studio에서 제공 된 **스레드** 창 및 기타 사용자 인터페이스 요소 다중 스레드 응용 프로그램을 디버그할 수 있도록 합니다. 사용 하는 방법을 보여 주는이 자습서는 **스레드** 창 및 **디버그 위치** 도구 모음입니다. 다른 도구에 대 한 자세한 내용은 참조 [다중 스레드 응용 프로그램 디버깅을 시작 하려면](../debugger/get-started-debugging-multithreaded-apps.md)합니다. 이 자습서에서는 몇 분 정도 걸리지만 완료에 익숙해질 수 다중 스레드 응용 프로그램 디버깅을 위한 기능입니다.   
  
이 자습서를 시작 하려면 다중 스레드 응용 프로그램 프로젝트를 해야 합니다. 여기에 나열된 단계에 따라 프로젝트를 만드십시오.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>다중 스레드 응용 프로그램 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로** 클릭 하 고 **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  에 **프로젝트 형식**s 상자에서 원하는 언어 클릭: **Visual Basic**, **Visual C#**, 또는 **Visual c + +** 합니다.  
  
3.  에 **템플릿** 상자 **콘솔 응용 프로그램**합니다.  
  
4.  에 **이름** 상자에 mythreadwalkthroughapp 라는 이름을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
     새 콘솔 프로젝트가 나타납니다. 프로젝트가 만들어지면 소스 파일이 나타납니다. 선택한 언어에 따라 소스 파일 이름이 Module1.vb, Program.cs 또는 MyThreadWalkthroughApp.cpp일 수 있습니다.  
  
6.  소스 파일에 표시 되는 코드를 삭제 하 고 항목의 "스레드 만들기" 섹션에 표시 되는 예제 코드와 함께 교체 [스레드 만들기 및 시작 시 데이터 전달](/dotnet/standard/threading/creating-threads-and-passing-data-at-start-time)합니다.  
  
7.  에 **파일** 메뉴를 클릭 하 여 **모두 저장**합니다.  
  
#### <a name="to-begin-the-tutorial"></a>자습서를 시작 하려면  
  
-   소스 코드 편집기에서 다음 코드를 찾습니다.  
  
    ```VB  
    Thread.Sleep(3000)   
    Console.WriteLine()
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
  
#### <a name="to-start-debugging"></a>디버깅을 시작하려면  
  
1.  왼쪽된 여백에서 클릭는 `Console.WriteLine` 새 중단점을 삽입 하는 문입니다.  
  
     소스 코드 편집기의 왼쪽 여백에 빨간색 원이 나타납니다. 이 공은 이 위치에 중단점이 설정되었음을 나타냅니다.  
  
2.  에 **디버그** 메뉴를 클릭 하 여 **디버깅 시작** (**F5**).  
  
     디버깅을 시작하면 콘솔 응용 프로그램이 실행되다가 중단점에서 중지됩니다.  
  
3.  이때 콘솔 응용 프로그램 창에 포커스가 있으면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 창을 클릭하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]로 포커스를 되돌립니다.  
  
4.  소스 코드 편집기에서 다음 코드를 포함 하는 줄을 찾습니다.  
  
    ```VB  
    Thread.Sleep(5000)   
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```
  
#### <a name="to-discover-the-thread-marker"></a>스레드 마커를 찾으려면  

1.  디버그 도구 모음에서을 클릭는 **소스의 스레드 표시** 단추 ![소스의 스레드 표시](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker")합니다. 
  
2.  창 왼쪽의 여백을 확인합니다. 이 줄에 표시 됩니다는 *스레드 마커* 아이콘 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker") 두 가닥의 실 유사한 합니다. 스레드 마커는 이 위치에서 스레드가 중지되었음을 나타냅니다.  
  
3.  스레드 마커에 포인터를 올려 놓습니다. DataTips가 나타납니다. DataTip을 통해 중지된 각 스레드의 이름과 스레드 ID 번호를 알 수 있습니다. 이 경우 이름이 `<noname>`인 스레드 한 개만 있습니다.  

    > [!TIP]
    > 이름이 없는 스레드 이름을 식별 하는 것이 유용할 수 있습니다. 스레드 창에 선택 **이름 바꾸기** 마우스 오른쪽 단추로 클릭 한 후의 **이름** 스레드 행의 열입니다.
  
4.  바로 가기 메뉴에서 사용할 수 있는 옵션을 보려면 스레드 마커를 마우스 오른쪽 단추로 클릭 합니다. 
    
  
## <a name="flagging-and-unflagging-threads"></a>스레드에 플래그 지정 및 해제  
특별 한 주의가 스레드에 플래그를 설정할 수 있습니다. 스레드에 플래그를 지정 하는 것이 중요 한 스레드를 추적 하 고에 대 한 중요 하지 않은 스레드를 무시 하도록 좋습니다.  
  
#### <a name="to-flag-threads"></a>스레드에 플래그를 지정하려면   

1.  **보기** 메뉴에서 **도구 모음**합니다.  
  
    다음 사항을 확인는 **디버그 위치** 도구 모음이 선택 되어 있습니다.

2.  이동 하는 **디버그 위치** 도구 모음을 클릭은 **스레드** 목록입니다.  
  
    > [!NOTE]
    >  세 가지 중요 한 목록을 통해이 도구 모음을 인식할 수 있습니다: **프로세스**, **스레드**, 및 **스택 프레임**합니다.  
  
3.  목록에 나타나는 스레드 수를 확인합니다.  
  
4.  스레드 마커를 마우스 오른쪽 단추로 클릭 하 고 소스 코드 편집기로 돌아갈 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker") 다시 합니다.  
  
5.  바로 가기 메뉴를 가리키고 **플래그**, 다음 스레드 이름과 ID 번호를 클릭 합니다.  
  
6.  로 돌아가서 **디버그 위치** 도구 모음 및 찾기는 **플래그가 지정 된 스레드만 표시** 아이콘 ![플래그가 지정 된 스레드 표시](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker") 에 오른쪽은 **스레드** 목록입니다.  
  
    플래그 아이콘 단추를 하기 전에 흐리게 표시 됩니다. 이제, 활성 단추입니다.  
  
7.  클릭는 **플래그가 지정 된 스레드만 표시** 아이콘입니다.  
  
    플래그가 지정된 스레드만 목록에 나타납니다. (단일 플래그 단추를 클릭할 수 있는 **모든 스레드 표시** 모드입니다.)

8. 선택 하 여 스레드 창을 열려면 **디버그 > Windows > 스레드**합니다.

    ![스레드 창](../debugger/media/dbg-threads-window.png "ThreadsWindow")  
  
    에 **스레드** 창에서 플래그가 지정 된 스레드에 중요 한 빨간색 플래그 아이콘이 연결 되어 있습니다.

    > [!TIP]
    > 일부 스레드 플래그 때 코드 편집기에서 코드의 줄을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **실행 플래그가 지정 된 스레드를 커서까지** (스레드를 플래그 지정 하는 코드에 도달 하면 선택 하 고 있는지 확인). 이것은 선택된 된 코드를 더 쉽게 실행 하 여 순서를 제어할 수 있으므로 줄에 있는 스레드를 일시 중지 [스레드 중지 및 재개](#bkmk_freeze)합니다.
  
11. 소스 코드 편집기에서 스레드 마커 오른쪽 단추로 다시 클릭 합니다.  
  
     바로 가기 메뉴에서 선택할 수 있는 항목을 확인합니다. 대신 **플래그**, 지금은 참조 **플래그 해제**합니다. 클릭 하지 마십시오 **플래그 해제**합니다.  

     스레드의 플래그를 해제 하는 방법을 알아보려면 다음 절차로 이동 합니다.  
  
#### <a name="to-unflag-threads"></a>스레드의 플래그를 해제하려면  
  
1.  에 **스레드** 창에서 플래그가 지정 된 스레드에 해당 하는 줄을 마우스 오른쪽 단추로 클릭 합니다.  
  
     바로 가기 메뉴가 표시됩니다. 옵션이 있습니다 **플래그 해제** 및 **모든 스레드 플래그 해제**합니다.  
  
2.  스레드의 플래그를 해제 하려면 **플래그 해제**합니다.  

    확인 된 **디버그 위치** 다시 도구 모음. **플래그가 지정 된 스레드만 표시** 단추가 다시 희미해 집니다. 플래그가 지정된 스레드의 플래그만 해제됩니다. 있기 때문에 플래그가 지정 된 스레드가 없는, 도구 모음 모음은 다시 **모든 스레드 표시** 모드입니다. 클릭는 **스레드** 나열 하 고 모든 스레드를 볼 수 있는지 확인 합니다.  
  
5.  로 돌아가기는 **스레드** 창 정보 열을 검사 합니다.  
  
    첫 번째 열에 스레드 목록의 각 행에 플래그 윤곽선 아이콘으로를 바뀝니다. (윤곽선 것 스레드가 플래그가 지정 된입니다.)  
  
6.  두 스레드, 두 번째 및 세 번째 목록 아래쪽에서 플래그 윤곽선 아이콘을 클릭 합니다. 

    플래그 아이콘은 빈 윤곽선 대신 빨간색으로 변합니다.  
  
7.  플래그 열 맨 위의 단추를 클릭합니다.  
  
    단추를 클릭하면 스레드 목록의 순서가 변경됩니다. 스레드 목록은 플래그가 지정된 스레드가 맨 위에 오도록 정렬됩니다.  
  
8.  플래그 열 맨 위의 단추를 다시 클릭합니다.  
  
    정렬 순서가 다시 변경됩니다.  
  
## <a name="more-about-the-threads-window"></a>스레드 창에 대한 추가 정보  
  
#### <a name="to-learn-more-about-the-threads-window"></a>스레드 창에 대해 자세히 알아 보려면  
  
1.  에 **스레드** 창 왼쪽에서 세 번째 열을 확인 합니다. 이 열의 맨 위에 있는 단추가 표시 **ID**합니다.  
  
2.  클릭 **ID**합니다.  
  
     스레드 목록이 스레드 ID 번호순으로 정렬됩니다.  
  
3.  목록의 스레드를 마우스 오른쪽 단추로 클릭합니다. 바로 가기 메뉴를 클릭 **16 진수 표시**합니다.  
  
     스레드 ID 번호 형식이 변경됩니다.  
  
4.  마우스 포인터를 올려는 **위치** 목록의 모든 스레드에 대 한 열입니다.  
  
     잠시 후 DataTip이 나타납니다. 여기에 스레드의 부분 호출 스택이 표시됩니다.

     > [!TIP]
     > 스레드에 대 한 호출 스택의 그래픽 보기를 열고는 [병렬 스택](../debugger/using-the-parallel-stacks-window.md) 창 (디버깅 하는 동안 선택 **디버그 / Windows / 병렬 스택**).  
  
5.  레이블이 있는 왼쪽에서 네 번째 열을 확인 **범주**합니다. 스레드가 범주로 분류되어 있습니다.  
  
     프로세스에서 만든 첫째 스레드를 주 스레드라고 합니다. 스레드 목록에서 주 스레드를 찾습니다.  
  
6.  주 스레드를 마우스 오른쪽 단추로 누른 **스레드로 전환**합니다.  
  
     A **중단 모드** 창이 나타납니다. 디버거가 현재 (있기 때문에 주 스레드)를 표시할 수 있는 모든 코드 실행 하 고 아닌가 알려 줍니다.   
  
7.  확인 된 **호출 스택** 창 및 **디버그 위치** 도구 모음입니다.  
  
     콘텐츠는 **호출 스택** 창 변경 되었습니다. 

## <a name="bkmk_freeze"></a> 중지 및 재개 스레드 실행 

고정 및 고정 해제 수 (일시 중단 및 다시 시작) 스레드 작업을 수행 하는 순서를 제어 하는 스레드입니다. 이 교착 상태 같은 동시성 문제를 해결 하 고 경합 조건을 수 있습니다.

> [!TIP]
> (또한 일반적인 디버깅 시나리오) 다른 스레드를 고정 하지 않고 단일 스레드를 따라, 참조 하려는 경우 [다중 스레드 응용 프로그램 디버깅을 시작 하려면](../debugger/get-started-debugging-multithreaded-apps.md#bkmk_follow_a_thread)합니다.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>스레드를 중지 및 해제하려면  
  
1.  에 **스레드** 창에서 스레드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **고정**합니다.  
  
2.  두 번째 열 (현재 스레드 열)을 확인 합니다. 일시 중지 아이콘 이제 있습니다 나타납니다. 이러한 일시 중지 아이콘은 스레드가 중지 되었음을 나타냅니다.  
  
3.  표시는 **일시 중단 횟수** 열에서 선택 하 고 **열** 목록.

    스레드의 일시 중단 횟수가 1입니다.  
  
4.  중지 된 스레드를 마우스 오른쪽 단추로 누른 **재개**합니다.  
  
     현재 스레드 열 및 **일시 중단 횟수** 열 변경 합니다. 
  
## <a name="switching-the-to-another-thread"></a>전환의 다른 스레드를 
  
#### <a name="to-switch-threads"></a>스레드를 전환하려면  
  
1.  에 **스레드** 창 (현재 스레드 열) 왼쪽에서 두 번째 열을 확인 합니다. 이 열의 맨 위에 있는 단추에는 텍스트나 아이콘이 없습니다.
  
2.  현재 스레드 열와 스레드 하나에 있는 노란색 화살표를 확인 하십시오. 노란색 화살표는이 스레드는 현재 스레드 (이것이 실행 포인터의 현재 위치) 임을 나타냅니다.
  
    현재 스레드 아이콘 나타나는 스레드 ID 번호를 메모를 확인 합니다. 현재 스레드 아이콘을 다른 스레드로 이동 합니다 있지만 끝나면 다시 전환 해야 합니다. 
  
3.  다른 스레드를 마우스 오른쪽 단추로 누른 **스레드로 전환**합니다.  
  
4.  확인 된 **호출 스택** 소스 코드 편집기 창입니다. 내용이 변경되었습니다.  
  
5.  확인 된 **디버그 위치** 도구 모음입니다. 현재 스레드 아이콘을 너무, 변경 되었습니다.  
  
6.  이동 하 여 **디버그 위치** 도구 모음입니다. 선택에서 다른 스레드는 **스레드** 목록입니다.  
  
7.  확인 된 **스레드** 창. 현재 스레드 아이콘 변경 되었습니다.  
  
8. 소스 코드 편집기에서 스레드 마커를 마우스 오른쪽 단추로 클릭 합니다. 바로 가기 메뉴를 가리키고 **스레드로 전환** 스레드 이름과 ID 번호를 클릭 합니다.  
  
     현재 스레드 아이콘을 다른 스레드로 변경 하는 방법을 살펴 보았습니다:를 사용 하는 **스레드** 창은 **스레드** 목록에 **디버그 위치** 도구 모음 및 소스 코드 편집기에서 스레드 표식입니다.  
  
     스레드 마커 특정 위치에 있는 중지 된 스레드로만에 전환할 수 있습니다. 사용 하 여는 **스레드** 창 및 **디버그 위치** 도구 모음에서 임의의 스레드로 전환할 수 있습니다.   
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [방법: 디버그 중 다른 스레드로 전환](../debugger/how-to-switch-to-another-thread-while-debugging.md)
