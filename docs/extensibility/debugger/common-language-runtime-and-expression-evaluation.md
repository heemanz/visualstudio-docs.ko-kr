---
title: 공용 언어 런타임 및 식 평가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, and common language runtime
ms.assetid: b36c1eb5-1aaf-48a6-b287-ee7a273d2b1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 370b7963c71b74674c7d323a5fa1c2650d3f08d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="common-language-runtime-and-expression-evaluation"></a>공용 언어 런타임 및 식 평가
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 컴파일러, Visual Basic 및 C# (C 형 발음이), 공용 언어 런타임 (CLR)를 대상으로 하는 생성 언어 MSIL (Microsoft Intermediate), 이후 인와 같은 네이티브 코드로 컴파일됩니다. CLR (DE) 결과 코드를 디버깅 하려면 디버그 엔진을 제공 합니다. Visual Studio IDE에 소유 하는 프로그래밍 언어를 통합 하려는 경우에 MSIL로 컴파일하는 데 선택할 수 있으며 따라서 직접 DE 작성 않아도 됩니다. 그러나 선택한 프로그래밍 언어의 컨텍스트 내에서 식을 평가할 수 있는 식 계산기 (EE)를 작성 해야 합니다.  
  
## <a name="discussion"></a>토론  
 데이터 개체의 집합 및 조작 하는 데 사용 되는 연산자 집합을 생성 하기 위해 컴퓨터 언어 식이 일반적으로 구문 분석 합니다. 예를 들어 데이터에 더하기 연산자 (+)를 적용 하려면 분석할 수 있습니다 "A + B" 식 "A"와 "B" 다른 데이터 개체에 있기 때문에 개체입니다. 데이터 개체, 연산자 및 해당 연결의 전체 집합에는 트리 노드에 연산자 및 분기에서 데이터 개체와 함께 트리로 프로그램에서 가장 많이 표시 됩니다. 트리 형식으로 분류 되어 있는 식은 구문 분석 된 트리를 라고도 합니다.  
  
 식을 구문 분석 되 면 각 데이터 개체를 평가 하는 기호 공급자 (SP) 라고 합니다. 예를 들어, "A"는 모두 둘 이상의 메서드를 다음 질문에 정의 된 경우 "어떤 A?" A의 값을 조사할 수 있습니다 전에 응답 해야 합니다. SP에서 반환 된 응답은 "다섯 번째 스택 프레임에 세 번째 항목" 또는 "는 50 바이트 정적 메모리의 시작 부분을 초과 하는이 메서드를 할당 합니다."  
  
 자체 프로그램에 대 한 MSIL을 생성, 외에도 CLR 컴파일러는 프로그램 데이터베이스 (.pdb) 파일에 기록 되는 매우 자세히 디버깅 정보를 만들어 수도 있습니다. CLR의 SP를 소유 언어 컴파일러에서 생성 하는 동일한 형식으로 CLR 컴파일러에서 디버그 정보도 나오는 언어의 이름이 데이터 개체를 식별할 수 있습니다. 명명 된 데이터 개체를 식별 EE 바인더 개체를 해당 개체의 값을 보유 하는 메모리 영역에 데이터 개체 연결 (또는 바인딩)를 사용 합니다. 그런 다음는 DE 가져오거나 데이터 개체에 대 한 새 값을 설정할 수 있습니다.  
  
 전용 컴파일러 CLR를 호출 하 여 디버깅 정보를 제공할 수는 `ISymbolWriter` 인터페이스 (네임 스페이스에서.NET Framework에 정의 된 `System.Diagnostics.SymbolStore`). MSIL로 컴파일 하 고 이러한 인터페이스를 통해 디버그 정보를 작성, 전용 컴파일러 및 사용 하 여 CLR DE SP. 이 크게 간소화 됩니다. Visual Studio IDE에 소유 언어를 통합 합니다.  
  
 CLR DE 식을 계산 하는 소유 EE를 호출할 때는 DE EE를 SP, 바인더 개체 인터페이스를 제공 합니다. 작성 하는 CLR 기반 디버그 엔진 방법 즉, 적절 한 식 계산기 인터페이스를 구현 하는 데에 필요 바인딩 및 사용자에 대 한 처리 기호는 CLR을 담당 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)