---
title: "Visual Studio 中的解决方案和项目| Microsoft Docs"
ms.custom: 
ms.date: 10/5/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.addnewsolutionitem
- vs.environment.projects
- vs.openproject
- vs.addnewitem
- vs.addexistingitem
- VS.SolutionExplorer
- vs.newproject
- vs.addexistingsolutionitem
- vs.environment.solutions
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solution items [Visual Studio]
- solutions [Visual Studio]
- project items [Visual Studio]
- solutions [Visual Studio], designing
- projects [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4d242a74bd1eaef86e3465d53aa148429af42f7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="solutions-and-projects-in-visual-studio"></a>Visual Studio 中的解决方案和项目

## <a name="projects"></a>项目

在 Visual Studio 中创建应用、网站、插件等时，会从项目开始。 在逻辑意义上，项目包含所有将编译到可执行文件、库或网站中的源代码文件、图标、图像、数据文件等。 项目还包含编译器设置以及程序将与之通信的各种服务或组件需要的其他配置文件。

> [!NOTE]
> 无需在 Visual Studio 中使用解决方案或项目来编辑、生成和调试代码。 只需在 Visual Studio 中打开包含源文件的文件夹并开始编辑。 请参阅[在 Visual Studio 中开发代码而无需创建项目或解决方案](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)了解详细信息。

项目在扩展名为 .vbproj、.csproj 或 .vcxproj 等的 XML 文件中进行定义。 此文件包含虚拟文件夹层次结构以及项目中所有项的路径。 它还包含生成设置。

> [!TIP]
> 若要在 Visual Studio 中查看项目文件的内容，请在解决方案资源管理器中选择项目名称，然后在上下文菜单（或右键单击菜单）中选择“卸载项目”，先卸载项目。 然后，再次打开上下文菜单，依次选择“编辑”、“项目名称”**\<\>**。

在 Visual Studio 中，项目文件由解决方案资源管理器用于显示项目内容和设置。 编译项目时，MSBuild 引擎会使用项目文件创建可执行文件。 还可以自定义项目以生成其他类型的输出。

## <a name="solutions"></a>解决方案

项目包含在解决方案中。 解决方案可能包含一个或多个相关项目，以及生成信息、Visual Studio 窗口设置和不与特定项目关联的任何杂项文件。 解决方案由格式唯一的文本文件（扩展名 .sln）描述；通常不应对其进行手动编辑。

解决方案具有关联的 *.suo 文件，该文件为处理过项目的每个用户存储设置、首选项和配置信息。

## <a name="creating-new-projects"></a>创建新项目

创建新项目最简单的方法是从特定类型的应用程序或网站的项目模板开始。 项目模板包含一组基本的预生成代码文件、配置文件、资产和设置。 依次选择“文件”、“新建”、“项目”或“文件”、“新建”、“网站”后，“新建项目”或“新建网站”对话框会显示这些模板。 有关详细信息，请参阅[创建解决方案和项目](../ide/creating-solutions-and-projects.md)。

还可以创建自定义项目和项模板。 有关详细信息，请参阅[创建项目和项模板](../ide/creating-project-and-item-templates.md)。

## <a name="managing-projects-in-solution-explorer"></a>在解决方案资源管理器中管理项目

创建新项目之后，可使用“解决方案资源管理器”查看和管理项目和解决方案及其关联项。 下图显示具有一个包含两个项目的 C# 解决方案的解决方案资源管理器。

![解决方案资源管理器](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")

## <a name="see-also"></a>请参阅

[Visual Studio IDE](../ide/visual-studio-ide.md)
