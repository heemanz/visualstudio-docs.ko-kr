---
title: 개요 (디버그 인터페이스 액세스 SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 807690edaf5626e3ec007a005717622592c14ce9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="overview-debug-interface-access-sdk"></a>개요(디버그 인터페이스 액세스 SDK)
DIA SDK를 사용 하 여 Microsoft 디버그 정보에 액세스할 수 있습니다. DIA SDK는 COM 기반 Microsoft 디버그 정보의 형식 변경 될 때마다 코드를 다시 작성 하지 않아도 API 집합을 제공 합니다. DIA SDK에서는 이전 버전에서 생성 한.pdb 및.dbg 파일에 있는 디버그 정보의 선택 집합을 읽을 수 있습니다 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 버전 5.0 이상.  
  
 DIA SDK에 있는 각 인터페이스 달리 명시 하는 경우를 제외 하 고 다른 COM 개체를 나타냅니다. 추가적인 인터페이스와 추가 개체와 같은 명시적 쿼리를 사용 하 여 생성 됩니다 [idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 또는 [idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md), 아닌 를호출하여`QueryInterface` 기존 인터페이스 포인터에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)