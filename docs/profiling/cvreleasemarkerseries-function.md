---
title: "CvReleaseMarkerSeries 函数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cvmarkers/CvReleaseMarkerSeries
helpviewer_keywords:
- CvReleaseMarkerSeries method
ms.assetid: 3b4711ee-e534-411d-9128-f69cd7932a48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3251db736e42d0b5e49d92b17720605c507d2184
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cvreleasemarkerseries-function"></a>CvReleaseMarkerSeries 函数
发布标记系列。 在发布之后请勿使用标记系列对象，否则应用程序可能会崩溃。 标记系列发布失败会导致内存泄漏。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CvReleaseMarkerSeries(  
   _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pMarkerSeries`  
 提供程序对象变量的地址。 地址不能为 NULL，该变量可以具有任何值。  
  
## <a name="return-value"></a>返回值  
 成功发布标记系列时返回 S_OK，出现任何错误时返回错误代码。 使用 SUCCEEDED/FAILED 宏检查错误条件。  
  
## <a name="requirements"></a>惠?  
 **标头：**cvmarkers.h  
  
## <a name="see-also"></a>请参阅  
 [C++ 库参考](../profiling/cpp-library-reference.md)