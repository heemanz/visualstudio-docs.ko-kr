---
title: "leftContext 속성 ($') (RegExp) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- $`
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- leftContext property ($`)
ms.assetid: 840e56c0-eb7c-461f-bb56-91acff9b5bcf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0234a547d2e26c6cf6b1d1a058a46135e577fdd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="leftcontext-property--regexp-javascript"></a>leftContext 속성($`)(RegExp)(JavaScript)
마지막 일치 항목의 시작 부분 앞 까지의 검색된 한 문자열의 시작 부분에서 문자를 반환합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.leftContext  
```  
  
## <a name="remarks"></a>설명  
 이 속성에 연결 된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 초기 값은 `leftContext` 속성은 빈 문자열입니다. 값은 `leftContext` 속성 때마다 변경 검색 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `leftContext` 속성을 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create the regular expression pattern.  
var re = new RegExp("d(b+)(d)","ig");  
var str = "cdbBdbsbdbdz";  
  
// Perform the search.  
var arr = re.exec(str);  
  
// Print the output.  
var s = ""   
s += "$1: " + RegExp.$1 + "<br />";  
s += "$2: " + RegExp.$2 + "<br />";  
s += "$3: " + RegExp.$3 + "<br />";  
s += "input: " + RegExp.input + "<br />";  
s += "lastMatch: " + RegExp.lastMatch + "<br />";  
s += "leftContext: " + RegExp.leftContext + "<br />";  
s += "rightContext: " + RegExp.rightContext + "<br />";   
s += "lastParen: " + RegExp.lastParen + "<br />";  
  
document.write(s);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [$1... $9 속성 (RegExp)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)   
 [index 속성 (RegExp)](../../javascript/reference/index-property-regexp-javascript.md)   
 [input 속성 ($_) (RegExp)](../../javascript/reference/input-property-dollar-regexp-javascript.md)   
 [lastIndex 속성 (RegExp)](../../javascript/reference/lastindex-property-regexp-javascript.md)   
 [lastMatch 속성 ($&) (RegExp)](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md)   
 [lastParen 속성 ($ +) (RegExp)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)   
 [rightContext 속성($')(RegExp)](../../javascript/reference/rightcontext-property-dollar-regexp-javascript.md)