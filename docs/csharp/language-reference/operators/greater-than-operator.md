---
title: '&gt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="gt-operator-c-reference"></a>Operator &gt; (C#-Referenz)
Alle numerischen und Emumerationstypen definieren einen relationalen „größer als“-Operator (`>`), der `true` zurückgibt, wenn der erste Operand größer dem zweiten ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `>` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Wenn `>` überladen ist, muss [<](../../../csharp/language-reference/operators/less-than-operator.md) auch überladen werden. Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)
