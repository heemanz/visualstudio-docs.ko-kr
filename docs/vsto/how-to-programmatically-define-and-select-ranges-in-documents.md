---
title: "방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택"
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
  - "문서[Visual Studio에서 Office 개발], 범위"
  - "문서[Visual Studio에서 Office 개발], 문장 선택"
  - "범위, 문서에서 정의"
  - "범위, 문서에서 선택"
  - "문장, 문서에서 선택"
ms.assetid: 0727c1cb-d44c-4f1c-a699-4365dd13be5d
caps.latest.revision: 46
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 45
---
# 방법: 프로그래밍 방식으로 문서의 범위 정의 및 선택
  <xref:Microsoft.Office.Interop.Word.Range> 개체를 사용하여 Microsoft Office Word 문서의 범위를 정의할 수 있습니다.  <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> 메서드 사용, <xref:Microsoft.Office.Tools.Word.Document> 클래스\(문서 수준 사용자 지정\) 또는 <xref:Microsoft.Office.Interop.Word.Document> 클래스\(VSTO 추가 기능\)의 Content 속성 사용 등 여러 가지 방법으로 전체 문서를 선택할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 범위 정의  
 다음 예제에서는 인쇄할 수 없는 문자를 비롯하여 활성 문서의 처음 7자를 포함하는 새로운 <xref:Microsoft.Office.Interop.Word.Range> 개체를 만드는 방법을 보여 줍니다.  그런 다음 범위 내의 텍스트를 선택합니다.  
  
#### 문서 수준 사용자 지정의 범위를 정의하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Range%2A> 메서드에 시작 및 끝 문자를 전달하여 문서에 범위를 추가합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#18)]
     [!code-vb[Trin_VstcoreWordAutomation#18](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#18)]  
  
#### VSTO 추가 기능을 사용하여 범위를 정의하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Document> 클래스의 <xref:Microsoft.Office.Interop.Word._Document.Range%2A> 메서드에 시작 및 끝 문자를 전달하여 문서에 범위를 추가합니다.  다음 코드 예제에서는 활성 문서에 범위를 추가합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#18](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#18)]  
  
## 문서 수준 사용자 지정의 범위 선택  
 다음 예제에서는 <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> 메서드를 사용하거나 <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Content%2A> 속성을 사용하여 전체 문서를 선택하는 방법을 보여 줍니다.  
  
#### Select 메서드를 사용하여 전체 문서를 범위로 선택하려면  
  
1.  전체 문서를 포함하는 <xref:Microsoft.Office.Interop.Word.Range>의 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> 메서드를 사용합니다.  다음 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#19](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#19)]
     [!code-vb[Trin_VstcoreWordAutomation#19](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#19)]  
  
#### 콘텐츠 속성을 사용하여 전체 문서를 범위로 선택하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.Document.Content%2A> 속성을 사용하여 전체 문서를 포함하는 범위를 정의합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#20)]
     [!code-vb[Trin_VstcoreWordAutomation#20](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#20)]  
  
 다른 개체의 메서드와 속성을 사용하여 범위를 정의할 수도 있습니다.  
  
#### 활성 문서에서 문장을 선택하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Sentences> 컬렉션을 사용하여 범위를 설정합니다.  선택하려는 문장의 인덱스를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#21](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#21)]
     [!code-vb[Trin_VstcoreWordAutomation#21](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#21)]  
  
 문장을 선택하는 다른 방법은 범위의 시작 및 끝 값을 수동으로 설정하는 것입니다.  
  
#### 시작 및 끝 값을 수동으로 설정하여 문장을 선택하려면  
  
1.  범위 변수를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#23](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#23)]
     [!code-vb[Trin_VstcoreWordAutomation#23](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#23)]  
  
2.  문서에 둘 이상의 문장이 있는지 확인하고, 범위의 *Start* 및 *End* 인수를 설정한 다음 범위를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#24](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#24)]
     [!code-vb[Trin_VstcoreWordAutomation#24](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#24)]  
  
## VSTO 추가 기능을 사용하여 범위 선택  
 다음 예제에서는 <xref:Microsoft.Office.Interop.Word.Range> 개체의 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> 메서드를 사용하거나 <xref:Microsoft.Office.Interop.Word.Document> 클래스의 <xref:Microsoft.Office.Interop.Word._Document.Content%2A> 속성을 사용하여 전체 문서를 선택하는 방법을 보여 줍니다.  
  
#### Select 메서드를 사용하여 전체 문서를 범위로 선택하려면  
  
1.  전체 문서를 포함하는 <xref:Microsoft.Office.Interop.Word.Range>의 <xref:Microsoft.Office.Interop.Word.Range.Select%2A> 메서드를 사용합니다.  다음 코드 예제에서는 활성 문서의 내용을 선택합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#19](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#19)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#19](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#19)]  
  
#### 콘텐츠 속성을 사용하여 전체 문서를 범위로 선택하려면  
  
1.  <xref:Microsoft.Office.Interop.Word._Document.Content%2A> 속성을 사용하여 전체 문서를 포함하는 범위를 정의합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#20](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#20)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#20](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#20)]  
  
 다른 개체의 메서드와 속성을 사용하여 범위를 정의할 수도 있습니다.  
  
#### 활성 문서에서 문장을 선택하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Sentences> 컬렉션을 사용하여 범위를 설정합니다.  선택하려는 문장의 인덱스를 사용합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#21](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#21](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#21)]  
  
 문장을 선택하는 다른 방법은 범위의 시작 및 끝 값을 수동으로 설정하는 것입니다.  
  
#### 시작 및 끝 값을 수동으로 설정하여 문장을 선택하려면  
  
1.  범위 변수를 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#23](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#23)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#23](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#23)]  
  
2.  문서에 둘 이상의 문장이 있는지 확인하고, 범위의 *Start* 및 *End* 인수를 설정한 다음 범위를 선택합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#24](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#24)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#24](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#24)]  
  
## 참고 항목  
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위의 시작 및 끝 문자 검색](../vsto/how-to-programmatically-retrieve-start-and-end-characters-in-ranges.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 확장](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word 문서의 범위 다시 설정](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [방법: 프로그래밍 방식으로 문서의 범위 또는 선택 영역 축소](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [방법: 프로그래밍 방식으로 범위를 만들 때 단락 표시 제외](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)  
  
  