---
title: 필드 m_children | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e71bc592e77daac877b571b14acd2d62a8657b9f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="mchildren-field"></a>m_children 필드
이 작업을 통해 등록 된 자식 작업의 목록입니다.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **어셈블리:** (mscorlib.dll)에 mscorlib  
  
 .NET Framework에서이 내부 멤버에 액세스할 수 없으므로, 다음 구문은 공통 중간 언어 (CIL) 제공 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>설명  
 작업이 실행 되는 동안 작업을 실행 하는 스레드가이 배열을 액세스 해야 합니다.  
  
 작업이 완료 되는 경우에 다른 스레드에서 아무것도 추가 또는에서 모든 항목을 제거 하지 않으면이 필드에 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ContingentProperties 클래스](../../extensibility/debugger/contingentproperties-class-internal-members.md)