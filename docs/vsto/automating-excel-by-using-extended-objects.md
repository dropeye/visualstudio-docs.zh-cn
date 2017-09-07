---
title: "使用扩展对象实现 Excel 自动化"
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
  - "Excel [Visual Studio 中的 Office 开发]，自动化"
  - "自动化 [Visual Studio 中的 Office 开发]，Excel"
  - "宿主控件，Excel"
  - "Excel [Visual Studio 中的 Office 开发]，宿主控件"
  - "扩展对象 [Visual Studio 中的 Office 开发]，Excel"
  - "宿主控件 [Visual Studio 中的 Office 开发]，Excel"
  - "自动化 Excel"
  - "宿主项 [Visual Studio 中的 Office 开发]，Excel"
  - "控件 [Visual Studio 中的 Office 开发]，Excel 宿主控件"
ms.assetid: 3ed99480-234d-46b1-b91c-226018bd3faf
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# 使用扩展对象实现 Excel 自动化
  当开发 Visual Studio 中的 Excel 解决方案时，可以使用解决方案中的*主机项*和*主机控件*。 这些对象可扩展 Excel 对象模型（即由 Excel 的主互操作程序集公开的对象模型）中某些常用对象，例如 <xref:Microsoft.Office.Interop.Excel.Worksheet> 和 <xref:Microsoft.Office.Interop.Excel.Range> 对象。 扩展的对象行为类似于其所基于的 Excel 对象，但它们可以将其他功能（如“新建事件”）和数据绑定功能添加到对象。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 虽然使用主机项和主机控件所在的上下文对于每种类型的解决方案有所不同，但它们均可用于 VSTO 外接程序和文档级自定义项。 有关详细信息，请参阅[宿主项和宿主控件概述](../vsto/host-items-and-host-controls-overview.md)。  
  
## Excel 主机项  
 Excel 项目可授予你访问几个主机项的权限：  
  
-   <xref:Microsoft.Office.Tools.Excel.Worksheet>。 此主机项包含项目中的一个工作表。 它还可充当托管控件（包括主机控件和 Windows 窗体控件），的容器并且还可保留有关其界面上的控件的信息。 有关详细信息，请参阅[工作表宿主项](../vsto/worksheet-host-item.md)。  
  
-   <xref:Microsoft.Office.Tools.Excel.Workbook>。 此主机项表示你项目中的工作簿，可充当工作簿中所有工作表共享的组件的容器。 有关详细信息，请参阅[工作簿宿主项](../vsto/workbook-host-item.md)。  
  
-   <xref:Microsoft.Office.Tools.Excel.ChartSheet>。 此主机项表示只包含一个图表并公开事件的 Excel 中的工作表。  
  
     当在设计时将图表工作表作为 Microsoft Office Excel 文档级自定义项目中的新工作表进行添加时，Visual Studio 将自动创建 <xref:Microsoft.Office.Tools.Excel.ChartSheet> 主机项。  
  
     尽管 <xref:Microsoft.Office.Tools.Excel.ChartSheet> 主机项是 Excel 中的一个工作表，但不能向该图表工作表添加任何控件。 如果想在包含图表的工作表上添加其他控件，请勿使用图表工作表。 相反，你可以通过使用 <xref:Microsoft.Office.Tools.Excel.Chart> 主机控件将图表作为工作表上嵌入的对象进行放置。 有关更多信息，请参见[Chart 控件](../vsto/chart-control.md)。  
  
## Excel 主机控件  
 有多个可用于 Excel 的主机控件，这些控件有助于你创建、组织和自动处理工作簿和工作表。 这些主机控件可提供本机 Excel 对象模型中的相应控件所无法提供的事件和数据绑定功能。  
  
 有关可以在 Excel 项目中使用的主机控件的详细信息，请参阅以下主题：  
  
-   [Chart 控件](../vsto/chart-control.md)  
  
-   [ListObject 控件](../vsto/listobject-control.md)  
  
-   [NamedRange 控件](../vsto/namedrange-control.md)  
  
-   [XmlMappedRange 控件](../vsto/xmlmappedrange-control.md)  
  
## 请参阅  
 [如何：用数据填充 ListObject 控件](../vsto/how-to-fill-listobject-controls-with-data.md)   
 [如何：向工作表添加 Chart 控件](../vsto/how-to-add-chart-controls-to-worksheets.md)   
 [如何：向工作表添加 ListObject 控件](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [如何：向工作表添加 NamedRange 控件](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [如何：向工作表添加 XMLMappedRange 控件](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)   
 [如何：调整 NamedRange 控件的大小](../vsto/how-to-resize-namedrange-controls.md)   
 [如何：调整 ListObject 控件的大小](../vsto/how-to-resize-listobject-controls.md)   
 [如何：在向 ListObject 控件添加新行时验证数据](../vsto/how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control.md)   
 [如何：将 ListObject 列映射到数据](../vsto/how-to-map-listobject-columns-to-data.md)   
 [演练：根据 NamedRange 控件的事件进行编程](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [在运行时在 VSTO 外接程序中扩展 Word 文档和 Excel 工作簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 文档上的控件](../vsto/controls-on-office-documents.md)   
 [在运行时向 Office 文档添加控件](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [宿主项和宿主控件概述](../vsto/host-items-and-host-controls-overview.md)   
 [宿主项和宿主控件的编程限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  