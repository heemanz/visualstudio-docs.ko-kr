---
title: R 도구 설치
description: 오프라인 설치를 포함하여 Visual Studio 2017 및 Visual Studio 2015에서 Visual Studio용 R 도구를 설치하는 방법입니다.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 894fc583e402f5fe5ceb5af2803239bd29ffa00d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-install-r-tools-for-visual-studio"></a>Visual Studio용 R 도구를 설치하는 방법

이 문서의 내용

- [지원되는 Visual Studio 버전](#supported-versions-of-visual-studio)
- [Visual Studio 2017에서 RTVS 설치](#installing-rtvs-in-visual-studio-2017)
- [Visual Studio 2015에서 RTVS 설치](#installing-rtvs-in-visual-studio-2015)
- [오프라인 설치](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> R 도구를 설치한 후 [옵션](options-for-r-tools-in-visual-studio.md) 문서의 설명에 따라 최적화된 데이터 과학자 레이아웃에 맞게 Visual Studio를 구성하는 것이 좋습니다.

## <a name="supported-versions-of-visual-studio"></a>지원되는 Visual Studio 버전

RTVS(Visual Studio용 R 도구)는 [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 및 [Visual Studio 2015 업데이트 3 이상](http://go.microsoft.com/fwlink/?LinkId=691129)(직접 다운로드)의 Community(무료), Professional 및 Enterprise 버전이 있는 Windows에서 지원됩니다.

RTVS는 현재 Mac용 Visual Studio에서 지원되지 않습니다.

Visual Studio Test Professional, SQL Server Management Studio 등의 제품에 포함된 Visual Studio Shell만 있는 경우에는 RTVS가 설치되지 않습니다. Visual Studio Shell에는 RTVS에 필요한 구성 요소가 없습니다.

## <a name="installing-rtvs-in-visual-studio-2017"></a>Visual Studio 2017에서 RTVS 설치

1. Visual Studio 설치 관리자를 실행하고 **수정** 옵션(세부 정보는 [Visual Studio 수정](../install/modify-visual-studio.md) 참조)을 선택합니다. Visual Studio가 설치되어 있지 않은 경우 [ Visual Studio 설치](../install/install-visual-studio.md)를 참조하세요. Windows 7에서 설치 관리자가 Visual Studio 2017 버전 ‘15.2 빌드 26430.12’ 이상을 표시하도록 업데이트되었는지 확인합니다.

1. **데이터 과학 및 분석 응용 프로그램** 워크로드를 선택합니다.

    ![VS2017의 데이터 과학 및 분석 응용 프로그램 워크로드](media/installation-data-science-workload.png)

1. 동일한 워크로드 이름 아래에서 오른쪽의 추가 옵션을 설정합니다. 기본적으로 이 워크로드에는 F# 및 Python 지원이 포함됩니다. R의 경우 최소 요구 사항은 **R 언어 지원**, **R 개발에 대한 런타임 지원** 및 **Microsoft R Client**입니다.

RTVS는 `%ProgramFiles(x86)%\Microsoft Visual Studio\<version>\<edition>Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`에 설치됩니다. 여기서 `<version>`은 일반적으로 `2017`이고 `<edition>`은 `Community`, `Professional` 또는 `Enterprise`입니다.

## <a name="installing-rtvs-in-visual-studio-2015"></a>Visual Studio 2015에서 RTVS 설치

Visual Studio 2015에서는 R 인터프리터 및 R 도구를 개별적으로 설치해야 합니다.

### <a name="install-an-r-interpreter"></a>R 인터프리터 설치

RTVS에는 다음 소스 중 하나 이상에서 제공되는 R 버전 3.2.1 이상의 64비트 설치가 필요합니다.

- [Microsoft R Open](https://mran.microsoft.com/download/)
- [Microsoft R Client](/machine-learning-server/r-client/what-is-microsoft-r-client)
- [CRAN R](https://cran.r-project.org/bin/windows/base/)

Microsoft R Open 및 CRAN R은 둘 다 여러 개의 동시 버전을 허용합니다. 하지만 Microsoft R Client는 하나의 버전만 지원하고 항상 설치된 최신 버전을 사용합니다.

### <a name="install-the-r-tools"></a>R 도구 설치

[https://aka.ms/rtvs-current](https://aka.ms/rtvs-current)에서 Visual Studio 2015용 최신 RTVS를 다운로드합니다. RTVS는 적합한 Visual Studio 버전을 확인하고 해당 버전이 아직 없는 경우 R 인터프리터를 설치하도록 지원합니다.

> [!Note]
> 독립 실행형 RTVS 설치 관리자는 Visual Studio 2015, Visual Studio 2017과만 작동합니다. 앞에서 설명한 대로 [데이터 과학 및 분석 응용 프로그램 작업](#installing-rtvs-in-visual-studio-2017)을 통해 R 지원을 설치합니다.

Visual Studio 2015용 RTVS는 `%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`에 설치됩니다.

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Visual Studio 및 RTVS의 오프라인 설치

오프라인 설치는 인터넷에 연결되지 않은 컴퓨터에 적합합니다.

1. 지침에 따라 사용 중인 Visual Studio 버전용 오프라인 설치 관리자를 만듭니다.

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. Visual Studio 2015의 경우 [https://aka.ms/rtvs-current-zip](https://aka.ms/rtvs-current-zip) 및 [https://aka.ms/rtvs-remote-zip](https://aka.ms/rtvs-remote-zip)에서 오프라인 RTVS 설치 관리자를 다운로드합니다.

1. 오프라인 설치 관리자에서 Visual Studio 및 RTVS를 설치합니다.

## <a name="see-also"></a>참고 항목

- [R 시작](getting-started-with-r.md)
- [R 도구 샘플 프로젝트](getting-started-samples.md)
- [도움말 보기](getting-started-help.md)
- [옵션 설정](options-for-r-tools-in-visual-studio.md)
- [Microsoft Machine Learning Server(이전의 R Server)](/machine-learning-server/)