---
title: "启用调试 Visual c + + 的功能 (-/d_debug) |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f1067ee5b60b8a8a402c9612357f2d83b6da138
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>在 Visual C++ 中启用调试功能 (/D_DEBUG)
在[!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)]，调试功能，例如，如果符号重新编译程序时启用断言**_DEBUG**定义。 你可以定义**_DEBUG**在两种方式之一：  
  
-   指定**#define _DEBUG**你在源代码中，或  
  
-   指定**/D_DEBUG**编译器选项。 (如果在 Visual Studio 中使用向导，创建你的项目**/D_DEBUG**调试配置中自动定义。)  
  
 当**_DEBUG**是定义，则编译器将编译包围的代码的部分**#ifdef _DEBUG**和`#endif`。  
  
 MFC 程序的调试配置必须与 MFC 库的调试版本链接。 MFC 标头文件确定要链接的 MFC 库的正确版本基于你已定义，如符号**_DEBUG**和**_UNICODE**。 有关详细信息，请参阅[MFC 库版本](/cpp/mfc/mfc-library-versions)。  
  
## <a name="see-also"></a>请参阅  
 [调试本机代码](../debugger/debugging-native-code.md)   
 [C++ 调试配置的项目设置](../debugger/project-settings-for-a-cpp-debug-configuration.md)