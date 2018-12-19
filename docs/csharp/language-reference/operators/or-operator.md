---
title: '|-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 19a37bbb54d2ef3e15e4465df05c9b6df705206c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240358"
---
# <a name="-operator-c-reference"></a>|-Operator (C#-Referenz)
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
