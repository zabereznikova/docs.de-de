---
title: +=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 5d48f2fe53a9bb6f781f8d35f1e0983bcaa30f88
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240930"
---
# <a name="-operator-c-reference"></a>+=-Operator (C#-Referenz)

Der Additionszuweisungsoperator.

Ein Ausdruck mit dem Operator `+=`, z.B.

```csharp
x += y
```

für die folgende Syntax:

```csharp
x = x + y
```

außer dass `x` nur einmal überprüft wird.
  
Für numerische Typen berechnet der [Additionsoperator](addition-operator.md) `+` die Summe der Operanden. Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der Additionsoperator die Zeichenfolgendarstellungen der Operanden. Für Delegattypen gibt der `+`-Operator eine neue Delegatinstanz zurück, die eine Kombination der Operanden ist.

Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [Additionsoperator](addition-operator.md) `+` [überlädt](../keywords/operator.md), wird auch der Additionszuweisungsoperator `+=` implizit überladen. Ein benutzerdefinierter Typ kann den Additionszuweisungsoperator nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) und [Ereigniszuweisung](~/_csharplang/spec/expressions.md#event-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Delegaten](../../programming-guide/delegates/index.md)
