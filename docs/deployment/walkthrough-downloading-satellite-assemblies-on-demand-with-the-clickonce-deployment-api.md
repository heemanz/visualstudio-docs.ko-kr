---
title: '연습: ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, globalization
- localization, Windows Forms
- Windows Forms, localization
- globalization, ClickOnce
- satellite assemblies, ClickOnce
- ClickOnce deployment, on-demand download
- localization, ClickOnce deployment
- ClickOnce deployment, localization
ms.assetid: fdaa553f-a27e-44eb-a4e2-08c122105a87
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b686feb370ff522b2b26866990cc8069b465d96
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api"></a>연습: ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드
위성 어셈블리를 사용하면 Windows Forms 응용 프로그램을 여러 문화권에 맞게 구성할 수 있습니다. *위성 어셈블리* 는 응용 프로그램의 기본 문화권 이외의 문화권을 위한 응용 프로그램 리소스가 포함된 어셈블리입니다.  
  
 에 설명 된 대로 [ClickOnce 응용 프로그램 지역화](../deployment/localizing-clickonce-applications.md), 동일한 내에 여러 문화권을 위한 여러 위성 어셈블리를 포함할 수 있습니다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다. 기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 에서는 단일 클라이언트에 하나의 위성 어셈블리만 필요한 경우라도 배포의 모든 위성 어셈블리를 클라이언트 컴퓨터에 다운로드합니다.  
  
 이 연습에서는 위성 어셈블리를 선택적 항목으로 표시하고 클라이언트 컴퓨터의 현재 문화권 설정에 필요한 어셈블리만 다운로드하는 방법을 설명합니다. 다음 절차에서는 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]에서 사용할 수 있는 도구를 사용합니다. 또한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서도 이 작업을 수행할 수 있습니다.  또한 [연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) 또는 [연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](http://msdn.microsoft.com/library/ms366788\(v=vs.120\))를 참조하세요.  
  
> [!NOTE]
>  테스트를 위해 다음 코드 예제에서는 프로그래밍 방식으로 문화권을 `ja-JP`로 설정합니다. 이 코드를 프로덕션 환경에 맞게 조정하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 "다음 단계" 섹션을 참조하세요.  
  
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 사용자가 Visual Studio를 사용하여 응용 프로그램에 지역화된 리소스를 추가하는 방법을 알고 있다고 가정합니다. 자세한 내용은 [연습: Windows Forms 지역화](https://msdn.microsoft.com/en-us/library/vstudio/y99d1cd3\(v=vs.100\).aspx)를 참조하세요.  
  
### <a name="to-download-satellite-assemblies-on-demand"></a>요청 시 위성 어셈블리를 다운로드하려면  
  
1.  요청 시 위성 어셈블리 다운로드 기능을 사용하려면 응용 프로그램에 다음 코드를 추가합니다.  
  
     [!code-csharp[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]
     [!code-vb[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]  
  
2.  사용 하 여 응용 프로그램에 대 한 위성 어셈블리 생성 [Resgen.exe (리소스 파일 생성기)](/dotnet/framework/tools/resgen-exe-resource-file-generator) 또는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
3.  응용 프로그램 매니페스트를 생성하거나 MageUI.exe를 사용하여 기존 응용 프로그램 매니페스트를 엽니다. 이 도구에 대 한 자세한 내용은 참조 [MageUI.exe (매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)합니다.  
  
4.  **파일** 탭을 클릭합니다.  
  
5.  **줄임표** 단추(**...**)를 클릭하고 Resgen.exe를 사용하여 생성한 위성 어셈블리를 비롯한 응용 프로그램의 모든 어셈블리와 파일이 포함된 디렉터리를 선택합니다. 위성 어셈블리의 이름은 *isoCode*\ApplicationName.resources.dll 형식입니다. 여기에서 *isoCode* 는 RFC 1766 형식의 언어 식별자입니다.  
  
6.  **채우기** 를 클릭하여 배포에 파일을 추가합니다.  
  
7.  각 위성 어셈블리의 **옵션** 확인란을 선택합니다.  
  
8.  각 위성 어셈블리의 그룹 필드를 해당 ISO 언어 식별자로 설정합니다. 예를 들어 일본어 위성 어셈블리의 경우 `ja-JP`에서 사용할 수 있는 도구를 사용합니다. 이렇게 하면 1단계에서 추가한 코드를 사용하여 사용자의 <xref:System.Threading.Thread.CurrentUICulture%2A> 속성 설정에 따라 적절한 위성 어셈블리를 다운로드할 수 있습니다.  
  
## <a name="next-steps"></a>다음 단계  
 프로덕션 환경에서는 기본적으로 클라이언트 컴퓨터에 올바른 값이 설정되어 있으므로 <xref:System.Threading.Thread.CurrentUICulture%2A> 를 특정 값으로 설정하는 줄을 코드 예제에서 제거해야 할 수 있습니다. 예를 들어 응용 프로그램이 일본어 클라이언트 컴퓨터에서 실행될 경우 <xref:System.Threading.Thread.CurrentUICulture%2A> 는 기본적으로 `ja-JP` 입니다. 응용 프로그램을 배포하기 전에 이 값을 프로그래밍 방식으로 설정하면 위성 어셈블리를 쉽게 테스트할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 지역화](../deployment/localizing-clickonce-applications.md)