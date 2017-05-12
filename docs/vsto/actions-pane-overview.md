---
title: "操作窗格概述"
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
  - "操作窗格 [Visual Studio 中的 Office 开发]"
  - "操作窗格 [Visual Studio 中的 Office 开发], 关于操作窗格"
  - "智能文档 [Visual Studio 中的 Office 开发]"
  - "用户控件 [Visual Studio 中的 Office 开发], 操作窗格"
ms.assetid: 1b9b7db5-b19f-44ea-a774-f0962ca03bd2
caps.latest.revision: 101
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 100
---
# 操作窗格概述
  操作窗格是可自定义的**“文档操作”**任务窗格，它附加到了特定的 Microsoft Office Word 文档或 Microsoft Office Excel 工作簿。  它与其他内置任务窗格（如 Excel 中的**“XML 源”**任务窗格或 Word 中的**“样式和格式”**任务窗格）一起都在 Office 任务窗格中进行托管。  可使用 Windows 窗体控件或 WPF 控件来设计操作窗格用户界面。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 可以只在文档级自定义项中为 Word 或 Excel 创建一个操作窗格。  不能在 VSTO 外接程序中创建操作窗格。  有关详细信息，请参阅[按 Office 应用程序和项目类型提供的功能](../vsto/features-available-by-office-application-and-project-type.md)。  
  
> [!NOTE]  
>  操作窗格不同于自定义任务窗格。  自定义任务窗格与应用程序（而不是特定文档）相关联。  你可以在 VSTO 外接程序中为某些 Microsoft Office 应用程序创建自定义任务窗格。  有关详细信息，请参阅[自定义任务窗格](../vsto/custom-task-panes.md)。  
  
 ![链接到视频](../vsto/media/playvideo.png "链接到视频") 有关相关的视频演示，请参见[如何实现：在 Excel 操作窗格中使用 WPF 控件](http://go.microsoft.com/fwlink/?LinkId=132763)。  
  
## 显示操作窗格  
 操作窗格表示为<xref:Microsoft.Office.Tools.ActionsPane> 类。  当你创建文档级项目时，通过使用项目中 `ThisWorkbook`（针对 Excel）或 `ThisDocument`（针对 Word）类的 `ActionsPane` 字段向你的代码提供此类的实例。  若要显示操作窗格，请将 Windows 窗体控件添加到 `ActionsPane` 字段的 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 属性。  下列代码示例将名为 `actions` 的控件添加到操作窗格。  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#7)]
 [!code-vb[Trin_VstcoreActionsPaneWord#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#7)]  
  
 一旦将控件显式添加到操作窗格，该窗格即在运行时变得可见。  显示操作窗格后，可根据用户的操作动态添加或删除控件。  通常情况下，你将添加代码以在 `ThisDocument` 或 `ThisWorkbook` 的 `Startup` 事件处理程序中显示操作窗格，从而使操作窗格在用户首次打开文档时可见。  但是，你可能只想根据文档中的用户操作来显示操作窗格。  例如，你可能回向文档上控件的 `Click` 事件添加代码。  
  
### 将多个控件添加到操作窗格  
 如果要将多个控件添加到操作窗格，在大多数情况下你应将控件分组到用户控件中，然后将用户控件添加到 <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> 属性。  此过程包括下列步骤：  
  
1.  通过向你的项目添加**“操作窗格控件”**或**“用户控件”**项，创建操作窗格的用户界面 \(UI\)。  这两项均包含自定义 Windows 窗体 <xref:System.Windows.Forms.UserControl> 类。  **“操作窗格控件”**和**“用户控件”**项是等效项；唯一的区别是它们的名称。  
  
2.  通过使用设计器或编写代码，将 Windows 窗体控件添加到 <xref:System.Windows.Forms.UserControl>。  
  
    > [!NOTE]  
    >  还可以通过将 WPF <xref:System.Windows.Controls.UserControl> 添加到 Windows 窗体 <xref:System.Windows.Forms.UserControl>来将 WPF 控件添加到操作窗格。  有关详细信息，请参阅[在 Office 解决方案中使用 WPF 控件](../vsto/using-wpf-controls-in-office-solutions.md)。  
  
3.  将自定义用户控件的实例添加到项目中 `ThisWorkbook`（针对 Excel）或 `ThisDocument`（针对 Word）类的 `ActionsPane` 字段中所内含的控件。  
  
 有关更详细演示此过程的示例，请参阅[如何：向 Word 文档或 Excel 工作簿添加操作窗格](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)。  
  
## 隐藏操作窗格  
 虽然 <xref:Microsoft.Office.Tools.ActionsPane> 类具有 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 方法和 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 属性，但不可通过使用 <xref:Microsoft.Office.Tools.ActionsPane> 类本身的任意成员从用户界面删除操作窗格。  调用 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 方法或将 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 属性设置为 **false** 只会隐藏操作窗格上的控件，而不会隐藏任务窗格。  
  
 若要隐藏解决方案中的任务窗格，可使用以下几个选项：  
  
-   对于 Word，请将表示文档操作任务窗格的 <xref:Microsoft.Office.Interop.Word.TaskPane> 对象的 <xref:Microsoft.Office.Interop.Word.TaskPane.Visible%2A> 属性设置为 **false**。  计划从项目的 `ThisDocument` 类中运行下列代码示例。  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#34](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#34)]
     [!code-vb[Trin_VstcoreActionsPaneWord#34](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#34)]  
  
-   对于 Excel，请将 <xref:Microsoft.Office.Tools.Excel.Workbook.Application%2A> 对象的 <xref:Microsoft.Office.Interop.Excel._Application.DisplayDocumentActionTaskPane%2A> 属性设置为 **false**。  计划从项目的 `ThisWorkbook` 类中运行下列代码示例。  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ThisWorkbook.vb#11)]  
  
-   对于 Word 或 Excel，还可以将表示任务窗格的命令栏的 <xref:Microsoft.Office.Core.CommandBar.Visible%2A> 属性设置为 **false**。  计划从项目的 `ThisDocument` 或 `ThisWorkbook` 类中运行下列代码示例。  
  
     [!code-csharp[Trin_VstcoreActionsPaneExcel#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ThisWorkbook.cs#9)]
     [!code-vb[Trin_VstcoreActionsPaneExcel#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ThisWorkbook.vb#9)]  
  
### 当文档打开时清除操作窗格  
 如果用户在操作窗格可见时保存文档，则无论操作窗格是否包含任何控件，每次文档打开时操作窗格都可见。  如果想在显示此窗格时进行控制，请调用 `ThisDocument` 或 `ThisWorkbook` 的 `Startup` 事件处理程序中 `ActionsPane` 字段的 <xref:Microsoft.Office.Tools.ActionsPane.Clear%2A> 方法，以确保操作窗格在文档打开时不可见。  
  
### 确定操作窗格何时关闭  
 操作窗格关闭时没有引发事件。  虽然 <xref:Microsoft.Office.Tools.ActionsPane> 类具有 <xref:Microsoft.Office.Tools.ActionsPane.VisibleChanged> 事件，但在最终用户关闭操作窗格时不会引发此事件。  相反，当通过调用 <xref:Microsoft.Office.Tools.ActionsPane.Hide%2A> 方法或将 <xref:Microsoft.Office.Tools.ActionsPane.Visible%2A> 属性设置为 **false** 来隐藏操作窗格上的控件时，将引发此事件。  
  
 如果最终用户关闭操作窗格，用户可以通过在应用程序的用户界面 \(UI\) 中执行下面其中一个过程来再次显示它。  
  
##### 通过使用 Word 或 Excel 的 UI 来显示操作窗格  
  
1.  在功能区上，单击**“查看”**选项卡。  
  
2.  在**“显示\/隐藏”**组中，单击**“文档操作”**切换按钮。  
  
## 操作窗格事件编程  
 你可以将多个用户控件添加到操作窗格，然后编写代码，以便通过显示和隐藏用户控件对文档上的事件做出响应。  如果将 XML 架构元素映射到文档，则在每次插入点位于其中一个 XML 元素的内部时都可在操作窗格中显示某些用户控件。  有关详细信息，请参阅[如何：将架构映射到 Visual Studio 内部的 Word 文档](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)和[如何：将架构映射到 Visual Studio 内部的工作表](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)。  
  
 你还可以编写代码以响应任意对象的事件，包括主机控件、应用程序或文档事件。  有关详细信息，请参阅[演练：根据 NamedRange 控件的事件进行编程](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)。  
  
## 将数据绑定到任务窗格上的控件  
 操作窗格上控件的数据绑定容量等于 Windows 窗体上控件的容量。  你可以将控件绑定到数据集、类型化数据集和 XML 等数据源。  有关详细信息，请参阅[数据绑定和 Windows 窗体](http://msdn.microsoft.com/library/419aac5e-819b-4aad-88b0-73a2f8c0bd27)。  
  
 可以将操作窗格上的控件和文档上的控件绑定到同一数据集。  例如，可以在操作窗格上的控件和工作表上的控件之间创建主\/从关系。  有关详细信息，请参阅[演练：将数据绑定到 Excel 操作窗格上的控件](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)。  
  
## 在操作窗格控件中验证数据  
 如果在操作窗格上控件的 <xref:System.Windows.Forms.Control.Validating> 事件处理程序中显示一个消息框，则可能在焦点从控件移动到消息框上时再次引发该事件。  若要避免此问题，请使用 <xref:System.Windows.Forms.ErrorProvider> 控件来显示任意验证错误消息。  
  
## 用户控件堆叠顺序  
 如果你正在使用多个用户控件，则无论用户控件是垂直停靠还是水平停靠，你都可以编写代码以在操作窗格上堆叠这些控件。  可以使用 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 属性的 <xref:Microsoft.Office.Tools.StackStyle> 枚举来设置操作窗格上用户控件的堆叠顺序。  有关详细信息，请参阅 [如何：管理操作窗格上的控件布局](../vsto/how-to-manage-control-layout-on-actions-panes.md)  
  
 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 属性可以接受下列 <xref:Microsoft.Office.Tools.StackStyle> 枚举值。  
  
|堆叠样式|定义|  
|----------|--------|  
|FromBottom|从操作窗格底部堆叠。|  
|FromLeft|从操作窗格左侧堆叠。|  
|FromRight|从操作窗格右侧堆叠。|  
|FromTop|从操作窗格顶部堆叠。|  
|None|未定义堆叠顺序；由开发人员控制顺序。|  
  
 下列代码将设置 <xref:Microsoft.Office.Tools.ActionsPane.StackOrder%2A> 属性，以从操作窗格顶部堆叠用户控件。  
  
 [!code-csharp[Trin_VstcoreActionsPaneExcel#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/CS/ThisWorkbook.cs#10)]
 [!code-vb[Trin_VstcoreActionsPaneExcel#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneExcel/VB/ThisWorkbook.vb#10)]  
  
## 定位控件  
 如果用户在运行时调整操作窗格的大小，则控件的大小可随操作窗格而变。  你可以使用 Windows 窗体控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性将控件定位到操作窗格。  还可以相同方式将 Windows 窗体控件定位到用户控件上。  有关详细信息，请参阅[如何：在 Windows 窗体上锚定控件](http://msdn.microsoft.com/library/59ea914f-fbd3-427a-80fe-decd02f7ae6d)。  
  
## 调整操作窗格的大小  
 无法直接更改 <xref:Microsoft.Office.Tools.ActionsPane> 的大小，因为 <xref:Microsoft.Office.Tools.ActionsPane> 内嵌在任务窗格中。  但是，通过设置表示任务窗格的 <xref:Microsoft.Office.Core.CommandBar> 的 <xref:Microsoft.Office.Core.CommandBar.Width%2A> 属性，即可以编程方式更改任务窗格的宽度。  无论任务窗格时水平停靠的还是浮动的，都可更改它的高度。  
  
 通常不建议以编程方式调整任务窗格的大小，因为用户应该能够选择最适合其需求的任务窗格大小。  但是，如果你必须调整任务窗格的宽度，可以使用下列代码来完成此任务。  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#102](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#102)]
 [!code-vb[Trin_VstcoreActionsPaneWord#102](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#102)]  
  
## 重新定位操作窗格  
 无法直接重新定位 <xref:Microsoft.Office.Tools.ActionsPane>，因为它内嵌在任务窗格中。  但是，通过设置表示任务窗格的 <xref:Microsoft.Office.Core.CommandBar> 的 <xref:Microsoft.Office.Core.CommandBar.Position%2A> 属性，即可以编程方式移动任务窗格。  
  
 通常不建议以编程方式重新定位任务窗格，因为用户应该能够选择最适合其需求的任务窗格位置。  但是，如果你必须将任务窗格移动到特定位置，可以使用下列代码来完成此任务。  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#100](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#100)]
 [!code-vb[Trin_VstcoreActionsPaneWord#100](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#100)]  
  
> [!NOTE]  
>  最终用户可随时手动重新定位任务窗格。  无法确保任务窗格将始终停靠在你以编程方式指示的位置。  但是，你可以检查方向更改，并确保操作窗格上的控件以正确的方向堆叠。  有关详细信息，请参阅[如何：管理操作窗格上的控件布局](../vsto/how-to-manage-control-layout-on-actions-panes.md)。  
  
 设置 <xref:Microsoft.Office.Tools.ActionsPane> 的 <xref:Microsoft.Office.Tools.ActionsPane.Top%2A> 和 <xref:Microsoft.Office.Tools.ActionsPane.Left%2A>性不会更改其位置，这是因为 <xref:Microsoft.Office.Tools.ActionsPane> 对象内嵌在任务窗格中。  
  
 如果任务窗格未停靠，则可设置表示任务窗格的 <xref:Microsoft.Office.Core.CommandBar> 的 <xref:Microsoft.Office.Core.CommandBar.Top%2A> 和 <xref:Microsoft.Office.Core.CommandBar.Left%2A> 属性。  下列代码将未停靠的任务窗格移动到文档的左上角。  
  
 [!code-csharp[Trin_VstcoreActionsPaneWord#101](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/CS/ThisDocument.cs#101)]
 [!code-vb[Trin_VstcoreActionsPaneWord#101](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreActionsPaneWord/VB/ThisDocument.vb#101)]  
  
## 请参阅  
 [在 Office 解决方案中使用 WPF 控件](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Office UI 自定义](../vsto/office-ui-customization.md)   
 [对 Office 项目中对象的全局访问](../vsto/global-access-to-objects-in-office-projects.md)   
 [如何：向 Word 文档或 Excel 工作簿添加操作窗格](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [演练：从操作窗格将文本插入到文档中](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [演练：将数据绑定到“Word 操作”窗格上的控件](../vsto/walkthrough-binding-data-to-controls-on-a-word-actions-pane.md)   
 [演练：将数据绑定到 Excel 操作窗格上的控件](../vsto/walkthrough-binding-data-to-controls-on-an-excel-actions-pane.md)   
 [如何：管理操作窗格上的控件布局](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [演练：从操作窗格将文本插入到文档中](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  