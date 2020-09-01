---
description: + und +=-Operatoren – C#-Referenz
title: + und +=-Operatoren – C#-Referenz
ms.date: 04/23/2020
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 00ba020939694d901afdbf5f5f93b584363d2cc7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141854"
---
# <a name="-and--operators-c-reference"></a>Operatoren „+“ und „+=“ (C#-Referenz)

Die Operatoren `+` und `+=` werden von den integrierten numerischen [integral](../builtin-types/integral-numeric-types.md)- und [floating-point](../builtin-types/floating-point-numeric-types.md)-Typen sowie den [string](../builtin-types/reference-types.md#the-string-type)- und [delegate](../builtin-types/reference-types.md#the-delegate-type)-Typen unterstützt.

Informationen zum arithmetischen Operator `+` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Additionsoperator +](arithmetic-operators.md#addition-operator-) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).

## <a name="string-concatenation"></a>Zeichenfolgenverkettung

Wenn ein Operand oder beide Operanden vom Typ [String](../builtin-types/reference-types.md#the-string-type) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden (die Zeichenfolgendarstellung von `null` is eine leere Zeichenfolge):

[!code-csharp-interactive[string concatenation](snippets/shared/AdditionOperator.cs#AddStrings)]

Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:

[!code-csharp-interactive[string interpolation](snippets/shared/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Kombinieren von Delegaten

Für Operanden des gleichen [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) gibt der Operator `+` eine neue Delegatinstanz zurück, die bei Aufruf den linken Operanden und dann den rechten Operanden aufruft. Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist). Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:

[!code-csharp-interactive[delegate combination](snippets/shared/AdditionOperator.cs#AddDelegates)]

Um eine Delegatentfernung auszuführen, verwenden Sie den [`-`-Operator](subtraction-operator.md#delegate-removal).

Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).

## <a name="addition-assignment-operator-"></a>Additionszuweisungsoperator (+=)

Ein Ausdruck mit dem Operator `+=`, z.B.

```csharp
x += y
```

für die folgende Syntax:

```csharp
x = x + y
```

außer dass `x` nur einmal überprüft wird.

Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:

[!code-csharp-interactive[+= examples](snippets/shared/AdditionOperator.cs#AddAndAssign)]

Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Operator `+`[überladen](operator-overloading.md). Wenn ein binärer Operator vom Typ `+` überladen wird, wird der Operator `+=` implizit ebenfalls überladen. Ein benutzerdefinierter Typ kann den Operator `+=` nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Verketten mehrerer Zeichenfolgen](../../how-to/concatenate-multiple-strings.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Arithmetic operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatoren „-“ und „-=“ (C#-Referenz)](subtraction-operator.md)
