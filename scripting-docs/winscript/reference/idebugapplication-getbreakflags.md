---
title: IDebugApplication::GetBreakFlags | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugApplication.GetBreakFlags
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::GetBreakFlags
ms.assetid: 0532ba94-f791-46ad-88ae-5f6ba220b667
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bdccefb3a679694360ed9a7c6fea35eae6bdb1b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationgetbreakflags"></a>IDebugApplication::GetBreakFlags
응용 프로그램에 대 한 현재 나누기 플래그를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetBreakFlags(  
   APPBREAKFLAGS*                   pabf,  
   IRemoteDebugApplicationThread**  pprdatSteppingThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pabf`  
 [out] 응용 프로그램에 대 한 현재 나누기 플래그를 지정 합니다.  
  
 `pprdatSteppingThread`  
 [out] 현재 실행 중인 스레드입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 응용 프로그램에 대 한 현재 나누기 플래그를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [APPBREAKFLAGS 열거형](../../winscript/reference/appbreakflags-enumeration.md)