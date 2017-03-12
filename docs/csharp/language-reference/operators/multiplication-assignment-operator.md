---
title: "Operator *= (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "*=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "*= (Operator) [C#]"
  - "Binärer Multiplikationszuweisungsoperator (*=) [C#]"
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operator *= (C#-Referenz)
Der binäre Multiplikationszuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `*=` verwendet wird, z. B.  
  
```  
x *= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x * y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Der [Operator \*](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen so definiert, dass er eine Multiplikation ausführt.  
  
 Der Operator `*=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator \*](../../../csharp/language-reference/operators/multiplication-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Beispiel  
 [!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#13)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)