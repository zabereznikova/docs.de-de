---
title: Operator %= (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 2b6a537ce189ab5a1c0c8c36995b6e9e98734e14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operator %= (C#-Referenz)
Der Restzuweisungsoperator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `%=`, z.B.  
  
```  
x %= y  
```  
  
 für die folgende Syntax:  
  
```  
x = x % y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator %](../../../csharp/language-reference/operators/remainder-operator.md) ist für numerische Typen vordefiniert, um den Rest nach einer Division zu berechnen.  
  
 Der Operator `%=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[Operator /](../../../csharp/language-reference/operators/remainder-operator.md) überladen (weitere Informationen unter [operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
