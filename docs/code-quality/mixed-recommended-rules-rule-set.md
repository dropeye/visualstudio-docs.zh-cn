---
title: "“混合建议规则”规则集 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c3186b5b-0149-4a75-826e-e3539e4e703f
caps.latest.revision: 3
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 3
---
# “混合建议规则”规则集
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

这些微软推荐的混合规则重点针对支持公共语言运行时的 C\+\+ 项目中的最常见问题和最关键问题，其中包括潜在安全漏洞、应用程序崩溃以及其他重要的逻辑错误和设计错误。  应在您为支持公共语言运行时的 C\+\+ 项目创建的任何自定义规则集中包含此规则集。  对于此规则集，应当使用 Visual Studio 专业版及更高版本进行配置。  
  
|规则|说明|  
|--------|--------|  
|[C6001](../code-quality/c6001.md)|正在使用未初始化的内存|  
|[C6011](../code-quality/c6011.md)|正在取消对空指针的引用|  
|[C6029](../code-quality/c6029.md)|使用未经检查的值|  
|[C6031](../code-quality/c6031.md)|返回值被忽略:|  
|[C6053](../code-quality/c6053.md)|调用中包含零终止|  
|[C6054](../code-quality/c6054.md)|零终止缺失|  
|[C6059](../code-quality/c6059.md)|串联错误|  
|[C6063](../code-quality/c6063.md)|格式函数缺少字符串参数|  
|[C6064](../code-quality/c6064.md)|格式函数缺少整数参数|  
|[C6066](../code-quality/c6066.md)|格式函数缺少指针参数|  
|[C6067](../code-quality/c6067.md)|格式函数缺少字符串指针参数|  
|[C6101](../code-quality/c6101.md)|正在返回未初始化的内存|  
|[C6200](../code-quality/c6200.md)|索引超出缓冲区最大容量|  
|[C6201](../code-quality/c6201.md)|索引超出堆栈缓冲区最大容量|  
|[C6214](../code-quality/c6214.md)|从 HRESULT 到 BOOL 的强制转换无效|  
|[C6215](../code-quality/c6215.md)|从 BOOL 到 HRESULT 的强制转换无效|  
|[C6216](../code-quality/c6216.md)|由编译器插入的从 BOOL 到 HRESULT 的强制转换无效|  
|[C6217](../code-quality/c6217.md)|对 HRESULT 的 NOT 测试无效|  
|[C6220](../code-quality/c6220.md)|HRESULT 与 1 的比较无效|  
|[C6226](../code-quality/c6226.md)|HRESULT 到 \-1 的赋值无效|  
|[C6230](../code-quality/c6230.md)|HRESULT 用作 Boolean 无效|  
|[C6235](../code-quality/c6235.md)|非零常量的逻辑或运算|  
|[C6236](../code-quality/c6236.md)|非零常量的逻辑或运算|  
|[C6237](../code-quality/c6237.md)|零使用逻辑和失去副作用|  
|[C6242](../code-quality/c6242.md)|已强制执行局部回退|  
|[C6248](../code-quality/c6248.md)|正在创建 空 DACL|  
|[C6250](../code-quality/c6250.md)|未释放的地址说明符|  
|[C6255](../code-quality/c6255.md)|不受保护的 Alloca 用法|  
|[C6258](../code-quality/c6258.md)|请使用终止线程|  
|[C6259](../code-quality/c6259.md)|按位或限制开关中存在死代码|  
|[C6260](../code-quality/c6260.md)|使用字节算术|  
|[C6262](../code-quality/c6262.md)|堆栈使用过多|  
|[C6263](../code-quality/c6263.md)|在循环中使用 alloca|  
|[C6268](../code-quality/c6268.md)|强制转换中缺少括号|  
|[C6269](../code-quality/c6269.md)|已忽略取消引用指针|  
|[C6270](../code-quality/c6270.md)|格式函数缺少浮点参数|  
|[C6271](../code-quality/c6271.md)|格式函数有多余参数|  
|[C6272](../code-quality/c6272.md)|格式函数有非浮点参数|  
|[C6273](../code-quality/c6273.md)|格式函数有非整型参数|  
|[C6274](../code-quality/c6274.md)|格式函数有非字符参数|  
|[C6276](../code-quality/c6276.md)|字符串强制转换无效|  
|[C6277](../code-quality/c6277.md)|CreateProcess 调用无效|  
|[C6278](../code-quality/c6278.md)|数组新建与标量删除不匹配|  
|[C6279](../code-quality/c6279.md)|数组新建与标量删除不匹配|  
|[C6280](../code-quality/c6280.md)|内存分配与解除分配不匹配|  
|[C6281](../code-quality/c6281.md)|按位关系优先顺序|  
|[C6282](../code-quality/c6282.md)|赋值替换测试|  
|[C6283](../code-quality/c6283.md)|基元数组新建与标量删除不匹配|  
|[C6284](../code-quality/c6284.md)|格式函数的对象参数无效|  
|[C6285](../code-quality/c6285.md)|常量的逻辑或运算|  
|[C6286](../code-quality/c6286.md)|非零逻辑或运算丧失副作用|  
|[C6287](../code-quality/c6287.md)|冗余测试|  
|[C6288](../code-quality/c6288.md)|相互包括逻辑和为 false|  
|[C6289](../code-quality/c6289.md)|基于逻辑或的互斥运算为 true|  
|[C6290](../code-quality/c6290.md)|逻辑的\-非按位智能\-优先|  
|[C6291](../code-quality/c6291.md)|逻辑非按位或优先|  
|[C6292](../code-quality/c6292.md)|循环从最大值开始向上计数|  
|[C6293](../code-quality/c6293.md)|循环从最小值开始向下计数|  
|[C6294](../code-quality/c6294.md)|从未执行循环体|  
|[C6295](../code-quality/c6295.md)|无限循环|  
|[C6296](../code-quality/c6296.md)|循环只执行一次|  
|[C6297](../code-quality/c6297.md)|移位结果转换为较大大小|  
|[C6299](../code-quality/c6299.md)|位域到布尔值比较|  
|[C6302](../code-quality/c6302.md)|格式函数的字符字符串参数无效|  
|[C6303](../code-quality/c6303.md)|格式函数的宽字符字符串参数无效|  
|[C6305](../code-quality/c6305.md)|大小和计数使用不匹配|  
|[C6306](../code-quality/c6306.md)|变量参数函数调用错误|  
|[C6308](../code-quality/c6308.md)|Realloc 泄漏|  
|[C6310](../code-quality/c6310.md)|非法的异常筛选器常量|  
|[C6312](../code-quality/c6312.md)|异常继续执行循环|  
|[C6314](../code-quality/c6314.md)|按位或优先顺序|  
|[C6317](../code-quality/c6317.md)|不是未完成|  
|[C6318](../code-quality/c6318.md)|异常继续搜索|  
|[C6319](../code-quality/c6319.md)|按逗号忽略|  
|[C6324](../code-quality/c6324.md)|字符串复制而非字符串比较|  
|[C6328](../code-quality/c6328.md)|潜在参数类型不匹配|  
|[C6331](../code-quality/c6331.md)|VirtualFree 无效标志|  
|[C6332](../code-quality/c6332.md)|VirtualFree 无效参数|  
|[C6333](../code-quality/c6333.md)|VirtualFree 无效大小|  
|[C6335](../code-quality/c6335.md)|泄漏进程句柄|  
|[C6381](../code-quality/c6381.md)|关机信息缺失|  
|[C6383](../code-quality/c6383.md)|元素计数字节计数缓冲区溢出|  
|[C6384](../code-quality/c6384.md)|指针大小划分|  
|[C6385](../code-quality/c6385.md)|读溢出|  
|[C6386](../code-quality/c6386.md)|写溢出|  
|[C6387](../code-quality/c6387.md)|参数值无效|  
|[C6388](../code-quality/c6388.md)|参数值无效|  
|[C6500](../code-quality/c6500.md)|无效特性属性|  
|[C6501](../code-quality/c6501.md)|特性属性值冲突|  
|[C6503](../code-quality/c6503.md)|引用不可为空|  
|[C6504](../code-quality/c6504.md)|非指针为 空|  
|[C6505](../code-quality/c6505.md)|Void 的 MustCheck|  
|[C6506](../code-quality/c6506.md)|非指针或数组的缓冲区大小|  
|[C6507](http://msdn.microsoft.com/zh-cn/18f88cd1-d035-4403-a6a4-12dd0affcf21)|在取消引用空的零不匹配|  
|[C6508](../code-quality/c6508.md)|常量写访问|  
|[C6509](../code-quality/c6509.md)|对前置条件使用了返回值|  
|[C6510](../code-quality/c6510.md)|Null 终止于非指针|  
|[C6511](../code-quality/c6511.md)|MustCheck 必须为 Yes 或 No|  
|[C6513](../code-quality/c6513.md)|无缓冲区大小的元素大小|  
|[C6514](../code-quality/c6514.md)|缓冲区大小超出数组大小|  
|[C6515](../code-quality/c6515.md)|非指针缓冲区大小|  
|[C6516](../code-quality/c6516.md)|特性无属性|  
|[C6517](../code-quality/c6517.md)|不可读缓冲区的有效大小|  
|[C6518](../code-quality/c6518.md)|不可写缓冲区的可写大小|  
|[C6519](http://msdn.microsoft.com/zh-cn/2b6326b0-0539-4d26-8fb1-720114933232)|无效的批注：“NeedsRelease”属性的值必须为 Yes 或 No|  
|[C6521](http://msdn.microsoft.com/zh-cn/e98d0ae3-6f13-47b2-9a15-15d4055af9ef)|无效的字符串大小间接引用|  
|[C6522](../code-quality/c6522.md)|无效大小字符串类型|  
|[C6523](http://msdn.microsoft.com/zh-cn/11397a31-b224-46b0-afb7-d49ca576a3bb)|无效的字符串大小参数|  
|[C6525](../code-quality/c6525.md)|无效大小字符串不可访问位置|  
|[C6526](http://msdn.microsoft.com/zh-cn/59c590c7-0098-4166-a1ac-87f324596002)|无效的字符串大小缓冲区类型|  
|[C6527](../code-quality/c6527.md)|无效的批注: 无法对 void 类型的值使用 NeedsRelease 属性|  
|[C6530](../code-quality/c6530.md)|无法识别的格式字符串样式|  
|[C6540](../code-quality/c6540.md)|对此函数使用特性批注将使其现有的所有 \_\_declspec 批注无效|  
|[C6551](../code-quality/c6551.md)|大小规范无效: 表达式不可分析|  
|[C6552](../code-quality/c6552.md)|Deref\= 或 Notref\= 无效: 表达式不可分析|  
|[C6701](../code-quality/c6701.md)|该值不是有效的 Yes\/No\/Maybe 值:|  
|[C6702](../code-quality/c6702.md)|该值不是字符串值|  
|[C6703](../code-quality/c6703.md)|该值不是数字:|  
|[C6704](../code-quality/c6704.md)|意外的批注表达式错误:|  
|[C6705](../code-quality/c6705.md)|参数所需数目的注释不匹配参数的实际数目的注释|  
|[C6706](../code-quality/c6706.md)|批注的意外批注错误:|  
|[C6995](../code-quality/c6995.md)|未能保存 XML 日志文件|  
|[C26100](../code-quality/c26100.md)|争用条件。|  
|[C26101](../code-quality/c26101.md)|未能正确使用联锁操作|  
|[C26110](../code-quality/c26110.md)|调用方未能持有锁|  
|[C26111](../code-quality/c26111.md)|调用方未能解除锁|  
|[C26112](../code-quality/c26112.md)|调用方无法持有任何锁|  
|[C26115](../code-quality/c26115.md)|未能解除锁|  
|[C26116](../code-quality/c26116.md)|未能获取或持有锁|  
|[C26117](../code-quality/c26117.md)|解除未持有的锁|  
|[C26140](../code-quality/c26140.md)|并发 SAL 注释错误|  
|[C28020](../code-quality/c28020.md)|表达式对于此调用不适用|  
|[C28021](../code-quality/c28021.md)|所批注的参数必须是指针|  
|[C28022](../code-quality/c28022.md)|此函数的函数类与用于定义它的 typedef 的函数类不匹配。|  
|[C28023](../code-quality/c28023.md)|分配或传递的函数应具有至少一类的\_Function\_class\_批注。|  
|[C28024](../code-quality/c28024.md)|要分配的函数指针是用函数类批注的，它未包含在函数类表中。|  
|[C28039](../code-quality/c28039.md)|实参的类型应与该类型完全匹配|  
|[C28112](../code-quality/c28112.md)|通过 Interlocked 函数访问的变量必须始终通过 Interlocked 函数来访问|  
|[C28113](../code-quality/c28113.md)|通过互锁函数访问本地变量|  
|[C28125](../code-quality/c28125.md)|该函数必须从 try\/except 块中调用|  
|[C28137](../code-quality/c28137.md)|该变量参数应改为（文本）常量|  
|[C28138](../code-quality/c28138.md)|该常量参数应改为变量|  
|[C28159](../code-quality/c28159.md)|请考虑改用其他函数|  
|[C28160](../code-quality/c28160.md)|错误批注|  
|[C28163](../code-quality/c28163.md)|该函数不应从 try\/except 块中调用|  
|[C28164](../code-quality/c28164.md)|正在将参数传递给一个函数，该函数需要一个指向某个对象的指针（而非指向某个指针的指针）|  
|[C28182](../code-quality/c28182.md)|取消对 NULL 指针的引用。  指针包含与其他指针的空值。|  
|[C28183](../code-quality/c28183.md)|该参数可能是一个值，并且是在指针中找到的值的副本。|  
|[C28193](../code-quality/c28193.md)|该变量保留了一个必须检查的值|  
|[C28196](../code-quality/c28196.md)|未满足要求。（该表达式未计算为 true。）|  
|[C28202](../code-quality/c28202.md)|对非静态成员进行了非法引用|  
|[C28203](../code-quality/c28203.md)|对类成员的不明确引用。|  
|[C28205](../code-quality/c28205.md)|在非法上下文中使用了 \_Success\_ 或 \_On\_failure\_|  
|[C28206](../code-quality/c28206.md)|左操作数指向 struct，使用'\-\>'。|  
|[C28207](../code-quality/c28207.md)|左操作数是 struct，使用“.”。|  
|[C28209](../code-quality/c28209.md)|符号的声明具有冲突的声明|  
|[C28210](../code-quality/c28210.md)|\_On\_failure\_ 上下文的批注不得位于显式 pre 上下文中|  
|[C28211](../code-quality/c28211.md)|SAL\_context 需要静态上下文名称|  
|[C28212](../code-quality/c28212.md)|批注需要指针表达式|  
|[C28213](../code-quality/c28213.md)|\_Use\_decl\_annotations\_ 批注必须用于引用\(无需修改\)以前的声明。|  
|[C28214](../code-quality/c28214.md)|特性参数名称必须为 p1...p9|  
|[C28215](../code-quality/c28215.md)|typefix 无法应用于已具有 typefix 的参数|  
|[C28216](../code-quality/c28216.md)|checkReturn批注仅适用于特定函数参数的后置条件。|  
|[C28217](../code-quality/c28217.md)|对于函数，批注的参数数量与在文件中找到的数量不匹配|  
|[C28218](../code-quality/c28218.md)|对于函数参数，批注的参数与在文件中找到的参数不匹配|  
|[C28219](../code-quality/c28219.md)|批注中的参数应为枚举成员|  
|[C28220](../code-quality/c28220.md)|批注中的参数应为整数表达式|  
|[C28221](../code-quality/c28221.md)|批注中的参数应为字符串表达式|  
|[C28222](../code-quality/c28222.md)|批注需要 \_\_yes、\_\_no 或 \_\_maybe|  
|[C28223](../code-quality/c28223.md)|对于批注，参数未找到预期的标记\/标识符|  
|[C28224](../code-quality/c28224.md)|批注需要参数|  
|[C28225](../code-quality/c28225.md)|在批注中找到的所需参数的数量不正确|  
|[C28226](../code-quality/c28226.md)|批注也不能为 PrimOp \(在当前声明中\)|  
|[C28227](../code-quality/c28227.md)|批注也不能为 PrimOp \(参见上一个声明\)|  
|[C28228](../code-quality/c28228.md)|批注参数：不能在批注中使用类型|  
|[C28229](../code-quality/c28229.md)|批注不支持参数|  
|[C28230](../code-quality/c28230.md)|参数类型没有成员|  
|[C28231](../code-quality/c28231.md)|批注仅对数组有效|  
|[C28232](../code-quality/c28232.md)|pre、post 或 deref 不适用于任何批注。|  
|[C28233](../code-quality/c28233.md)|pre、post 或 deref 适用于块。|  
|[C28234](../code-quality/c28234.md)|\_at\_ 表达式不适用于当前函数。|  
|[C28235](../code-quality/c28235.md)|函数不能作为批注单独存在|  
|[C28236](../code-quality/c28236.md)|不能在表达式中使用该批注|  
|[C28237](../code-quality/c28237.md)|不再支持参数上的批注|  
|[C28238](../code-quality/c28238.md)|参数上的批注有多个 value、stringValue 和 longValue。  使用 paramn\=xxx|  
|[C28239](../code-quality/c28239.md)|参数上的批注同时具有 value、stringValue 或 longValue 之一和 paramn\=xxx。  仅使用 paramn\=xxx|  
|[C28240](../code-quality/c28240.md)|参数上的批注有 param2，但没有 param1|  
|[C28241](../code-quality/c28241.md)|无法识别参数上函数的批注|  
|[C28243](../code-quality/c28243.md)|参数上函数的批注需要的取消引用次数多于已批注的实际类型所允许的次数|  
|[C28244](../code-quality/c28244.md)|函数的批注包含无法分析的参数\/外部批注|  
|[C28245](../code-quality/c28245.md)|函数的批注在非成员函数上批注“this”|  
|[C28246](../code-quality/c28246.md)|函数的参数不匹配参数的类型批注|  
|[C28250](../code-quality/c28250.md)|函数的注解不一致:上一个实例有错误|  
|[C28251](../code-quality/c28251.md)|函数的注解不一致:此实例有错误|  
|[C28252](../code-quality/c28252.md)|函数的批注不一致:参数在此实例上有另一个批注|  
|[C28253](../code-quality/c28253.md)|函数的批注不一致:参数在此实例上有另一个批注|  
|[C28254](../code-quality/c28254.md)|批注中不支持 dynamic\_cast\<\>\(\)。|  
|[C28262](../code-quality/c28262.md)|在函数中找到了批注的语法错误\(对于批注\):|  
|[C28263](../code-quality/c28263.md)|内部批注的条件批注中发现了语法错误|  
|[C28264](http://msdn.microsoft.com/zh-cn/bf6ea983-a06e-4752-a042-747a7dbf338c)|结果列表值必须是常量。|  
|[C28267](../code-quality/c28267.md)|在函数中找到了批注的语法错误\(对于批注\):|  
|[C28272](../code-quality/c28272.md)|检查时针对函数参数的批注与函数声明不一致|  
|[C28273](../code-quality/c28273.md)|对于函数，线索与函数声明不一致|  
|[C28275](../code-quality/c28275.md)|\_Macro\_value\_ 的参数为 null|  
|[C28279](../code-quality/c28279.md)|对于符号，已找到“begin”，但没有匹配的“end”|  
|[C28280](../code-quality/c28280.md)|对于符号，发现了没有与之匹配的“begin”的“end”|  
|[C28282](../code-quality/c28282.md)|格式字符串必须位于前置条件中:|  
|[C28285](../code-quality/c28285.md)|对于函数，参数中有语法错误|  
|[C28286](../code-quality/c28286.md)|对于函数，结尾附近有语法错误|  
|[C28287](../code-quality/c28287.md)|对于函数， 批注中存在语法错误\(无法识别的参数名\)|  
|[C28288](../code-quality/c28288.md)|对于函数，\_At\_\(\) 批注中存在语法错误\(无效的参数名\)|  
|[C28289](../code-quality/c28289.md)|对于函数: ReadableTo 或 WritableTo 没有用作参数的限制规范。|  
|[C28290](../code-quality/c28290.md)|函数的批注包含的外部对象多于参数的实际数量|  
|[C28291](../code-quality/c28291.md)|deref 级别 0 处的 post null\/notnull 对于函数无意义。|  
|[C28300](../code-quality/c28300.md)|运算符的不兼容类型的表达式操作数|  
|[C28301](../code-quality/c28301.md)|函数的第一个声明没有批注|  
|[C28302](../code-quality/c28302.md)|在批注上发现额外的 \_Deref\_ 运算符|  
|[C28303](../code-quality/c28303.md)|在批注上发现不明确的 \_Deref\_ 运算符|  
|[C28304](../code-quality/c28304.md)|发现对令牌应用了放置位置不正确的 \_Notref\_ 运算符|  
|[C28305](../code-quality/c28305.md)|分析 token 时发现了错误。|  
|[C28306](../code-quality/c28306.md)|对参数的批注已过时|  
|[C28307](../code-quality/c28307.md)|对参数的批注已过时|  
|[C28350](../code-quality/c28350.md)|该注释描述了在特定条件下不适用的情况.|  
|[C28351](../code-quality/c28351.md)|批注描述了一种无法使用动态值\(变量\)的情况。|  
|[CA1001](../Topic/CA1001:%20Types%20that%20own%20disposable%20fields%20should%20be%20disposable.md)|那自己可支配领域类型应该是一次性的|  
|[CA1009](../code-quality/ca1009-declare-event-handlers-correctly.md)|正确声明事件处理程序|  
|[CA1016](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|用AssemblyVersionAttribute标记组件|  
|[CA1033](../Topic/CA1033:%20Interface%20methods%20should%20be%20callable%20by%20child%20types.md)|接口方法能由子类可调用|  
|[CA1049](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|拥有本机资源的类型应该是一次性的|  
|[CA1060](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|移动P\/Invokes 到 NativeMethods类|  
|[CA1061](../code-quality/ca1061-do-not-hide-base-class-methods.md)|不要隐藏基类方法|  
|[CA1063](../code-quality/ca1063-implement-idisposable-correctly.md)|正确实现IDisposable|  
|[CA1065](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|不提高在意外的位置异常|  
|[CA1301](../Topic/CA1301:%20Avoid%20duplicate%20accelerators.md)|避免重复加速器|  
|[CA1400](../Topic/CA1400:%20P-Invoke%20entry%20points%20should%20exist.md)|P \/ Invoke入口点应该存在|  
|[CA1401](../Topic/CA1401:%20P-Invokes%20should%20not%20be%20visible.md)|P\/Invokes应该是不可见|  
|[CA1403](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|自动布局类型不应该是COM可见|  
|[CA1404](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|P \/ Invoke后立即调用GetLastError|  
|[CA1405](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM可见类型的基类型应该是COM可见|  
|[CA1410](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|COM注册方法应该匹配|  
|[CA1415](../code-quality/ca1415-declare-p-invokes-correctly.md)|正确声明P\/Invokes|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|移除空的终结|  
|[CA1900](../code-quality/ca1900-value-type-fields-should-be-portable.md)|值类型字段应该是便携的|  
|[CA1901](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|P\/Invoke 声明应为可移植声明|  
|[CA2002](../Topic/CA2002:%20Do%20not%20lock%20on%20objects%20with%20weak%20identity.md)|不要锁定具有弱标识的对象|  
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|检查SQL查询的安全漏洞|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|指定封送处理的P \/ Invoke字符串参数|  
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|审查的声明性安全上的值类型|  
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|指针应该是不可见|  
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|有保证的类型不应公开栏|  
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|方法的安全性应该是类型的一个超集|  
|[CA2116](../Topic/CA2116:%20APTCA%20methods%20should%20only%20call%20APTCA%20methods.md)|APTCA方法应该只调用APTCA方法|  
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA类型应该只延长APTCA基本类型|  
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|不要使用链接请求间接公开方法|  
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|重写的链接请求应与基相同|  
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|裹在外层的try脆弱的finally子句|  
|[CA2126](../Topic/CA2126:%20Type%20link%20demands%20require%20inheritance%20demands.md)|类型链接请求需要继承要求|  
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|安全关键类型可能不参与类型等价|  
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|默认构造函数必须至少与基类型默认构造函数一样关键|  
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|委托必须绑定到具有一致透明度的方法|  
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|重写基方法时，方法必须保持一致的透明度|  
|[CA2137](../Topic/CA2137:%20Transparent%20methods%20must%20contain%20only%20verifiable%20IL.md)|透明方法必须只包含可验证的IL|  
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|透明方法不得调用与SuppressUnmanagedCodeSecurity属性的方法|  
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|透明代码不得引用安全关键项|  
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|透明方法不得满足LinkDemands|  
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|类型必须至少与其基类型和接口一样关键|  
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|透明方法不得使用安全断言|  
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|透明方法不能调用本地代码|  
|[CA2200](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|重新抛出保存堆栈的详细信息|  
|[CA2202](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|不要多次释放对象|  
|[CA2207](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|以内联方式初始化值类型的静态字段|  
|[CA2212](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|不要使用 WebMethod 标记服务组件|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|应释放可释放的字段|  
|[CA2214](../Topic/CA2214:%20Do%20not%20call%20overridable%20methods%20in%20constructors.md)|不要调用构造函数重写的方法|  
|[CA2216](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|可释放类型应声明终结器|  
|[CA2220](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|终结器应调用基类的终结器|  
|[CA2229](../code-quality/ca2229-implement-serialization-constructors.md)|实现序列化构造函数|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|重写 ValueType.Equals 时应重载相等运算符|  
|[CA2232](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|使用 STAThread 标记 Windows 窗体的入口点|  
|[CA2235](../code-quality/ca2235-mark-all-non-serializable-fields.md)|标记所有不可序列化的字段|  
|[CA2236](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|对 ISerializable 的类调用基类方法|  
|[CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|以 SerializableAttribute 标记 ISerializable 类型|  
|[CA2238](../code-quality/ca2238-implement-serialization-methods-correctly.md)|正确实现序列化方法|  
|[CA2240](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)|正确实现 ISerializable|  
|[CA2241](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|为格式化方法提供正确的参数|  
|[CA2242](../code-quality/ca2242-test-for-nan-correctly.md)|正确测试NaN|