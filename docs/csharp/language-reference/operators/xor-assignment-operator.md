---
title: ^=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: cf39c8e8586e9d4f537fe38d8b28f55542db6ab8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237154"
---
# <a name="-operator-c-reference"></a>^=-Operator (C#-Referenz)
Der XOR-Zuweisungsoperator („exklusives Oder“)  
  
## <a name="remarks"></a>Hinweise  
 Ein Ausdruck der Form  
  
```csharp  
x ^= y  
```  
  
 wird als ausgewertet,  
  
```csharp  
x = x ^ y  
```  
  
 außer dass `x` nur einmal überprüft wird. Der [Operator ^](../../../csharp/language-reference/operators/xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../../../csharp/language-reference/keywords/bool.md)-Operanden aus.  
  
 Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](../../../csharp/language-reference/operators/xor-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
