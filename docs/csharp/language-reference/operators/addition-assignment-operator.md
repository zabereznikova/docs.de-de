---
title: Operator += (C#-Referenz)
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192030"
---
# <a name="-operator-c-reference"></a>Operator += (C#-Referenz)

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

Wenn ein benutzerdefinierter Typ den [Additionsoperator](addition-operator.md) `+` [überlädt](../keywords/operator.md), wird auch der Additionszuweisungsoperator `+=` implizit überladen.

Sie verwenden den `+=`-Operator auch, um eine Ereignishandlermethode anzugeben, wenn Sie ein [Ereignis](../keywords/event.md) abonnieren. Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

Im folgenden Beispiel wird die Verwendung des `+=`-Operators veranschaulicht:

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Ereignisse](../../programming-guide/events/index.md)
- [Delegaten](../../programming-guide/delegates/index.md)
