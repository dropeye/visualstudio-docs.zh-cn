---
title: "实用程序节点 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ff732221-b731-424c-ad5b-82ef5f21dff5
caps.latest.revision: 11
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 11
---
# 实用程序节点
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

在着色器设计器中，实用工具节点表示通用，不调整完全到其他类别的有用的着色器计算。  某些实用工具节点执行简单的操作，如一起追加向量或条件选择结果，同时，其他基于常见的照明模型执行复杂的操作，如计算光照基值。  
  
## “实用工具”节点引用  
  
|节点|详细信息|属性|  
|--------|----------|--------|  
|**追加向量**|通过追加指定的输入在一起创建一个矢量。<br /><br /> **输入：**<br /><br /> `Vector`: `float`, `float2` 或 `float3`<br /> 要追加的值。<br /><br /> `Value to Append`: `float`<br /> 要追加的值。<br /><br /> **输出：**<br /><br /> `Output`: `float2`、`float3` 或 `float4` 取决于输入 `Vector` 的类型<br /> 新的向量。|无|  
|**菲涅耳**|基于指定表面法线计算菲涅尔衰减。<br /><br /> 菲涅尔衰减值表示当前像素的表面法线与视图矢量的重合度。  当两个矢量对齐时，函数的结果为 0；两个矢量的相似度越低，结果值就越大，当两个矢量正交时，结果将达到最大值。  可使用菲涅尔衰减，根据当前像素和照相机的方向之间的关系强化或弱化效果。<br /><br /> **输入：**<br /><br /> `Surface Normal`: `float3`<br /> 当前像素的表面法线，定义在当前像素的正切空间中。  使用此工具，您可以混乱明显的表面法线，就像在正常映射中一样。<br /><br /> **输出：**<br /><br /> `Output`: `float`<br /> 当前像素的反射率。|**指数**<br /> 用于计算菲涅尔衰减的指数。|  
|**如果**|有条件地选择每个元素的三个予考虑结果之一。  条件由其他两个指定的输入之间的关系定义。<br /><br /> 对于结果的每个分量，将根据前两个输入的对应分量之间的关系选择三个可能结果之一的对应分量。<br /><br /> **输入：**<br /><br /> `X`：`float`、`float2`、 `float3` 或 `float4`<br /> 比较左侧的值。<br /><br /> `Y`：与输入 `X` 相同类型<br /> 比较右侧的值。<br /><br /> `X > Y`：与输入 `X` 相同类型<br /> 当 `X` 大于 `Y` 时，该值为所选值。<br /><br /> `X = Y`：与输入 `X` 相同类型<br /> 当 `X` 与 `Y` 相等时，该值为所选值。<br /><br /> `X < Y`：与输入 `X` 相同类型<br /> 当 `X` 小于 `Y` 时，该值为所选值。<br /><br /> **输出：**<br /><br /> `Output`: `float3`<br /> 每个元素的选择结果。|无|  
|**朗伯**|通过使用指定图面规则，根据朗伯照明模型计算当前像素的颜色。<br /><br /> 此颜色是直接光照下的环境颜色和漫射光照量之和。  环境颜色约等于间接光照的总量，但如果没有其他光照的帮助，则会显得单调暗淡。  漫射光照可帮助为对象增加形状和深度。<br /><br /> **输入：**<br /><br /> `Surface Normal`: `float3`<br /> 当前像素的表面法线，定义在当前像素的正切空间中。  使用此工具，您可以混乱明显的表面法线，就像在正常映射中一样。<br /><br /> `Diffuse Color`: `float3`<br /> 当前像素的漫射色通常为**“点颜色”**。  如果未提供输入，则默认值为空白。<br /><br /> **输出：**<br /><br /> `Output`: `float3`<br /> 当前像素的散射颜色。|无|  
|**掩码向量**|指定向量的掩码组件。<br /><br /> 可使用此运算从某个颜色值中移除特定颜色通道，或阻止特定分量对后续计算产生影响。<br /><br /> **输入：**<br /><br /> `Vector`: `float4`<br /> 要过滤的向量。<br /><br /> **输出：**<br /><br /> `Output`: `float4`<br /> 掩码矢量。|**“红色 \/X”**<br /> 若要遮住红色\(x\)分量，则为 **False**；否则为 **True**。<br /><br /> **绿色 \/Y**<br /> 若要遮住绿色\(y\)分量，则为 **False**；否则为 **True**。<br /><br /> **“蓝色 \/Z”**<br /> 若要遮住蓝色 \(z\) 分量，则为 **False**；否则为 **True**。<br /><br /> **Alpha \/ W**<br /> 若要遮住 alpha \(w\) 分量，则为**“False”**；否则为**“True”**。|  
|**反射向量**|根据照相机位置计算当前像素在正切空间内的反射矢量。<br /><br /> 可使用此方法计算反射、立方体贴图坐标和反射光照量<br /><br /> **输入：**<br /><br /> `Tangent Space Surface Normal`: `float3`<br /> 当前像素的表面法线，定义在当前像素的正切空间中。  使用此工具，您可以混乱明显的表面法线，就像在正常映射中一样。<br /><br /> **输出：**<br /><br /> `Output`: `float3`<br /> 反射向量。|无|  
|**镜像**|通过使用指定图面规则，根据 Phong 照明模型计算反射光照量。<br /><br /> 反射光照可为对象\(例如，水、塑料或金属\)提供发光的反射外观。<br /><br /> **输入：**<br /><br /> `Surface Normal`: `float3`<br /> 当前像素的表面法线，定义在当前像素的正切空间中。  使用此工具，您可以混乱明显的表面法线，就像在正常映射中一样。<br /><br /> **输出：**<br /><br /> `Output`: `float3`<br /> 镜像突出显示的颜色基值。|无|