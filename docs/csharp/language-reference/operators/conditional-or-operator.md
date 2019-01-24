---
title: '||-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 079c021eb68ece097c7f644416f1e9469a82dcea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415428"
---
# <a name="-operator-c-reference"></a>Operator || (C#-Referenz)

Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der [bool](../keywords/bool.md)-Operanden. Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt. Andernfalls ist das Ergebnis `false`. Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `true`. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

Der [logische OR-Operator](or-operator.md) `|` berechnet auch die logische OR-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den bedingten logischen OR-Operator nicht überladen. Wenn ein benutzerdefinierter Typ die Operatoren [logisches OR](or-operator.md) sowie [true und false](../keywords/true-false-operators.md) jedoch in einer bestimmten Weise überlädt, kann der `||`-Vorgang für die Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [&&-Operator ](conditional-and-operator.md)
- [\!-Operator](logical-negation-operator.md)
- [|-Operator](or-operator.md)
