---
title: "Operator %= (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "%=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "%=-Zuweisungsoperator (Modulozuweisung) [C#]"
  - "Modulozuweisungsoperator (=%) [C#]"
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Operator %= (C#-Referenz)
Der Restzuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `%=` verwendet wird, z. B.  
  
```  
x %= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x % y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Der [Operator %](../../../csharp/language-reference/operators/modulus-operator.md) ist für numerische Typen so definiert, dass er den Rest nach einer Division berechnet.  
  
 Der Operator `%=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator %](../../../csharp/language-reference/operators/modulus-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Beispiel  
 [!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)