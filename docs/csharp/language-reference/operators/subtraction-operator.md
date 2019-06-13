---
title: '- und -= (Operatoren) – C#-Referenz'
ms.custom: seodec18
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
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816071"
---
# <a name="--and---operators-c-reference"></a>Operatoren „-“ und „-=“ (C#-Referenz)

Der Operator `-` wird von den integrierten numerischen Typen sowie von [Delegattypen](../keywords/delegate.md) unterstützt.

Informationen zum arithmetischen Operator `-` finden Sie in den Abschnitten [Unäre Plus- und Minusoperatoren](arithmetic-operators.md#unary-plus-and-minus-operators) und [Subtraktionsoperator -](arithmetic-operators.md#subtraction-operator--) des Artikels [Arithmetische Operatoren (C#-Referenz)](arithmetic-operators.md).

## <a name="delegate-removal"></a>Delegatentfernung

Für Operanden des gleichen [Delegattyps](../keywords/delegate.md) gibt der Operator `-` eine wie folgt berechnete Delegatinstanz zurück:

- Wenn beide Operanden nicht NULL sind und es sich bei der Aufrufliste des zweiten Operanden um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des ersten Operanden handelt, entsteht durch den Vorgang eine neue Aufrufliste, bei der die Einträge des zweiten Operanden aus der Aufrufliste des ersten Operanden entfernt wurden. Wenn die Liste des zweiten Operanden mehreren zusammenhängenden Unterlisten aus der Liste des ersten Operanden entspricht, wird nur die äußerst rechte übereinstimmende Unterliste entfernt. Sollte durch die Entfernung eine leere Liste entstehen, ist das Ergebnis `null`.

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- Wenn es sich bei der Aufrufliste des zweiten Operanden nicht um eine ordnungsgemäße zusammenhängende Unterliste der Aufrufliste des ersten Operanden handelt, ist das Ergebnis des Vorgangs der erste Operand. Z. B. entfernt einen Delegaten, der nicht Teil der Multicastdelegat ist führt keine Aktion aus und führt den unveränderten Multicastdelegaten.

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  Im vorherige Beispiel veranschaulicht auch, dass während des Delegaten entfernen Delegatinstanzen verglichen werden. Z. B. Delegaten, die erstellt werden, aus der Auswertung von identischen [Lambda-Ausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md) ungleich sind. Weitere Informationen bezüglich der Gleichheit der Delegaten finden Sie unter der [Gleichheitsoperatoren Delegieren](~/_csharplang/spec/expressions.md#delegate-equality-operators) im Abschnitt der [ C# -Sprachspezifikation](../language-specification/index.md).

- Ist der erste Operand `null`, ist das Ergebnis des Vorgangs `null`. Ist der zweite Operand `null`, ist das Ergebnis des Vorgangs der erste Operand.

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

Verwenden Sie zum Kombinieren von Delegaten, der [ `+` Operator](addition-operator.md#delegate-combination).

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

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

Mit dem Operator `-=` können Sie auch eine Ereignishandlermethode zum Entfernen angeben, wenn Sie das Abonnement eines [Ereignisses](../keywords/event.md) kündigen. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den Operator `-` [überladen](../keywords/operator.md). Wenn ein binärer Operator vom Typ `-` überladen wird, wird der Operator `-=` implizit ebenfalls überladen. Ein benutzerdefinierter Typ kann den Operator `-=` nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Unärer Minusoperator](~/_csharplang/spec/expressions.md#unary-minus-operator) und [Subtraktionsoperator](~/_csharplang/spec/expressions.md#subtraction-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Delegaten](../../programming-guide/delegates/index.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Checked und unchecked](../keywords/checked-and-unchecked.md)
- [Arithmetic operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatoren „+“ und „+=“ (C#-Referenz)](addition-operator.md)
