---
title: "生成并配置你的应用模型 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dc8f572-a09e-4d19-a92d-f1df383e728b
caps.latest.revision: 7
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 8f84f22444a5df5b9f4f4af44cd8ee9136403467
ms.openlocfilehash: 864963f32fe703ada943f7e5202d7ebf6bf21e51
ms.lasthandoff: 02/22/2017

---
# <a name="generate-and-configure-your-app-from-models"></a>从模型中生成并配置你的应用程序
你可从模型生成或配置你的应用程序的不同部件。
  
 模型比代码更能直接表示要求。 与更新代码相比，通过直接从模型派生应用程序的行为，你可以更加快速可靠地对更改的需求做出响应。 尽管需要做一些初始工作来设置派生，但如果你预计要求会发生改变，或者你计划生成产品的几个变体，则这种投资是会有回报的。  
  
## <a name="generating-the-code-of-your-application-from-a-model"></a>从模型生成应用程序代码  
 生成代码的最便捷方法是使用模板。 您可以在同一个生成代码[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]您在其中保存该模型的解决方案。 有关详细信息，请参见:  
  
-   [使用 T4 文本模板生成设计时代码](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
-   [从域特定语言生成代码](../modeling/generating-code-from-a-domain-specific-language.md)  
  
 这种方法易于进行增量应用。 首先使用一个仅适用于特定情况的应用程序，并从模型中选择一些你希望更改的应用程序部分。 重命名这些部分的源文件，以便这些文件成为文本模板 (.tt) 文件。 此时，将自动从模板文件生成 .cs 源文件，该应用程序能像以前一样工作。  
  
 然后，你可以取用一部分代码并将其替换为文本模板表达式，该表达式读取模型并生成这部分的源文件。 至少模型的一个值应生成原始源，这样你才能再次运行该应用程序，该应用程序才能像以前一样工作。 在测试过不同的模型值之后，你可以继续在另一部分代码中插入模板表达式。  
  
 这种递增方法意味着代码生成通常是一种低风险的方式。 生成的应用程序通常能执行与手写版本几乎一样的操作。  
  
 但是，如果是从一个现有应用程序开始，你可能会发现需要进行很多重构才能隔开受模型控制的不同行为，以便这些行为可以独立改变。 建议你在估计项目成本时，将应用程序的这一方面评估在内。  
  
## <a name="configuring-your-application-from-a-model"></a>从模型进配置应用程序  
 如果你希望在运行时改变应用程序的行为，则无法使用在编译应用程序前生成源代码的代码生成。 相反，您可以设计您的应用程序若要读取模型，并相应地改变其行为。 有关详细信息，请参见:  
  
-   [如何：在程序代码中从文件打开模型](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 也可以以增量方式应用此方法，但一开始会有更多的工作要做。 你需要编写读取模型代码，并设置一个允许可变部分访问其值的框架。 生成泛型的可变部分比代码生成的开销更大。  
  
 一个泛型应用程序的执行效果通常没有其特定的对应应用程序好。 如果性能很关键，则你的项目计划应将这种风险评估在内。  
  
## <a name="developing-a-derived-application"></a>开发派生应用程序  
 你可能会发现以下一般准则会很有帮助。  
  
-   **先具体后一般化。** 首先编写一个特定版本的应用程序。 此版本应能在一组条件下工作。 当你认为该应用程序能正常工作时，你可以从模型派生一些部分。 逐渐扩展派生的部分。  
  
     例如，设计一个具有一组特定网页的网站，然后设计一个 Web 应用程序来表示在模型中定义的页面。  
  
-   **模型的变体方面。** 确定将发生改变的方面，两个不同部署之间的改变，或随着需求变化而改变。 这些方面应从模型派生。  
  
     例如，如果一组网页及其之间的链接发生更改，但这些网页的样式和格式始终是相同的，那么模型应描述这些链接，但不必描述网页的格式。  
  
-   **任务分离。** 如果可变方面能分成独立的区域，则为每个区域使用单独的模型。 使用 ModelBus，你可以定义同时影响各模型及其之间的约束的操作。  
  
     例如，使用一个模型来定义网页导航，使用另一个模型来定义网页布局。
  
-   **模型的要求，而不是解决方案。** 设计模型，以便用来描述用户需求。 与此相反，不要根据实现的可变方面设计表示法。  
  
     例如，Web 导航模型应表示网页和网页间的超链接。 Web 导航模型不应表示应用程序中的 HTML 或类的片段。  
  
-   **生成或解释？** 如果特定部署的需求将很少更改，则从模型生成程序代码。 如果需求可能会频繁更改，或者可能共存于同一部署的多个变体中，则编写应用程序，以便该应用程序可以读取和解释模型。  
  
     例如，如果你使用网站模型来开发一系列独立安装的不同网站，则应从模型生成网站代码。 但如果你使用模型来控制一个每天改变的网站，则最好编写一个 Web 服务器来相应地读取模型和表示网站。  
  
-   **UML 或 DSL？** 考虑通过使用构造型扩展 UML 来创建你的建模表示法。 如果没有符合目标的 UML 关系图，则定义一个 DSL。 但要避免中断 UML 的标准语义。  
  
     例如，UML 类图是框和箭头的集合；有了这种表示法，你在理论上能定义任何内容。 但是，除非你实际需要描述一组类型，否则我们不建议你使用类图。 例如，你可以采用类图来描述不同类型的网页。  
  
## <a name="see-also"></a>另请参阅  
 [从域特定语言生成代码](../modeling/generating-code-from-a-domain-specific-language.md)   
 [如何︰ 从程序代码中的文件打开模型](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [使用 T4 文本模板生成设计时代码](../modeling/design-time-code-generation-by-using-t4-text-templates.md)