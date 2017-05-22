---
title: "prototype 속성(Intl.DateTimeFormat) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: e1e693ff-1775-407e-b655-18a60d238ded
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# prototype 속성(Intl.DateTimeFormat)
포맷터의 프로토타입에 대한 참조를 반환합니다.  
  
## 구문  
  
```javascript  
dateTimeFormat.prototype  
```  
  
## 설명  
 `dateTimeFormat` 인수는 포맷터의 이름입니다.  
  
 `prototype` 속성은 개체 클래스에 기본적인 함수 집합을 제공하기 위해 사용합니다.  개체의 새로운 인스턴스는 해당 개체에 할당된 프로토타입의 동작을 "상속"받습니다.  
  
 예를 들어 가장 큰 집합 요소의 값을 반환하는 `Intl.DateTimeFormat` 개체에 메서드를 추가하려면 함수를 선언하고 이를 `Intl.DateTimeFormat.prototype`에 추가한 후 사용합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]