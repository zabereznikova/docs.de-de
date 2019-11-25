---
title: + und +=-Operatoren – C#-Referenz
ms.custom: seodec18
ms.date: 05/24/2019
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
ms.openlocfilehash: e6a190e3d6e283f2ce3b1690ec2bfd15d50dfc6e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972639"
---
# <a name="-and--operators-c-reference"></a>Operatoren „+“ und „+=“ (C#-Referenz)

Die Operatoren `+` und `+=` werden von den integrierten numerischen [integral](../builtin-types/integral-numeric-types.md)- und [floating-point](../builtin-types/floating-point-numeric-types.md)-Typen sowie den [string](../builtin-types/reference-types.md#the-string-type)- und [delegate](../builtin-types/reference-types.md#the-delegate-type)-Typen unterstützt.

Informationen zum arithmetischen Operator `+` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Additionsoperator +](arithmetic-operators.md#addition-operator-) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).

## <a name="string-concatenation"></a>Zeichenfolgenverkettung

Wenn ein Operand oder beide Operanden vom Typ [String](../builtin-types/reference-types.md#the-string-type) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden:

[!code-csharp-interactive[string concatenation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddStrings)]

Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:

[!code-csharp-interactive[string interpolation](~/samples/csharp/language-reference/operators/AdditionOperator.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Kombinieren von Delegaten

Für Operanden des gleichen [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) gibt der Operator `+` eine neue Delegatinstanz zurück, die bei Aufruf den linken Operanden und dann den rechten Operanden aufruft. Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist). Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:

[!code-csharp-interactive[delegate combination](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddDelegates)]

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

[!code-csharp-interactive[+= examples](~/samples/csharp/language-reference/operators/AdditionOperator.cs#AddAndAssign)]

Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Operator `+` [überladen](operator-overloading.md). Wenn ein binärer Operator vom Typ `+` überladen wird, wird der Operator `+=` implizit ebenfalls überladen. Ein benutzerdefinierter Typ kann den Operator `+=` nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Verketten mehrerer Zeichenfolgen](../../how-to/concatenate-multiple-strings.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Arithmetic operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatoren „-“ und „-=“ (C#-Referenz)](subtraction-operator.md)
