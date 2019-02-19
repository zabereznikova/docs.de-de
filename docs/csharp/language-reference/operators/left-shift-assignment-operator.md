---
title: <<=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: d2105fbee4ddfe1b2cb3325d82b0f2f8c5559297
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219450"
---
# <a name="-operator-c-reference"></a>\<\<=-Operator (C#-Referenz)

Der Linksschiebezuweisungs-Operator

Ein Ausdruck mit dem Operator `<<=`, z.B.

```csharp
x <<= y
```

für die folgende Syntax:

```csharp
x = x << y
```

außer dass `x` nur einmal überprüft wird.

Der [`<<`-Operator](left-shift-operator.md) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird.

Im folgenden Beispiel wird die Verwendung des `<<=`-Operators veranschaulicht:

[!code-csharp-interactive[left shift assignment](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftAssignment)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Wenn ein benutzerdefinierter Typ den [`<<`-Operator](left-shift-operator.md) [überlädt](../keywords/operator.md), wird auch der Zuweisungsoperator für die Linksverschiebung (`<<=`) implizit überladen. Ein benutzerdefinierter Typ kann den Zuweisungsoperator für die Linksverschiebung nicht explizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
