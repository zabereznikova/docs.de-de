---
title: /-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286532"
---
# <a name="-operator-c-reference"></a>Operator / (C#-Referenz)

Der Divisionsoperator `/` dividiert den ersten Operanden durch den zweiten Operanden. Alle numerischen Typen unterstützen den Divisionsoperator.

## <a name="integer-division"></a>Ganzzahldivision

Für die Operanden von Ganzzahltypen weist das Ergebnis des `/`-Operators einen Ganzzahltyp auf und ist gleich dem Quotienten der beiden Operanden, gerundet auf Null:

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

Um den Quotienten der beiden Operanden als Gleitkommazahl abzurufen, verwenden Sie den Typ `float`, `double` oder `decimal`:

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a>Gleitkommadivision

Für die Typen `float`, `double` oder `decimal` ist das Ergebnis des `/`-Operators der Quotient der beiden Operanden:

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

Wenn einer der Operanden `decimal` lautet, kann ein anderer Operand weder `float` noch `double` sein, weil weder `float` noch `double` implizit zu `decimal` konvertiert werden können. Sie müssen den Operanden `float` oder `double` explizit zum Typ `decimal` konvertieren. Weitere Informationen zu impliziten Konvertierungen zwischen numerischen Typen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `/` [überladen](../keywords/operator.md). Wenn der `/`-Operator überladen ist, wird der [Divisionszuweisungsoperator](division-assignment-operator.md) `/=` auch implizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Divisionsoperator](~/_csharplang/spec/expressions.md#division-operator) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [%-Operator](remainder-operator.md)
