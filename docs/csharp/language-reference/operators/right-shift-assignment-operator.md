---
title: '>>=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 51914bb5e9ebffd5d868528b5a8d3072a956cea6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220912"
---
# <a name="-operator-c-reference"></a>>>=-Operator (C#-Referenz)

Der Rechtsschiebezuweisungsoperator.

Ein Ausdruck mit dem Operator `>>=`, z.B.

```csharp
x >>= y
```

für die folgende Syntax:

```csharp
x = x >> y
```

außer dass `x` nur einmal überprüft wird.

Der [`>>`-Operator](right-shift-operator.md) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.

Im folgenden Beispiel wird die Verwendung des `>>=`-Operators veranschaulicht:

[!code-csharp-interactive[right shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftAssignment)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [`>>`-Operator](right-shift-operator.md) [überlädt](../keywords/operator.md), wird auch der Zuweisungsoperator für die Rechtsverschiebung (`>>=`) implizit überladen. Ein benutzerdefinierter Typ kann den Zuweisungsoperator für die Rechtsverschiebung nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)