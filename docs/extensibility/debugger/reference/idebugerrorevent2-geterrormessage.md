---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4dffd06c7342b77f1e4293d50217a0c6a468bf18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
사람이 읽을 수 있는 오류 메시지 생성을 허용 하는 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMessageType`  
 [out] 값을 반환 된 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) 메시지의 형식을 설명 하는 열거형입니다.  
  
 `pbstrErrorFormat`  
 [out] 사용자에 게 마지막 메시지의 형식 (자세한 내용은 "주의"를 참조).  
  
 `hrErrorReason`  
 [out] 오류 코드는 메시지에 대 한입니다.  
  
 `pdwType`  
 [out] 오류의 심각도 (에 대 한 MB_XXX 상수를 사용 하 여 `MessageBox`등 `MB_EXCLAMATION` 또는 `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] 경로 도움말 파일 (도움말 파일이 없는 경우 null 값으로 설정 됨)입니다.  
  
 `pdwHelpId`  
 [out] (도움말 항목에 없는 경우 0으로 설정 됨)을 표시 하려면 도움말 항목의 ID입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 오류 메시지의 서식을 지정 하는 `"What I was doing.  %1"`합니다. `"%1"` 는 다음 오류 코드에서 파생 하 고 오류 메시지가 호출자에 의해 대체 됩니다 (반환 되는 `hrErrorReason`). `pMessageType` 매개 변수는 마지막 오류 메시지를 표시할 방법을 호출자에 게 지시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)