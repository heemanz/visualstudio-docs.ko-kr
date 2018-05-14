---
title: Visual Studio용 모델링 SDK - 도메인별 언어
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6dc87ba31e1f693559384977588471af753738e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="modeling-sdk-for-visual-studio---domain-specific-languages"></a>Visual Studio용 모델링 SDK - 도메인별 언어
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 위한 Modeling SDK를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 통합할 수 있는 강력한 모델 기반의 개발 도구를 만들 수 있습니다. 동일한 방식으로 하나 이상의 모델 정의를 만들고 그것들을 도구 집합으로 통합할 수 있습니다.

 MSDK의 핵심은 비즈니스 영역에서 개념을 나타내기 위해 당신이 만든 모델의 정의입니다. 다이어그램 보기, 코드와 다른 아티팩트를 생성하는 기능, 모델 변환 명령, 코드와 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 다른 개체와 상호 작용하는 기능과 같은 다양한 도구를 사용하여 모델을 감쌀 수 있습니다. 모델을 개발할 때 다른 모델 및 도구와 결합하여 개발에 중점을 두는 강력한 도구 집합을 구성할 수 있습니다.

 MSDK를 사용하여 도메인 관련 언어(DSL) 형태로 모델을 신속하게 개발할 수 있습니다. 특수 편집기를 사용하여 그래픽 표시법과 함께 스키마 또는 추상 구문을 정의하기 시작합니다. 이 정의로부터 VMSDK는 다음을 생성합니다.

-   트랜잭션 기반 저장소에서 실행되는 강력한 형식의 API를 사용하는 모델 구현입니다.

-   트리 기반 탐색기입니다.

-   자신이 정의하는 모델이나 모델의 일부를 사용자가 볼 수 있는 그래픽 편집기입니다.

-   읽을 수 있는 XML에 모델을 저장하는 Serialization 메서드입니다.

-   프로그램 코드 및 텍스트 템플릿을 사용하는 다른 아티팩트를 생성하기 위한 기능입니다.

 이런 모든 기능을 사용자 지정하고 확장할 수 있습니다. 그래도 DSL 정의를 업데이트하고 확장을 손실하지 않으면서 기능을 다시 생성할 수 있는 방식으로 확장이 통합됩니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

 [관련된 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

 고급 기술 및 문제 해결에 대 한 지침을 참조 하세요. [Visual Studio DSL 및 도구 확장성 모델링 포럼](http://go.microsoft.com/fwlink/?LinkID=186074)합니다.

## <a name="in-this-section"></a>섹션 내용
 [도메인별 언어 시작](../modeling/getting-started-with-domain-specific-languages.md)

 [모델, 클래스 및 관계 이해](../modeling/understanding-models-classes-and-relationships.md)

 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)

 [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)

 [도메인별 언어에서 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)

 [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)

 [도메인별 언어에서 코드 생성](../modeling/generating-code-from-a-domain-specific-language.md)

 [DSL 코드 이해](../modeling/understanding-the-dsl-code.md)

 [파일 저장소 및 XML Serialization 사용자 지정](../modeling/customizing-file-storage-and-xml-serialization.md)

 [도메인별 언어 솔루션 배포](../modeling/deploying-domain-specific-language-solutions.md)

 [Windows Forms 기반 도메인별 언어 만들기](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

 [WPF 기반 도메인별 언어 만들기](../modeling/creating-a-wpf-based-domain-specific-language.md)

 [방법: 도메인별 언어 디자이너 확장](../modeling/how-to-extend-the-domain-specific-language-designer.md)

 [시각화 및 모델링 SDK에서 지원되는 Visual Studio 버전](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md)

 [방법: 도메인별 언어를 새 버전으로 마이그레이션](../modeling/how-to-migrate-a-domain-specific-language-to-a-new-version.md)

 [Visual Studio용 모델링 SDK에 대한 API 참조](../modeling/api-reference-for-modeling-sdk-for-visual-studio.md)
