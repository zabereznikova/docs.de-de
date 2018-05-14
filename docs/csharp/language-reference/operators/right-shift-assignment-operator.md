---
title: '&gt;Operator &gt;= (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 41203f6e7c9929bb349d29c40cf7cc6c24550c36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-c-reference"></a>&gt;Operator &gt;= (C#-Referenz)
Der Rechtsschiebezuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck der Form  
  
```  
x >>= y  
```  
  
 wird als ausgewertet,  
  
```  
x = x >> y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) verschiebt `x` um einen durch `y` angegebenen Wert nach rechts.  
  
 Der >>=-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
