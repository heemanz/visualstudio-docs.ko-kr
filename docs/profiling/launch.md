---
title: Launch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c9fc350a3eaadd919f339a37843f37291ed6ff3
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="launch"></a>Launch
**Launch** 옵션은 샘플링 방법을 사용하여 프로파일러를 시작하고 지정된 응용 프로그램도 시작합니다.  
  
 **Launch** 옵션을 사용하려면 **Start** 옵션에서 **Sample** 메서드를 지정해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `AppName`  
 시작하려는 응용 프로그램의 이름입니다. 현재 디렉터리에서 전체 및 부분 경로를 사용할 수 있습니다.  
  
## <a name="valid-options"></a>유효한 옵션  
 다음 VSPerfCmd 옵션은 단일 명령줄에서 **Launch** 옵션과 함께 결합될 수 있습니다.  
  
 **Start:** `Method`  
 명령줄 프로파일러 세션을 초기화하고 지정된 프로파일링 방법을 설정합니다.  
  
 **GlobalOn** 및 **GlobalOff**  
 프로파일링을 다시 시작(**GlobalOn**)하거나 일시 중지(**GlobalOff**)하지만 프로파일링 세션을 종료하지 않습니다.  
  
 **ProcessOn:** `PID` 및 **ProcessOff**:`PID`  
 지정된 프로세스에 대한 프로파일링을 다시 시작(**ProcessOn**)하거나 일시 중지(**ProcessOff**)합니다.  
  
 **TargetCLR**  
 프로파일링 세션에 두 개 이상의 버전이 로드된 경우 프로파일링할 .NET Framework CLR(공용 언어 런타임) 버전을 지정합니다. 기본적으로 첫 번째 로드된 버전이 프로파일링됩니다.  
  
## <a name="exclusive-options"></a>전용 옵션  
 다음 옵션은 **Launch** 옵션에만 사용할 수 있습니다.  
  
 **콘솔**  
 새 창에서 지정된 명령줄 응용 프로그램을 시작합니다.  
  
 **Args:** `ArgList`  
 응용 프로그램에 전달할 인수의 목록을 지정합니다.  
  
 **LineOff**  
 줄 수준 프로파일링 데이터 수집을 비활성화합니다.  
  
## <a name="sampling-options"></a>샘플링 옵션  
 다음 샘플링 간격 옵션 중 하나를 **Launch** 명령줄에 지정할 수 있습니다. 기본 샘플링 간격은 10,000,000 프로세서 클록 주기입니다.  
  
 **Timer**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`]**Counter**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**할당**&#124;**수명**]  
 샘플링 간격의 종류와 수를 지정합니다.  
  
-   **Timer** - 모든 `Cycles` 무중단 프로세서 클록 주기를 샘플링합니다. `Cycles`를 지정하지 않은 경우 10,000,000 주기가 사용됩니다.  
  
-   **PF** - 모든 `Events` 페이지 폴트를 샘플링합니다. `Events`가 지정되지 않은 경우 10 페이지 폴트가 사용됩니다.  
  
-   **Sys** - 운영 체제에 대한 모든 `Events` 호출을 샘플링합니다. `Events`가 지정되지 않은 경우 10 시스템 호출이 사용됩니다.  
  
-   **Counter** - `Name`에서 지정된 CPU 성능 카운터의 모든 `Reload` 수를 샘플링합니다. 필요에 따라 `FriendlyName`은 프로파일러 보고서의 열 헤더로 사용할 문자열을 지정할 수 있습니다.  
  
-   **GC** - .NET 메모리 데이터를 수집합니다. 기본적으로(**allocation**) 모든 메모리 할당 이벤트에서 데이터가 수집됩니다. **lifetime** 매개변수가 지정되면 데이터는 각 가비지 컬렉션 이벤트에서도 수집됩니다.  
  
## <a name="example"></a>예  
 이 예제에서는 응용 프로그램을 시작하는 **Launch**의 사용을 보여 줍니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)