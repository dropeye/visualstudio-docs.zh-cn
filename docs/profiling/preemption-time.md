---
title: "抢占时间 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.preemption
helpviewer_keywords:
- Concurrency Visualizer, Preemption Time
ms.assetid: 6b78f91e-a006-440c-83fb-e7368040951d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0ee0f1be5d687c145bc2c8af448b30ec364df2f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="preemption-time"></a>抢占时间
时间线中的这些段与归类为“抢占”的阻塞时间关联。 此类别表示由于以下原因之一断开线程：  
  
-   计划程序使用更高优先级的线程将其替换。  
  
-   线程的执行量程过期，且其他线程已作好执行准备。  
  
 在此时间内，由于并发可视化工具被视为“抢占”这一内核等待原因，已阻止线程。 当线程被排出逻辑核心时，抢占段开始；当线程继续执行时，抢占段结束。  
  
 抢占段的工具提示会显示导致抢占的进程或线程的名称。 然而，这并不表示接管的进程或线程在抢占期间内会实际运行。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)