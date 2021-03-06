---
title: '방법: 바로 가기 메뉴에 명령 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office menus, creating
- Office development in Visual Studio, context menus
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0d1bf0aee988e194b51220588a710a4b5b8d66ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-commands-to-shortcut-menus"></a>방법: 바로 가기 메뉴에 명령 추가
  이 항목에서는 VSTO 추가 기능을 사용하여 Office 응용 프로그램의 바로 가기 메뉴에 명령을 추가하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
### <a name="to-add-commands-to-shortcut-menus-in-office"></a>Office에서 바로 가기 메뉴에 명령을 추가하려면  
  
1.  **리본 XML** 항목을 문서 수준 또는 VSTO 추가 기능 프로젝트에 추가합니다. 자세한 내용은 [How to: Get Started Customizing the Ribbon](../vsto/how-to-get-started-customizing-the-ribbon.md)을 참조하십시오. 입력  
  
2.  **솔루션 탐색기**에서 **ThisAddin.cs** 또는 **ThisAddin.vb**를 선택합니다.  
  
3.  메뉴 모음에서 **보기**, **코드**를 차례로 선택합니다.  
  
     **ThisAddin** 클래스 파일이 코드 편집기에서 열립니다.  
  
4.  **ThisAddin** 클래스에 다음 코드를 추가합니다. 이 코드 프로젝트 메서드를 재정의 하 고 Office 응용 프로그램에 리본 XML 클래스를 반환 합니다.  
  
     [!code-csharp[Trin_WordAddIn_Menus#1](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#1)]
     [!code-vb[Trin_WordAddIn_Menus#1](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#1)]  
  
5.  **솔루션 탐색기**에서 리본 XML 파일을 선택합니다. 기본적으로 리본 XML 파일의 이름은 Ribbon1.xml입니다.  
  
6.  메뉴 모음에서 **보기**, **코드**를 차례로 선택합니다.  
  
     코드 편집기에서 리본 xml 파일이 열립니다.  
  
7.  코드 편집기에서 바로 가기 메뉴와 바로 가기 메뉴에 추가할 컨트롤을 설명하는 XML을 추가합니다.  
  
     다음 예제에서는 Word 문서의 바로 가기 메뉴에 단추, 메뉴 및 갤러리 컨트롤을 추가합니다. 이 바로 가기 메뉴의 컨트롤 ID는 ContextMenuText입니다. Office 2010 바로 가기 컨트롤의 전체 목록은 ID 참조 [Office 2010 도움말 파일: Office Fluent 사용자 인터페이스 컨트롤 식별자](http://go.microsoft.com/fwlink/?LinkID=181052)합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="MyButton" label="My Button" insertBeforeMso="HyperlinkInsert" onAction="GetButtonID" />  
          <menu id="MySubMenu" label="My Submenu" >  
            <button id="MyButton2" label="Button on submenu" />  
          </menu>  
          <gallery id="galleryOne" label="My Gallery">  
            <item id="item1" imageMso="HappyFace" />  
            <item id="item2" imageMso="HappyFace" />  
            <item id="item3" imageMso="HappyFace" />  
            <item id="item4" imageMso="HappyFace" />  
          </gallery>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
8.  **솔루션 탐색기**에서 **MyRibbon.cs** 또는 **MyRibbon.vb**를 선택합니다.  
  
9. 처리하려는 각 컨트롤의 `Ribbon1` 클래스에 콜백 메서드를 추가합니다.  
  
     다음 콜백 메서드는 **My Button** 단추를 처리합니다. 이 코드는 활성 문서의 현재 커서 위치에 문자열을 추가합니다.  
  
     [!code-vb[Trin_WordAddIn_Menus#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/ribbon1.vb#2)]
     [!code-csharp[Trin_WordAddIn_Menus#2](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/ribbon1.cs#2)]  
  
## <a name="see-also"></a>참고 항목  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [연습: 책갈피에 대 한 바로 가기 메뉴 만들기](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [Office 2010의 상황에 맞는 메뉴를 사용자 지정](http://go.microsoft.com/fwlink/?LinkId=182186)  
  
  