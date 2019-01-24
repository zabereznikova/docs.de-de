---
title: '&lt;&lt;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333524"
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;-Operator (C#-Referenz)

Der Left Shift-Operator (`<<`) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird. Der Typ des zweiten Operanden muss ein [int](../keywords/int.md) oder ein Typ sein, der eine vordefinierte implizite numerische Konvertierung in `int` besitzt.

## <a name="remarks"></a>Hinweise

Ist der erste Operand ein [int](../keywords/int.md) oder [uint](../keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben. Die tatsächliche Umschaltanzahl beträgt also 0 bis 31 Bits.

Ist der erste Operand ein [long](../keywords/long.md) oder [ulong](../keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben. Die tatsächliche Umschaltanzahl beträgt also 0 bis 63 Bits.

Alle höherwertigen Bits, die nach der Verschiebung nicht im Bereich des Typs des ersten Operanden liegen, werden verworfen. Die niederwertigen leeren Bits werden mit Nullen angefüllt. Schiebeoperationen verursachen nie Überläufe.

Benutzerdefinierte Typen können den `<<`-Operator überladen (siehe [Operator](../keywords/operator.md)). Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden `int`. Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>Kommentare

Beachten Sie, dass `i<<1` und `i<<33` dasselbe Ergebnis liefern, da die fünf niederwertigen Bits von 1 und 33 übereinstimmen.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
