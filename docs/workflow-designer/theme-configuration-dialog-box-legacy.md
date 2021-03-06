---
title: "主题配置对话框 （旧版） |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.ComponentModel.Design.ThemeConfigurationDialog.UI
helpviewer_keywords:
- themes, configuring
- Theme Configuration dialog box
ms.assetid: 9e6d182a-c4d9-4e71-b2b9-02f675fc2b29
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4d59ffe46ed9b85eb64eeda39275b6566b1ca497
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="theme-configuration-dialog-box-legacy"></a>“主题配置”对话框（旧版）
本主题介绍如何使用**主题配置**旧的 Windows 工作流设计器中的对话框。 在需要面向 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 或 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 时，请使用旧 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]。

 主题定义工作流的背景和前景颜色、样式、图标及其他可视元素。 可以保存主题以供其他工作流重复使用。

 创建和编辑主题使用**主题配置**对话框。 若要打开对话框中，选择**创建新主题**上**工作流**菜单上，或者右键单击工作流设计图面并选择**创建新主题**。

 下表描述的用户界面 (UI) 元素**主题配置**对话框。

|UI 元素|描述|
|----------------|-----------------|
|**主题名称：**|标识中的主题的名称[主题、 工作流设计器选项对话框 （旧版）](../workflow-designer/themes-workflow-designer-options-dialog-box-legacy.md)。 将为新主题生成可更改的名称。|
|**主题位置：**|主题文件的文件名和路径。 将基于已生成的主题名称为新主题生成可更改的文件名。 如果更改生成的主题名称，则可能需要更改文件名以与主题名称匹配。|
|**...**|单击以选择位置来保存使用 .wtm 文件扩展名的工作流主题文件。 所选的路径将被发现中**主题位置**文本框。|
|**选择设计器，并配置属性：**|左窗格列出了可为其自定义主题的活动的树视图。 选择树视图中的活动，该活动的主题属性将显示在树视图窗格右边的属性窗格中。 单击属性以更改其值。|
|**预览**|单击以显示一个窗口来预览属性更改的效果。|

## <a name="see-also"></a>请参阅

- [“主题、工作流设计器和选项”对话框（旧版）](../workflow-designer/themes-workflow-designer-options-dialog-box-legacy.md)
- [Windows Workflow Foundation 的旧版设计器 UI 帮助](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)