---
title: "演练： 复杂数据绑定在 VSTO 外接程序项目 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], Excel
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 95f8d2d30bb5d8bedfe70f0b15f9e956d91f4345
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-complex-data-binding-in-vsto-add-in-project"></a>演练：VSTO 外接程序项目中的复杂数据绑定
  可以将数据绑定到 VSTO 外接程序项目中的宿主控件和 Windows 窗体控件。 本演练演示如何在运行时向 Microsoft Office Excel 工作表中添加控件并将控件绑定到数据。  
  
 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]  
  
 本演练阐释了以下任务：  
  
-   在运行时将 <xref:Microsoft.Office.Tools.Excel.ListObject> 控件添加到工作表。  
  
-   创建用于将该控件连接到某个数据集实例的 <xref:System.Windows.Forms.BindingSource> 。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 或 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]。  
  
-   对附加了 `AdventureWorksLT` 示例数据库且正在运行的 SQL Server 2005 或 SQL Server 2005 Express 实例的访问权限。 你可以从 `AdventureWorksLT` CodePlex 网站 [下载](http://go.microsoft.com/fwlink/?LinkId=115611)数据库。 有关附加数据库的详细信息，请参阅下列主题：  
  
    -   若要使用 SQL Server Management Studio 或 SQL Server Management Studio Express 来附加数据库，请参阅 [如何：附加数据库 (SQL Server Management Studio)](http://msdn.microsoft.com/en-us/b4efb0ae-cfe6-4d81-a4b4-6e4916885caa)。  
  
    -   若要使用命令行来附加数据库，请参阅 [如何：将数据库文件附加到 SQL Server Express](http://msdn.microsoft.com/en-us/0f8e42b5-7a8c-4c30-8c98-7d2bdc8dcc68)。  
  
## <a name="creating-a-new-project"></a>创建新项目  
 第一步是创建 Excel VSTO 外接程序项目。  
  
#### <a name="to-create-a-new-project"></a>创建新项目  
  
1.  使用 Visual Basic 或 C# 创建一个名为“从数据库填充工作表” 的 Excel VSTO 外接程序项目。  
  
     有关详细信息，请参阅 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
     Visual Studio 会打开 `ThisAddIn.vb` 或 `ThisAddIn.cs` 文件，并将“从数据库填充工作表”  项目附加到“解决方案资源管理器” 中。  
  
## <a name="creating-a-data-source"></a>创建数据源  
 使用 **“数据源”** 窗口将类型化数据集添加到项目中。  
  
#### <a name="to-add-a-typed-dataset-to-the-project"></a>向项目中添加类型化数据集  
  
1.  如果 **“数据源”** 窗口不可见，则在菜单栏上，通过选择 **“查看”**， **“其他窗口”**、 **“数据源”**显示它。  
  
2.  选择 **“添加新数据源”** 以启动 **“数据源配置向导”**。  
  
3.  单击“数据库” ，然后单击“下一步” 。  
  
4.  如果已与 `AdventureWorksLT` 数据库建立连接，请选择此连接，然后单击“下一步” 。  
  
     否则，单击“新建连接” ，然后使用“添加连接”  对话框创建新连接。 有关详细信息，请参阅[添加新连接](../data-tools/add-new-connections.md)。  
  
5.  在“将连接字符串保存到应用程序配置文件中”  页中，单击“下一步” 。  
  
6.  在“选择数据库对象”  页中展开“表”  ，再选择“Address (SalesLT)” 。  
  
7.  单击 **“完成”**。  
  
     AdventureWorksLTDataSet.xsd 文件即会添加到“解决方案资源管理器” 中。 此文件定义以下各项：  
  
    -   一个名为 `AdventureWorksLTDataSet`的类型化数据集。 此数据集表示 AdventureWorksLT 数据库中“Address (SalesLT)”  表的内容。  
  
    -   名为 TableAdapter `AddressTableAdapter`。 此 TableAdapter 可用于读取和写入数据中`AdventureWorksLTDataSet`。 有关详细信息，请参阅 [TableAdapter Overview](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview)。  
  
     在本演练后面的部分中，你将使用这两个对象。  
  
## <a name="creating-controls-and-binding-controls-to-data"></a>创建控件并将控件绑定到数据  
 对于本演练，只要用户打开工作薄， <xref:Microsoft.Office.Tools.Excel.ListObject> 控件就会在所选表中显示所有数据。 列表对象使用 <xref:System.Windows.Forms.BindingSource> 将控件连接到数据库。  
  
 有关将控件绑定到数据的详细信息，请参阅 [Binding Data to Controls in Office Solutions](../vsto/binding-data-to-controls-in-office-solutions.md)。  
  
#### <a name="to-add-the-list-object-dataset-and-table-adapter"></a>添加列表对象、数据集和表适配器  
  
1.  在 `ThisAddIn` 类中，声明以下控件以显示 `Address` 数据集的 `AdventureWorksLTDataSet` 表。  
  
     [!code-csharp[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#1)]  
  
2.  在 `ThisAddIn_Startup` 方法中，添加以下代码以初始化数据集，并使用 `AdventureWorksLTDataSet` 数据集的信息来填充此数据集。  
  
     [!code-csharp[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#2)]  
  
3.  将以下代码添加到 `ThisAddIn_Startup` 方法中。 这会生成一个可扩展工作表的宿主项。 有关更多信息，请参见 [在运行时在 VSTO 外接程序中扩展 Word 文档和 Excel 工作簿](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)。  
  
     [!code-csharp[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#3)]  
  
4.  创建一个范围并添加 <xref:Microsoft.Office.Tools.Excel.ListObject> 控件。  
  
     [!code-csharp[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#4)]
     [!code-vb[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#4)]  
  
5.  使用 `AdventureWorksLTDataSet` 将列表对象绑定到 <xref:System.Windows.Forms.BindingSource>。 传入你想要绑定到列表对象的列的名称。  
  
     [!code-csharp[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#5)]
     [!code-vb[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#5)]  
  
## <a name="testing-the-add-in"></a>测试外接程序  
 打开 Excel 时， <xref:Microsoft.Office.Tools.Excel.ListObject> 会显示来自 `Address` 数据集的 `AdventureWorksLTDataSet` 表的数据。  
  
#### <a name="to-test-the-vsto-add-in"></a>若要测试 VSTO 外接程序  
  
-   按 F5 。  
  
     已在工作表中创建了一个名为 <xref:Microsoft.Office.Tools.Excel.ListObject> 的 `addressListObject` 控件。 同时，向项目添加了一个名为 `adventureWorksLTDataSet` 的数据集对象和一个名为 <xref:System.Windows.Forms.BindingSource> 的 `addressBindingSource` 。 已将 <xref:Microsoft.Office.Tools.Excel.ListObject> 绑定到 <xref:System.Windows.Forms.BindingSource>，而后者又绑定到该数据集对象。  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案中的数据](../vsto/data-in-office-solutions.md)   
 [将数据绑定到 Office 解决方案中的控件](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [如何： 用数据库中的数据填充工作表](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [如何： 用数据库中的数据填充文档](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [如何： 用服务中的数据填充文档](../vsto/how-to-populate-documents-with-data-from-services.md)   
 [如何： 用对象中的数据填充文档](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [如何： 在工作表中的数据库记录滚动](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [如何： 使用主机控件中的数据更新数据源](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [演练： 文档级项目中的简单数据绑定](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)   
 [演练： 文档级项目中的复杂数据绑定](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)   
 [使用 Office 解决方案概述中的本地数据库文件](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [添加新数据源](/visualstudio/data-tools/add-new-data-sources)   
 [在 Visual Studio 中将 Windows 窗体控件绑定到数据](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [使用 Office 解决方案概述中的本地数据库文件](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [连接到 Windows 窗体应用程序中的数据](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource 组件概述](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  