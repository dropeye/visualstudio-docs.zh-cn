---
title: "在 Visual Studio 中重构方法签名 | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: c181eb27ccdbc2f1efb7294e1610a6055245241c
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="change-a-method-signature-refactoring"></a>“更改方法签名”重构

此重构适用于：

- C#

- Visual Basic

功能：删除或更改方法的参数顺序。

时机：想要移动或删除当前用于多个位置的方法参数时。

原因：可以手动删除和重新排列参数，然后找到对此方法的所有调用并逐一更改，但这样可能会引发错误。  此重构工具可自动执行此任务。

## <a name="how-to"></a>操作说明

1. 突出显示要修改的方法的名称或其用法之一，或将文本光标置于其中：

   - C#：

    ![突出显示的代码 C#](media/changesignature-highlight-cs.png)

   - VB：

    ![突出显示的代码 Visual Basic](media/changesignature-highlight-vb.png)

1. 接下来，执行以下操作之一：

   - **键盘**
     - 按“Ctrl+R”，然后按“Ctrl+V”。  （请注意，键盘快捷方式可能因所选的配置文件而有所不同。）
     - 按“Ctrl”+**。** 触发“快速操作和重构”菜单，然后从“预览”弹出窗口选择“更改签名”。
   - **鼠标**
     - 选择“编辑 > 重构 > 删除参数”。
     - 选择“编辑 > 重构 > 重新排列参数”。
     - 右键单击代码，选择“快速操作和重构”菜单，然后从“预览”弹出窗口选择“更改签名”。

1. 在弹出的“更改签名”对话框中，可以使用右侧的按钮更改方法签名：

   ![“更改签名”对话框](media/changesignature-dialog-cs.png)

   | Button | 描述
   | ------ | ---
   | 上移/下移 | 在列表中向上和向下移动所选的参数
   | **移除**  | 从列表删除所选的参数
   | 还原 | 将所选择的已删除参数还原到列表

   > [!TIP]
   > 提交前，使用“预览引用更改”复选框[查看最后的结果](../../ide/preview-changes.md)。

1. 完成后，按“确定”按钮进行更改。

   - C#：

    ![“更改签名”的结果 - C#](media/changesignature-result-cs.png)

   - Visual Basic：

    ![“更改签名”的结果 - Visual Basic](media/changesignature-result-vb.png)

## <a name="see-also"></a>请参阅

- [重构](../refactoring-in-visual-studio.md)
- [预览更改](../../ide/preview-changes.md)