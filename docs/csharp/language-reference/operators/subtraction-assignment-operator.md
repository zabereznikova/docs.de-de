---
title: "Operator /= (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (Divisionszuweisungsoperator) [C#]"
  - "Divisionszuweisungsoperator (/=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Operator /= (C#-Referenz)
Der Divisionszuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `/=` verwendet wird, z. B.  
  
```  
x /= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x / y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Der [Operator \/](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen so definiert, dass er eine Division ausführt.  
  
 Der Operator `/=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator \/](../../../csharp/language-reference/operators/division-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Bei allen Verbundzuweisungsoperatoren wird durch das Überladen des binären Operators die entsprechende Verbundzuweisung implizit überladen.  
  
## Beispiel  
 [!code-cs[csRefOperators#5](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#5)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)