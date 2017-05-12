---
title: "演练：在 Visual Basic 项目中调用 VBA 中的代码"
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
  - "文档 [Visual Studio 中的 Office 开发]，Visual Basic for Applications 和"
  - "ThisDocument 类"
  - "Word [Visual Studio 中的 Office 开发]，从 VBA 中调用代码"
  - "Visual Basic [Visual Studio 中的 Office 开发]，从 VBA 中调用代码"
  - "VBA [Visual Studio 中的 Office 开发]，调用文档级自定义项中的代码"
  - "Office 文档 [Visual Studio 中的 Office 开发]，Visual Basic for Applications 和"
  - "从 VBA 中调用代码"
  - "文档级自定义项 [Visual Studio 中的 Office 开发]，调用代码"
ms.assetid: 798bc2fa-449e-4d1a-86b4-18e57b02a4a8
caps.latest.revision: 45
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# 演练：在 Visual Basic 项目中调用 VBA 中的代码
  本演练演示如何在 Microsoft Office Word 的文档级自定义项中从文档的 Visual Basic for Applications \(VBA\) 代码中调用方法。 该过程包括三个基本步骤：向 `ThisDocument` 主机项类添加方法，向 VBA 代码公开方法，然后从文档中的 VBA 代码调用方法。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 尽管本演练专门使用 Word，但本演练演示的概念也适用于 Excel 文档级项目。  
  
 本演练阐释了以下任务：  
  
-   创建一个包含 VBA 代码的文档。  
  
-   使用 Word 中的“信任中心”信任文档位置。  
  
-   向 `ThisDocument` 主机项类添加方法。  
  
-   向 VBA 代码公开方法。  
  
-   从 VBA 代码中调用方法。  
  
> [!NOTE]  
>  以下说明中的某些 Visual Studio 用户界面元素在计算机上出现的名称或位置可能会不同。 这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/zh-cn/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
## 系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## 创建包含 VBA 代码的文档  
 第一步是创建一个启用宏且包含简单 VBA 宏的文档。 该文档必须包含 VBA 项目，然后才能创建基于该文档的 Visual Studio 项目。 否则，Visual Studio 将无法修改 VBA 项目以允许 VBA 代码调入自定义项程序集。  
  
 如果已经拥有包含要使用的 VBA 代码的文档，可以跳过此步骤。  
  
#### 创建包含 VBA 代码的文档  
  
1.  启动 Word。  
  
2.  将活动文档另存为 Word**“启用宏的文档 \(\*.docm\)”**，命名为 **DocumentWithVBA**。 将文档保存在一个方便的位置，例如桌面。  
  
3.  在功能区上，单击**“开发人员”**选项卡。  
  
    > [!NOTE]  
    >  如果看不到**“开发人员”**选项卡，则必须首先显示它。 有关详细信息，请参阅[如何：在功能区上显示“开发人员”选项卡](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)。  
  
4.  在**“代码”**组中，单击**“Visual Basic”**。  
  
     将打开 Visual Basic 编辑器。  
  
5.  在**“项目”**窗口中，双击**“ThisDocument”**。  
  
     将打开 `ThisDocument` 对象的代码文件。  
  
6.  向代码文件中添加以下 VBA 代码。 此代码定义一个不执行任何操作的简单函数。 此函数的唯一作用是确保文档中有 VBA 项目。 这是本演练中的后续步骤所必需的。  
  
    ```  
    Sub EmptySub() End Sub  
    ```  
  
7.  保存文档并退出 Word。  
  
## 创建项目  
 现在即可创建 Word 文档级项目，该项目使用先前创建的启用宏的文档。  
  
#### 创建新项目  
  
1.  启动 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]。  
  
2.  在**“文件”**菜单上，指向**“新建”**，然后单击**“项目”**。 如果 IDE 设置为使用 Visual Basic 开发设置，请在**“文件”**菜单上，单击**“新建项目”**。  
  
3.  在模板窗格中，展开**“Visual Basic”**，然后展开**“Office\/SharePoint”**。  
  
4.  选择“Office 外接程序”节点。  
  
5.  在项目模板列表中，选择**“Word 2010 文档”**或**“Word 2013 文档”**项目。  
  
6.  在“名称”框中，键入 **CallingCodeFromVBA**。  
  
7.  单击“确定”。  
  
     将打开“Visual Studio Tools for Office 项目向导”。  
  
8.  选择**“复制现有文档”**，然后在**“现有文档的完整路径”**框中，指定先前创建的 **DocumentWithVBA** 文档的位置。 如果使用你自己的启用宏的文档，请改为指定此文档的位置。  
  
9. 单击**“完成”**。  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 将在设计器中打开 **DocumentWithVBA** 文档，并将**“CallingCodeFromVBA”**项目添加到**“解决方案资源管理器”**。  
  
## 信任文档的位置  
 向文档中的 VBA 代码公开解决方案中的代码之前，必须先信任 VBA 中的文档运行。 有若干方法可实现此操作。 对于本演练，在 Word 的**“信任中心”**信任文档的位置。  
  
#### 信任文档的位置  
  
1.  启动 Word。  
  
2.  单击**“文件”**选项卡。  
  
3.  单击**“Word 选项”**按钮。  
  
4.  在类别窗格中，单击**“信任中心”**。  
  
5.  在细节窗格中，单击**“信任中心设置”**。  
  
6.  在类别窗格中，单击**“受信任位置”**。  
  
7.  在细节窗格中，单击**“添加新位置”**。  
  
8.  在“Microsoft Office 受信任位置”对话框中，浏览到包含 **CallingCodeFromVBA** 项目的文件夹。  
  
9. 选择**“同时信任此位置的子文件夹”**。  
  
10. 在**“Microsoft Office 受信任位置”**对话框中，单击**“确定”**。  
  
11. 在**“信任中心”**对话框中，单击**“确定”**。  
  
12. 在**“Word 选项”**对话框中，单击**“确定”**。  
  
13. 退出 Word。  
  
## 向 ThisDocument 类添加方法  
 现在已设置 VBA 项目，请向可以从 VBA 代码调用的 `ThisDocument` 主机项类添加方法。  
  
#### 向 ThisDocument 类添加方法  
  
1.  在**“解决方案资源管理器”**中，右键单击**“ThisDocument.vb”**，然后单击**“查看代码”**。  
  
     **ThisDocument.vb** 文件将在代码编辑器中打开。  
  
2.  将以下方法添加到 `ThisDocument` 类。 此方法将在文档的开头创建一个具有两行和两列的表格。 参数指定在第一行中显示的文本。 在本演练中，稍后将从文档中的 VBA 代码调用此方法。  
  
     [!code-vb[Trin_CallingVBCustomizationFromVBA#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CallingVBCustomizationFromVBA/VB/ThisDocument.vb#1)]  
  
3.  生成项目。  
  
## 向 VBA 代码公开方法  
 若要向文档中的 VBA 代码公开 `CreateTable` 方法，请将 `ThisDocument` 主机项的**“EnableVbaCallers”**属性设置为**“True”**。  
  
#### 向 VBA 代码公开方法  
  
1.  在**“解决方案资源管理器”**中，双击 **ThisDocument.vb**。  
  
     **DocumentWithVBA** 文件将在设计器中打开。  
  
2.  在**“属性”**窗口中，选择**“EnableVbaCallers”**属性，并将值改为**“True”**。  
  
3.  在显示的消息中单击**“确定”**。  
  
4.  生成项目。  
  
## 从 VBA 代码中调用方法  
 现在即可从文档中的 VBA 代码调用 `CreateTable` 方法。  
  
> [!NOTE]  
>  在本演练中，你将在调试项目时向文档添加 VBA 代码。 在下次生成项目时，添加到此文档中的 VBA 代码将被覆盖，因为 Visual Studio 会将生成输出文件夹中的文档替换为主项目文件夹中文档的副本。 如果想要保存 VBA 代码，可以将其复制到项目文件夹中的文档。 有关详细信息，请参阅[结合 VBA 和文档级自定义项](../vsto/combining-vba-and-document-level-customizations.md)。  
  
#### 从 VBA 代码调用方法  
  
1.  按 F5 运行项目。  
  
2.  在**“开发人员”**选项卡上的**“代码”**组中，单击**“Visual Basic”**。  
  
     将打开 Visual Basic 编辑器。  
  
3.  在**“插入”**菜单上，单击**“模块”**。  
  
4.  向新模块添加以下代码。  
  
     此代码调用自定义项程序集中的 `CreateTable` 方法。 宏通过使用 `ThisDocument` 对象的 `CallVSTOAssembly` 属性访问此方法。 此属性是你在本演练前面部分设置**“EnableVbaCallers”**属性时自动生成的。  
  
    ```  
    Sub CreateTable() Call ThisDocument.CallVSTOAssembly.CreateTable("Employee Name", "Start Date") End Sub  
    ```  
  
5.  按 F5。  
  
6.  验证新表格已添加到文档。  
  
7.  退出 Word 但不保存更改。  
  
## 后续步骤  
 在以下主题中，你可以了解有关从 VBA 调用 Office 解决方案中的代码的详细信息：  
  
-   从 VBA 调用 Visual C\# 自定义项中的代码。 此过程不同于 Visual Basic 过程。 有关更多信息，请参见[演练：在 Visual C&#35; 项目中调用 VBA 中的代码](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)。  
  
-   从 VBA 调用 VSTO 外接程序中的代码。 有关详细信息，请参阅[演练：从 VBA 调用 VSTO 外接程序中的代码](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)。  
  
## 请参阅  
 [结合 VBA 和文档级自定义项](../vsto/combining-vba-and-document-level-customizations.md)   
 [对文档级自定义项进行编程](../vsto/programming-document-level-customizations.md)   
 [如何：向 VBA 公开 Visual Basic 项目中的代码](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [如何：向 VBA 公开 Visual C&#35; 项目中的代码](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [演练：在 Visual C&#35; 项目中调用 VBA 中的代码](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)  
  
  