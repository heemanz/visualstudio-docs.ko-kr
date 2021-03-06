---
title: 출력 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acaf2271357cb33cfaadbe9da653a8f57bd5627d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="output"></a>출력
**Output** 옵션은 성능 세션에 대한 프로파일링 데이터 파일의 이름을 지정합니다. **Output**은 **Start** 옵션과 함께 사용되어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `FileName`  
 데이터 파일의 이름입니다. 전체 및 부분 경로를 사용할 수 있습니다. 경로가 지정되지 않은 경우 파일이 현재 디렉터리에 만들어집니다.  
  
## <a name="required-options"></a>필수 옵션  
 **Output** 옵션은 **Start** 옵션과 함께 사용되어야 합니다.  
  
 **Start:** `Method`  
 출력 파일 이름을 지정합니다.  
  
## <a name="example"></a>예  
 다음 예제에서 프로파일링 데이터 파일은 현재 디렉터리에 만들어집니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)