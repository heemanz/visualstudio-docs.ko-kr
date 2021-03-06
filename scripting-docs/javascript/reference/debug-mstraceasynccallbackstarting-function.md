---
title: "Debug.msTraceAsyncCallbackStarting 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 0e2ca7c4-103c-44f2-b76c-102fb1e42543
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49203cdf16e7cbd74493c882d9cf17b7629da79a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugmstraceasynccallbackstarting-function"></a>Debug.msTraceAsyncCallbackStarting 함수
콜백 스택을 이전에 지정된 비동기 작업에 연결합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Debug.msTraceAsyncCallbackStarting(asyncOperationId)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `asyncOperationId`  
 필수 요소. 비동기 작업과 연결된 ID입니다.  
  
## <a name="remarks"></a>설명  
 `Debug.msTraceAsyncOperationCompleted`를 호출한 후에 비동기 작업에 대한 콜백 함수에서 이 함수를 호출합니다.  
  
> [!NOTE]
>  일부 디버깅 도구는 디버거에 전달된 정보를 표시하지 않습니다.  
  
 `asyncOperationId`는 이전에 `Debug.msTraceAsyncOperationStarting`에서 반환된 작업 이름과 일치해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에 대한 비동기 호출을 추적하는 예제를 제공합니다.  
  
```JavaScript  
function asyncWrapperFunction() {  
    var opID = Debug.msTraceAsyncOperationStarting('async trace');  
    doSomethingAsync().then(function (result) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_SUCCESS);  
        Debug.msTraceAsyncCallbackStarting(opID);  
        // Process result of async operation.  
    }, function (error) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_ERROR);  
        Debug.msTraceAsyncCallbackStarting(opID);  
    });  
  
    Debug.msTraceAsyncCallbackCompleted();  
}  
  
function doSomethingAsync() {  
    return WinJS.Promise.as(true);  
}  
  
asyncWrapperFunction();  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]