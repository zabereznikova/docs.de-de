---
title: Operator &amp;= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: f3a6fe20ca89a90b5a64118d73fb39e9a364d1e9
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933951"
---
# <a name="amp-operator-c-reference"></a>Operator &amp;= (C#-Referenz)
Der AND-Zuweisungsoperator.  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `&=`, z.B.  
  
```csharp  
x &= y  
```  
  
 für die folgende Syntax:  
  
```csharp  
x = x & y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator &](../../../csharp/language-reference/operators/and-operator.md) führt eine bitweise logische AND-Operation für ganzzahlige Operanden und eine logische AND-Operation für `bool`-Operanden aus.  
  
 Der Operator `&=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den binären [Operator &](../../../csharp/language-reference/operators/and-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
