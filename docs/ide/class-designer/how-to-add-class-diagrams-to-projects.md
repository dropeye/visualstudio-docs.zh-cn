---
title: "如何：向项目中添加类图（类设计器）| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e4017c5944a6cbc2e8f04980cdd349be92c02717
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-add-class-diagrams-to-projects-class-designer"></a>如何：向项目中添加类图（类设计器）
若要设计、编辑及重构类和其他类型，请将类图添加到 C#、Visual Basic 或 C++ 项目中。 若要直观显示项目中代码的不同部分，请将多个类图添加到该项目中。  
  
你不可以从在多个应用间共享代码的项目创建类图。 要创建 UML 类图，请参阅[创建 UML 建模项目和关系图](../../modeling/create-uml-modeling-projects-and-diagrams.md)。  
  
### <a name="to-add-a-blank-class-diagram-to-a-project"></a>向项目中添加空白类图  
  
1.  在解决方案资源管理器中，右击项目名称。 然后选择“添加新项”或“添加”、“新建项”。  
  
2.  从模板列表中选择“类图”。 对于 Visual C++ 项目，请查看“模板”下方，然后查看“实用工具”下方以查找该模板。  
  
     类图随即在类设计器中打开，并在解决方案资源管理器的项目层次结构中以一个带 .cd 扩展名的文件出现。 使用“类设计器”工具箱将形状和线条拖动到类图中。  
  
3.  要添加多个类图，请重复上述步骤。  
  
### <a name="to-add-a-class-diagram-based-on-existing-types"></a>基于现有类型添加类图  
  
1.  在解决方案资源管理器中，打开类文件上下文菜单，然后选择“查看类图”。  
  
     或  
  
     在“类视图”中，打开命名空间或类型上下文菜单，然后选择“查看类图”。  
  
### <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>在类图中显示完整项目的内容  
  
1.  在“解决方案资源管理器”或“类视图”中，右键单击该项目并选择“视图”，然后选择“查看类图”。

     即会创建一个自动填充的类图。  
  
## <a name="see-also"></a>请参阅
[如何：使用类设计器创建类型](how-to-create-types.md)   
[如何：查看现有类型](how-to-view-existing-types.md)   
[设计类和类型](designing-classes-and-types.md)   
[查看类型和关系](viewing-types-and-relationships.md)   
[使用类图](working-with-class-diagrams.md)