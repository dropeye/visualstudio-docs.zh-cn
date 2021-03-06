---
title: "Android 调试器属性 (C++) | Microsoft Docs"
ms.custom: 
ms.date: 10/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 3ca25e560a4bc3060d86972b4000b3d9ad59ba1f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="android-debugger-properties"></a>Android 调试器属性

属性 | 描述 | 选项
--- | ---| ---
调试器类型 | 指定要调试的代码类型。 | **仅限本机**<br>仅限 Java<br>
调试目标 | 指定要用于调试的仿真器或设备。 如果没有仿真器正在运行，请使用“Android 虚拟设备(AVD)管理器”启动设备。
要启动的包 | 指定要调试的 .apk 的位置。 选择此选项指定调试应用程序时应启动的特定包 (APK)。
启动活动 | 用于启动应用程序的 Android 活动必须与清单中所使用的活动相匹配。 按“应用”从 AndroidManifest.xml 检索列表并动态填充该列表。
其他符号搜索路径 | 调试符号的其他搜索路径。
其他 Java 源搜索路径 | Java 源文件的其他搜索路径。 （仅在调试器类型为仅限 Java 时适用。）
