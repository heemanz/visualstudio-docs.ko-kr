---
title: SharePoint에서 지 원하는 MSBuild 속성 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, MSBuild properties
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1e60843119ee72f1164288f50b27116cdda31e9b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="msbuild-properties-supported-by-sharepoint"></a>SharePoint에서 지원하는 MSBuild 속성
  모든 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] Microsoft.VisualStudio.SharePoint.targets 파일, 프로젝트 파일 또는 프로젝트 사용자 파일에 정의 된 속성에 사용할 수 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트. 공통 외에도 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] SharePoint 프로젝트에 관련 된 추가 속성을 정의 하는 프로젝트를 SharePoint에서 제공 하는 속성입니다.  
  
 공통 목록은 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 속성 참조 [일반적인 MSBuild 프로젝트 속성](http://go.microsoft.com/fwlink/?LinkID=168687)합니다. 선택한 프로그래밍 언어에서 지 원하는 속성의 전체 목록을 찾아봅니다.targets 파일, 프로젝트 파일 (.csproj 또는.vbproj) 또는 프로젝트 사용자 파일 (csproj.user 또는. vbproj.user).  
  
## <a name="msbuild-properties-specific-to-sharepoint"></a>SharePoint에만 적용 됨 MSBuild 속성  
 다음 표에서 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 에서 SharePoint 프로젝트에 특별히 적용 되는 속성 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 다른 속성도 있지만 내부용입니다.  
  
|속성 이름|설명|  
|-------------------|-----------------|  
|SharePointSiteUrl|나타내는 string는 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] SharePoint 사이트에 있습니다.|  
|SandboxedSolution|솔루션이 샌드박스 솔루션 인지 여부를 나타내는 부울 값입니다.|  
|ActiveDeploymentConfiguration|활성 배포 구성입니다.|  
|IncludeAssemblyInPackage|어셈블리 패키지 파일에 포함 되는지 여부를 나타내는 부울 값입니다.|  
|PreDeploymentCommand|배포 전 명령이 단계에서 실행할 명령을 나타내는 문자열 값입니다.|  
|PostDeploymentCommand|배포 후 명령이 단계에서 실행할 명령을 나타내는 문자열 값입니다.|  
|CustomBeforeSharePointTargets|경로 나타내는 문자열을 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 대상 파일입니다. 대상 파일 존재 하 고 정의 된 경우 모든 SharePoint 대상 데이터 하기 전에 가져오기 됩니다. 이 속성을 사용 하면 제공된 SharePoint 대상 파일을 수정 하지 않고 미리 정의 패키징 관련 속성에 의해 패키지 프로세스를 사용자 지정할 수 있지만 대상 파일은 여전히 모든 SharePoint 프로젝트에 적용 됩니다.|  
|CustomAfterSharePointTargets|경로 나타내는 문자열을 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 대상 파일입니다. 존재 하 고 정의 된 대상 파일을 하는 경우 SharePoint 대상 데이터의 모든 가져올 않습니다. 이 속성을 사용 하면 제공된 SharePoint 대상 파일을 수정 하지 않고도 패키징 관련 속성 및 목표를 재정의 하 여 패키지 프로세스를 사용자 지정할 수 있지만 대상 파일은 여전히 모든 SharePoint 프로젝트에 적용 됩니다.|  
|LayoutPath|각 패키지할 파일 일시적으로 위치.wsp 파일에 추가 하기 전에 루트 디렉터리를 나타내는 문자열입니다. 이 경로를 추가, 제거 또는 파일을 수정 하려면 패키지할 수.wsp 파일의 내용을 변경 하는 데 사용할 수 있으므로 BeforeLayout 및 AfterLayout 대상을 재정의할 때 유용할 수 있습니다.|  
|BasePackagePath|패키지가 배치 되는 폴더를 나타내는 문자열입니다. 이 값 Bin\Debug 등 프로젝트의 출력 디렉터리를 사용합니다.|  
|PackageExtension|패키지에 추가할 파일 이름 확장명을 나타내는 문자열입니다. 기본값은 wsp 합니다.|  
|AssemblyDeploymentTarget|SharePoint 서버에 프로젝트 어셈블리를 배포할 위치를 나타내는 문자열입니다. 해당 값은 GlobalAssemblyCache (기본값) 또는 웹 응용 프로그램입니다. 속성 창에서이 속성을 설정할 수도 있습니다.|  
|PackageWithValidation|패키징 전에 유효성 검사를 수행할지 여부를 지정 하는 부울 값입니다. 이 속성을 사용 하면 패키지를 작성 하는 동안 유효성 검사 오류를 무시할 수 있습니다.|  
|ValidatePackageDependsOn|추가 ValidatePackage 대상 보다 먼저 실행할 대상을 정의 하는 문자열입니다.|  
|TokenReplacementFileExensions|토큰을 패키징 중에 대체 하는 파일을 정의 하는 문자열입니다.|  
  
## <a name="using-msbuild-properties-in-the-properties-page"></a>MSBuild 속성을 사용 하 여 속성 페이지에서  
 하드 코드 된 문자열을 사용 하는 대신 유연성을 **배포 전 명령줄** 및 **배포 후 명령줄** 상자 SharePoint 속성 페이지에는 SharePoint를 사용 하 여 인수로 속성입니다. 예를 들어 특정을 지정 하는 대신 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 문자열 SharePoint 사이트에 대 한 대신 사용할 수 있습니다 `$(SharePointSiteUrl)`합니다.  
  
> [!NOTE]  
>  하나를 사용할 수는 [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] 변수 구문을 `$(` *propertyName* `)` 또는 환경 변수 구문을 `%` *propertyName* `%` 속성을 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 참조](/visualstudio/msbuild/msbuild-reference)  
  
  