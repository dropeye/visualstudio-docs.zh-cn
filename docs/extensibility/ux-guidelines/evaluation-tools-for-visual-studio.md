---
title: "评估 Tools for Visual Studio |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94e0e9a3-440c-4943-ad7b-772ed742e034
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7026a14a4880a47f415f5aecd1c15f8a2423d86e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="evaluation-tools-for-visual-studio"></a>评估 Tools for Visual Studio
## <a name="craftsmanship-checklist-for-visual-studio"></a>针对 Visual Studio 的编程工作核对清单  
 使用此清单来评估视觉和交互的详细信息的用户体验质量。  
  
### <a name="overview"></a>概述  
  
-   请验证所有命令都产生反馈，告诉用户开展其命令。  
  
-   验证所有 UI 元素和控件都在所有的主题和高对比度模式中可见。  
  
-   验证的非活动和活动选择始终区别在于，同时在 standard 和高对比度模式。  
  
-   验证焦点始终可见和明显。  
  
### <a name="performance"></a>性能  
  
-   请检查某些类型的"忙"指示器显示命令是否采用多个 1 秒来完成。  
  
-   如果命令需要多个 10 秒钟的时间来完成，一个显式的进度栏，请验证确定 （首选） 或不确定的将显示。  
  
### <a name="ui-text"></a>UI 文本  
  
-   验证所有标签都的句子或词首字母大写，并且没有文本采用完全小写形式。  
  
    ||更正|不正确|  
    |-|-------------|---------------|  
    |**命令文本 （全部）**|句子大小写：<br /><br /> **目录名称：**|目录名称：|  
    |**按钮文本 （客户端）**|词首字母大写：<br /><br /> **[设为默认值]**|集 AS 默认|  
    |**按钮文本 （联机）**|句子大小写：<br /><br /> **[设为默认值]**||  
  
-   验证所有标签，除组标题和按钮，以冒号结尾，以及前面与其它们成对的控件。  
  
-   验证按钮、 命令和启动 UI，以捕获用户输入的命令链接结束省略号中**[…]**.  
  
     示例：  
  
    -   **[高级...]**对话框上的按钮。  
  
    -   工具菜单下的命令选项 (**工具 > 选项**) 应获取省略号，因为启动对话框本身是该命令的意图。  
  
-   验证 UI 包含任何缩写，行业标准条款除外。 例如，HTML 和 TCP/IP 都不需要拼，但应在 OOM （内存） 不足和 PII （个人身份信息）。  
  
### <a name="keyboard-access"></a>键盘访问  
  
-   验证有一种方法来完成与键盘每个任务。 通常这一点通过为每个控件的键盘访问，但对于某些极为直观的区域，如转到代码视图一种解决方法是可接受。  
  
-   验证你可以通过按逻辑顺序 （从左到右和从上到下） 的控件选项卡。 尽管这是大多数控件的最佳做法，并非所有控件都要求这种方法。 例如，验证该控件是具有单个制表位的组中的单选按钮。  
  
-   验证所有控件都有标签以及每个标签是否助记键 （例外情况包括某些非标记为控件，可以按照在选项卡中的标记的控件）。  
  
-   验证有没有助记键冲突。  
  
### <a name="fonts"></a>字体  
  
-   验证所有字体 （字体、 大小、 颜色） 一致地使用和维护层次结构。  
  
-   验证所有 UI 元素都使用环境字体服务。 (请参阅[字体和格式设置为 Visual Studio](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md))  
  
     若要检查是否正在使用该服务，请转到**工具 > 选项 > 字体和颜色**。 在设置下拉列表中，选择环境字体，更改到 stylistically （如 Harrington 或漫画 San） 的其他内容的字体，并将大小设置为 12 pt。 然后单击确定。 你可能需要重新启动 IDE 中，但大多数 UI 将会立即更改。 即使在重启字体更改不会获得的区域不使用环境字体。  
  
-   验证是派生的服务 （例如，放大或缩小粗体文本） 的字体保留其大小和环境字体大小更改时，相对于"normal"的文本格式。  
  
-   验证不由于放大字体任何剪辑 bug。 获取剪切的字体可能是导致的固定的高度控件或固定的高度容器。  
  
### <a name="dialogs"></a>对话框  
  
-   验证对话框的标题启动它的命令相同。  
  
-   验证所有标准控件是否与操作系统一致： 背景色为标准并且任何控件应具有特殊的重新模板化样式，使它们看起来不同于标准控件。  
  
-   验证在窗体的边距应为 12 像素和应显示统一和一致。  
  
-   验证对话框显示在 IDE shell 或生成它们的窗口内居中。  
  
-   时很有用，应调整对话框。 对于可调整大小的对话框，请验证，在调整大小时，相应的控件必须调整时对话框的其他部分保持不变。  
  
-   验证可调整大小的对话框将保存任何用户调整大小 （大小、 位置、 扩展的对话框控件和等等）。  
  
-   验证在标题栏中有无图标。  
  
-   验证在标题栏中有没有最小化和最大化按钮。  
  
#### <a name="dialog-operation-buttons-vs-client-only"></a>对话框操作按钮 （仅限 VS 客户端）  
  
-   验证操作按钮是否按以下顺序：**确定**，**取消**，**应用**。  
  
-   验证**确定**和**取消**按钮是标准的大小： 75 x 23 像素为单位。  
  
-   验证**确定**和**取消**按钮都而不考虑字符串长度大小相等。  
  
-   如果上一个操作按钮标签要求要高于标准的按钮，验证相应**取消**按钮是大小相等。  
  
-   验证有之间按钮和关联的控件 6 像素填充。  
  
-   验证**确定**和**取消**按钮没有助记键 （访问键加带下划线的字母定义）。  
  
-   验证该一个按钮 (通常**确定**) 默认情况下具有焦点。  
  
-   验证**Esc**取消对话框  
  
-   验证**Enter**焦点不在处理输入控件中会执行默认按钮。  
  
-   验证**确定**和**取消**按钮位于右下角的对话框。 在少数例外情况外，它是可接受他们在右上角垂直堆积。  
  
-   验证使用垂直配置了仅当其他按钮都保持在对话框内水平对齐。  
  
### <a name="control-standards"></a>控制标准  
  
#### <a name="general"></a>常规  
  
-   验证，在可能的情况下，有很好的默认值，以加快用户交互以及向安全或常见结果将用户。  
  
-   验证，标准控件的行为方式相同，以便用户知道将发生的基于早期体验。  
  
#### <a name="label-controls"></a>Label 控件  
  
-   请验证每个控件具有的标签，并且每个标签以可视方式配合 （通常在 4-6 像素范围） 内其控件更接近于其相应的控件，可比其他控件。  
  
-   验证标签将定位刷新与该控件的左侧如果定位上面左边缘和居中水平，以便如果定位到左侧，与输入文本的基线对齐的标签的基线。  
  
-   验证是否多个堆积的标签和输入的控件控件左侧定位的标签左对齐，并从对话框中，边缘等距永远不会刷新权限和来自控件等差。 除非所需增加额外的空间，以指示分组，对应均匀分布。  
  
#### <a name="input-controls-text-boxes-and-combo-boxes"></a>输入的控件 （文本框和组合框）  
  
-   验证时使用的默认环境字体，文本框、 组合框和按钮的显示高度所有 23 像素。  
  
-   如果使用提示文本，则验证颜色设置为`Environment.ControlEditHintText`使用颜色服务。  
  
-   如果字段为必填的字段，必须标识为此，请验证：  
  
    -   后台设置为`Environment.ControlEditRequiredBackground`和前景色设置为`Environment.ControlEditRequiredHintText`  
  
    -   没有显示为控件中的提示文本**"\<所需 >"**  
  
#### <a name="button-controls"></a>按钮控件  
  
-   除非容纳较长的文本，请验证按钮 75 x 23 像素为单位的最小大小。  
  
-   验证按钮已离开和右键 3-5 像素为单位，以及填充内容的边距。  
  
-   它是可接受的小正方形按钮用于仅省略号**[…]**它而不是**[浏览...]**按钮 （或类似的功能）。 如果使用，请验证按钮为 23 x 23 大小。  
  
-   如果存在多个**[浏览...]**按钮在对话框中，然后确认缩写的版本 (仅省略号**[…]**) 应用于所有。  
  
-   验证该省略号**[…]**按钮没有助记键。 当焦点在其旁边的输入控件上时，一个选项卡应将焦点移到旁边的省略号按钮。  
  
-   验证按钮、 命令和启动辅助捕获更多用户输入的用户界面的命令链接必须以省略号结尾**[…]**.  
  
#### <a name="hyperlinks"></a>超链接  
  
-   验证超链接控件永远不会闪烁红色活动时。 这是颜色服务将不会使用指示器  
  
-   验证使用的 VS 颜色：  
  
    -   `Environment.ControlLinkText`  
  
    -   `Environment.ControlLinkTextHover`  
  
    -   `Environment.ControlLinkTextPressed`  
  
-   验证超链接显示蓝色使用没有下划线除非嵌入到一个段落中。  
  
#### <a name="check-boxes"></a>复选框  
  
-   如果复选框具有多行文本，请验证框中对齐文本，不能跨所有行垂直居中位置的第一行。  
  
-   请验证复选框始终指示二进制选择和执行不将用户定位或者打开新窗口或页。  
  
-   如果复选框呈现与相关输入控件的一个选项，请验证其定位刷新向左和非常关闭在该控件，以指示其关系。  
  
-   验证是否复选框**永远不会**作为一种方法用于启用对话框或页的全部内容。  
  
#### <a name="group-boxes"></a>分组框  
  
-   验证一个对话框不包含一个单个组框中，它包含对话框中的全部内容。  
  
-   验证在每个组框中的至少两个控件。  
  
-   极少数情况下应该有一个对话框上的两个以上组框。  
  
-   验证有任何嵌套的组框。  
  
### <a name="icons"></a>图标  
  
-   验证在深色主题中的图标显示正确倒排。  
  
-   验证所有图标都基于核心概念。  
  
-   验证每个图标是明确的、 可轻松地识别，并且不包含两个以上概念 （无状态修饰符/语言）。  
  
-   验证该基图标将显示空间内居中。  
  
-   验证所有图标都显示在高对比度模式中清晰。  
  
-   验证使用任何颜色符合颜色用法标准。  
  
-   围绕图标，验证不有任何光晕 （边框）。 （如果存在，光环应匹配相邻的用户界面的背景色）。  
  
### <a name="touch-enabled-ui"></a>触控 UI  
  
-   验证交互式控件是否足够大，无法轻松地 touchable-最小**23 x 23 像素**大小  
  
-   验证最常用的控件是否至少**40 x 40 像素**大小。  
  
-   验证是否至少具有交互式控件**的间距的 5 个像素**它们之间