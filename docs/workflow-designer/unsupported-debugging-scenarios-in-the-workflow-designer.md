---
title: "不受支持的调试方案中工作流设计器 |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 958937e8d846c07cafc8293b4592ad6c67479849
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>工作流设计器中不受支持的调试方案
[!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 中的工作流设计器添加了许多新功能，但仍存在一些它不支持的调试方案。 本文档详细介绍了不受支持的工作流设计器调试方案。  
  
-   在编辑代码之后不能继续执行。  
  
-   不能从工作流中的任意点继续执行（“设置下一语句”）。  
  
-   只有在到达光标处之后才能继续执行（“运行到光标处”）。  
  
-   不能使用工作流设计器来调试通过代码创建（未使用工作流设计器）的工作流。  
  
-   也不能在 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 设计器中调试通过 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 早期版本创建的工作流。  
  
-   不能在两个活动或 <xref:System.Activities.Statements.Flowchart> 节点之间的链接上定义断点。  
  
-   调试期间剪贴板不可用。  
  
-   复制或粘贴活动时不会保留断点。  
  
-   不能在调用堆栈窗口中设置工作流断点。  
  
-   在设计器中创建断点时**行**和**字符**中的设置**新断点**不使用对话框。  
  
-   “断点”窗口或快捷菜单不支持以下用于工作流调试的列或选项：  
  
    -   条件  
  
    -   命中次数  
  
    -   命中条件  
  
    -   函数  
  
    -   数据  
  
    -   进程  
  
    -   转到反汇编