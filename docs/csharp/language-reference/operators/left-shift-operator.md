---
title: '&lt;&lt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: bacb444c08b1f9d6e18278337015d8a427fdbe46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltlt-operator-c-reference"></a>&lt;&lt;-Operator (C#-Referenz)
Der Left Shift-Operator (`<<`) verschiebt den ersten Operanden um die Anzahl von Bits nach links, die durch den zweiten Operanden angegeben wird. Der Typ des zweiten Operanden muss ein [int](../../../csharp/language-reference/keywords/int.md) oder ein Typ sein, der eine vordefinierte implizite numerische Konvertierung in `int` besitzt.  
  
## <a name="remarks"></a>Hinweise  
 Ist der erste Operand ein [int](../../../csharp/language-reference/keywords/int.md) oder [uint](../../../csharp/language-reference/keywords/uint.md) (32-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen fünf Bits des zweiten Operanden angegeben. Die tatsächliche Umschaltanzahl beträgt also 0 bis 31 Bits.  
  
 Ist der erste Operand ein [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-Bit-Menge), wird die Umschaltanzahl durch die niederwertigen sechs Bits des zweiten Operanden angegeben. Die tatsächliche Umschaltanzahl beträgt also 0 bis 63 Bits.  
  
 Alle höherwertigen Bits, die nach der Verschiebung nicht im Bereich des Typs des ersten Operanden liegen, werden verworfen. Die niederwertigen leeren Bits werden mit Nullen angefüllt. Schiebeoperationen verursachen nie Überläufe.  
  
 Benutzerdefinierte Typen können den `<<`-Operator überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)). Der Typ des ersten Operanden muss daher der benutzerdefinierte Typ sein, der Typ des zweiten Operanden `int`. Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a>Kommentare  
 Beachten Sie, dass `i<<1` und `i<<33` dasselbe Ergebnis liefern, da die fünf niederwertigen Bits von 1 und 33 übereinstimmen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
