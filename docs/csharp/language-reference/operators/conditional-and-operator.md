---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529234"
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp;-Operator (C#-Referenz)

Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der [bool](../keywords/bool.md)-Operanden. Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden. Andernfalls ist das Ergebnis `false`. Wenn der erste Operand als `false` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `false`. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

Der [logische AND-Operator](and-operator.md) `&` berechnet auch die logische AND-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den bedingten logischen AND-Operator nicht überladen. Wenn ein benutzerdefinierter Typ die [logischen AND](and-operator.md)-, [true](../keywords/true-operator.md)- und [false](../keywords/false-operator.md)-Operatoren jedoch in einer bestimmten Weise überlädt, kann die `&&`-Operation für die Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [||-Operator](conditional-or-operator.md)
- [!-Operator](logical-negation-operator.md)
- [&-Operator](and-operator.md)
