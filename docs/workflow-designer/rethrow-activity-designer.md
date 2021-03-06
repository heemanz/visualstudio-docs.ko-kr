---
title: Rethrow 활동 디자이너-워크플로 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1d441724afa1cf481bc15e2a43e6ec744a951187
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="rethrow-activity-designer"></a>Rethrow 활동 디자이너

**다시 Throw** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Rethrow> 활동입니다.

## <a name="the-rethrow-activity"></a>Rethrow 활동
 <xref:System.Activities.Statements.Rethrow> 활동은 이전에 throw된 예외를 throw합니다. 이 활동은 <xref:System.Activities.Statements.Catch> 활동의 <xref:System.Activities.Statements.TryCatch> 처리기에서만 사용할 수 있습니다.

### <a name="using-the-rethrow-activity-designer"></a>ReThrow 활동 디자이너 사용
 **다시 Throw** 활동 디자이너에서 확인할 수 있습니다는 **의 오류 처리** 의 범주는 **도구 상자**, 클릭 하 여 액세스는 **도구 상자**워크플로 디자이너의 왼쪽에 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **다시 Throw** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 <xref:System.Activities.Statements.Rethrow> 기본값 활동 **DisplayName** 의 Throw 합니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **다시 Throw** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-rethrow-properties"></a>Rethrow 속성
 다음 표에서는 <xref:System.Activities.Statements.Rethrow> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Rethrow> 활동의 선택적 이름을 지정합니다. 기본값은 Rethrow입니다.|

## <a name="see-also"></a>참고자료

- [컬렉션](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)