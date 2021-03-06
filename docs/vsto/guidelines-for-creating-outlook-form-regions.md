---
title: Outlook을 만들기 위한 지침 양식 영역 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], guidelines
- icons [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dae7f03c49223c9919dc67b1c6a13768c597698d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="guidelines-for-creating-outlook-form-regions"></a>Outlook 양식 영역 만들기 지침
  다음 정보를 통해 양식 영역을 최적화하고 잠재적인 문제를 방지할 수 있습니다.  
  
-   [양식 영역 이름 사용](#UsingFormRegions)  
  
-   [양식 영역 상속을 사용하지 않도록 설정](#DisablingInheritance)  
  
-   [형식 및 메시지 클래스 이름 이해](#ClassNames)  
  
-   [읽기 창의 인접 양식 영역 디자인](#ReadingPane)  
  
-   [최적 아이콘 크기 사용](#UsingOptimal)  
  
 양식 영역에 대한 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
##  <a name="UsingFormRegions"></a> Using Form Region Names  
 양식 영역을 설명하기 위해 사용하는 여러 가지 이름이 있습니다. 이러한 이름과 이들이 양식 영역에 영향을 미치는 방법 간의 차이점을 이해하는 것이 중요합니다. 다음 표에서는 각 이름에 대해 설명합니다.  
  
|양식 영역 이름|설명|  
|----------------------|-----------------|  
|양식 영역 항목 이름|**새 항목 추가** 대화 상자에서 **Outlook 양식 영역** 항목에 대해 지정한 이름입니다. 이 이름은 **솔루션 탐색기**에 나타나는 양식 영역 코드의 이름입니다.|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> 속성|**새 Outlook 양식 영역** 마법사의 **설명 텍스트를 입력하고 디스플레이 기본 설정을 선택하세요.** 페이지에서 이 이름을 지정합니다. 이 이름은 **속성** 창에 **FormRegionName** 속성으로 나타납니다.<br /><br /> <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> 속성을 사용하여 Outlook UI(사용자 인터페이스)에서 양식 영역을 식별하는 레이블을 지정합니다. 별도 양식 영역의 경우 이 이름이 Outlook 항목의 리본에 단추로 나타납니다.<br /><br /> 인접한 양식 영역의 경우 이 이름이 양식 영역 위에 머리글 텍스트로 나타납니다.|  
|Microsoft.Office.Tools.Outlook.FormRegionName 특성|**Outlook 양식 영역** 항목을 프로젝트에 추가하는 경우 Visual Studio는 이 속성을 양식 영역의 정규화된 이름으로 설정합니다. 기본 정규화된 이름은 VSTO 추가 기능 이름, 점, 양식 영역 이름이 차례로 연결된 이름입니다(예: `OutlookAddIn1.FormRegion1`).<br /><br /> 또한 이 정규화된 이름은 양식 영역 팩터리 클래스의 맨 위에 특성으로 나타납니다.<br /><br /> 모든 Outlook VSTO 추가 기능에서 양식 영역을 고유 하 게 식별 하려면 Microsoft.Office.Tools.Outlook.FormRegionName 특성을 사용 합니다. 양식 영역 항목 이름 바꾸기 또는 변경 하 여 Microsoft.Office.Tools.Outlook.FormRegionName 특성의 값을 변경할 수 없습니다는 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> 속성입니다. 이 이름을 변경 하려면 양식 영역 코드 파일에서 Microsoft.Office.Tools.Outlook.FormRegionName 특성을 수정 해야 합니다.|  
  
##  <a name="DisablingInheritance"></a> Disabling Form Region Inheritance  
 기본적으로 사용자 지정 메시지 클래스는 기본 메시지 클래스의 모든 양식 영역 연결을 상속합니다. 예를 들어 라는 메시지 클래스가 `IPM.Task.Contoso` IPM에서 파생 됩니다. 작업입니다. 따라서 `IPM.Task.Contoso` IPM의 양식 영역 연결을 상속 합니다. 작업입니다.  
  
 양식 영역을 파생된 메시지 클래스와 연결하지 않으려면 양식 영역의 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> 속성을 **true**를 참조하세요. 예를 들어 ipm 인접 양식 영역을 연결 하는 경우. 작업 및 설정의 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> 속성을 **true**, 양식 영역이 표준 작업 양식의 하단에만 추가 됩니다. 양식 영역이 사용자 지정된 버전의 표준 작업 양식 하단에는 추가되지 않습니다.  
  
##  <a name="ClassNames"></a> 형식 및 메시지 클래스 이름 이해  
 Outlook 항목의 형식 이름은 Outlook 항목의 메시지 클래스 이름과 다릅니다. 예를 들어 RSS 항목의 형식 이름을 Microsoft.Office.Interop.Outlook.PostItem 됩니다. RSS 항목의 메시지 클래스 이름과 IPM 합니다. Post.RSS 합니다.  
  
 형식 이름을 사용하여 코드의 Outlook 항목을 참조합니다. 형식 이름 목록에 대해서는 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)를 참조하세요.  
  
 **새 Outlook 양식 영역** 마법사에서 Outlook 항목의 메시지 클래스 이름을 사용하여 항목을 양식 영역과 연결합니다. 올바른 메시지 클래스 이름 목록에 대해서는 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)를 참조하세요.  
  
##  <a name="ReadingPane"></a> Designing Adjoining Form Regions for the Reading Pane  
 Outlook 읽기 창을 사용하여 항목을 열지 않고도 Outlook 항목을 미리 볼 수 있습니다. 읽기 창은 읽기 전용으로 설계되어 있습니다. 따라서 항목 및 양식 영역이 읽기 창에서 열리는 경우 인접 양식 영역에 추가하는 입력 컨트롤(예: 텍스트 상자)이 예상대로 동작하지 않을 수 있습니다.  
  
 예를 들어 인접 양식 영역을 가진 항목이 읽기 창에서 열려 있으면 다음과 같은 상황이 가능합니다.  
  
1.  양식 영역에 있는 텍스트 상자에서 일부 텍스트를 선택합니다.  
  
2.  Delete 키를 누릅니다.  
  
3.  텍스트 상자의 텍스트 대신 전체 메일 항목이 삭제됩니다.  
  
 입력 컨트롤을 포함하는 인접 양식 영역을 디자인하는 경우 읽기 창에서 컨트롤을 테스트하여 제대로 작동하는지 확인합니다. 예상대로 작동하지 않는 컨트롤을 사용하지 않도록 설정하는 사용자 지정 코드를 추가하는 것이 좋습니다.  
  
 또는 양식 영역의 <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ShowInspectorRead%2A> 속성을 **False**를 참조하세요. 이렇게 하면 읽기 창에서 양식 영역을 사용할 수 없습니다.  
  
##  <a name="UsingOptimal"></a> Using Optimal Icon Sizes  
 **속성** 창의 **아이콘** 속성 그룹에서 아이콘 속성을 설정하여 양식 영역에 표시하려는 아이콘을 지정할 수 있습니다. 가장 좋은 시각적 품질을 달성하려면 다음 지침을 따릅니다.  
  
-   **페이지** 아이콘에 대해서는 PNG(이동식 네트워크 그래픽) 파일을 사용합니다.  
  
-   **창** 아이콘은 32X32 픽셀이어야 합니다.  
  
-   다른 모든 아이콘은 16X16 픽셀이어야 합니다.  
  
 별도, 대체 및 모두 대체 양식 영역을 포함하는 항목에 대해 검사기의 리본에 표시할 **페이지** 아이콘입니다.  
  
 **창** 아이콘이 대체 또는 모두 대체 양식 영역을 표시하는 열린 항목에 대해 ALT+TAB 대화 상자 및 알림 영역에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  