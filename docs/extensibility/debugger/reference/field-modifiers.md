---
title: "FIELD_MODIFIERS |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FIELD_MODIFIERS
helpviewer_keywords:
- FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 98f6e4d3f187261bcf9c0d1ad3959093d864e222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
指定字段类型的修饰符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_FIELD_MODIFIERS {   
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
typedef DWORD FIELD_MODIFIERS;  
```  
  
```csharp  
public enum enum_FIELD_MODIFIERS {  
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
```  
  
## <a name="members"></a>成员  
 FIELD_MOD_ACCESS_TYPE  
 指示无法访问该字段。  
  
 FIELD_MOD_ACCESS_PUBLIC  
 指示字段具有公共访问权限。  
  
 FIELD_MOD_ACCESS_PROTECTED  
 指示字段具有访问受保护。  
  
 FIELD_MOD_ACCESS_PRIVATE  
 指示字段具有私有访问权限。  
  
 FIELD_MOD_NOMODIFIERS  
 指示字段具有任何修饰符。  
  
 FIELD_MOD_STATIC  
 指示该字段是静态。  
  
 FIELD_MOD_CONSTANT  
 指示字段为常数。  
  
 FIELD_MOD_TRANSIENT  
 指示该字段是暂时性的。  
  
 FIELD_MOD_VOLATILE  
 指示该字段是易失性。  
  
 FIELD_MOD_ABSTRACT  
 指示该字段是抽象。  
  
 FIELD_MOD_NATIVE  
 指示该字段是本机。  
  
 FIELD_MOD_SYNCHRONIZED  
 指示该字段保持同步。  
  
 FIELD_MOD_VIRTUAL  
 指示该字段是虚拟的。  
  
 FIELD_MOD_INTERFACE  
 指示该字段是一个接口。  
  
 FIELD_MOD_FINAL  
 指示该字段是最后一个。  
  
 FIELD_MOD_SENTINEL  
 指示字段 sentinel。  
  
 FIELD_MOD_INNERCLASS  
 指示该字段是一个内部的类。  
  
 FIELD_TYPE_OPTIONAL  
 指示该字段是可选的。  
  
 FIELD_MOD_BYREF  
 指示字段引用自变量。 这是专门为方法参数。  
  
 FIELD_MOD_HIDDEN  
 指示必须隐藏或显示在另一个上下文; 字段例如，[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]静态局部变量。  
  
 FIELD_MOD_MARSHALASOBJECT  
 指示字段表示的对象`IUnknown`接口。  
  
 FIELD_MOD_SPECIAL_NAME  
 指示字段具有特殊名称，例如，`.ctor`的构造函数 ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]仅)。  
  
 FIELD_MOD_HIDEBYSIG  
 指示该字段具有`Overloads`关键字应用于它 ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]仅)。  
  
 FIELD_MOD_WRITEONLY  
 指示该字段是只写。 此值不包括在`FIELD_MOD_ALL`，此类只写的字段的唯一用途是函数求值。 用户必须明确要求提供`FIELD_MOD_WRITEONLY`字段。  
  
 FIELD_MOD_ACCESS_MASK  
 指示字段访问权限的掩码。  
  
 FIELD_MOD_MASK  
 指示字段修饰符的掩码。  
  
## <a name="remarks"></a>备注  
 用于`dwModifiers`的成员[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)结构。  
  
 这些值也将传递给[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)方法来筛选出存在特定字段。  
  
## <a name="requirements"></a>惠?  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)