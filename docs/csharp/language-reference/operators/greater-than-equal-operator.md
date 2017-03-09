---
title: "Operator &gt;= (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">= (Operator) [C#]"
  - "Größer oder gleich-Operator (>=) [C#]"
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Operator &gt;= (C#-Referenz)
Alle numerischen Typen und Enumerationstypen definieren einen relationalen Operator "größer oder gleich" \(`>=`\), der `true` zurückgibt, wenn der erste Operand größer oder gleich dem zweiten ist. Andernfalls wird `false` zurückgegeben.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `>=` überladen.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  Wenn `>=` überladen wird, muss auch [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) überladen werden.  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#39)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)