---
title: "在 Visual Studio 中生成方法重写 | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: df0eecdeb2aad15e1da68cef3b125c3c95f57e78
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="generate-an-override-in-visual-studio"></a>在 Visual Studio 中生成方法重写

此代码生成适用于：

- C#

- Visual Basic

功能：快速生成针对任意方法的代码，以从基类替代它。

时机：想要替代一个基类方法并自动生成签名时。

原因：可以自己编写方法签名，但此功能可自动生成签名。

## <a name="how-to"></a>操作说明

1. 在 C# 中键入 `override` 或在 Visual Basic 中键入 `Overrides`，后接空格（可在此处插入重写方法）。

   - C#：

    ![重写 IntelliSense C#](media/override-intellisense-cs.png)

   - Visual Basic：

    ![重写 IntelliSense VB](media/override-intellisense-vb.png)

1. 从基类中选择要重写的方法。

   > [!TIP]
   > - 使用“属性”图标 ![“属性”图标](media/override-property-cs.png) 显示或隐藏列表中的属性。
   > - 使用“方法”图标 ![“方法”图标](media/override-method-cs.png) 显示或隐藏列表中的方法。

   所选方法或属性将作为替代添加到类中以供实现。

   - C#：

      ![重写结果 C#](media/override-result-cs.png)

   - Visual Basic：

      ![重写结果 VB](media/override-result-vb.png)

## <a name="see-also"></a>请参阅

[代码生成](../code-generation-in-visual-studio.md)
