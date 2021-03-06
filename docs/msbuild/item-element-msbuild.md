---
title: Item 요소(MSBuild) | Microsoft 문서
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Item Element [MSBuild]
- <Item> Element [MSBuild]
ms.assetid: dcef5f91-0613-4bfc-8ee9-d7004bb6d3a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b55cadc738fb54b1a7fe07a2d891103c0daa755d
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="item-element-msbuild"></a>Item 요소(MSBuild)
사용자 정의 항목 및 해당 메타데이터를 포함합니다. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 프로젝트에서 사용되는 모든 항목은 `ItemGroup` 요소의 자식으로 지정해야 합니다.  

 \<Project>  
 \<ItemGroup>  
 \<Item>  

## <a name="syntax"></a>구문  

```  
<Item Include="*.cs"  
        Exclude="MyFile.cs"  
        Remove="RemoveFile.cs"  
        Condition="'String A'=='String B'" >  
    <ItemMetadata1>...</ItemMetadata1>  
    <ItemMetadata2>...</ItemMetadata2>  
</Item>  
```  

## <a name="specify-metadata-as-attributes"></a>메타데이터를 특성으로 지정
MSBuild 15.1 이상에서는 현재 특성 목록과 충돌하지 않는 이름을 가진 메타데이터를 특성으로 선택적으로 표시할 수 있습니다.

예를 들어 NuGet 패키지 목록을 지정하려면 일반적으로 다음과 같은 구문을 사용합니다.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1-beta1<Version>
  </PackageReference>
</ItemGroup>
```

하지만 이제 다음 구문과 같이 `Version` 메타데이터를 특성으로 전달할 수 있습니다.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1-beta1" />  
</ItemGroup>
```

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  

### <a name="attributes"></a>특성  

|특성|설명|  
|---------------|-----------------|  
|`Include`|선택적 특성입니다.<br /><br /> 항목 목록에 포함할 파일 또는 와일드카드입니다.|  
|`Exclude`|선택적 특성입니다.<br /><br /> 항목 목록에서 제외할 파일 또는 와일드카드입니다.|  
|`Condition`|선택적 특성입니다.<br /><br /> 평가할 조건입니다. 자세한 내용은 [조건](../msbuild/msbuild-conditions.md)을 참조하세요.|  
|`Remove`|선택적 특성입니다.<br /><br /> 항목 목록에서 제거할 파일 또는 와일드카드입니다.<br /><br />|  
|`KeepDuplicates`|선택적 특성입니다.<br /><br /> 항목이 기존 항목의 정확한 복제본인 경우 대상 그룹에 추가할지 여부를 지정합니다. 소스 항목과 대상 항목의 `Include` 값은 같고 메타데이터는 다르면 `KeepDuplicates`가 `false`로 설정되어 있어도 항목이 추가됩니다. 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하세요.<br /><br /> 이 특성은 `ItemGroup`에 포함된 `Target`의 항목에 대해 지정된 경우에만 유효합니다.|  
|`KeepMetadata`|선택적 특성입니다.<br /><br /> 대상 항목에 추가할 소스 항목의 메타데이터입니다. 이름이 세미콜론으로 구분된 목록에 지정되어 있는 메타데이터만 소스 항목에서 대상 항목으로 전송됩니다. 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하세요.<br /><br /> 이 특성은 `ItemGroup`에 포함된 `Target`의 항목에 대해 지정된 경우에만 유효합니다.|  
|`RemoveMetadata`|선택적 특성입니다.<br /><br /> 대상 항목에으로 전송하지 않을 소스 항목의 메타데이터입니다. 이름이 세미콜론으로 구분된 이름 목록에 포함되어 있는 메타데이터를 제외한 모든 메타데이터는 소스 항목에서 대상 항목으로 전송됩니다. 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하세요.<br /><br /> 이 특성은 `ItemGroup`에 포함된 `Target`의 항목에 대해 지정된 경우에만 유효합니다.|  
|`Update`|선택적 특성입니다. Visual Studio 2017 이상 버전의 .NET Core 프로젝트에만 사용할 수 있습니다.<br /><br /> GLOB를 사용하여 포함된 파일의 메타데이터를 수정할 수 있습니다.<br /><br />  이 특성은 `Target`에 포함되지 않은 `ItemGroup`의 항목에 대해 지정된 경우에만 유효합니다.|  

### <a name="child-elements"></a>자식 요소  

|요소|설명|  
|-------------|-----------------|  
|[ItemMetadata](../msbuild/itemmetadata-element-msbuild.md)|항목 메타데이터 값을 포함하는 사용자 정의 항목 메타데이터 키입니다. 항목에는 `ItemMetadata` 요소가 없을 수도 있고 하나 이상 있을 수도 있습니다.|  

### <a name="parent-elements"></a>부모 요소  

|요소|설명|  
|-------------|-----------------|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|항목의 grouping 요소입니다.|  

## <a name="remarks"></a>설명  
 `Item` 요소는 빌드 시스템에 대한 입력을 정의하며 사용자 정의 컬렉션 이름을 기준으로 하여 항목 컬렉션으로 그룹화됩니다. 이러한 항목 컬렉션은 빌드 프로세스의 단계를 수행하기 위해 컬렉션의 개별 항목을 사용하는 [작업](../msbuild/msbuild-tasks.md)의 매개 변수로 사용할 수 있습니다. 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하세요.  

 `@(`*myType*`)` 표기법을 사용하면 *myType* 형식의 항목 컬렉션을 세미콜론으로 구분된 문자열 목록으로 확장한 다음 매개 변수로 전달할 수 있습니다. 매개 변수가 `string` 형식인 경우 매개 변수 값은 세미콜론으로 구분된 요소 목록입니다. 매개 변수가 문자열 배열(`string[]`)이면 각 요소는 세미콜론의 위치를 기준으로 배열에 삽입됩니다. 작업 매개 변수가 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 형식이면 값은 항목 컬렉션의 내용(연결된 메타데이터 포함)입니다. 세미콜론 이외의 문자를 사용하여 각 항목을 구분하려면 `@(`*myType*`, '`*구분 기호*`')` 구문을 사용합니다.  

 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 엔진은 `*`, `?` 등의 와일드카드와 `/**/*.cs` 등의 재귀 와일드카드를 평가할 수 있습니다. 자세한 내용은 [항목](../msbuild/msbuild-items.md)을 참조하세요.  

## <a name="examples"></a>예제  
 다음 코드 예제에서는 `CSFile` 형식의 두 항목을 선언하는 방법을 보여 줍니다. 두 번째로 선언된 항목은 `MyMetadata`가 `HelloWorld`로 설정된 메타데이터를 포함합니다.  

```xml  
<ItemGroup>  
    <CSFile Include="engine.cs; form.cs" />  
    <CSFile Include="main.cs" >  
        <MyMetadata>HelloWorld</MyMetadata>  
    </CSFile>  
</ItemGroup>  
```  
다음 코드 예제에서는 `Update` 특성을 사용하여 GLOB를 통해 포함된 somefile.cs 파일에서 메타데이터를 수정하는 방법을 보여 줍니다. Visual Studio 2017 이상 버전의 .NET Core 프로젝트에만 사용할 수 있습니다.

```xml  
<ItemGroup>
    <Compile Update="somefile.cs">  // or Update="*.designer.cs"
        <MetadataKey>MetadataValue</MetadataKey>
    </Compile>
</ItemGroup>  
```  


## <a name="see-also"></a>참고 항목  
 [항목](../msbuild/msbuild-items.md)   
 [MSBuild 속성](../msbuild/msbuild-properties.md)   
 [프로젝트 파일 스키마 참조](../msbuild/msbuild-project-file-schema-reference.md)
