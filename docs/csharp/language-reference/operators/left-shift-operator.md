---
title: <<-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219436"
---
# <a name="-operator-c-reference"></a>\<\<-Operator (C#-Referenz)

Der Operator zur Linksverschiebung (`<<`) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird. Alle Integertypen unterstützen den `<<` Operator. Der Typ des zweiten Operanden muss jedoch ein [int](../keywords/int.md)-Typ oder ein Typ sein, der eine [vordefinierte implizite numerische Konvertierung](../keywords/implicit-numeric-conversions-table.md) in `int` aufweist.

Die hohen Bits, die außerhalb des Bereichs des Ergebnistyps liegen, werden verworfen, und die niedrigen leeren Bitpositionen werden auf null festgelegt, wie im folgenden Beispiel gezeigt:

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a>Verschiebungsanzahl

Für den Ausdruck `x << count` hängt die tatsächliche Verschiebungsanzahl folgendermaßen vom Typ von `x` ab:

- Ist der Typ von `x` [int](../keywords/int.md) oder [uint](../keywords/uint.md), wird die Verschiebungsanzahl durch die niedrigen *fünf* Bits des zweiten Operanden angegeben. Die Verschiebungsanzahl errechnet sich daher aus `count & 0x1F` (oder `count & 0b_1_1111`).

- Ist der Typ von `x` [long](../keywords/long.md) oder [ulong](../keywords/ulong.md), wird die Verschiebungsanzahl durch die niedrigen *sechs* Bits des zweiten Operanden angegeben. Die Verschiebungsanzahl errechnet sich daher aus `count & 0x3F` (oder `count & 0b_11_1111`).

Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a>Anmerkungen

Verschiebevorgänge verursachen niemals Überläufe und führen sowohl in [geprüften als auch in ungeprüften](../keywords/checked-and-unchecked.md) Kontexten zu identischen Ergebnissen.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `<<` [überladen](../keywords/operator.md). Wenn ein benutzerdefinierter Typ `T` den `<<`-Operator überlädt, muss der Typ des ersten Operanden `T` und der Typ des zweiten Operanden `int` lauten. Wenn der `<<`-Operator überladen ist, wird der [Zuweisungsoperator für die Linksverschiebung](left-shift-assignment-operator.md) `<<=` ebenfalls implizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Verschiebungsoperatoren](~/_csharplang/spec/expressions.md#shift-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [>>-Operator](right-shift-operator.md)
