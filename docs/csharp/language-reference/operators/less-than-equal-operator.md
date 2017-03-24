---
title: "Operator&#160;&lt;= (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<= (Operator) [C#]"
  - "Kleiner oder gleich-Operator (<=) [C#]"
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operator&#160;&lt;= (C#-Referenz)
Alle numerischen und Enumerationstypen definieren einen relationalen Operator "kleiner oder gleich" \(`<=`\), der `true` zurückgibt, wenn der erste Operand kleiner oder gleich dem zweiten ist. Andernfalls wird `false` zurückgegeben.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `<=` überladen.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  Wenn `<=` überladen wird, muss auch [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) überladen werden.  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Explizit](../../../csharp/language-reference/keywords/explicit.md)