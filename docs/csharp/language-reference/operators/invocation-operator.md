---
title: ()-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 3a0af33739c9cb4d090842219eba4ece9700ef89
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362781"
---
# <a name="-operator-c-reference"></a>()-Operator (C#-Referenz)

Klammern „`()`“ werden in der Regel für den Methoden- oder Delegataufruf oder in Cast-Ausdrücken verwendet.

Mit Klammern geben Sie auch die Reihenfolge an, in der Vorgänge in einem Ausdruck ausgewertet werden sollen. Weitere Informationen finden Sie im Abschnitt [Hinzufügen von Klammern](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) des Artikels [Operatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/operators.md). Die Liste der Operatoren ist nach der Rangfolge sortiert, siehe [C#-Operatoren](index.md).

## <a name="method-invocation"></a>Methodenaufruf

Im folgenden Beispiel wird der Aufruf einer Methode mit oder ohne Argumente sowie eines Delegaten veranschaulicht:

[!code-csharp-interactive[use for invocation](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

Klammern verwenden Sie auch beim Aufrufen eines [Konstruktors](../../programming-guide/classes-and-structs/constructors.md) mit einem [ `new` ](../keywords/new-operator.md)-Operator.

Weitere Informationen über Methoden finden Sie unter [Methoden](../../programming-guide/classes-and-structs/methods.md). Weitere Informationen über Delegaten finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).

## <a name="cast-expression"></a>Cast-Ausdruck

Ein Cast-Ausdruck der Form `(T)E` ruft einen Konvertierungsoperator zum Konvertieren des Werts des Ausdrucks `E` in Typ `T` auf. Wenn keine explizite Konvertierung von Typ `E` in Typ `T` möglich ist, tritt ein Fehler während der Kompilierung auf. Weitere Informationen zum Definieren von Konvertierungsoperatoren finden Sie in den Schlüsselwortartikeln [explicit (C#-Referenz)](../keywords/explicit.md) und [implicit (C#-Referenz)](../keywords/implicit.md).

Das folgende Beispiel veranschaulicht die Typenkonvertierung zwischen numerischen Typen:

[!code-csharp-interactive[use for cast](~/samples/snippets/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

Weitere Informationen zu vordefinierten expliziten Konvertierungen zwischen numerischen Typen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).

Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)](../../programming-guide/types/casting-and-type-conversions.md) und [Konvertierungsoperatoren (C#-Programmierhandbuch)](../../programming-guide/statements-expressions-operators/conversion-operators.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Der Operator `()` kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Aufrufausdrücke](~/_csharplang/spec/expressions.md#invocation-expressions) und [CAST-Ausdrücke](~/_csharplang/spec/expressions.md#cast-expressions) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)