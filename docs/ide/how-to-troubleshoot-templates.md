---
title: "对 Visual Studio 项目模板和项模板加载进行故障排除 | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [Visual Studio], troubleshooting
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9242d053044fa66e6eb3d506382cf7cfb5d0295
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-troubleshoot-templates"></a>如何：对模板进行故障排除

如果模板在开发环境中无法加载，可以采用以下几种方法找出问题。

## <a name="validate-the-vstemplate-file"></a>验证 .vstemplate 文件

如果模板中的 .vstemplate 文件未遵循 Visual Studio 模板架构，则“新建项目”对话框中可能不会显示该模板。

### <a name="to-validate-the-vstemplate-file"></a>验证 .vstemplate 文件

1. 找到包含模板的 .zip 文件。

1. 解压缩 .zip 文件。

1. 在 Visual Studio 的“文件”菜单上，选择“打开” > “文件”。

1. 选择模板的 .vstemplate 文件，然后选择“打开”。

1. 验证 .vstemplate 文件的 XML 是否遵循模板架构。 有关 .vstemplate 架构的详细信息，请参阅[模板架构引用](../extensibility/visual-studio-template-schema-reference.md)。

    > [!NOTE]
    > 要在创作 .vstemplate 文件时获得 IntelliSense 支持，请将 `xmlns` 特性添加到 `VSTemplate` 元素，并为其赋值 http://schemas.microsoft.com/developer/vstemplate/2005。

1. 保存并关闭 .vstemplate 文件。

1. 选择模板中包含的文件，右键单击，然后选择“发送至” > “压缩的文件夹（zip 格式）”。 所选的文件被压缩到一个 .zip 文件中。

1. 将新的 .zip 文件与旧的 .zip 文件放在同一目录中。

1. 删除解压缩的模板文件和旧的 .zip 模板文件。

## <a name="enable-diagnostic-logging"></a>启用诊断记录

可按照[模板发现疑难解答（扩展性）](../extensibility/troubleshooting-template-discovery.md)中的步骤启用模板发现的诊断日志记录。

## <a name="see-also"></a>请参阅

[模板发现疑难解答（扩展性）](../extensibility/troubleshooting-template-discovery.md)  
[自定义模板](../ide/customizing-project-and-item-templates.md)  
[创建项目和项模板](../ide/creating-project-and-item-templates.md)  
[模板架构引用](../extensibility/visual-studio-template-schema-reference.md)