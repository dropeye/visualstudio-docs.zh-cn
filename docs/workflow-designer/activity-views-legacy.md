---
title: "活动视图 （旧版） |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 10661aa3f12b83a383defaa204b5bba0b93e236a
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="activity-views-legacy"></a>活动视图（旧版）
提供的活动的许多[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]，包括工作流，具有旧的 Windows 工作流设计器中可用的多个设计视图。 当将某个活动设计器从**工具箱**拖到设计图面中，并且之后每当选择该活动时，你可以通过使用不同的设计视图之间进行切换**工作流**菜单或通过右键单击选定的活动。 同时，当您将指针移到选定活动的名称上时，将出现一组以下拉方式显示的选项卡，可以用来在不同的视图之间切换。

 每个活动都至少一个视图;这是显示拖动某个活动设计器从时的默认视图**工具箱**拖到设计图面。 此活动默认视图是可用作**查看 [活动类型]**选项菜单和选项卡上，例如，**视图并行**。 大多数活动都有附加视图，并且不同活动可以有不同的视图。 例如， [TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)活动具有补偿视图和[EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)活动具有事件视图。 有许多 Windows Workflow Foundation 附带的活动的**查看取消处理程序**和**视图错误**设计视图的视图[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)和[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)与其关联。

 下表列出了每个视图的名称和说明。

|菜单/选项卡选项|描述|
|----------------------|-----------------|
|**查看 [活动类型]**|选择此菜单或选项卡选项可查看选定活动的默认图形表示形式。|
|**查看取消处理程序**|选择此菜单或选项卡选项视图可查看[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)与选定活动关联。|
|**查看错误处理程序**|选择此菜单或选项卡选项视图可查看[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)与选定活动关联。|
|**查看补偿处理程序**|选择此菜单或选项卡选项视图可查看[CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053)关联与所选[TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)。|
|**查看事件处理程序**|选择此菜单或选项卡选项视图可查看[EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018)关联与所选[EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)。|

 有关类似视图的信息，请参阅[顺序工作流视图 （旧版）](../workflow-designer/sequential-workflow-views-legacy.md)。

## <a name="see-also"></a>请参阅

- [旧版工作流活动](../workflow-designer/legacy-workflow-activities.md)
- [顺序工作流视图（旧版）](../workflow-designer/sequential-workflow-views-legacy.md)