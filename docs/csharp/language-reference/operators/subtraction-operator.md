---
title: '- und +=-Operatoren: C#-Referenz'
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: c126837309b5fe3495a5e9e6af589892670b62c3
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063080"
---
# <a name="--and---operators-c-reference"></a>Operatoren „-“ und -=“ (C#-Referenz)

Die Operatoren `-` und `-=` werden von den integrierten numerischen [integral](../builtin-types/integral-numeric-types.md)- und [floating-point](../builtin-types/floating-point-numeric-types.md)-Typen sowie [delegate](../builtin-types/reference-types.md#the-delegate-type)-Typen unterstützt.

Informationen zum arithmetischen Operator `-` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Subtraktionsoperator -](arithmetic-operators.md#subtraction-operator--) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).

## <a name="delegate-removal"></a>Delegatentfernung

Für Operanden des gleichen [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) gibt der Operator `-` eine wie folgt berechnete Delegatinstanz zurück:

- Wenn beide Operanden nicht NULL sind und es sich bei der Aufrufliste des rechten Operanden um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, entsteht durch den Vorgang eine neue Aufrufliste, bei der die Einträge des rechten Operanden aus der Aufrufliste des linken Operanden entfernt wurden. Wenn die Liste des rechten Operanden mehreren zusammenhängenden Unterlisten aus der Liste des linken Operanden entspricht, wird nur die äußerst rechte übereinstimmende Unterliste entfernt. Sollte durch die Entfernung eine leere Liste entstehen, ist das Ergebnis `null`.

  [!code-csharp-interactive[delegate removal](snippets/shared/SubtractionOperator.cs#DelegateRemoval)]

- Wenn es sich bei der Aufrufliste des rechten Operanden nicht um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des linken Operanden handelt, ist das Ergebnis des Vorgangs der linke Operand. Beim Entfernen eines Delegaten, der nicht Teil des Multicastdelegaten ist, passiert nichts, und der Multicastdelegat bleibt unverändert.

  [!code-csharp-interactive[delegate removal with no effect](snippets/shared/SubtractionOperator.cs#DelegateRemovalNoChange)]

  Das vorherige Beispiel veranschaulicht auch, dass Delegatinstanzen beim Entfernen von Delegaten verglichen werden. Delegaten, die durch die Auswertung identischer [Lambdaausdrücke](lambda-expressions.md) erzeugt werden, sind beispielsweise nicht gleich. Weitere Informationen über die Delegatgleichheit finden Sie in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) unter [Delegieren von Gleichheitsoperatoren](~/_csharplang/spec/expressions.md#delegate-equality-operators).

- Ist der linke Operand `null`, ist das Ergebnis des Vorgangs `null`. Ist der rechte Operand `null`, ist das Ergebnis des Vorgangs der linke Operand.

  [!code-csharp-interactive[delegate removal and null](snippets/shared/SubtractionOperator.cs#DelegateRemovalAndNull)]

Verwenden Sie zum Kombinieren von Delegaten den [`+`-Operator](addition-operator.md#delegate-combination).

Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).

## <a name="subtraction-assignment-operator--"></a>Subtraktionszuweisungsoperator „-=“

Ein Ausdruck mit dem Operator `-=`, z.B.

```csharp
x -= y
```

für die folgende Syntax:

```csharp
x = x - y
```

außer dass `x` nur einmal überprüft wird.

Im folgenden Beispiel wird die Verwendung des `-=`-Operators veranschaulicht:

[!code-csharp-interactive[-= examples](snippets/shared/SubtractionOperator.cs#SubtractAndAssign)]

Mit dem Operator `-=` können Sie auch eine Ereignishandlermethode zum Entfernen angeben, wenn Sie das Abonnement eines [Ereignisses](../keywords/event.md) kündigen. Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Operator `-`[überladen](operator-overloading.md). Wenn ein binärer Operator vom Typ `-` überladen wird, wird der Operator `-=` implizit ebenfalls überladen. Ein benutzerdefinierter Typ kann den Operator `-=` nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Unärer Minusoperator](~/_csharplang/spec/expressions.md#unary-minus-operator) und [Subtraktionsoperator](~/_csharplang/spec/expressions.md#subtraction-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Arithmetic operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatoren „+“ und „+=“ (C#-Referenz)](addition-operator.md)
