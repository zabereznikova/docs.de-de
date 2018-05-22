---
title: '&lt;Operator &lt;= (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="ltlt-operator-c-reference"></a>&lt;Operator &lt;= (C#-Referenz)
Der Linksschiebezuweisungs-Operator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck der Form  
  
```csharp  
x <<= y  
```  
  
 wird als ausgewertet,  
  
```csharp  
x = x << y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator <<](../../../csharp/language-reference/operators/left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.  
  
 Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) überladen (weitere Informationen unter [Operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
