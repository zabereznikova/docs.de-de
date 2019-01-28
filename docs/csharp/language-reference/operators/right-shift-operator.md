---
title: '&gt;&gt;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: f7cacd740966f0716e125887568a39abf0d9e454
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725427"
---
# <a name="gtgt-operator-c-reference"></a>&gt;&gt;-Operator (C#-Referenz)

Der Right Shift-Operator (`>>`) verschiebt den ersten Operanden um die Anzahl von Bits nach rechts, die durch den zweiten Operanden angegeben wird.

## <a name="remarks"></a>Hinweise

Ist der erste Operand ein [int](../keywords/int.md) oder [uint](../keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben (zweiter Operand & 0x1F).

Ist der erste Operand ein [long](../keywords/long.md) oder [ulong](../keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben (zweiter Operand & 0x3F).

Ist der erste Operand ein [int](../keywords/int.md) oder [long](../keywords/long.md), handelt es sich bei der Verschiebung nach rechts um eine arithmetische Verschiebung (höherwertige leere Bits werden auf das Vorzeichenbit festgelegt). Ist der erste Operand vom Typ [uint](../keywords/uint.md) oder [ulong](../keywords/ulong.md), handelt es sich bei der Verschiebung nach rechts um eine logische Verschiebung (höherwertige Bits werden mit Nullen angefüllt).

Benutzerdefinierte Typen können den `>>`-Operator überladen. Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden [int](../keywords/int.md). Weitere Informationen finden Sie unter [Operator](../keywords/operator.md). Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)