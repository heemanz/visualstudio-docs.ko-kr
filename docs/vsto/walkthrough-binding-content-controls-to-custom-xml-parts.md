---
title: "연습: 콘텐츠 컨트롤을 사용자 지정 XML 부분에 바인딩"
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
  - "콘텐츠 컨트롤[Visual Studio에서 Office 개발], 데이터 바인딩"
  - "사용자 지정 XML 부분, 콘텐츠 컨트롤에 바인딩"
  - "데이터 바인딩[Visual Studio에서 Office 개발], 콘텐츠 컨트롤"
  - "DatePickerContentControl, 사용자 지정 XML 부분에 바인딩"
  - "DropDownListContentControl, 사용자 지정 XML 부분에 항목 바인딩"
  - "PlainTextContentControl, 사용자 지정 XML 부분에 바인딩"
ms.assetid: 10d67769-6157-4703-a10c-d33e988f9095
caps.latest.revision: 51
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 50
---
# 연습: 콘텐츠 컨트롤을 사용자 지정 XML 부분에 바인딩
  이 연습에서는 문서에 저장된 XML 데이터에 Word에 대한 문서 수준 사용자 지정의 콘텐츠 컨트롤을 바인딩하는 방법을 보여 줍니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Word에서는 *사용자 지정 XML 부분*이라는 XML 데이터를 문서에 저장할 수 있습니다.  사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩하여 이 데이터의 표시를 제어할 수 있습니다.  이 연습의 예제 문서에서는 사용자 지정 XML 부분에 저장된 직원 정보를 표시합니다.  문서를 열면 콘텐츠 컨트롤에 XML 요소의 값이 표시됩니다.  콘텐츠 컨트롤의 텍스트에 대한 모든 변경 내용은 사용자 지정 XML 부분에 저장됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   디자인 타임에 문서 수준 프로젝트의 Word 문서에 콘텐츠 컨트롤 추가  
  
-   콘텐츠 컨트롤에 바인딩할 요소를 정의하는 XML 데이터 파일 및 XML 스키마 만들기  
  
-   디자인 타임에 문서에 XML 스키마 연결  
  
-   런타임에 문서의 사용자 지정 XML 부분에 XML 파일의 내용 추가  
  
-   사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤 바인딩  
  
-   XML 스키마에 정의된 값 집합에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> 바인딩  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 새 Word 문서 프로젝트 만들기  
 연습에서 사용할 Word 문서를 만듭니다.  
  
#### 새 Word 문서 프로젝트를 만들려면  
  
1.  이름이 EmployeeControls인 Word 문서 프로젝트를 만듭니다.  솔루션에 대한 새 문서를 만듭니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하세요.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 디자이너에 새 Word 문서가 열리고 EmployeeControls 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 문서에 콘텐츠 컨트롤 추가  
 사용자가 직원에 대한 정보를 보거나 편집할 수 있는 세 가지 형식의 콘텐츠 컨트롤을 포함하는 테이블을 만듭니다.  
  
#### 문서에 콘텐츠 컨트롤을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 디자이너에 호스트된 Word 문서의 리본 메뉴에서 **삽입** 탭을 선택합니다.  
  
2.  **테이블** 그룹에서 **테이블**을 선택하고 2열, 3행의 테이블을 삽입합니다.  
  
3.  다음 열과 비슷하도록 첫 번째 열에 텍스트를 입력합니다.  
  
    ||  
    |-|  
    |Employee Name|  
    |Hire Date|  
    |제목|  
  
4.  테이블의 두 번째 열에서 첫 번째 행을 선택합니다\(**Employee Name** 옆\).  
  
5.  리본 메뉴에서 **개발자** 탭을 선택합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)를 참조하세요.  
  
6.  **컨트롤** 그룹에서 **텍스트** 단추 ![PlainTextContentControl](../vsto/media/plaintextcontrol.png "PlainTextContentControl")를 선택하여 첫 번째 셀에 <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>을 추가합니다.  
  
7.  테이블의 두 번째 열에서 두 번째 행을 선택합니다\(**Hire Date** 옆\).  
  
8.  **컨트롤** 그룹에서 **날짜 선택** 단추 ![DatePickerContentControl](../vsto/media/datepicker.png "DatePickerContentControl")를 선택하여 두 번째 셀에 <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>을 추가합니다.  
  
9. 테이블의 두 번째 열에서 세 번째 행을 선택합니다\(**Title** 옆\).  
  
10. **컨트롤** 그룹에서 **드롭다운 목록** 단추 ![DropDownListContentControl](../vsto/media/dropdownlist.png "DropDownListContentControl")를 선택하여 마지막 셀에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 추가합니다.  
  
 이 프로젝트에 대한 전체 사용자 인터페이스입니다.  지금 프로젝트를 실행하는 경우 첫 번째 행에 텍스트를 입력하고 두 번째 행에서 날짜를 선택할 수 있습니다.  다음 단계는 XML 파일의 문서에 표시하려는 데이터를 연결하는 것입니다.  
  
## XML 데이터 파일 만들기  
 일반적으로 파일 또는 데이터베이스와 같은 외부 소스에서 사용자 지정 XML 부분에 저장할 XML 데이터를 가져옵니다.  이 연습에서는 문서의 콘텐츠 컨트롤에 바인딩할 요소로 표시된, 직원 데이터를 포함하는 XML 파일을 만듭니다.  런타임에 데이터를 사용할 수 있게 하려면 사용자 지정 어셈블리에 XML 파일을 리소스로 포함합니다.  
  
#### 데이터 파일을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  **템플릿** 창에서 **XML 파일**을 선택합니다.  
  
3.  파일 이름을 **employees.xml**로 지정하고 **추가** 단추를 선택합니다.  
  
     **employees.xml** 파일이 코드 편집기에서 열립니다.  
  
4.  **employees.xml** 파일의 내용을 다음 텍스트로 바꿉니다.  
  
    ```  
  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
      <employee>  
        <name>Karina Leal</name>  
        <hireDate>1999-04-01</hireDate>  
        <title>Manager</title>  
      </employee>  
    </employees>  
    ```  
  
5.  **솔루션 탐색기**에서 **employees.xml** 파일을 선택합니다.  
  
6.  **속성** 창에서 **빌드 작업** 속성을 선택하고 값을 **포함 리소스**로 변경합니다.  
  
     이 단계에서는 프로젝트를 빌드할 때 XML 파일을 어셈블리에 리소스로 포함합니다.  이렇게 하면 런타임에 XML 파일의 내용에 액세스할 수 있습니다.  
  
## XML 스키마 만들기  
 사용자 지정 XML 부분의 단일 요소에 콘텐츠 컨트롤을 바인딩하려는 경우 XML 스키마를 사용할 필요가 없습니다.  그러나 값 집합에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩하려면 앞에서 만든 XML 데이터 파일의 유효성을 검사하는 XML 스키마를 만들어야 합니다.  XML 스키마는 `title` 요소에 대한 가능한 값을 정의합니다.  이 연습의 뒷부분에서 이 요소에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩합니다.  
  
#### XML 스키마를 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  **템플릿** 창에서 **XML 스키마**를 선택합니다.  
  
3.  스키마 이름을 **employees.xsd**로 지정하고 **추가** 단추를 선택합니다.  
  
     스키마 디자이너가 열립니다.  
  
4.  **솔루션 탐색기**에서 **employees.xsd**의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.  
  
5.  **employees.xsd** 파일의 내용을 다음 스키마로 바꿉니다.  
  
    ```  
  
    <xs:schema xmlns="http://schemas.microsoft.com/vsto/samples"   
        targetNamespace="http://schemas.microsoft.com/vsto/samples"  
        xmlns:xs="http://www.w3.org/2001/XMLSchema"  
        elementFormDefault="qualified">  
      <xs:element name="employees" type="EmployeesType"></xs:element>  
      <xs:complexType name="EmployeesType">  
        <xs:all>  
          <xs:element name="employee" type="EmployeeType"/>  
        </xs:all>  
      </xs:complexType>  
      <xs:complexType name="EmployeeType">  
        <xs:sequence>  
          <xs:element name="name" type="xs:string" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="hireDate" type="xs:date" minOccurs="1" maxOccurs="1"/>  
          <xs:element name="title" type="TitleType" minOccurs="1" maxOccurs="1"/>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:simpleType name="TitleType">  
        <xs:restriction base="xs:string">  
          <xs:enumeration value ="Engineer"/>  
          <xs:enumeration value ="Designer"/>  
          <xs:enumeration value ="Manager"/>  
        </xs:restriction>  
      </xs:simpleType>  
    </xs:schema>  
    ```  
  
6.  **파일** 메뉴에서 **모두 저장**을 클릭하여 **employees.xml** 및 **employees.xsd** 파일의 변경 내용을 저장합니다.  
  
## 문서에 XML 스키마 연결  
 `title` 요소의 유효한 값에 <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 바인딩하려면 문서에 XML 스키마를 연결해야 합니다.  
  
#### 문서에 XML 스키마를 연결하려면\([!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]\)  
  
1.  디자이너에서 **EmployeeControls.docx**를 활성화합니다.  
  
2.  리본 메뉴에서 **개발자** 탭을 선택한 다음 **추가 기능** 단추를 선택합니다.  
  
3.  **템플릿 및 추가 기능** 대화 상자에서 **XML 스키마** 탭을 선택한 다음 **스키마 추가** 단추를 선택합니다.  
  
4.  프로젝트 디렉터리에 있는, 이전에 만든 **employees.xsd** 스키마로 이동한 다음 **열기** 단추를 선택합니다.  
  
5.  **스키마 설정** 대화 상자에서 **확인** 단추를 선택합니다.  
  
6.  **확인** 단추를 선택하여 **템플릿 및 추가 기능** 대화 상자를 닫습니다.  
  
#### 문서에 XML 스키마를 연결하려면\(Word 2010\)  
  
1.  디자이너에서 **EmployeeControls.docx**를 활성화합니다.  
  
2.  리본 메뉴에서 **개발자** 탭을 선택합니다.  
  
3.  **XML** 그룹에서 **스키마** 단추를 선택합니다.  
  
4.  **템플릿 및 추가 기능** 대화 상자에서 **XML 스키마** 탭을 선택한 다음 **스키마 추가** 단추를 선택합니다.  
  
5.  프로젝트 디렉터리에 있는, 이전에 만든 **employees.xsd** 스키마로 이동한 다음 **열기** 단추를 선택합니다.  
  
6.  **스키마 설정** 대화 상자에서 **확인** 단추를 선택합니다.  
  
7.  **확인** 단추를 선택하여 **템플릿 및 추가 기능** 대화 상자를 닫습니다.  
  
     **XML 구조** 작업창이 열립니다.  
  
8.  **XML 구조** 작업창을 닫습니다.  
  
## 문서에 사용자 지정 XML 부분 추가  
 XML 파일의 요소에 콘텐츠 컨트롤을 바인딩하려면 먼저 문서의 새 사용자 지정 XML 부분에 XML 파일의 내용을 추가해야 합니다.  
  
#### 문서에 사용자 지정 XML 부분을 추가하려면  
  
1.  **솔루션 탐색기**에서 **ThisDocument.cs** 또는 **ThisDocument.vb**의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.  
  
2.  `ThisDocument` 클래스에 다음 선언을 추가합니다.  이 코드는 문서에 사용자 지정 XML 부분을 추가하는 데 사용할 여러 개체를 선언합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/CS/ThisDocument.cs#1)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/VB/ThisDocument.vb#1)]  
  
3.  다음 메서드를 `ThisDocument` 클래스에 추가합니다.  이 메서드는 어셈블리에 리소스로 포함된 XML 데이터 파일의 내용을 가져오고 XML 문자열로 반환합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/CS/ThisDocument.cs#3)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/VB/ThisDocument.vb#3)]  
  
4.  다음 메서드를 `ThisDocument` 클래스에 추가합니다.  `AddCustomXmlPart` 메서드는 메서드에 전달된 XML 문자열을 포함하는 새 사용자 지정 XML 부분을 만듭니다.  
  
     사용자 지정 XML 부분이 한 번만 생성되도록 이 메서드는 일치하는 GUID를 가진 사용자 지정 XML 부분이 문서에 없는 경우에만 사용자 지정 XML 부분을 만듭니다.  이 메서드를 처음 호출하면 <xref:Microsoft.Office.Core._CustomXMLPart.Id%2A> 속성의 값이 `employeeXMLPartID` 문자열에 저장됩니다.  `employeeXMLPartID` 문자열의 값은 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 사용하여 선언되었으므로 문서에 유지됩니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/CS/ThisDocument.cs#4)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/VB/ThisDocument.vb#4)]  
  
## 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤 바인딩  
 각 콘텐츠 컨트롤의 **XMLMapping** 속성을 사용하여 사용자 지정 XML 부분의 요소에 각 콘텐츠 컨트롤을 바인딩합니다.  
  
#### 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩하려면  
  
1.  다음 메서드를 `ThisDocument` 클래스에 추가합니다.  이 메서드는 사용자 지정 XML 부분의 요소에 각 콘텐츠 컨트롤을 바인딩하고 <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>의 날짜 표시 형식을 설정합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/CS/ThisDocument.cs#5)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/VB/ThisDocument.vb#5)]  
  
## 문서를 열 때 코드 실행  
 문서를 열 때 사용자 지정 XML 부분을 만들고 사용자 지정 컨트롤을 데이터에 바인딩합니다.  
  
#### 문서를 열 때 코드를 실행하려면  
  
1.  `ThisDocument` 클래스의 `ThisDocument_Startup` 메서드에 다음 코드를 추가합니다.  이 코드는 **employees.xml** 파일에서 XML 문자열을 가져오고, 문서의 새 사용자 지정 XML 부분에 XML 문자열을 추가한 다음 사용자 지정 XML 부분의 요소에 콘텐츠 컨트롤을 바인딩합니다.  
  
     [!code-csharp[Trin_ContentControlXmlPartWalkthrough#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/CS/ThisDocument.cs#2)]
     [!code-vb[Trin_ContentControlXmlPartWalkthrough#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ContentControlXmlPartWalkthrough/VB/ThisDocument.vb#2)]  
  
## 프로젝트 테스트  
 문서를 열면 콘텐츠 컨트롤이 사용자 지정 XML 부분에 있는 요소의 데이터를 표시합니다.  <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>을 클릭하여 **employees.xsd** 파일에서 정의된 `title` 요소에 대한 세 가지 유효한 값 중 하나를 선택할 수 있습니다.  콘텐츠 컨트롤의 데이터를 편집하는 경우 문서의 사용자 지정 XML 부분에 새 값이 저장됩니다.  
  
#### 콘텐츠 컨트롤을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  문서의 테이블이 다음 테이블과 유사한지 확인합니다.  두 번째 열의 각 문자열은 문서의 사용자 지정 XML 부분에 있는 요소에서 가져옵니다.  
  
    |||  
    |-|-|  
    |Employee Name|**Karina Leal**|  
    |Hire Date|**April 1, 1999**|  
    |제목|**관리자가**|  
  
3.  Employee Name 셀의 오른쪽에 있는 셀을 선택하고 다른 이름을 입력합니다.  
  
4.  Hire Date 셀의 오른쪽에 있는 셀을 선택하고 날짜 선택에서 다른 날짜를 선택합니다.  
  
5.  Title 셀의 오른쪽에 있는 셀을 선택하고 드롭다운 목록에서 새 항목을 선택합니다.  
  
6.  문서를 저장한 후 닫습니다.  
  
7.  파일 탐색기에서 프로젝트 위치 아래에 있는 \\bin\\Debug 폴더를 엽니다.  
  
8.  EmployeeControls.docx에 대한 바로 가기 메뉴를 열고 **이름 바꾸기**를 선택합니다.  
  
9. 파일 이름을 EmployeeControls.docx.zip으로 지정합니다.  
  
     EmployeeControls.docx 문서가 Open XML 형식으로 저장됩니다.  이 문서의 이름을 .zip 파일 이름 확장명으로 바꾸면 문서 내용을 검사할 수 있습니다.  Open XML에 대한 자세한 내용은 기술 문서 [Office\(2007\) Open XML 파일 형식 소개](http://msdn.microsoft.com/ko-kr/96018532-f62c-4da7-bbff-16b96a483fbf)를 참조하세요.  
  
10. EmployeeControls.docx.zip 파일을 엽니다.  
  
11. **customXml** 폴더를 엽니다.  
  
12. **item2.xml**에 대한 바로 가기 메뉴를 열고 **열기**를 선택합니다.  
  
     이 파일에는 문서에 추가한 사용자 지정 XML 부분이 포함됩니다.  
  
13. `name`, `hireDate` 및 `title` 요소에 문서의 콘텐츠 컨트롤에 입력한 새 값이 포함되어 있는지 확인합니다.  
  
14. **item2.xml** 파일을 닫습니다.  
  
## 다음 단계  
 다음 항목에서 콘텐츠 컨트롤을 사용하는 방법에 대해 자세히 알아볼 수 있습니다.  
  
-   사용 가능한 모든 콘텐츠 컨트롤을 사용하여 서식 파일을 만듭니다.  자세한 내용은 [연습: 콘텐츠 컨트롤을 사용하여 서식 파일 만들기](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)를 참조하세요.  
  
-   문서가 닫혀 있는 동안 사용자 지정 XML 부분의 데이터를 수정합니다.  다음에 사용자가 문서를 열면 XML 요소에 바인딩된 콘텐츠 컨트롤이 새 데이터를 표시합니다.  
  
-   콘텐츠 컨트롤을 사용하여 문서 부분을 보호합니다.  자세한 내용은 [방법: 콘텐츠 컨트롤을 사용하여 문서 부분 보호](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)를 참조하세요.  
  
## 참고 항목  
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [콘텐츠 컨트롤](../vsto/content-controls.md)   
 [방법: Word 문서에 콘텐츠 컨트롤 추가](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [방법: 콘텐츠 컨트롤을 사용하여 문서 부분 보호](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  