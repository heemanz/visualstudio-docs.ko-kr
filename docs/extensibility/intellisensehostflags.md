---
title: IntelliSenseHostFlags | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a096e79a64168f74150103a5f3ba3a8683fe184e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
IntelliSense 호스트 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|멤버|설명|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|컨텍스트 버퍼는 읽기 전용입니다.|  
|`IHF_NOSEPARATESUBJECT`|제목 텍스트가 없습니다. IntelliSense 대상 컨텍스트 버퍼에 포함 (의미 `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|제목 텍스트는 다중 명령줄 수 없습니다.|  
|`IHF_FORCECOMMITTOCONTEXT`|`CanCommitIntoReadOnlyBuffer`와 동일합니다.|  
|`IHF_OVERTYPE`|(제목 또는 컨텍스트)에서 편집 겹쳐쓰기 모드에서 수행 되어야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop>