---
title: 隐式数值转换表（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 4bbc6086dc5fd3838ef9361762c3068ca44efd0e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417591"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>隐式数值转换表（C# 参考）
下表显示预定义隐式数值转换。 隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。  
  
|From|到|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`、`int`、`long`、`float`、`double` 或 `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`、`long`、`float`、`double` 或 `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`。|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`、`float`、`double` 或 `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`、`double` 或 `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`、`double` 或 `decimal`|  
  
## <a name="remarks"></a>备注  
  
-   在从 `int`、`uint`、`long` 或 `ulong` 转换为 `float`，以及从 `long` 或 `ulong` 转换为 `double` 时，可能会丢失精度，但不会丢失量值。  
  
-   不存在针对 `char` 类型的隐式转换。  
  
-   浮点类型与 `decimal` 类型之间不存在隐式转换。  
  
-   `int` 类型的常数表达式可以转换为 `sbyte`、`byte`、`short`、`ushort`、`uint` 或 `ulong`，前提是常数表达式的值处于目标类型的范围内。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [整型表](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
