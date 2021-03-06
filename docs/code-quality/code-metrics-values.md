---
title: "计算在 Visual Studio 中的代码度量值 |Microsoft 文档"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code metrics [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 553ed7d6a6fcc2edef436251d720919fe399653a
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="code-metrics-values"></a>代码度量值

现代的软件应用程序的复杂性增加也会增加使代码保持可靠、 可维护困难。 代码度量是一组软件度量值，使开发人员可以更好地了解他们正在开发的代码。 通过利用代码度量，开发人员可以了解哪些类型和/或方法应返工或更彻底的测试。 开发团队可以标识潜在的风险，了解的当前状态的一个项目，并在软件开发过程中跟踪进度。

开发人员可以使用 Visual Studio 生成代码度量值数据中测量的复杂性和可维护性托管代码。 可以为整个解决方案或单个项目中生成代码度量数据。

有关如何在 Visual Studio 中生成代码度量数据的信息，请参阅[如何： 生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)。

## <a name="software-measurements"></a>软件度量值

以下列表显示的代码的 Visual Studio 计算的度量结果：

- **可维护性指数**-计算表示相对易用性的维护代码的索引值介于 0 和 100 之间。 较高的值意味着更好的可维护性。 颜色编码分级可用来快速确定你的代码中的故障点。 绿色等级介于 20 和 100 之间，表示的代码具有良好的可维护性。 黄色分级介于 10 和 19 之间，指示代码可维护性中等。 红色分级是 0 到 9 之间的分级，并指示低的可维护性。

- **圈复杂度**-衡量代码的结构化的复杂程度。 通过计算的流中的程序不同的代码路径数则创建它。 具有复杂控制流的程序将需要更多测试来实现良好的代码覆盖率，并且不容易维护。

- **继承深度**-指示的类层次结构的根到扩展的类定义的数量。 深的层次结构更难有可能是为了了解其中定义特定的方法和字段或 / 和重新定义。

- **类耦合**-测量与通过参数、 本地变量、 返回类型、 方法调用、 泛型或模板实例化、 基类，这些类、 接口实现、 外部类型上定义的字段的唯一类耦合和特性修饰。 软件良好的设计指出类型和方法应具有高内聚和较低的耦合。 耦合较高指示重复使用和维护由于其他类型其许多依存关系会很困难的设计。

- **代码行**-指示代码中的行的大致数目。 计数基于 IL 代码，因此不精确的源代码文件中的行数。 非常高的计数可能指示类型或方法尝试执行的操作过多的工作，并且应拆分。 此外，它也可能表示的类型或方法可能难以维护。

## <a name="anonymous-methods"></a>匿名方法

*匿名方法*就是没有名称的方法。 匿名方法是最常用于将代码块作为委托参数传递。 匿名方法中的成员，如方法或访问器，声明的度量结果都与声明方法的成员关联。 它们不具有成员的调用的方法相关联。

有关代码度量如何处理匿名方法的详细信息，请参阅[匿名方法和代码分析](../code-quality/anonymous-methods-and-code-analysis.md)。

## <a name="generated-code"></a>生成的代码

某些软件工具和编译器生成的代码，它将添加到项目和项目开发人员看不到或不应更改。 大多数情况下，代码度量忽略生成的代码，当它计算度量值时。 这使度量值以反映开发人员可以查看和更改。

不忽略生成为 Windows 窗体的代码，因为它是开发人员可以查看和更改的代码。

## <a name="next-steps"></a>后续步骤

- [如何： 生成代码度量数据](../code-quality/how-to-generate-code-metrics-data.md)
- [使用代码度量结果窗口](../code-quality/working-with-code-metrics-data.md)