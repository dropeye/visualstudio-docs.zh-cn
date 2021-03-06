---
title: "T4 程序集指令 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 9f586931bd14089beca787c24d92bc2605c4d5de
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="t4-assembly-directive"></a>T4 程序集指令
在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 设计时文本模板中，`assembly` 指令可加载程序集，以便您的模板代码可使用其类型。 该作用类似于在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 项目中添加程序集引用。  
  
 编写文本模板的常规概述，请参阅[编写 T4 文本模板](../modeling/writing-a-t4-text-template.md)。  
  
> [!NOTE]
>  运行时（预处理）文本模板中不需要 `assembly` 指令。 相反，请添加必要的程序集到**引用**的你[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]项目。  
  
## <a name="using-the-assembly-directive"></a>使用 Assembly 指令  
 该指令的语法如下所示：  
  
```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 程序集名称应为以下各项之一：  
  
-   GAC 中程序集的强名称，例如 `System.Xml.dll`。 还可以使用长形式，例如 `name="System.Xml, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"`。 有关详细信息，请参阅<xref:System.Reflection.AssemblyName>。  
  
-   程序集的绝对路径  
  
 你可以使用 `$(variableName)` 语法引用 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 变量（如 `$(SolutionDir)`），以及使用 `%VariableName%` 来引用环境变量。 例如:  
  
```  
<#@ assembly name="$(SolutionDir)\MyProject\bin\Debug\SomeLibrary.Dll" #>  
```  
  
 在预处理文本模板中，assembly 指令无效。 相反，包括在必要的引用**引用**部分你[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]项目。 有关详细信息，请参阅[使用 T4 文本模板的运行时文本生成](../modeling/run-time-text-generation-with-t4-text-templates.md)。  
  
## <a name="standard-assemblies"></a>标准程序集  
 将自动加载以下程序集，您无需为它们编写程序集指令：  
  
-   `Microsoft.VisualStudio.TextTemplating.1*.dll`  
  
-   `System.dll`  
  
-   `WindowsBase.dll`  
  
 如果您使用自定义指令，则指令处理器可能会加载其他程序集。 例如，如果您为域特定语言 (DSL) 编写模板，则无需为以下程序集编写程序集指令：  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.1*.dll`  
  
-   `Microsoft.VisualStudio.Modeling.Sdk.Diagrams.1*.dsl`  
  
-   `Microsoft.VisualStudio.TextTemplating.Modeling.1*.dll`  
  
-   包含 DSL 的程序集。  
  
##  <a name="msbuild"></a>使用在 MSBuild 和 Visual Studio 中的项目属性  
 MSBuild 中，如 $ （solutiondir） 的 visual Studio 宏不起作用。 如果你想要在生成计算机中转换模板，则必须改用项目属性。  
  
 编辑 .csproj 或 .vbproj 文件以定义项目属性。 此示例定义一个名为 `myLibFolder` 的属性：  
  
```xml  
<!-- Define a project property, myLibFolder: -->  
<PropertyGroup>  
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myLibFolder">  
      <Value>$(myLibFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 现在你可在文本模板中使用项目属性，此类模板将在 Visual Studio 和 MSBuild 中正确转换：  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
```  
  
## <a name="see-also"></a>请参阅  
 [T4 包含指令](../modeling/t4-include-directive.md)