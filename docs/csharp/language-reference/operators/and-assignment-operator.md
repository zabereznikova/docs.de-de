---
title: Operator &amp;= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bea90651faaafe7b754ce1cf16bddbab997d5f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a>Operator &amp;= (C#-Referenz)
Der AND-Zuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `&=`, z.B.  
  
```  
x &= y  
```  
  
 für die folgende Syntax:  
  
```  
x = x & y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator &](../../../csharp/language-reference/operators/and-operator.md) führt eine bitweise logische AND-Operation für ganzzahlige Operanden und eine logische AND-Operation für `bool`-Operanden aus.  
  
 Der Operator `&=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den binären [Operator &](../../../csharp/language-reference/operators/and-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
