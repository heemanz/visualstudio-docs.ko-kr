---
title: IDebugDocumentHelper::AddDeferredText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugDocumentHelper.AddDeferredText
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::AddDeferredText
ms.assetid: 9463cfb0-76cc-45ee-b32c-f37dce2b2e0e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c92909874429075bebc6a1f0a252573d049584e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugdocumenthelperadddeferredtext"></a>IDebugDocumentHelper::AddDeferredText
지정된 된 텍스트를 사용할 수 있지만 문자를 제공 하지 않으며 도우미를에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddDeferredText(  
   ULONG  cChars,  
   DWORD  dwTextStartCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cChars`  
 [in] 추가할 (유니코드) 문자의 수입니다.  
  
 `dwTextStartCookie`  
 [in] 텍스트의 시작 위치를 나타내는 호스트 정의 쿠키입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|메서드가 실패 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드를 연기할 정확한 알림 및 크기 정보를 생성 하는 도우미를 허용 하면서 현재 필요할 때까지 추가 하는 문자를 제공 하는 호스트 수 있습니다. `dwTextStartCookie` 매개 변수는 텍스트의 시작 위치를 나타내는 호스트에 의해 정의 된 쿠키입니다. 에 대 한 후속 호출 `IDebugDocumentText::GetText` 이 쿠키를 제공 해야 합니다. 예를 들어 DBCS에 텍스트를 나타내는 호스트에서 쿠키 바이트 오프셋 수 있습니다.  
  
 있다고 가정를 한 번 호출 `IDebugDocumentText::GetText` 문자에 대 한 여러 호출 로부터 얻을 수 `AddDeferredText`합니다. 도우미 클래스 지연 된 문자의 동일한 범위에 대 한 두 번 이상 요청 될 수 있습니다.  
  
> [!NOTE]
>  에 대 한 호출이 `AddDeferredText` 호출 하 여 혼합 `AddUnicodeText` 또는 `AddDBCSText`합니다. 이 경우 `E_FAIL` 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentText::GetText](../../winscript/reference/idebugdocumenttext-gettext.md)