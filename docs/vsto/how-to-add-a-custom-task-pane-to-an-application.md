---
title: "如何：向应用程序中添加自定义任务窗格"
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
  - "自定义任务窗格 [Visual Studio 中的 Office 开发], 添加到应用程序"
  - "任务窗格 [Visual Studio 中的 Office 开发], 添加到应用程序"
ms.assetid: 67b4ed5b-d77e-4630-b851-34bb25bdc9b3
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 如何：向应用程序中添加自定义任务窗格
  你可以通过使用 VSTO 外接程序向上面列出的应用程序添加自定义任务窗格。  有关详细信息，请参阅[自定义任务窗格](../vsto/custom-task-panes.md)。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  以下说明中的某些 Visual Studio 用户界面元素在计算机上出现的名称或位置可能会不同。  这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。  有关详细信息，请参阅 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/zh-cn/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## 向应用程序添加自定义任务窗格  
  
#### 若要向应用程序添加自定义任务窗格  
  
1.  为上面列出的应用程序之一打开或创建 VSTO 外接程序项目。  有关详细信息，请参阅[如何：在 Visual Studio 中创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
2.  在**“项目”**菜单上，单击**“添加用户控件”**。  
  
3.  在**“添加新项”**对话框中，将新用户控件的名称更改为 **MyUserControl**，然后单击**“添加”**。  
  
     用户控件将在设计器中打开。  
  
4.  从**“工具箱”**向用户控件添加一个或多个 Windows 窗体控件。  
  
5.  打开 **ThisAddIn.cs** 或 **ThisAddIn.vb** 代码文件。  
  
6.  向 `ThisAddIn` 类添加下面的代码。  此代码将 `MyUserControl` 和 <xref:Microsoft.Office.Tools.CustomTaskPane> 的实例声明为 `ThisAddIn` 类的成员。  
  
     [!code-csharp[Trin_TaskPaneBasic#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_TaskPaneBasic#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/VB/ThisAddIn.vb#1)]  
  
7.  将以下代码添加到 `ThisAddIn_Startup` 事件处理程序中。  此代码通过将 `MyUserControl` 对象添加到 `CustomTaskPanes` 集合来创建新 <xref:Microsoft.Office.Tools.CustomTaskPane>。  代码还将显示任务窗格。  
  
     [!code-csharp[Trin_TaskPaneBasic#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_TaskPaneBasic#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_TaskPaneBasic/VB/ThisAddIn.vb#2)]  
  
    > [!NOTE]  
    >  此代码将自定义任务窗格与应用程序中的活动窗口关联。  对于某些应用程序，你可能想要修改此代码以确保任务窗格与应用程序中的其他文档或项目一起显示。  有关详细信息，请参阅[自定义任务窗格](../vsto/custom-task-panes.md)。  
  
## 请参阅  
 [Office UI 自定义](../vsto/office-ui-customization.md)   
 [自定义任务窗格](../vsto/custom-task-panes.md)   
 [演练：从自定义任务窗格自动化应用程序](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)  
  
  