---
title: -&gt;-Operator (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 09d67b8386da371f7d98a8171f60298b316091ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-gt-operator-c-reference"></a>-&gt;-Operator (C#-Referenz)
Der Operator `->` kombiniert Zeigerdereferenzierung und Memberzugriff.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck der Form  
  
```  
x->y  
```  
  
 (wobei `x` ein Zeiger vom Typ `T*` und `y` ein Member von `T` ist) ist äquivalent zu  
  
```  
(*x).y  
```  
  
 Der Operator `->` kann nur in Code verwendet werden, der als [unsicher](../../../csharp/language-reference/keywords/unsafe.md) markiert ist.  
  
 Operator `->` kann nicht überladen werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
