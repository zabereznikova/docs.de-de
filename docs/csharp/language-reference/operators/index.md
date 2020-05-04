---
title: C#-Operatoren – C#-Referenz
ms.date: 04/28/2020
f1_keywords:
- cs.operators
helpviewer_keywords:
- operators [C#]
- operator precedence [C#]
- operator associativity [C#]
- expressions [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 76a9b1efb46af976e59e5f16d3180891ec54ecee
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507402"
---
# <a name="c-operators-c-reference"></a>C#-Operatoren (C#-Referenz)

C# bietet eine Reihe von Operatoren, die von den integrierten Typen unterstützt werden. Beispielsweise führen [arithmetische Operatoren](arithmetic-operators.md) arithmetische Vorgänge mit numerischen Operanden durch, und [boolesche logische Operatoren](boolean-logical-operators.md) führen logische Vorgänge mit den [bool](../builtin-types/bool.md)-Operanden durch. Bestimmte Operatoren können [überladen](operator-overloading.md) werden. Mit Operatorüberladung können Sie das Operatorverhalten für die Operanden eines benutzerdefinierten Typs angeben.

In einem [Ausdruck](../../programming-guide/statements-expressions-operators/expressions.md) legen die Operatorrangfolge und -assoziativität die Reihenfolge fest, in der die Vorgänge durchgeführt werden. Sie können Klammern verwenden, um die Reihenfolge der Auswertung zu ändern, die durch die Operatorrangfolge und -assoziativität festgelegt wird.

## <a name="operator-precedence"></a>Operatorrangfolge

In einem Ausdruck mit mehreren Operatoren werden die Operatoren mit höherer Rangfolge vor den Operatoren mit niedrigerer Rangfolge ausgewertet. Im folgenden Beispiel wird die Multiplikation zuerst durchgeführt, da Sie eine höhere Rangfolge aufweist als die Addition:

```csharp-interactive
var a = 2 + 2 * 2;
Console.WriteLine(a); //  output: 6
```

Verwenden Sie Klammern, um die Reihenfolge der Auswertung zu ändern, die durch die Operatorrangfolge festgelegt ist:

```csharp-interactive
var a = (2 + 2) * 2;
Console.WriteLine(a); //  output: 8
```

Die folgende Tabelle listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge. Die Operatoren in jeder Zeile weisen die gleiche Rangfolge auf.

| Operatoren | Kategorie oder Name |
| --------- | ---------------- |
| [x.y](member-access-operators.md#member-access-expression-), [f(x)](member-access-operators.md#invocation-expression-), [a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [`x?[y]`](member-access-operators.md#null-conditional-operators--and-), [x++](arithmetic-operators.md#increment-operator-), [x--](arithmetic-operators.md#decrement-operator---), [x!](null-forgiving.md), [new](new-operator.md), [typeof](type-testing-and-cast.md#typeof-operator), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [nameof](nameof.md), [delegate](delegate-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [x->y](pointer-related-operators.md#pointer-member-access-operator--) | Primär |
| [+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [\!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++x](arithmetic-operators.md#increment-operator-), [--x](arithmetic-operators.md#decrement-operator---), [^x](member-access-operators.md#index-from-end-operator-), [(T)x](type-testing-and-cast.md#cast-expression), [await](await.md), [&x](pointer-related-operators.md#address-of-operator-), [*x](pointer-related-operators.md#pointer-indirection-operator-), [true und false](true-false-operators.md) | Unär |
| [x..y](member-access-operators.md#range-operator-) | Bereich |
| [switch](../../whats-new/csharp-8.md#switch-expressions) | `switch`-Ausdruck |
| [x * y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-) | Multiplikativ|
| [x + y](arithmetic-operators.md#addition-operator-), [x – y](arithmetic-operators.md#subtraction-operator--) | Additiv |
| [x \<\<  y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-) | Shift |
| [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-), [is](type-testing-and-cast.md#is-operator), [as](type-testing-and-cast.md#as-operator) | Relational und Typtest |
| [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-) | Gleichheit |
| `x & y` | [Boolescher logischer AND-Operator](boolean-logical-operators.md#logical-and-operator-) oder [bitweiser logischer AND-Operator](bitwise-and-shift-operators.md#logical-and-operator-) |
| `x ^ y` | [Boolescher logischer XOR-Operator](boolean-logical-operators.md#logical-exclusive-or-operator-) oder [bitweiser logischer XOR-Operator](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) |
| <code>x &#124; y</code> | [Boolescher logischer OR-Operator](boolean-logical-operators.md#logical-or-operator-) oder [bitweiser logischer OR-Operator](bitwise-and-shift-operators.md#logical-or-operator-) |
| [x && y](boolean-logical-operators.md#conditional-logical-and-operator-) | Bedingtes AND |
| [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) | Bedingtes OR |
| [x ?? y](null-coalescing-operator.md) | Nullzusammensetzungsoperator |
| [c ? t : f](conditional-operator.md) | Bedingter Operator |
| [x = y](assignment-operator.md), [x += y](arithmetic-operators.md#compound-assignment), [x -= y](arithmetic-operators.md#compound-assignment), [x *= y](arithmetic-operators.md#compound-assignment), [x /= y](arithmetic-operators.md#compound-assignment), [x %= y](arithmetic-operators.md#compound-assignment), [x &= y](boolean-logical-operators.md#compound-assignment), [x &#124;= y](boolean-logical-operators.md#compound-assignment), [x ^= y](boolean-logical-operators.md#compound-assignment), [x <<= y](bitwise-and-shift-operators.md#compound-assignment), [x >>= y](bitwise-and-shift-operators.md#compound-assignment), [x ??= y](null-coalescing-operator.md), [=>](lambda-operator.md) | Zuweisungs- und Lambdadeklaration |

## <a name="operator-associativity"></a>Operatorassoziativität

Wenn Operatoren die gleiche Rangfolge aufweisen, legt die Assoziativität der Operatoren die Reihenfolge fest, in der Vorgänge durchgeführt werden:

- *Linksassoziative* Operatoren werden von links nach rechts ausgewertet. Mit Ausnahme der [Zuweisungsoperatoren](assignment-operator.md) und des [NULL-Sammeloperators ](null-coalescing-operator.md)sind alle binären Operatoren linksassoziativ. `a + b - c` wird beispielsweise als `(a + b) - c` ausgewertet.
- *Rechtsassoziative* Operatoren werden von rechts nach links ausgewertet. Die Zuweisungsoperatoren, die NULL-Sammeloperatoren und der [bedingte Operator `?:`](conditional-operator.md) sind rechtsassoziativ. `x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.

Verwenden Sie Klammern, um die Reihenfolge der Auswertung zu ändern, die durch die Operatorassoziativität festgelegt ist:

```csharp-interactive
int a = 13 / 5 / 2;
int b = 13 / (5 / 2);
Console.WriteLine($"a = {a}, b = {b}");  // output: a = 1, b = 6
```

## <a name="operand-evaluation"></a>Operandenauswertung

Unabhängig von der Operatorrangfolge und -assoziativität werden die Operanden in einem Ausdruck von links nach rechts ausgewertet. Die folgenden Beispiele veranschaulichen die Reihenfolge, in der Operatoren und Operanden ausgewertet werden:

| expression | Reihenfolge der Auswertung |
| ---------- | ------------------- |
|`a + b`|a, b, +|
|`a + b * c`|a, b, c, *, +|
|`a / b + c * d`|a, b, /, c, d, *, +|
|`a / (b + c) * d`|a, b, c, +, /, d, *|

In der Regel werden alle Operanden eines Operators ausgewertet. Einige Operatoren werten Operanden jedoch bedingt aus. Das heißt, der Wert des Operanden ganz links in einem solchen Operator definiert, ob (oder welche) andere(n) Operanden ausgewertet werden sollen. Diese Operatoren sind die bedingten logischen Operatoren [AND (`&&`)](boolean-logical-operators.md#conditional-logical-and-operator-) und [OR (`||`)](boolean-logical-operators.md#conditional-logical-or-operator-), die [NULL-Sammeloperatoren `??` und `??=`](null-coalescing-operator.md), die [NULL-bedingten Operatoren `?.` und `?[]`](member-access-operators.md#null-conditional-operators--and-) sowie der [bedingte Operator `?:`](conditional-operator.md). Weitere Informationen finden Sie in der Beschreibung jedes Operators.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Operatoren](~/_csharplang/spec/expressions.md#operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Ausdrücke](../../programming-guide/statements-expressions-operators/expressions.md)
