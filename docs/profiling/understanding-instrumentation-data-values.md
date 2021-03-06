---
title: 계측 데이터 값 이해 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation
- instrumentation profiling method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec882cc5797eb99370beac5e28b87ca0b981cf2a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="understanding-instrumentation-data-values"></a>계측 데이터 값 이해

Visual Studio의 ‘계측’ 프로파일링 방법은 함수 호출, 줄 및 프로파일링된 응용 프로그램의 명령에 대해 자세한 타이밍 정보를 기록합니다.

계측 메서드는 프로파일링된 바이너리에서 대상 함수의 시작 및 끝 부분에 코드를 삽입하고 다른 함수들에 대한 이러한 함수의 각 호출 이전 및 다음 위치에 코드를 삽입합니다. 주입되는 코드는 다음 항목을 기록합니다.

- 이 수집 이벤트와 이전 수집 이벤트 사이의 간격

- 운영 체제가 간격 중에 작업을 수행했는지 여부. 운영 체제가 디스크 읽기/쓰기를 수행했거나 다른 프로세스에서 대상 스레드와 다른 프로세스 간을 전환한 경우를 예로 들 수 있습니다.

프로파일러 분석에서는 각 간격에 대해 간격 끝에 있었던 호출 스택을 재생성합니다. 호출 스택은 특정 시점에 프로세서에서 활성 상태였던 함수의 목록입니다. 하나의 함수(현재 함수)만이 코드를 실행하고 있으며, 다른 함수는 현재 함수를 호출한 함수 호출 체인(호출 스택)입니다.

호출 스택의 각 함수에 대해 간격을 기록할 때 프로파일러 분석에서는 함수의 4개 데이터 값 중 하나 이상에 간격을 추가합니다. 이때 다음의 두 기준에 따라 데이터 값에 간격을 추가합니다.

- 해당 함수 또는 *자식 함수*(해당 함수가 호출한 함수)의 코드에서 간격이 발생했는지 여부

- 간격에서 운영 체제 이벤트가 발생했는지 여부

함수 또는 데이터 범위의 간격에 대한 데이터 값의 이름은 *경과된 포괄 시간*, *경과된 전용 시간*, *응용 프로그램 포괄 시간* 및 *응용 프로그램 전용 시간*입니다.

- 함수의 모든 간격은 경과된 포괄 시간 데이터 값에 추가됩니다.

- 자식 함수가 아닌 함수의 코드에서 발생한 간격은 함수의 경과된 전용 시간 데이터 값에 추가됩니다.

- 간격에서 운영 체제 이벤트가 발생하지 않은 경우 간격은 응용 프로그램 포괄 시간 데이터 값에 추가됩니다.

- 간격에서 운영 체제 이벤트가 발생하지 않았으며 자식 이벤트에서가 아니라 함수 코드의 직접 실행에서 간격이 발생한 경우 간격은 응용 프로그램 전용 시간 데이터 값에 추가됩니다.

프로파일링 도구 보고서에는 프로파일링 세션 자체와 세션의 프로세스/스레드/이진 파일에 있는 함수의 총 값이 집계되어 표시됩니다.

## <a name="elapsed-inclusive-values"></a>경과된 포괄 시간값

함수 및 해당 자식 함수를 실행하는 데 소요된 총 시간입니다.

경과된 포괄 시간값에는 함수 코드를 직접 실행하는 데 소요된 간격과 대상 함수의 자식 함수를 실행하는 데 소요된 간격이 포함됩니다. 운영 체제 대기를 포함하는 함수 또는 해당 자식 함수의 간격도 경과된 포괄 시간값에 포함됩니다.

## <a name="elapsed-exclusive-values"></a>경과된 전용 시간 값

자식 함수에서 소요된 시간을 제외하고 함수를 실행하는 데 소요된 시간입니다.

경과된 전용 시간 값에는 간격에서 운영 체제 이벤트가 발생했는지 여부에 관계없이 함수 코드를 직접 실행하는 데 소요된 간격이 포함됩니다. 대상 함수가 호출한 자식 함수에서 소요된 모든 간격은 경과된 전용 시간 값에 포함되지 않습니다.

## <a name="application-inclusive-values"></a>응용 프로그램 포괄 시간 값

운영 체제 이벤트에서 소요된 시간을 제외하고 함수 및 해당 자식 함수를 실행하는 데 소요된 시간입니다.

응용 프로그램 포괄 시간 값에는 운영 체제 이벤트를 포함 하는 간격이 포함되지 않습니다. 응용 프로그램 포괄 시간 값에는 간격이 함수 코드를 직접 실행하는 데 소요되었는지 아니면 대상 함수의 자식 함수에서 소요되었는지에 관계없이 함수를 실행하는 데 소요된 기타 모든 간격이 포함됩니다.

## <a name="application-exclusive-values"></a>응용 프로그램 전용 시간 값

자식 함수에서 소요된 시간과 운영 체제 이벤트에서 소요된 시간을 제외하고 함수를 실행하는 데 소요된 시간입니다.

응용 프로그램 전용 시간 값에는 운영 체제 이벤트가 포함된 간격이나 함수가 호출한 함수를 실행하는 데 소요된 간격은 포함되지 않습니다. 함수 코드를 직접 실행하는 데 소요되었으며 운영 체제 이벤트를 포함하지 않는 간격만 응용 프로그램 전용 시간 값에 포함됩니다.

## <a name="elapsed-inclusive-percent"></a>경과된 포괄 시간 백분율

함수, 모듈, 스레드 또는 프로세스의 경과된 포괄 시간값인 프로파일링 세션의 총 경과된 포괄 시간값 백분율입니다.

100 * 함수 경과된 포괄 시간/세션 경과된 포괄 시간

## <a name="elapsed-exclusive-percent"></a>경과된 전용 시간 백분율

함수, 모듈, 스레드 또는 프로세스의 경과된 전용 시간값인 프로파일링 세션의 총 경과된 포괄 시간값 백분율입니다.

100 * 함수 경과된 전용 시간/세션 경과된 포괄 시간

## <a name="application-inclusive-percent"></a>응용 프로그램 포괄 시간 백분율

함수, 모듈, 스레드 또는 프로세스의 응용 프로그램 포괄 시간 값인 프로파일링 세션의 총 응용 프로그램 포괄 시간 값 백분율입니다.

100 * 함수 응용 프로그램 포괄 시간/세션 응용 프로그램 포괄 시간

## <a name="application-exclusive-percent"></a>응용 프로그램 전용 시간 백분율

함수, 모듈, 스레드 또는 프로세스의 응용 프로그램 전용 간격 값인 프로파일링 세션의 총 응용 프로그램 포괄 시간 값 백분율입니다.

100 * 함수 응용 프로그램 전용 시간/세션 응용 프로그램 포괄 시간

## <a name="see-also"></a>참고 항목

[성능 도구 데이터 분석](../profiling/analyzing-performance-tools-data.md)  
[방법: 수집 방법 선택](../profiling/how-to-choose-collection-methods.md)