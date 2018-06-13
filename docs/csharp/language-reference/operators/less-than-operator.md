---
title: '&lt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: eceb6214e4e625aa71e12788d5dd5e8324c75443
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270230"
---
# <a name="lt-operator-c-reference"></a>&lt;-Operator (C#-Referenz)
Alle numerischen und Emumerationstypen definieren einen relationalen „weniger als“-Operator (`<`), der `true` zurückgibt, wenn der erste Operand weniger dem zweiten ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `<` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Wenn `<` überladen ist, muss [>](../../../csharp/language-reference/operators/greater-than-operator.md) auch überladen werden. Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
