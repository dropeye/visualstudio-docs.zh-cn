---
title: "错误： 无法连接到机&lt;名称&gt;。 在网络上找不到计算机。 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e8b7ef99717f0a68fbd17245958840c89cdf8544
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>错误： 无法连接到机&lt;名称&gt;。 在网络上找不到计算机。
如果满足下列某项条件，则会发生此行为：  
  
-   您与远程计算机的连接中断。  
  
-   您在远程计算机上的用户帐户被禁用。  
  
-   您在远程计算机上的密码过期。  
  
### <a name="to-resolve-this-behavior"></a>解决此问题  
  
-   确保本地计算机和远程计算机处于同一个网络中。 若要执行此操作，请使用 Microsoft Windows 资源管理器（或文件资源管理器）尝试访问远程计算机。  
  
     - 和 -  
  
-   确保您用来连接远程计算机的用户帐户是启用的。  
  
     - 和 -  
  
-   确保您用来连接远程计算机的密码是有效的并且尚未过期。  
  
## <a name="see-also"></a>请参阅  
 [远程调试](../debugger/remote-debugging.md)   
 [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)