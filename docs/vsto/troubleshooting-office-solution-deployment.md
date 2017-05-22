---
title: "Office 솔루션 배포 문제 해결"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "ClickOnce 배포[Visual Studio에서 Office 개발], 문제 해결"
  - "Visual Studio에서 Office 개발, 문제 해결"
  - "응용 프로그램 배포[Visual Studio에서 Office 개발], 문제 해결"
ms.assetid: 2206aeb6-44b3-4786-ba99-9c7dad5cce7c
caps.latest.revision: 74
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 73
---
# Office 솔루션 배포 문제 해결
  이 항목에는 Office 솔루션을 배포할 때 발생할 수 있는 일반적인 문제를 해결하는 방법에 대한 정보가 포함되어 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 이벤트 뷰어를 사용하여 Office 솔루션 문제 해결  
 Windows 이벤트 뷰어를 사용하여 Office 솔루션을 설치하거나 제거할 때 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 캡처하는 오류 메시지를 표시할 수 있습니다. 이벤트 로거에서 이러한 메시지를 사용하여 설치 및 배포 문제를 해결할 수 있습니다. 자세한 내용은 [Office 솔루션에 대한 이벤트 로깅](../vsto/event-logging-for-office-solutions.md)을 참조하세요.  
  
## 어셈블리 이름 변경 시 충돌 발생  
 솔루션 배포 후에 **프로젝트 디자이너**의 **응용 프로그램** 페이지에서 **어셈블리 이름** 값을 변경한 경우 하나의 Setup.exe 파일과 두 개의 배포 매니페스트를 포함하도록 게시 도구가 설치 패키지를 수정합니다. 두 개의 매니페스트 파일을 배포하는 경우 다음 상황이 발생할 수 있습니다.  
  
-   최종 사용자가 두 버전을 모두 설치한 경우 응용 프로그램이 두 VSTO 추가 기능을 모두 로드합니다.  
  
-   어셈블리 이름이 변경되기 전에 VSTO 추가 기능이 설치된 경우 최종 사용자에게 업데이트가 전달되지 않습니다.  
  
 이러한 상황을 방지하려면 솔루션 배포 후 솔루션의 **어셈블리 이름** 값을 변경하지 마세요.  
  
## 업데이트 확인 시간이 오래 걸림  
 Visual Studio 2010 Tools for Office Runtime은 관리자가 매니페스트 및 솔루션 다운로드를 위한 시간 제한 값을 설정하는 데 사용할 수 있는 레지스트리 항목을 제공합니다.  
  
#### 시간 제한 값을 설정하려면  
  
1.  레지스트리에서 다음 키로 이동합니다.  
  
     HKEY\_CURRENT\_USER\\Software\\Microsoft\\VSTA  
  
2.  **AddInTimeout** 하위 키에서 시간 제한 값을 밀리초 단위로 설정합니다.  
  
     **AddInTimeout** 하위 키가 존재하지 않는 경우 DWORD 값으로 만듭니다.  
  
## 네트워크 파일 공유를 업데이트하거나 게시할 수 없음  
 업데이트가 게시되는 동안 프로세스에서 솔루션의 Setup.exe 파일이 잠긴 경우 업데이트 중 네트워크 파일 공유의 Office 솔루션에서 잘못된 메시지를 표시할 수 있습니다. 나타나는 메시지는 "'setup.exe'를 웹 사이트에 추가할 수 없습니다. 이 웹 사이트에 'setup.exe' 파일이 이미 있습니다."입니다.  
  
 파일 잠금을 방지하기 위해 공유를 최종 사용자에 대해 읽기 전용으로 만들 수 있습니다. 그러나 공유에 문서가 있는 경우 해당 문서도 최종 사용자에 대해 읽기 전용으로 설정됩니다.  
  
## Microsoft Office용 필수 조건이 설치되지 않음  
 Office 솔루션과 함께 배포되는 필수 조건으로 .NET Framework, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 및 Office 주 interop 어셈블리를 설치 패키지에 추가할 수 있습니다. 주 interop 어셈블리 설치 방법에 대한 자세한 내용은 [Office 솔루션을 개발할 수 있도록 컴퓨터 구성](../vsto/configuring-a-computer-to-develop-office-solutions.md) 및 [방법: Office 주 Interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md)를 참조하세요.  
  
## 'Localhost'를 사용하여 게시할 경우 설치 문제가 발생할 수 있음  
 문서 수준 솔루션의 게시 또는 설치 위치로 "http:\/\/localhost"를 사용하면 **게시 마법사**가 문자열을 실제 컴퓨터 이름으로 변환하지 않습니다. 이 경우 개발 컴퓨터에 솔루션을 설치해야 합니다. 배포된 솔루션에서 개발 컴퓨터의 IIS를 사용하게 하려면 localhost 대신 모든 HTTP\/HTTPS\/FTP 위치에 대한 정규화된 이름을 사용합니다.  
  
## 업데이트된 어셈블리 대신 캐시된 어셈블리가 로드됨  
 .NET Framework 어셈블리 로더인 Fusion은 프로젝트 출력 경로가 네트워크 파일 공유에 있고, 어셈블리가 강력한 이름으로 서명되고, 사용자 지정의 어셈블리 버전이 변경되지 않은 경우 캐시된 어셈블리 복사본을 로드합니다. 이러한 조건을 충족하는 어셈블리를 업데이트할 경우 다음에 프로젝트를 실행할 때 캐시된 복사본이 로드되기 때문에 업데이트가 나타나지 않습니다.  
  
 프로젝트를 실행할 때마다 Fusion에서 어셈블리를 다운로드하도록 Visual Studio를 구성할 수 있습니다.  
  
#### 캐시된 복사본을 로드하지 않고 어셈블리를 다운로드하려면  
  
1.  메뉴 모음에서 **프로젝트**, *ProjectName* **속성**을 선택합니다.  
  
2.  **응용 프로그램** 페이지에서 **어셈블리 정보**를 선택합니다.  
  
3.  첫 번째 **어셈블리 버전** 상자에서 별표\(\*\)를 입력한 다음 **확인** 단추를 선택합니다.  
  
 어셈블리 버전을 변경하면 강력한 이름으로 어셈블리에 서명할 수 있고 Fusion에서 최신 버전의 사용자 지정을 로드합니다.  
  
## URI에 US\-ASCII가 아닌 문자가 있는 경우 설치 실패  
 HTTP\/HTTPS\/FTP 위치에 Office 솔루션을 게시할 경우 경로에 US\-ASCII가 아닌 유니코드 문자를 사용할 수 없습니다. 이러한 문자를 사용하면 설치 프로그램에서 일관되지 않은 동작이 발생할 수 있습니다. 설치 경로에 US\-ASCII 문자를 사용합니다.  
  
## 개발 컴퓨터에 솔루션을 게시 및 설치할 때 수동으로 제거 메시지가 표시됩니다.  
 Office 솔루션을 빌드하면 빌드된 버전이 자동으로 등록됩니다. 이전에 개발 컴퓨터에 동일한 솔루션을 게시 및 설치한 적이 있는 경우 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 게시된 버전 및 빌드된 버전의 설치 경로가 솔루션이 다음에 빌드, 다시 빌드 또는 게시된 이후 달라졌다는 것을 감지합니다. 오류 메시지는 "다른 버전이 현재 설치되어 있고 이 위치에서 업그레이드할 수 없기 때문에 사용자 지정을 설치할 수 없습니다."입니다. 레지스트리 키는 솔루션이 다시 빌드될 때마다 업데이트됩니다. 따라서 새 버전을 게시, 디버그 또는 실행하기 전에 이전 버전을 제거해야 합니다.  
  
 메시지가 나타나지 않게 하려면 개발 컴퓨터에서 다른 사용자 계정을 만들어 배포를 테스트합니다. 또는 다음에 솔루션을 게시, 디버그 또는 다시 빌드하기 전에 컴퓨터에 설치된 프로그램 목록에서 해당 버전을 제거할 수 있습니다.  
  
## 솔루션 설치 시 Catch되지 않은 예외 또는 메서드를 찾을 수 없음 오류 발생  
 배포 매니페스트\(.vsto 파일\), Office 응용 프로그램, 문서 또는 통합 문서를 열어 Office 솔루션을 설치할 때 다음과 같은 오류 메시지가 나타날 수 있습니다.  
  
-   메서드를 찾을 수 없습니다.  
  
-   MissingMethodException.  
  
-   Catch되지 않은 예외  
  
 이러한 오류 메시지를 방지하려면 설치 프로그램을 실행하여 솔루션을 설치합니다.  
  
 설치 프로그램을 실행하지 않고 솔루션을 설치할 때는 설치 관리자가 필수 조건을 확인하거나 설치하지 않습니다. 필수 조건의 올바른 버전을 확인하고 필요에 따라 설치하는 것은 설치 프로그램의 역할입니다.  
  
## InstallShield Limited Edition 프로젝트 빌드 후 추가 기능용 매니페스트 레지스트리 키 변경  
 InstallShield Limited Edition 프로젝트를 빌드할 때 VSTO 추가 기능 설치 프로그램의 일부인 매니페스트 레지스트리 키가 .vsto에서 .dll.manifest로 변경될 때가 있습니다.  
  
 이 문제를 해결하려면 다른 솔루션에서 InstallShield Limited Edition 프로젝트를 만들거나, VSTO 추가 기능 이름이 포함된 레지스트리 키 값으로 CompanyName.AddinName을 사용합니다.  
  
## Office 솔루션에 대한 ClickOnce 설치 관리자가 주 Interop 어셈블리를 설치하지 않음  
 Office 솔루션에 대해 ClickOnce가 만드는 설치 프로그램을 실행할 때 Office PIA\(주 Interop 어셈블리\)용 설치 관리자는 PIA가 이미 설치되어 있지 않은 경우에만 실행됩니다.  
  
 설치 프로그램에서 PIA를 올바르게 설치하지 않는 경우 설치 디렉터리에서 이름이 o2007pia.msi인 설치 관리자 파일을 실행하여 수동으로 설치합니다.  
  
## Office 솔루션 다시 설치 시 인수가 범위를 벗어남 예외 발생  
 Office 솔루션을 다시 설치할 때 '지정한 인수가 유효한 값 범위를 벗어났습니다.'라는 오류 메시지와 함께 <xref:System.ArgumentOutOfRangeException> 예외가 나타날 수 있습니다.  
  
 이러한 문제는 설치 위치에 대한 URL의 대소문자가 다른 경우 발생합니다. 예를 들어 [http:\/\/fabrikam.com\/ExcelSolution.vsto](http://fabrikam.com/ExcelSolution.vsto)에서 Office 솔루션을 처음 설치하고 두 번째 사용할 때 [http:\/\/fabrikam.com\/excelsolution.vsto](http://fabrikam.com/excelsolution.vsto)를 지정한 경우 발생합니다.  
  
 메시지를 표시하지 않으려면 Office 솔루션을 설치할 때 동일한 대\/소문자를 사용합니다.  
  
## 웹에서 배포 매니페스트를 열어 ClickOnce 솔루션을 설치할 수 없습니다.  
 사용자는 웹에서 배포 매니페스트를 열어 Office 솔루션을 설치할 수 있습니다. 그러나 IIS\(인터넷 정보 서비스\)의 일부 설치는 .vsto 파일 이름 확장명을 차단합니다. 이를 사용하여 Office 솔루션을 배포하기 전에 IIS에서 MIME 형식을 정의해야 합니다.  
  
 IIS 6에서 MIME 형식을 정의하는 방법에 대한 자세한 내용은 [MIME 형식 구성\(IIS 6.0\)](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/cd72c0dc-c5b8-42e4-96c2-b3c656f99ead.mspx?mfr=true)을 참조하세요.  
  
 IIS 7에서 MIME 형식을 정의하는 방법에 대한 자세한 내용은 [MIME 형식 추가\(IIS7\)](http://technet.microsoft.com/library/cc725608(WS.10).aspx)를 참조하세요.  
  
 확장명을 **.vsto**로 설정하고 MIME 형식을 **application\/x\-ms\-vsto**로 설정합니다.  
  
## 참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  