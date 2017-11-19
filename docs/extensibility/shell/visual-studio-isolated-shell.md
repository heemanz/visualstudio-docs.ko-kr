---
title: "Visual Studio 격리 셸 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], shell-based applications, isolated mode
- Visual Studio shell, isolated mode
- isolated shell-based applications [Visual Studio]
- Visual Studio shell, shell-based applications, isolated mode
- Shell [Visual Studio], isolated mode
ms.assetid: d2620e71-be9e-44c9-b5b7-03a4c8d9cf0b
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6f4056e778e7d8f6aa62e84b03897c810160fa41
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-isolated-shell"></a>Visual Studio 격리 셸
Visual Studio 격리 셸을 사용 하 여 병렬 실행할 수 있는 독립 실행형 응용 프로그램을 만들 수 있습니다 다른 버전의 Visual Studio입니다. Visual Studio 서비스를 사용할 수 있지만 사용자 지정 된 모양이 있는 특수 도구를 호스트 하는 데 주로 사용 되는 및 브랜딩 않습니다. Visual Studio 기능 및 메뉴 명령 그룹 수 쉽게 설정 및 해제 합니다. 응용 프로그램 타이틀, 응용 프로그램 아이콘 및 시작 화면은 완전히 사용자 지정할 수 있습니다. 목록이 지정이 가능한 기능에 대 한 참조 [격리 셸 사용자 지정](customizing-the-isolated-shell.md)합니다.  
  
 격리 셸 프로젝트를 사용 하려면 Visual Studio SDK를 설치 해야 합니다. Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../installing-the-visual-studio-sdk.md)합니다.  
  
 격리 셸 응용 프로그램을 만들려면 Visual Studio Shell 격리 된 프로젝트를 시작 합니다. 이 프로젝트를 포함 하는 개발 및 테스트 격리 셸 응용 프로그램에 필요한 모든 합니다. 응용 프로그램을 배포 하는 설치 프로그램을 쓸 준비가 되 면에서 격리 셸 재배포 가능 패키지를 구해야 [Microsoft Visual Studio Shell (격리) 재배포 가능 패키지](http://go.microsoft.com/fwlink/?LinkId=616022)합니다.  
  
> [!NOTE]
>  격리 셸 재배포 가능 패키지에 액세스 하기 전에 한 간략 한 고객 설문 조사 해야 합니다.  설문 조사를 채운 후에 재배포 가능 패키지 다운로드 링크는 Visual Studio 연결 페이지로 이동 합니다.  아래에서 Visual Studio Connect 사이트에 대 한 후속 방문에서 다운로드 링크를 찾을 수 있습니다는 **프로그램 &#124; VISUAL STUDIO 2015 통합 및 ISOLATED SHELL** 탭 합니다.  
  
> [!NOTE]
>  격리 셸 기반 응용 프로그램을 배포 하는 방법에 대 한 자세한 내용은 참조 [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
## <a name="working-with-the-isolated-shell"></a>격리 셸 사용  
 Visual Studio 격리 셸 응용 프로그램 Visual Studio services에 대 한 모든 권한을 가지 며 특수 한 사용자 지정 브랜딩 및 지원 여러 가지 방법으로 격리 셸 응용 프로그램을 사용자 지정할 수 있습니다.  
  
-   다른 Visual Studio 확장에 사용 하려는 것 처럼 격리 셸 응용 프로그램을 확장 하려면 Vspackage 및 MEF Managed Extensibility Framework () 구성 요소 부분을 사용할 수 있습니다. 자세한 내용은 참조 [격리 셸 확장](extending-the-isolated-shell.md)합니다.  
  
-   사용할 수 없거나 사용할 수 없는 Visual Studio 기능 및 명령 그룹 메뉴를 확인 하려면 응용 프로그램의 사용자 인터페이스 (UI) 프로젝트에.vsct 파일을 업데이트 합니다.  
  
-   제거 하려면 **옵션** 페이지 또는 다른 Visual Studio 셸 구성 요소는 응용 프로그램에서 응용 프로그램의.pkgundef 파일을 업데이트 합니다.  
  
-   모양의 다른 측면 또는 셸의 동작을 수정 하려면 응용 프로그램의.pkgdef 파일을 업데이트 합니다.  
  
-   셸의 일부 측면은 응용 프로그램이 시작 될 때 지정할 수 있습니다. 이 작업을 수행 하려면는 appenvstub.dll의 시작 진입점으로 호출의 매개 변수를 업데이트 합니다.  
  
 사용자 지정할 수 있는 다양 한 요소에 대 한 자세한 내용은 참조 하십시오. [격리 셸 요소의](elements-of-the-isolated-shell.md)합니다.  
  
## <a name="standard-features-of-the-isolated-shell"></a>격리 셸의 표준 기능  
 다음 기능은 Visual Studio의 모든 버전에 표준입니다.  
  
|기능 범주|기능|  
|----------------------|-------------|  
|IDE 기능|설정 가져오기/내보내기<br /><br /> 도구 상자 컨트롤 설치 관리자<br /><br /> 작업 목록 및 오류 목록<br /><br /> 출력 창<br /><br /> 시작 페이지<br /><br /> 속성 창<br /><br /> 도구 상자<br /><br /> 솔루션 탐색기<br /><br /> 책갈피 창<br /><br /> 클래스 뷰<br /><br /> 개체 브라우저<br /><br /> 명령 창<br /><br /> 문서 개요<br /><br /> 리소스 뷰<br /><br /> 외부 도구<br /><br /> Windows Communication Foundation (WCF) 서비스 참조 추가<br /><br /> 언어 통합 쿼리 (LINQ) 지원|  
|편집기/디자이너|코드 검색 도구 (통합된 찾기, 원본 정의 상속)<br /><br /> IntelliSense<br /><br /> 스마트 태그<br /><br /> 코드 조각 관리자<br /><br /> 코드 조각<br /><br /> 리팩터링<br /><br /> 서식이 다시 적용<br /><br /> IntelliSense 필터링<br /><br /> 코드 정의 창<br /><br /> 응용 프로그램 디자이너<br /><br /> Windows Forms 디자이너<br /><br /> Windows Presentation Foundation (WPF) 디자이너|  
|디버깅|C# 식 계산기<br /><br /> 로컬 디버깅<br /><br /> 관리 되는 디버깅<br /><br /> 편집하며 계속하기<br /><br /> 크로스 스레드 디버깅<br /><br /> 시각화<br /><br /> 데이터 팁<br /><br /> 네이티브 디버깅<br /><br /> 스크립트 디버깅<br /><br /> Interop 디버깅<br /><br /> 타임 (JIT) 디버깅<br /><br /> 다중 프로세스 디버깅<br /><br /> XSLT 디버깅<br /><br /> 로컬 프로세스에 연결<br /><br /> 추적 지점<br /><br /> 중단점 제약 조건|  
|데이터|서버 탐색기 (간체-데이터만)<br /><br /> 로컬 데이터에 데이터 바인딩 (합니다. MDF 또는 합니다. MDB)<br /><br /> 개체에 데이터 바인딩<br /><br /> 웹 서비스에 데이터 바인딩<br /><br /> 데이터 컨트롤의 전체 집합<br /><br /> XML 편집기<br /><br /> 로컬 데이터베이스 서버에 데이터 바인딩<br /><br /> 데이터 소스 창|  
|웹|HTML 편집기<br /><br /> 웹 브라우저<br /><br /> Web Forms 디자이너<br /><br /> 웹 사이트 프로젝트<br /><br /> 웹 응용 프로그램 프로젝트|  
|확장성|Vspackage 및 MEF 구성 요소를 사용합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [셸(격리 또는 통합)](shell-isolated-or-integrated.md)