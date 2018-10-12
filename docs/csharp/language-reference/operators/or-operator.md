---
title: Operator | (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46706147"
---
# <a name="-operator-c-reference"></a>Operator | (C#-Referenz)
Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert. Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden. Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zum [bedingten OR-Operator](conditional-or-operator.md) `||` wertet der binäre `|`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.
 
 Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
