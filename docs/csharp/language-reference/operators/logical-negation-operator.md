---
title: '! -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303711"
---
# <a name="-operator-c-reference"></a>! operator (C#-Referenz)

Der logische Negationsoperator `!` ist ein unärer Operator, der eine logische Negation des zugehörigen [bool](../keywords/bool.md)-Operanden berechnet. D. h., er ergibt `true`, wenn der Operand `false` ist, und `false`, wenn der Operand `true` ist:

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `!` [überladen](../keywords/operator.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Logischer Negationsoperator](~/_csharplang/spec/expressions.md#logical-negation-operator) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)