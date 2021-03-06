---
title: 프로파일링의 새로운 기능 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec85de208c7761b69a73cc17a72bdb4a59fe6bb4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]에 포함된 프로파일링 도구의 새로운 기능
진단 도구에는 수정해야 하는 앱의 문제를 식별하는 데 사용할 수 있는 새로운 시각화가 포함되어 있습니다. 이제는 진단 도구에 ASP.NET 앱 지원이 포함됩니다.

자세한 내용은 [[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] 릴리스 정보](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag)를 참조하세요.

성능 분석을 위한 주요 영역을 중점적으로 확인할 수 있는 **요약** 탭이 도구에 추가되었습니다. 이 탭에서는 발생한 이벤트의 수를 확인하고, 힙의 스냅샷을 생성하고, CPU 사용량 데이터 수집을 빠르게 활성화할 수 있습니다. 이 뷰에는 모든 [Application Insights](https://azure.microsoft.com/en-us/documentation/articles/app-insights-visual-studio/) 또는 [UI 분석](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#UIAnalysis) 이벤트가 표시됩니다. 또한 Visual Studio Enterprise의 경우 이 뷰에는 IntelliTrace 이벤트도 표시됩니다.

![진단 도구 요약 탭](../profiling/media/DiagToolsSummaryTab-2.png "DiagToolsSummaryTab")

CPU 사용량 도구에는 성능 문제를 발생시킬 가능성이 가장 높은 기능을 식별하는 데 사용할 수 있는 [새로운 시각화](../profiling/Beginners-Guide-to-Performance-Profiling.md)가 포함되어 있습니다. 새로운 **호출자/호출 수신자** 뷰에서는 선택한 함수와의 함수 호출 비용을 조사할 수 있습니다.

![진단 도구 호출자/호출 수신자 뷰](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 프로파일링](../profiling/index.md)  
 [프로파일링 기능 둘러보기](../profiling/profiling-feature-tour.md)