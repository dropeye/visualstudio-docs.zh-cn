---
title: "Idiaenumsourcefiles:: Next |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Next method
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 37eafe2093fc978f202afa5675ffca41bdd028b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsourcefilesnext"></a>IDiaEnumSourceFiles::Next
检索指定的数目的枚举序列中的源文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next (   
   ULONG            celt,  
   IDiaSourceFile** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]要检索的枚举器中的源代码文件的数量。  
  
 rgelt  
 [out]数组，它是在用来填充[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)代表所需的源文件的对象。  
  
 pceltFetched  
 [out]在提取枚举器返回源文件数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更多的源文件。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession:: Findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)