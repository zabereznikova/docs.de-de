---
title: ~-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 57e5baee423c0b5d9292d0ad4cbf909646eb3a38
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235718"
---
# <a name="-operator-c-reference"></a>Operator ~ (C#-Referenz)

Der bitweise Komplementoperator `~` ist ein unärer Operator, der ein bitweises Komplement seines Operanden erzeugt, indem jedes Bit umgekehrt wird. Alle Integertypen unterstützen den `~` Operator.

> [!NOTE]
> Das `~`-Symbol wird auch für das Deklarieren von Finalizern verwendet. Weitere Informationen finden Sie unter [Finalizer](../../programming-guide/classes-and-structs/destructors.md).

Im folgenden Beispiel wird die Verwendung des `~`-Operators veranschaulicht:

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> Im Beispiel oben werden die [in C# 7.0 eingeführten](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) und [in C# 7.2 erweiterten](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals) binären Literale verwendet.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `~` [überladen](../keywords/operator.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bitweiser Komplementoperator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Finalizer](../../programming-guide/classes-and-structs/destructors.md)
- [&-Operator](and-operator.md)
- [|-Operator](or-operator.md)
- [^-Operator](xor-operator.md)
