---
title: "常量（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81a085ff016fb9ee8f8a13167728c37ca799920a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="constants-c-programming-guide"></a>常量（C# 编程指南）
常量是不可变的值，在编译时是已知的，在程序的生命周期内不会改变。 常量使用 [const](../../../csharp/language-reference/keywords/const.md) 修饰符声明。 仅 C# 内置类型（不包括 <xref:System.Object?displayProperty=nameWithType>）可声明为 `const`。 有关内置类型的列表，请参阅[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)。 用户定义的类型（包括类、结构和数组）不能为 `const`。 使用 [readonly](../../../csharp/language-reference/keywords/readonly.md) 修饰符创建在运行时一次性（例如在构造函数中）初始化的类、结构或数组，此后不能更改。  
  
 C# 不支持 `const` 方法、属性或事件。  
  
 枚举类型使你能够为整数内置类型定义命名常量（例如 `int`、`uint`、`long` 等）。 有关详细信息，请参阅[枚举](../../../csharp/language-reference/keywords/enum.md)。  
  
 常量在声明时必须初始化。 例如:   
  
 [!code-csharp[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 在此示例中，常量 `months` 始终为 12，即使类本身也无法更改它。 实际上，当编译器遇到 C# 源代码中的常量标识符（例如，`months`）时，它直接将文本值替换到它生成的中间语言 (IL) 代码中。 因为运行时没有与常量相关联的变量地址，所以 `const` 字段不能通过引用传递，并且不能在表达式中显示为左值。  
  
> [!NOTE]
>  引用其他代码（如 DLL）中定义的常量值时要格外小心。 如果新版本的 DLL 定义了新的常量值，则程序仍将保留旧的文本值，直到根据新版本重新编译。  
  
 可以同时声明多个同一类型的常量，例如：  
  
 [!code-csharp[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 如果不创建循环引用，则用于初始化常量的表达式可以引用另一个常量。 例如:   
  
 [!code-csharp[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 常量可以标记为[公共](../../../csharp/language-reference/keywords/public.md)，[私有](../../../csharp/language-reference/keywords/private.md)，[保护](../../../csharp/language-reference/keywords/protected.md)，[内部](../../../csharp/language-reference/keywords/internal.md)，[受保护内部](../../../csharp/language-reference/keywords/protected-internal.md)或[私有受保护](../../../csharp/language-reference/keywords/private-protected.md)。 这些访问修饰符定义该类的用户访问该常量的方式。 有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。  
  
 常量是作为[静态](../../../csharp/language-reference/keywords/static.md)字段访问的，因为常量的值对于该类型的所有实例都是相同的。 不使用 `static` 关键字来声明这些常量。 不在定义常量的类中的表达式必须使用类名、句点和常量名称来访问该常量。 例如:   
  
 [!code-csharp[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [属性](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [类型](../../../csharp/programming-guide/types/index.md)  
 [只读](../../../csharp/language-reference/keywords/readonly.md)  
 [C# 不变性第一部分：不变性类型](http://go.microsoft.com/fwlink/?LinkId=112379)
