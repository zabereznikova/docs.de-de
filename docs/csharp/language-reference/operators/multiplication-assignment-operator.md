---
title: Operator *= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517167"
---
# <a name="-operator-c-reference"></a>Operator *= (C#-Referenz)
Der binäre Multiplikationszuweisungsoperator  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.  
  
```csharp  
x *= y  
```  
  
 für die folgende Syntax:  
  
```csharp  
x = x * y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen und Multiplikationen vordefiniert.  
  
 Der Operator `*=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
