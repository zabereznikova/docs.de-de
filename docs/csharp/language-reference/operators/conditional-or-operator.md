---
title: "Operator&#160;|| (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "||_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|| (Operator) [C#]"
  - "Bedingter OR-Operator (||) [C#]"
  - "Logischer OR-Operator [C#]"
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# Operator&#160;|| (C#-Referenz)
Der bedingte Operator OR \(`||`\) führt ein logischen ODER seiner `bool` Operanden aus.  Wenn der erste Operand zu `true` ergibt, wird der zweite Operand nicht ausgewertet.  Wenn der erste Operand zu `false` ergibt, bestimmt, ob der zweite Operator OR Ausdruck als Ganzes zu `true` oder zu `false` ergibt.  
  
## Hinweise  
 Die Operation  
  
```  
x || y  
```  
  
 entspricht der Operation  
  
```  
x | y  
```  
  
 außer dass, wenn `x``true` ist, wird `y` nicht ausgewertet, da die OR\-Operation `true` unabhängig vom Wert von `y` ist.  Dieses Konzept wird als "Kurzschluss" Auswertung.  
  
 Der bedingte Operator OR kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren und der [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md)\-Operatoren werden, mit bestimmten Einschränkungen, auch als Überladungen der bedingten logischen Operatoren betrachtet.  
  
## Beispiel  
 In den folgenden Beispielen ergibt der Ausdruck, der verwendet wird, `||` nur den ersten Operanden aus.  Der Ausdruck, der verwendet `|`wertet beide Operanden aus.  Im zweiten Beispiel eine Laufzeitausnahme tritt auf, wenn beide Operanden ausgewertet werden.  
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#52)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)