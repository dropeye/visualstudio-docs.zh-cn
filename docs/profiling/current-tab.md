---
title: "“当前”选项卡 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.reportnav.current
helpviewer_keywords:
- Concurrency Visualizer, Callstack at Selection Point
ms.assetid: 2c7b1ae5-3756-4795-bc59-f6bb113f2ba5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: eb69f11081015960cd79d54fb90893a9202c9bae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="current-tab"></a>当前选项卡
如果选择一个 CPU 线程段，则通过单击“当前”选项卡，可以查看时间线中最接近当前选择点的调用堆栈（如果有）。  在这种情况下，选择点由时间线上方的黑色箭头或插入符号来表示。 选择阻塞段时，将不显示插入符号，因为没有任何执行操作。 但是，仍会突出显示该段，并显示调用堆栈。  
  
 “当前”选项卡还显示有关 DirectX 活动段、标记和 I/O 访问的信息。  对于 DirectX 活动段，将会显示有关硬件队列如何处理 DMA 数据包的信息。  对于标记，将会显示有关说明和标记类型的信息。  对于 I/O 访问，将会显示有关文件和读取或写入字节数的信息。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)