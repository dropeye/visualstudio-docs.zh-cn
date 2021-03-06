---
title: IDE 常量 |Microsoft 文档
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0184cd4654f07b407a12ca12f0ff9da39c9ec890
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="ide-constants"></a>IDE 常量

<xref:Microsoft.VisualStudio.VSConstants>类提供特定于集成的开发环境 (IDE) 并且，以前仅在标头文件中定义的常量。

## <a name="logical-and-physical-views"></a>逻辑和物理视图

|值|描述|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序应传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法以获取**打开**对话框中，在这种情况下可能代码视图。|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序会传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法以获取**打开**对话框中，在这种情况下填充具有可能<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid>调试视图这些映射到同一个视图作为视图<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>。|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Designer_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序会传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法以获取**打开**对话框中，在此用例与**查看表单**设计器视图。|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Primary_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序会传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法以获取**打开**对话框中，在这种情况下编辑器工厂的默认/主视图。|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.TextView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序会传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法以获取**打开**对话框中，在此文档或数据的文本编辑器视图。|
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.UserChooseView_guid>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` 处理程序会传递到此值<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法提示用户选择的用户定义的视图，以使用该方法。|

## <a name="editor-factory-flags"></a>编辑器工厂标志

|值|描述|
|-----------|-----------------|
|[CEF.CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>)|已过时的标志的第一个参数的按位组合<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>方法。|
|[CEF.OpenAsNew](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenAsNew>)|作为第一个参数的按位组合<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>，方法，这指示的编辑器工厂应执行必要的修补程序。|
|[CEF.OpenFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_OpenFile>)|作为第一个参数的按位组合<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>方法，此标志会相互是 exclusive 的[CEF。CloneFile](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_CloneFile>)。|
|[CEF.Silent](<xref:Microsoft.VisualStudio.VSConstants.CEF#Microsoft_VisualStudio_VSConstants_CEF_Silent>)|作为第一个参数的按位组合<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>方法，这指示的编辑器工厂应编辑器创建而不显示用户界面 (UI)。|

## <a name="visual-studio-errors"></a>Visual Studio 错误

|值|描述|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|返回到异步行为的接口的常量时所述，在对象已忙|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]"不兼容的文档数据"。|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"未加载的包。"|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]和该异常指示"已存在项目。"|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"项目配置失败。"|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"未加载的项目。"|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"已打开解决方案"。|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"未打开解决方案"。|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|返回包含指定从一个字符串数组的参数的生成接口<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput>接口，但实现仅可以对所有输出应用方法。|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>方法返回此值，如果文档具有格式不能在编辑器中打开。|
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|HRESULT 值，该值指示用户命中中的后退按钮[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]向导。|

## <a name="visual-studio-constants"></a>Visual Studio 常量

|值|描述|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|错误 HRESULT 特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及指示"转发的项目。"|
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|一个常数，用于特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]"工具箱标记"。|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|一个常数，用于特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以便为广播通知消息通过<xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A>指示模式的开头的方法。|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|一个常数，用于特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以便为广播通知消息通过<xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A>指示模式的末尾的方法。|
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|一个常数，用于特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以便为广播通知消息通过<xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A>，该值指示命令栏度量值已更改的方法。|
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|一个常数，用于特定于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，该值指示尚未设置 cookie。|
|[VSITEMID.Nil](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Nil>)|A[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]表示没有的项目项的项标识符。 当前没有选定内容时，使用此值。|
|[VSITEMID.Root](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)|A[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]表示项目层次结构的根，用于标识整个层次结构，而不是单个项的项标识符。|
|[VSITEMID.Selection](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Selection>)|A[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]表示当前所选的一个或多个项目，可以包括层次结构的根的项标识符。|

## <a name="ivsselectionevents"></a>IVsSelectionEvents
 描述在 IDE 的哪些组件只是已选择，在<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>调用，例如。

|返回的常量|值|
|--------------|-----------|
|[SelectionElement.DocumentFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_DocumentFrame>)|0x2|
|[SelectionElement.PropertyBrowserSID](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_PropertyBrowserSID>)|0x4|
|[SelectionElement.StartupProject](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_StartupProject>)|0x3|
|[SelectionElement.UndoManager](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UndoManager>)|0x0|
|[SelectionElement.UserContext](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UserContext>)|0x5|
|[SelectionElement.WindowFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_WindowFrame>)|0x1|

## <a name="vsselelemid"></a>VSSELELEMID
 用于表示新的所选内容状态的常量。

|返回的常量|值|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1|

## <a name="component-selector-dialog-constants"></a>组件选择器对话框常量

|返回的常量|值|
|--------------|-----------|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1280|
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER + 1281|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER + 1290|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER + 1287|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER + 1285|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289|

## <a name="see-also"></a>另请参阅

- [用于扩展项目系统的 IDE 定义的命令](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)