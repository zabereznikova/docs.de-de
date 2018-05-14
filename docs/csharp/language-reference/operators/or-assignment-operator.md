---
title: Operator |= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: 2abfbcbabb4229049c97aa6827abef3a053d6992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Operator |= (C#-Referenz)
Der OR-Zuweisungsoperator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `|=`, z.B.  
  
```  
x |= y  
```  
  
 für die folgende Syntax:  
  
```  
x = x | y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) führt eine bitweise logische OR-Operation für integrale Operanden und eine logische OR-Operation für boolesche Operanden aus.  
  
 Der Operator `|=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
