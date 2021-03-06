---
title: IDiaStackWalkHelper::get_registerValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ccc491ec9e966b8d893b6d669aafc64ebc5c8cf
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
레지스터의 값을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 값은 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 값을 가져올 등록를 지정 하는 열거형입니다.  
  
 `pRetVal`  
 [out] 레지스터의 현재 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 크기를 불구 하 고는 `pRetVal` 매개 변수를 구현만 등록 일반적으로 저장을 저장 해야 합니다. 예를 들어 8 비트 레지스터만는 가장 낮은 8 비트를 지정된 된 값을 보유합니다. 8 비트 값이이 메서드에서 반환 하는 경우 64 비트로 확장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)