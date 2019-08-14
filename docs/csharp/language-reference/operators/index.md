---
title: C#-Operatoren – C#-Referenz
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 0e49c28f05d52c704a46806559407381c7eb3530
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971250"
---
# <a name="c-operators-c-reference"></a>C#-Operatoren (C#-Referenz)

C# bietet eine Reihe vordefinierter Operatoren, die von den integrierten Typen unterstützt werden. Beispielsweise führen [arithmetische Operatoren](arithmetic-operators.md) arithmetische Vorgänge mit Operanden von integrierten numerischen Typen durch, und [boolesche logische Operatoren](boolean-logical-operators.md) führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden aus.

Ein benutzerdefinierter Typ kann bestimmte Operatoren überladen, um das zugehörige Verhalten für die Operanden dieses Typs zu definieren. Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).

Die folgende Tabelle listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge. Die Operatoren in jeder Zeile verwenden die gleiche Rangfolgenebene.

| Operatoren | Kategorie oder Name |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-operator-), [x?.y](member-access-operators.md#null-conditional-operators--and-), [x?[y]](member-access-operators.md#null-conditional-operators--and-), [f(x)](member-access-operators.md#invocation-operator-), [a&#91;x&#93;](member-access-operators.md#indexer-operator-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [new](new-operator.md), [typeof](type-testing-and-conversion-operators.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [->](pointer-related-operators.md#pointer-member-access-operator--) | Primär |
| [+x](addition-operator.md), [-x](subtraction-operator.md), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [(T)x](type-testing-and-conversion-operators.md#cast-operator-), [await](../keywords/await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true und false](true-false-operators.md) | Unär |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Multiplikativ|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Additiv |
| [x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Shift |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-conversion-operators.md#is-operator), [as](type-testing-and-conversion-operators.md#as-operator) | Relational und Typtest |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Gleichheit |
| `x & y` | [Boolescher logischer AND-Operator](boolean-logical-operators.md#logical-and-operator-) oder [bitweiser logischer AND-Operator](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [Boolescher logischer XOR-Operator](boolean-logical-operators.md#logical-exclusive-or-operator-) oder [bitweiser logischer XOR-Operator](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [Boolescher logischer OR-Operator](boolean-logical-operators.md#logical-or-operator-) oder [bitweiser logischer OR-Operator](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | Bedingtes AND |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | Bedingtes OR |
| [x ?? y](null-coalescing-operator.md) | Nullzusammensetzungsoperator |
| [t ? x : y](conditional-operator.md) | Bedingter Operator |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [=>](lambda-operator.md) | Zuweisungs- und Lambdadeklaration |

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Operatoren](../../programming-guide/statements-expressions-operators/operators.md)
