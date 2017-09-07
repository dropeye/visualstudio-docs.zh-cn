---
title: "Visual Studio 的复合模式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e48ecfb2-f4b5-4d3a-b4a2-7a4d62fa4ec0
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# Visual Studio 的复合模式
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

复合模式组合不同的配置中的交互和设计元素。 在 Visual Studio 中的一致性方面的最重要复合模式包括︰  
  
-   [数据可视化](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_DataVisualization)  
  
-   [对象上的用户界面和查看](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_OnObjectUI)  
  
-   [选择模型](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_SelectionModels)  
  
-   [持久性和保存设置](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_PersistenceAndSavingSettings)  
  
-   [触摸输入](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_TouchInput)  
  
##  <a name="a-namebkmkdatavisualizationa-data-visualization"></a><a name="BKMK_DataVisualization"></a> 数据可视化  
  
### <a name="overview"></a>概述  
 图表是以直观的方式进行聚合并将数据可视化以便增强决策制定过程。 它们可以帮助用户面对大量的数据，但很少，则表示看到什么都应该关注而且哪些方面可能需要一项操作。  
  
 如果任意下列条件为 true，用户将从图表中受益︰  
  
-   图表将帮助用户识别的任务能够对吗？  
  
-   图表将使用户能够预测结果可能存在的更改？  
  
-   图表将帮助用户发现趋势和识别模式？  
  
-   图表将使用户可以更好的决策？  
  
-   图表将帮助解答用户可能具有给定的上下文中的特定问题？  
  
#### <a name="general-rules-for-charts"></a>用于图表的一般规则  
  
-   清楚地标签数据。 而无需解释图例只是美感和实用性。  
  
-   启动为零，以避免扭曲比例的轴。 行长度和栏大小是重要的视觉提示，了解数据点之间的关系。  
  
-   创建图表，不信息图。 信息图是艺术的表示形式的数据，以及其主要目标是可视的讲故事。 图表可以 （并且应该） 是好的视觉效果，但让数据自己说话。  
  
-   避免 skeumorphism、 图形化的条形图、 对比度 hashmarks 和其他信息图收尾工作。  
  
-   不要将三维效果用作装饰元素。 仅当使用这些它们真正不可或缺的一部分用户是否能够理解的信息。  
  
-   避免使用多个线条和填充，因为两个以上的颜色可以进行这种图表类型难以阅读和正确解释。  
  
-   不使用图表 （或任何图） 作为了解一个概念或与数据进行交互的唯一方法。 这会带来有视觉障碍的用户的问题。  
  
-   不要将图表用作页面上的不必要或装饰性元素。 换而言之，如果图表不会添加任何值或帮助用户解决问题，不要使用它。  
  
### <a name="chart-types"></a>图表类型  
 在 Visual Studio 中使用的图表的类型包括条形图、 折线图、 已修改的饼图称作 ring 图表或"圆环图图表，"时间线，散点图 （也称为"群集图表"） 和甘特图。 每种类型是信息的图表的用于传达不同类型。  
  
### <a name="other-charting-considerations"></a>图表的其他注意事项  
  
#### <a name="color"></a>颜色  
 没有一个特定的图表定义 Visual Studio 中使用的颜色调色板。 调色板进行访问的主要类型的色盲，并可以区分颜色，即使使用为范围非常窄扇区的颜色。 您可以使用这些颜色中以任意组合的任何类型的图表或图形中您的 UI。 不需要使用所有七个颜色，如果您不需要那么多不同的颜色。 这些颜色不旨在用于任何前台元素，因此，不要将文本或基于这些颜色的标志符号。 应硬编码和向下的用户自定义公开这些色调 **工具 > 选项** (请参阅 [为最终用户公开颜色](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers))。  
  
|样本|十六进制|RGB|  
|------------|---------|---------|  
|![样本 71B252](../../extensibility/ux-guidelines/media/0711_71b252.png "0711_71B252")|#71B252|113,178,82|  
|![样本 BF3F00](../../extensibility/ux-guidelines/media/0711_bf3f00.png "0711_BF3F00")|#BF3F00|191,63,0|  
|![样本 FCB714](../../extensibility/ux-guidelines/media/0711_fcb714.png "0711_FCB714")|#FCB714|252,183,20|  
|![样本 903F8B](../../extensibility/ux-guidelines/media/0711_903f8b.png "0711_903F8B")|#903F8B|144,63,139|  
|![样本 117AD1](../../extensibility/ux-guidelines/media/0711_117ad1.png "0711_117AD1")|#117AD1|17,122,209|  
|![样本 79D7F2](../../extensibility/ux-guidelines/media/0711_79d7f2.png "0711_79D7F2")|#79D7F2|121,215,242|  
|![样本 B5B5B5](../../extensibility/ux-guidelines/media/0711_b5b5b5.png "0711_B5B5B5")|#B5B5B5|181,181,181|  
  
##  <a name="a-namebkmkonobjectuia-on-object-ui-and-peeking"></a><a name="BKMK_OnObjectUI"></a> 对象上的用户界面和查看  
 本部分将对查看，也称为代码查看视图中，一种类型的对象上的用户界面到 Visual Studio 唯一给上下文。  
  
### <a name="overview"></a>概述  
  
-   对象上的 UI 应为用户提供更多的信息或交互功能而无需使其主要任务。  
  
-   在 Visual Studio 中的对象上的 UI 的主模式被称为"在关注点的信息。"  
  
-   Visual Studio 中的对象上的用户界面是既内联或浮点和持久或过渡状态。  
  
    -   代码窥视视图中，一种类型的对象上的用户界面在 Visual Studio 中，是内联和持久。  
  
    -   CodeLens、 一种类型的对象上的用户界面在 Visual Studio 中，是浮点型和暂时性  
  
 了解如何工作的一段代码，或查找有关该代码的详细信息通常需要开发人员可将上下文切换，并转到其他内容或另一个窗口。 这些上下文变化可能中断性的因为如果他们离开其主窗口中，用户可能会丢失其初始任务的焦点。 此外，获取原始上下文后，可能很困难，尤其当切换窗口导致原始代码，以便其他用户界面被遮盖。  
  
 对象上的用户界面遵循模式称为"在关注点的信息。" 这些消息、 弹出窗口和对话框向用户提供附加的相关而不会丢失专注于其主要任务添加说明或交互功能的信息。 对象上的用户界面的示例包括当用户悬停在通知区域中的图标、 拼错的单词，并在 Visual Studio 2013 中引入的扫视视图下的红色波形曲线上其指针时出现的弹出窗口。  
  
### <a name="decision-points"></a>决策点  
 在 Visual Studio 中，有多种方式来使用此模式在关注点的信息。 选择适当的机制和实现一致、 可预测的方式是至关重要的总体体验。 否则，用户可能会出现提供了会影响焦点从内容本身的混乱或不一致的体验。  
  
#### <a name="relationships-between-master-and-detail-content"></a>母版和详细信息内容之间的关系  
 在关注点的信息用于显示关系内容之间的用户是专注于 （"主"内容） 和其他相关内容 （"详细信息"内容）。 在此模式中，详细信息内容清楚地与用户正在使用的内容，可以显示接近母版页的内容。 补充信息或不能进行汇总而无需使不堪重负母版页的内容的信息应按照另一种模式，如工具窗口。  
  
-   **始终** 在较近的母版内容中显示详细信息内容。  
  
-   **始终** 确保详细信息内容仍使用户能够专注于母版的内容。 通常，实现此目的的最好办法是呈现作为接近作为可能的主内容的详细信息内容。 这可在呈现中的主内容旁边的弹出窗口的详细信息内容或呈现下方母版页的内容的详细信息内容内联。  
  
-   **永远不会** 使用在采用用户将无法访问主内容的关注点的信息。 如果用户需要分别查看详细信息内容，公开使用户能够执行此操作的显式操作。  
  
#### <a name="design-details"></a>设计详细信息  
 确定对象上的用户界面是正确的选择后，有四个主要设计注意事项︰  
  
1.  **持久性︰** 内容应为持久的还是暂时？   
    用户想要的信息保持可见，请参阅或与之交互？ 或者，将用户想要快速查看信息，然后继续进行其主要任务？  
  
2.  **内容类型︰** 内容将信息性、 可操作，或者导航？   
    用户是否需要有关主内容的更多详细信息？ 用户是否需要完成一个任务，它会影响主内容？ 或者，用户需要位于和定向到另一个资源？  
  
3.  **指示器类型︰** 那么环境的指示符有意义？   
    可信息汇总以有用的方式和显示，而无需使不堪重负母版页的内容？  
  
4.  **手势︰** 什么笔势均将用于调用并解除 UI？   
    如何将用户显示的详细信息内容并将其发送消失吗？ 添加手势如钉住暂时性的而且持久状态之间进行切换中是否有值？  
  
 每个四个决策点会产生影响的对象上的用户界面的主要组件。  
  
### <a name="on-object-ui-components"></a>对象上的用户界面组件  
  
1.  容器 （内容表示器） 类型  
  
    -   浮动  
  
    -   内联  
  
2.  内容类型  
  
    -   可能是静态或动态的信息︰ 数据  
  
    -   更改主内容的可操作︰ 命令  
  
    -   将用户带到另一个窗口或应用程序，如 MSDN 的导航︰ 链接  
  
3.  笔势  
  
    -   调用  
  
    -   开除  
  
    -   钉住  
  
    -   其他交互  
  
4.  持久性和提交模型  
  
    -   瞬态  
  
    -   Durable  
  
    -   自动  
  
    -   按需  
  
5.  环境指示器 （可选）  
  
    -   波浪线下划线  
  
    -   智能标记图标  
  
    -   其他环境的指示符  
  
#### <a name="container-content-presenter-type"></a>容器 （内容表示器） 类型  
 有两个主要选项可用于呈现在关注点的内容︰  
  
1.  **内联︰** 内联演示者，如在 Visual Studio 2013 代码编辑器中，引入了扫视视图得到的新内容的空间，通过转换现有内容。  
  
    -   **喜欢** 提供内联演示者如果希望用户可能需要花费大量时间指或与内容交互。  
  
    -   **避免** 内联演示者如果希望用户将需要粗略地看一下您呈现，然后继续以最低的中断其主要任务的信息。  
  
2.  **浮点︰** 浮点表示器位于尽可能接近尽可能所选内容，但是不会更改现有内容的布局。 可采用各种策略，例如，通过显示浮动内容面板最近的可用的空白区域，选定的符号。  
  
    -   **喜欢** 浮点演示者，如果希望用户将需要粗略地看一下您呈现，然后继续以最低的中断其主要任务的信息。  
  
    -   **避免** 浮点演示者，如果希望用户将需要花费大量时间指或与内容交互您存在。  
  
#### <a name="content-type"></a>内容类型  
 有三种主要类型的可以显示在对象上的用户界面的任何容器内的内容。 可以显示这些类型的信息的任意组合。 有三种类型︰  
  
1.  **信息︰** 大多数对象上的 UI 容器将显示某种类型的信息性内容。 内容可以表示环境的当前状态有关的信息，或者它可能表示环境的潜在未来的状态有关的信息。 例如，它可以用于显示特定的命令，如重构，对现有代码的效果。  
  
    -   **始终** 使用的规范表示形式显示的信息。 例如，代码应如下所示代码中完成，但语法突出显示，并应遵守任何字体和其他用户所设置的环境设置。  
  
    -   **始终** 则应考虑的信息性内容中，如果主内容形式显示报表相同的信息可能会通过支持的任何操作。 例如，如果提供的对象上的 UI 容器中的现有代码，强烈建议考虑支持浏览和修改该代码的能力。  
  
    -   **始终** 如果考虑使用不同的背景色显示信息性内容表示潜在未来的状态。  
  
2.  可操作︰ 一些对象上的 UI 容器将提供对主内容，如执行重构操作执行某些操作的能力。  
  
    -   **始终** 定位独立于信息性内容可操作的命令。  
  
    -   **始终** 启用和禁用操作在适当的时候。  
  
    -   **始终** 指表示对话框中的命令的标准准则。  
  
    -   **始终** 绝对对象上的 UI 容器中公开的操作的数量保持在最小值。 与对象上的 UI 交互应是轻量、 快速的体验。 用户不一定非要花费精力管理的对象上的 UI 容器本身。  
  
    -   **始终** 考虑何时以及如何将关闭或解除对象上的 UI 容器。 作为最佳做法，最后，对话框中的母版和详细信息内容之间的任何操作也应该关闭对象上的 UI 容器，调用该操作时。  
  
3.  **导航︰** 某些对象上的 UI 容器包括能够将用户带到另一个窗口或应用程序，例如在用户的 web 浏览器中打开 MSDN 文章的链接。  
  
    -   **始终** 前面带有"打开"的任何导航链接添加，以便用户将不会感到惊讶要导航到某些其他内容。  
  
    -   **始终** 单独从可操作的链接的导航链接。  
  
#### <a name="ambient-indicators-optional"></a>环境指示器 （可选）  
 环境的指示器可以是代码的细微，其中包括从其余，一种对比颜色中显示的文本或显而易见的包括 tickler 符号，例如波形曲线下划线和智能标记图标。 环境指示器通信相关的其他信息的可用性。 理想情况下，它们提供有用的信息甚至无需用户与之交互。  
  
-   **始终** 定位环境的指示符，以便它不会打乱或用户。 如果无法按照这种方式定位环境指示器，请考虑另一种解决方案。  
  
-   **始终** 环境指示器与相关的内容尽可能近的位置。  
  
-   **始终** 尝试创建一个指示符，总结了可提供的信息。 请考虑提供的可用数据项目数的计数 （例如，"3 个引用"而不是只需"参考"），或者认为的某种其他方式来汇总数据。  
  
    -   在其中一个指示器的数据无法始终计算和显示的情况下，立即考虑提供渐进式反馈，如计算的值。 例如，考虑反映到可用的数据，类似于电子邮件动态磁贴在 Windows Phone 上的刷新未读的电子邮件会增加的数量相同的方式更新的更改进行动画处理。  
  
-   **永远不会** 添加多个指示器不是用户可以合理地执行给定的一段的内容。 环境指示器应非常有用，而无需用户进行任何互动。 如果它们需要溢出和其他管理控件以将它们放入视图，指示器会丢失其环境。  
  
#### <a name="gestures"></a>笔势  
 这样就允许用户继续关注于母版的内容的一个重要方面是通过支持右的手势，即可打开和关闭的更多详细信息内容。  
  
-   **始终** 需要用户执行某些显式的手势，若要打开的其他内容。 常见打开手势包括︰  
  
    -   **悬停时︰** 工具提示或非交互的信息性内容  
  
    -   **显式命令︰** 内联演示者  
  
    -   **双击环境标记︰** CodeLens 弹出窗口  
  
-   **始终** 每当用户按 Esc 键关闭的详细信息内容。  
  
-   **始终** 考虑对象上的用户界面的上下文。 允许在容器内的交互的内容表示器，请仔细考虑是否显示其他信息的悬停时，它很可能会破坏用户的工作流。  
  
-   **永远不会** 似乎是可编辑或邀请用户交互的悬停时显示的内容。 如果他们尝试将光标悬停在详细信息内容作为工具提示的标准行为是光标位于时不能再通过主生成它的内容立即关闭此行为可以让用户感到失望。  
  
##  <a name="a-namebkmkselectionmodelsa-selection-models"></a><a name="BKMK_SelectionModels"></a> 选择模型  
  
### <a name="overview"></a>概述  
 选择模型是用来指示和确认的用户界面中相关的一个或多个对象上的操作的机制。 本主题讨论在 Visual Studio 文档编辑器内的所选内容交互模式︰ 文本编辑器、 设计曲面和建模图面。  
  
 用户必须具有一种方法，该值指示对 Visual Studio 他们在做什么，和 Visual Studio 必须响应可预见的方式提供反馈有关它在操作的用户。 在用户和用户界面之间的交流不畅或之间的差异可能导致用户不会注意到的操作，这将产生意外的结果。 通常情况下，该错误不明显，直到用户将看到的内容丢失，或已更改。 选择模型因此是一个用户界面设计的最关键部分。 在 Visual Studio 中的所选内容模型是与 Windows 保持一致，尽管有细微的变体。  
  
 在 Visual Studio 中，例如在窗口中，选择模型而异发生交互操作的上下文。 选择可能出现在四种对象类型︰  
  
-   Text  
  
-   图形对象  
  
-   列表和树  
  
-   网格  
  
 这些对象中有三种类型的选择︰  
  
-   连续  
  
-   不连续的  
  
-   Region  
  
#### <a name="scope"></a>范围  
 所选内容的最重要的组件确保用户知道他们正在哪个窗口中处理 （激活） 和焦点的位置 （选择） 的位置。 Visual Studio 扩展的窗口管理功能在 Windows 中，但激活方案都是相同︰ 与窗口交互将焦点移到窗口中。 Visual Studio 提供了用于激活的两个指示器︰ 一个用于文档窗口，一个工具窗口。  
  
 对于文档窗口中，由一个文档窗口选项卡到前面即将发生和更改其背景色指示活动窗口中︰  
  
 ![Visual Studio 中的“活动”选项卡选择](../../extensibility/ux-guidelines/media/0713-01_activetab.png "0713-01_ActiveTab")  
  
 **活动选项卡上所选内容**  
  
 工具窗口的活动窗口中的工具窗口的标题栏区域的颜色的更改表示︰  
  
 ![Visual Studio 中的”活动”工具窗口选择](../../extensibility/ux-guidelines/media/0713-02_activetoolwindow.png "0713-02_ActiveToolWindow")  
  
 **活动工具窗口中显示的节点的主要选择**  
  
 ![Visual Studio 中的”非活动”工具窗口选择](../../extensibility/ux-guidelines/media/0713-03_inactivetoolwindow.png "0713-03_InactiveToolWindow")  
  
 **显示潜在选择的节点的非活动状态的工具窗口**  
  
 后一个窗口处于活动状态，根据这些准则的此部分中所述的所选内容模型表示其焦点。  
  
#### <a name="context"></a>上下文  
 Visual Studio 旨在保留强概念的上下文中，跟踪用户正在使用。 只能有一个窗口处于活动状态，，无论它是工具或文档窗口。 但是，最顶层的文档窗口始终保留潜在的所选内容。 尽管焦点可能是在工具窗口中，最后处于活动状态的文档窗口显示所选内容，即使在非活动状态。 这样做是为了保留它们所编辑的向他们展示 Visual Studio 已保留其状态，以便他们能够返回和工具窗口和文档窗口之间无缝移动的文档中的用户的上下文。  
  
### <a name="text-selection"></a>所选文本  
 Visual Studio 编辑器中严格文本，例如内置的文本编辑器中，使用相同的文本选择模型和外观中所述 [鼠标和指针](https://msdn.microsoft.com/en-us/library/dn742466.aspx) 的 Windows 用户体验交互准则在 MSDN 上的页。 在文本编辑器中的输入的焦点的竖线称为插入点指示。 插入点位于粗线和其后面出现的任何内容的逆向彩色的单一像素。 根据设置的速率，它就闪烁 **光标闪烁频率** 中设置 **速度** 的选项卡上 **键盘** 控制面板中的小程序。  
  
#### <a name="contiguous-and-disjoint-selection"></a>连续和非连续选择  
 在文本编辑器中的选择才连续。 不连续的文本选择不允许使用，但应该解决图形对象编辑器中。 当用户的鼠标指针位于文本区域时，光标将变为 i 形标记。 一次单击将插入点放置在文本编辑器中的单击位置中。 按住鼠标左键选择突出显示前后松开鼠标按钮选择突出显示。  
  
#### <a name="region-selection-box-selection"></a>选择区域 （框中选择）  
 Visual Studio 在文本编辑器中，支持区域的选择，这称为框选择。 框中选择允许用户选择不遵循以下常规文本流的文本的区域。 与标准文本选择所选内容必须是连续的。 在使用鼠标拖动的同时按住 Alt 键来启动框选择。 也可以按住 Alt 和 Shift 键并使用箭头键以指示所选内容的区域中启动框选择。 框中选择使用普通选择突出显示，并演示插入点光标闪烁的所选内容区域的末尾。  
  
 ![区域 #40; 框 &#41;在 Visual Studio 中的选定内容](../../extensibility/ux-guidelines/media/0713-04_boxselection.png "0713-04_BoxSelection")  
  
 **Visual Studio 中的区域 （框） 选择**  
  
#### <a name="text-selection-appearance"></a>文本选定内容的外观  
 可以自定义用于在编辑器中的活动和非活动选择的颜色。 若要自定义编辑器的可视外观，用户可以转到 **工具 > 选项**, ，然后查看下 **环境 > 字体和颜色 > 文本编辑器**。  
  
### <a name="graphical-selection"></a>图形所选内容  
  
#### <a name="interaction"></a>交互  
 图形对象选择可能十分复杂，而且取决于多种因素︰  
  
-   **编辑器的主选定内容模型。** 包含图形对象的编辑器还可以用于编辑文本或网格。 例如，编辑器中可能是一种基于文本的编辑器，还支持图形对象，如 Visual Studio XAML 设计器的位置。 支持多个对象类型可能会影响如何在用户选择的不同类型的对象组成的组。  
  
-   **对主要和次要选择状态提供支持。** 编辑器可以提供主要和次要选择状态，以便对象可以编辑发挥作用，相互对齐，调整大小在一起，依次类推。  
  
-   **就地编辑支持。** 编辑器还可以允许其图形对象要编辑的内容。 例如，矩形形状还可能包含上的用户可以更改内的文本。 此外，该文本可以居中或两端对齐。 就地编辑涉及用户交互的更详细的级别，因此需要一组适当的视觉提示用于向用户显示状态信息。  
  
#### <a name="mouse-interaction"></a>鼠标交互  
  
|输入|结果|  
|-----------|------------|  
|单击未选定的对象|选择的对象并显示一条虚线和选择控点，如果对象是可调整大小。|  
|单击所选的对象|激活就地编辑如果对象支持它。 单击对象以外的区域禁用就地编辑模式。|  
|双击某个对象|此时将打开代码隐藏的对象进行编辑，并根据可能插入默认事件处理程序。|  
|指向的对象|将指针更改到移动光标。 对象的外观，例如，其亮度或颜色，可能会更改。|  
|指向一个选择控点|将指针更改为调整大小的光标。 对于支持旋转的对象，某些所选内容句柄可能会将指针更改为旋转游标为指针定位以不同的方式 （例如，远一点移动） 方面的选择控点。|  
|拖动|即使以前未选择该对象，将指针更改为移动光标并将对象移动。|  
|编辑器失去焦点|停用的就地编辑模式下，尽管对象所保留的内容和在其最后一个操作/选择状态过程具有的外观。|  
|所选对象|由边框、 点线或其他在视觉上不同的处理，就可以突出显示该对象的边界来表示。|  
|调整所选的对象的大小|由所选内容句柄。<br /><br /> 可调整大小的对象具有八个控点，表示在其中可以调整大小的每个方向。 如果该对象仅在某些方向上可调整大小，则可能使用较少的句柄。 当用户调整到其中八个句柄不会交互的对象的大小时，则可使用四个句柄。 句柄大小应限于使用的窗口边框和边缘指标 **GetSystemMetrics** API 函数根据按比例显示分辨率的大小。<br /><br /> ![调整大小图柄](../../extensibility/ux-guidelines/media/0713-05_resizehandles.png "0713-05_ResizeHandles")|  
|旋转选定的对象|![旋转句柄](../../extensibility/ux-guidelines/media/0713-06_rotate.png "0713-06_Rotate")|  
  
#### <a name="keyboard-interaction"></a>键盘交互  
  
|输入|结果|  
|-----------|------------|  
|Tab|在编辑器中移动焦点指示符之间的对象的逻辑顺序。 这可能是从左到右还是从顶部到底部具体取决于 **TabIndex** （或等效） 属性值、 对象创建的顺序和编辑器的全部用途。 按 shift + Tab 将反转焦点指示器的方向。|  
|空格键|激活平移模式，而维护击键。 需要其他鼠标输入可以移动视区位置。|  
|Ctrl+空格键|而维护击键将激活缩放模式。 需要其他鼠标输入来增加和减少缩放系数。|  
|Ctrl + Alt + 减号|降低一个级别的缩放因子。|  
|Ctrl + Alt + 加号|增加了一级的缩放因子。|  
|Shift 或 ctrl 键|将对象添加到选择组。 Ctrl 还允许您从选择组分别删除对象。|  
|Enter|对象执行默认命令 （通常会打开或编辑）。|  
|F2|激活的对象进行就地编辑。|  
|箭头键|将所选的对象移动的方向箭头键，以较小增量 （例如，一次的 1 像素）|  
|Ctrl + 箭头键|将所选的对象移动的方向箭头键按下，较大的增量 （例如，一次的 10 个像素）|  
|Shift + 箭头键|调整所选对象在各自的方向，以较小增量 （例如，一次的 1 像素）|  
|Ctrl + Shift + 箭头键|调整所选对象在各自的方向，以较大的增量 （例如，一次的 10 个像素）|  
  
 当用户编辑控件就绪后的时，可能有意义的对象需要用户输入自动调整大小。 例如，如果用户编辑标签控件，然后标签应将增大以显示用户刚刚键入的文本。 如果不执行此操作，用户必须手动调整大小控件编辑的文本之后。 如果用户拥有大量控件，这变得机械和用于生产任务。  
  
#### <a name="graphical-containers"></a>图形容器  
 在某些情况下，图形编辑器对于其他图形对象，如 Windows 窗体 Panel 控件或 HTML 设计器中的网格布局控件提供容器。 如果您的编辑器的其他图形对象提供容器，然后应为容器仅 （对象在容器按照上面描述的标准模型作为） 使用以下所选内容模型︰  
  
|输入|结果|  
|-----------|------------|  
|单键单击容器上|选定的容器对象而无需直接选择任何包含的对象。 容器可能移动并且/或者随标准鼠标和键盘输入 （如上文所述） 一起调整大小。 包含的对象在关系中移动到容器，但除非还直接选择它们包含的对象无法调整大小。|  
|将鼠标悬停在容器的边界区域|移动光标，，指示可以移动该容器将变成鼠标。|  
|将容器的边界区域拖动|移动光标将变为鼠标并将移动的容器 （及其内包含的对象）。 容器不能移动而不必首先选中一次单击。|  
|单击在容器内的对象|取消选择该容器 （如果处于选中状态），并选择仅将被单击的对象。|  
|Shift + 单击或 ctrl 键并单击包含的对象和/或容器上|将被单击的对象添加到现有的选择或选择组。 如果已单击的对象已存在的选择组成员，它是从选择组中删除。|  
  
 包含的对象应遵循的基本选择模型中上一节所述。 从可用性测试的 Windows 窗体设计器，用户应包含的对象的无缝访问而无需干预的步骤 （施加的包含对象）。  
  
#### <a name="disjoint-and-region-selections"></a>非连续和区域选择  
 图形对象编辑器应支持不相互连接的选择。 请注意，此图形不显示 Visual Studio 的控件外观。 请参阅 [图形对象选择外观](../../extensibility/ux-guidelines/composite-patterns-for-visual-studio.md#BKMK_GraphicalObjectSelectionAppearance) 对详细 visual 规范。  
  
 ![非连续选择器和区域选择器](../../extensibility/ux-guidelines/media/0713-07_disjointregionselectors.png "0713-07_DisjointRegionSelectors")  
  
 **不连续的所选内容**  
  
 图形编辑器还应提供字幕类型选择指示符的区域选择。 如果图形编辑器支持其他对象类型 （如文本），然后区域选择可能无法根据这些其他对象类型的约束。  
  
 ![字幕选择](../../extensibility/ux-guidelines/media/0713-08_marqueeselection.png "0713-08_MarqueeSelection")  
  
 **字幕选择**  
  
#### <a name="primary-and-secondary-selections"></a>主要和次要选择  
 某些图形对象编辑器允许用户编辑或对齐组中的对象。 在这种情况下，这一概念主要和次要选择内容的需要，将会推出。 主要选择是所有其他对象响应操作进行分组的对象。 用户第一次选择的对象将成为主控件，并且后续选择成为辅助选项。 为主选择具有不同的视觉处理从第二的选择，以指示哪些对象是主︰  
  
 ![主要和次要选择](../../extensibility/ux-guidelines/media/0713-09_primarysecondary.png "0713-09_PrimarySecondary")  
  
 **具有两个辅助选项的主要选择**  
  
####  <a name="a-namebkmkgraphicalobjectselectionappearancea-graphical-object-selection-appearance"></a><a name="BKMK_GraphicalObjectSelectionAppearance"></a> 图形对象选择外观  
 选择控点都按矩形模式的边界框的对象周围绘制的方块。 下图显示图形对象都可以有句柄、 大小调整，与就地编辑外观的各种状态的示例。 句柄大小应绑定到窗口边框和边缘度量值使用 **GetSystemMetrics** API。  
  
|状态|外观|可视的详细信息|  
|-----------|----------------|--------------------|  
|**处于未选中状态**|默认|![默认按钮状态](../../extensibility/ux-guidelines/media/0713-10_defaultstate.png "0713-10_DefaultState")||  
|**主要选择**|可调整大小|![具有重设大小句柄的主要选择](../../extensibility/ux-guidelines/media/0713-11_primaryresize.png "0713-11_PrimaryResize")|![具有的主要选择调整大小控点和 #40; 放大 &#41;](../../extensibility/ux-guidelines/media/0713-12_primaryresizezoom.png "0713-12_PrimaryResizeZoom")|  
|**主要选择**|不可调整大小|![没有重设大小句柄的主要选择](~/extensibility/ux-guidelines/media/0713-13_primarynoresize.png "0713-13_PrimaryNoResize")|![没有的主要选择调整大小控点和 #40; 放大 &#41;](../../extensibility/ux-guidelines/media/0713-14_primarynoresizezoom.png "0713-14_PrimaryNoResizeZoom")|  
|**主要选择**|锁定|![锁定的主要选择](../../extensibility/ux-guidelines/media/0713-15_primarylocked.png "0713-15_PrimaryLocked")|![锁定的主要选择 &#40; 放大 &#41;](../../extensibility/ux-guidelines/media/0713-16_primarylockedzoom.png "0713-16_PrimaryLockedZoom")|  
|**次要选择**|可调整大小|![具有重设大小句柄的次要选择](../../extensibility/ux-guidelines/media/0713-17_secondaryresize.png "0713-17_SecondaryResize")|![具有的次要选择调整大小控点和 #40; 放大 &#41;](~/extensibility/ux-guidelines/media/0713-18_secondaryresizezoom.png "0713-18_SecondaryResizeZoom")|  
|**次要选择**|不可调整大小|![没有重设大小句柄的次要选择](~/extensibility/ux-guidelines/media/0713-19_secondarynoresize.png "0713-19_SecondaryNoResize")|![没有重设大小 &#40; 的次要选择缩放 &#41;](~/extensibility/ux-guidelines/media/0713-20_secondarynoresizezoom.png "0713-20_SecondaryNoResizeZoom")|  
|**次要选择**|锁定|![锁定的次要选择](../../extensibility/ux-guidelines/media/0713-21_secondarylocked.png "0713-21_SecondaryLocked")|![锁定的次要选择 （&) #40; 放大 &#41;](../../extensibility/ux-guidelines/media/0713-22_secondarylockedzoom.png "0713-22_SecondaryLockedZoom")|  
|**UI 活动**|默认|![UI 活动状态](../../extensibility/ux-guidelines/media/0713-23_uiactive.png "0713-23_UIActive")|![UI 活动状态 &#40; 放大 &#41;](../../extensibility/ux-guidelines/media/0713-24_uiactivezoom.png "0713-24_UIActiveZoom")|  
  
### <a name="view-selection-models"></a>查看所选内容模型  
  
#### <a name="tree-view"></a>树视图  
 与简单突出显示一起显示在树视图中的所选内容。 如果用户单击节点名称或节点图标上时，将成为选择的节点。 展开左侧的节点的三角形标志符号或协定树控件，但不是会影响用户的选择，但有一个例外︰ 在折叠父节点，该节点的子节点上所选内容时，所选内容将移到父级。  
  
 ![Visual Studio 中的典型树视图](~/extensibility/ux-guidelines/media/0713-25_treeview.png "0713-25_TreeView")  
  
 **Visual Studio 中的典型树视图**  
  
 树视图可以支持连续且不相互连接的选择，甚至可以跨多个级别在树中。 连续或连续必须可见的树节点上进行多个选择。 如果一个节点处于折叠状态，不相互连接的所选内容都将丢失，并已折叠的节点获取所选内容。 在这种方式，用户可以看到将受影响的操作的节点。 如果节点处于折叠状态，它变得不清晰的节点可能会受到影响。  
  
 当选中父节点时，该操作应当应用于父代、，尽管可能有意义的位置为应用于父及其所有子级操作的情况。 在这种情况下，在操作时，如复选框或确认对话框中，使用户显式的"应用于所有子项"选项提供其他用户界面。  
  
##### <a name="renaming"></a>重命名  
 如果树中的节点支持重命名，则应在位置完成重命名。 在 Visual Studio 中的所有树控件中适当地操作应标准。 提供立即激活，其涵盖整个名称的节点，准备好接受用户输入的选定文本的就地编辑模式时，重命名命令。 如果该节点表示一个文件，文件名应包含扩展插件。 选择突出显示应包括只会将正文的文件名和非扩展名。  
  
|输入|结果|  
|-----------|------------|  
|Enter 键|提交重命名操作|  
|Esc 键|取消重命名操作|  
|将就地编辑在区域外单击|提交重命名操作|  
|撤消|提供简单撤消取消重命名操作|  
  
#### <a name="selection-within-lists-and-grid-controls"></a>列表和网格控件中选定内容  
 在该列表中选择的关键概念在于，它是基于行的则表示该参数时进行选择整行作为一个单元选择。 与此相反，网格可以允许特定的单元格，而不会影响任何其他方面的行的选择。 网格还可能包含嵌套的行 （如树网格） 允许整个分支层次结构，以取消选择通过与父行进行交互和所选的层次结构。 在整行数据的简单突出显示颜色显示为列表中的选择。 单像素虚线边框的当前可编辑的行或单元格 （如果所有单元格都是只读的则为行） 显示为焦点。  
  
> [!NOTE]
>  **焦点** 和 **选择** 是不同的概念。 *焦点* 是哪种 UI 的目标元素指示接收的输入未显式定向到另一个对象，同时 *选择* 指的是一个对象包含在后续操作可能会发生的对象的一组的状态。  
  
 在列表中的选择可能是连续的、 不相互连接，或地区。 当多个选择是允许的连续未分配并不相互连接的所选内容应始终受支持，同时对区域 （框） 选择的支持是可选的。 通过拖动列表正文的空白空间中发起了区域的选择。  
  
|对象|选择|  
|------------|---------------|  
|列表|连续|始终支持 （时允许多重选择）。|  
|列表|不连续的|始终支持 （时允许多重选择）。|  
|列表|Region|可选支持。 在列表正文空白拖动鼠标来启动。|  
  
 单击列表上的一次可以选择单击发生处的行。 如果用户碰巧支持就地编辑的列表单元内单击，该单元格也会立即激活就地编辑。 否则为整行立即选择并显示突出显示。  
  
 拖动列表正文中会执行三个操作之一︰  
  
-   如果列表支持它，并且鼠标按下的空白区域中，启动区域选取  
  
-   如果列表单元格或行支持正在作为拖动源，启动拖放操作  
  
-   选择当前行  
  
##### <a name="in-place-editing"></a>就地编辑  
 允许就地编辑时有两种基本模式︰ 简单的编辑控件和属性选取器。 简单的编辑控件后，内容是突出显示并且可供用户输入就立即进行就地编辑被激活。 属性选取器实现时，激活的就地编辑模式，并不突出显示当前所选内容后，将显示时，将调用属性选取器按钮。 在单元格中应为右对齐选取器按钮。 有关就地编辑示例，请参阅 **属性窗口** 和 **任务列表** Visual Studio 中。  
  
##### <a name="keyboard-support"></a>键盘支持  
 在列表和网格中选择键盘支持遵循标准的 Windows 约定︰  
  
-   箭头键导航的列表中，选择移动焦点时，为每个行/单元格。  
  
-   Shift + 箭头的方向箭头键执行连续的选择。  
  
-   Ctrl + 空格键切换跟有之间添加和删除列表项从选择创建非连续选择的箭头。  
  
-   对于包含嵌套层次结构的网格，向右箭头键扩展父行，并向左箭头键将折叠其中一个。  
  
-   Tab 键将焦点移在当前行中单元格之间如果单元格都是可编辑。  
  
-   Enter 键对列表中的项执行默认命令 (通常 **打开**)。  
  
-   F2 键激活就地编辑当前所选单元格。  
  
##  <a name="a-namebkmkpersistenceandsavingsettingsa-persistence-and-saving-settings"></a><a name="BKMK_PersistenceAndSavingSettings"></a> 持久性和保存设置  
  
### <a name="overview"></a>概述  
 尽管 Visual Studio 中的每个软件组件是通常负责其自己的状态和持久性，但 Visual Studio 自动将设置保存在某些情况下，例如为与窗口大小和位置。 下表是自动保存的设置和设置需要显式的用户或编程所采取操作的组合。  
  
|对象|要保存的内容|当保存|保存的位置|  
|------------|------------------|------------------|-------------------|  
|可选择对象 （例如，一行代码）|断点的代码行上<br /><br /> 用户快捷方式的代码行与相关联|保存项目时| **用户选项 (.suo)** 项目文件|  
|对话框|对话框中，如果它已被移动的位置<br /><br /> 用户上次使用对话框中的视图|对话框关闭时<br /><br /> Visual Studio 会话结束时|在内存中<br /><br /> 在注册表中的 **HKEY_Current_User**|  
|窗口|大小和窗口的位置|当该窗口将关闭<br /><br /> Visual Studio 模式发生更改时<br /><br /> Visual Studio 会话结束时| **用户选项 (.suo)** 项目文件<br /><br /> 窗口设置的自定义选项文件|  
|Document|在文档中当前所选内容<br /><br /> 文档的视图<br /><br /> 最后的几个位置，该用户访问|当保存文档| **用户选项 (.suo)** 项目文件|  
|Project|对文件的引用<br /><br /> 对磁盘上的目录的引用<br /><br /> 对其他软件的引用<br /><br /> 组件数<br /><br /> 有关项目本身的状态信息|保存项目时|项目文件|  
|解决方案|对项目的引用<br /><br /> 对文件的引用|保存项目或解决方案时| **解决方案 (.sln)** 文件|  
|中的设置 **工具 > 选项**|键盘自定义项<br /><br /> 工具栏自定义<br /><br /> 配色方案|当 **工具 > 选项** 对话框关闭<br /><br /> Visual Studio 会话结束时|在注册表中的 **HKEY_Current_User**|  
  
 用户正在执行，并当他们这么做，指示设置是否要保存在保存到磁盘 （跨多个会话为注册表设置），（会话），期间的内存中的作为组成部分的项目或解决方案文件本身，作为一部分 **解决方案选项 (.suo)** 文件中，或自定义设置文件，只有该软件组件都知道。 上表中显示的设置可以保存多个事件。 但是，存在一些其他的情况下您可能要保存状态︰  
  
-   当用户更改的对话框或窗口内的位置  
  
-   用户将焦点转移到另一个窗口的时  
  
-   当用户切换从设计，以调试模式  
  
-   当用户注销其帐户  
  
-   当计算机进入休眠或关机  
  
-   当计算机/硬盘空间即将被重新格式化，并再次设置  
  
### <a name="window-configurations"></a>窗口配置  
 窗口配置基本的表示法的开发环境，它是一种方案组成的工具窗口存在的列表以及排列它们的方式。 对于 windows 管理的 IDE （IDE 窗口），布局信息将保留每个用户，因此当上次在 IDE 的窗口布局显示相同用户启动时退出 Visual Studio。 状态和位置的 IDE 窗口将保留在以 XML 格式的自定义选项文件。 创建的包加载到 IDE 中的工具窗口保留它们在注册表中的状态信息并可能会或可能不是每个用户。  
  
#### <a name="profile-specific-layouts"></a>特定于配置文件的布局  
 每个配置文件包含以熟悉的特定开发人员角色的方式组织的工具窗口布局 (Visual c + + 开发人员希望看到 **解决方案资源管理器** IDE 中，而 C# 开发人员希望看到左侧 **解决方案资源管理器** 右侧)。 在用户选择的配置文件在启动时加载特定于配置文件的窗口布局。 包的作者应确定最适合于他们的客户体验的窗口布局知道随后将保存到的窗口配置用户所做的更改。  
  
##  <a name="a-namebkmktouchinputa-touch-input"></a><a name="BKMK_TouchInput"></a> 触摸输入  
 在触摸设备上，用户正在越来越多地使用 Microsoft 开发产品。 但是，有一些难以使用触摸设备上的开发工具的障碍。 用户会认为我们的产品提供可靠、 精确的触摸体验。 这些准则的目的是要决定哪些触摸功能，以便合并，并鼓励一致的触摸体验跨 Visual Studio 和相关的产品。  
  
### <a name="levels-of-experience"></a>级别的体验  
 以下级别的体验旨在作为指南来帮助团队确定哪些触摸功能提供根据触摸投资关注其所需级别。  
  
-    **基本体验** 是团队想要提供触摸功能，因此没有在他们的工作没有死胡同。  
  
-    **优化体验** 为想要提供最常用的触摸功能 （例如，那些通常可以在 internet 浏览器应用程序） 的团队。  
  
-    **提升体验** 是为想要添加此类功能的团队一样笔势或其他可选功能，可以使他们的应用程序触摸优先友好。  
  
||基本体验|优化的体验|提升的体验|  
|-|----------------------|--------------------------|-------------------------|  
|使用户可以...|修复代码和阅读并不死胡同的解决方案/项目的级别|执行维护、 重构方法和导航任务|自信地操作中保持一致、 直观和流畅的体验|  
|编辑器|触摸平移和所选内容<br /><br /> 滚动条触控跳转和按并拖动|捏合缩放<br /><br /> 快速滚动<br /><br /> 选择<br /><br /> 易于使用的上下文菜单||  
|顶部的工具窗口|列表平移<br /><br /> 所选择的项目<br /><br /> 滚动条触控跳转和按并拖动|简单项目滚动和所选内容||  
|窗口||调整窗口的大小<br /><br /> 快速访问||  
|好的文档||打开的文件之间轻松导航||  
|笔势||确保在 IDE 中常见的手势工作|基于手势的操作<br /><br /> 支持拖放和设计器|  
|其他注意事项|||自定义屏幕键盘|  
  
#### <a name="gestures"></a>笔势  
 手势为用户提供的快捷方式命令，否则可能需要更复杂的交互。 请参阅 Windows 指南上 [的桌面应用程序的常用的触摸手势](http://msdn.microsoft.com/en-us/library/windows/desktop/dd940543\(v=vs.85\).aspx), ，并按照本指南为大多数手势，包括简单的手势，例如平移和缩放。