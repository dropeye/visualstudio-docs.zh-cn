---
title: "Idiaimagedata:: Get_imagebase |Microsoft 文档"
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
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5e3730e7bc543d0b7bdea18e162dfe83e1d803bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
检索其中应基于映像的内存位置。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回的建议的映像的基础价值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 由于映像基冲突而进行映像可能会重新设定基址自动到未使用的内存位置加载。 此方法返回时在编译时存储在该模块的基提示 （建议的内存位置）。  
  
## <a name="see-also"></a>请参阅  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)