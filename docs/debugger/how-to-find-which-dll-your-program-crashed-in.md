---
title: "如何： 查找导致程序崩溃的 DLL |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: df872ea52d716b4eaedc9414bc7234ba7c6294d3
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>如何：查找导致程序崩溃的 DLL
  
 如果应用程序在调用系统 DLL 或别人的代码时出现崩溃，则需要找出在崩溃发生时哪个 DLL 是活动的。 如果在你自己的程序外部的 DLL 中崩溃，你可以识别位置使用**模块**窗口。  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>使用“模块”窗口查找崩溃发生的位置  
  
1.  记下崩溃发生的地址。

    如果地址未显示错误消息中，你可能需要使用替代方法来确定的 DLL。 如果你怀疑系统 DLL，则可以[加载符号](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)从在调试时的 Microsoft 符号服务器。 否则，你可能需要[创建转储文件](../debugger/using-dump-files.md)改为使用堆信息。 各种[工具](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/)可用于创建转储文件。
  
2.  上**调试**菜单上，选择**Windows**，然后单击**模块**。  
  
3.  在**模块**窗口中，查找**地址**列。 可能需要使用滚动条来查看。  
  
4.  单击**地址**Dll 按地址进行排序的列顶部的按钮。  
  
5.  细查排序的列表，找到其地址包含崩溃位置的 DLL。  
  
6.  查看**名称**和**路径**列，查看 DLL 的名称和路径。  
  
## <a name="see-also"></a>请参阅  
 [调试 DLL 项目](../debugger/debugging-dll-projects.md)   
 [如何：使用“模块”窗口](../debugger/how-to-use-the-modules-window.md)