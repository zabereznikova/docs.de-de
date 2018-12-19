---
title: '&amp;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 223d2f30ee77457e1f9d5304ec299517932499d0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237024"
---
# <a name="amp-operator-c-reference"></a>&amp;=-Operator (C#-Referenz)

Der AND-Zuweisungsoperator.

Ein Ausdruck mit dem Operator `&=`, z.B.

```csharp
x &= y
```

für die folgende Syntax:

```csharp
x = x & y
```

außer dass `x` nur einmal überprüft wird.

Für ganzzahlige Operanden berechnet der [`&`-Operator](and-operator.md) die bitweise logische AND-Operation der Operanden. Für [bool](../keywords/bool.md)-Operanden wird die logische AND-Operation der Operanden berechnet.

Im folgenden Beispiel wird die Verwendung des `&=`-Operators veranschaulicht:

[!code-csharp-interactive[AND assignment example](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#AndAssignmentExample)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [`&`-Operator](and-operator.md) [überlädt](../keywords/operator.md), wird auch der AND-Zuweisungsoperator `&=` implizit überladen. Ein benutzerdefinierter Typ kann den AND-Zuweisungsoperator nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
