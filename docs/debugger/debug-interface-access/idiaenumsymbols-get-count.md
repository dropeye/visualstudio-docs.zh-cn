---
title: "Idiaenumsymbols:: Get_count |Microsoft 文档"
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
- IDiaEnumSymbols::get_Count method
ms.assetid: fdaae6d7-e67b-4262-84c9-fbae381e8297
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2f6a54b217a3dea8daca1266dd494949921f977a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsymbolsgetcount"></a>IDiaEnumSymbols::get_Count
检索符号的数。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 pRetVal  
 [out]返回符号的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaEnumSymbols::Item](../../debugger/debug-interface-access/idiaenumsymbols-item.md)