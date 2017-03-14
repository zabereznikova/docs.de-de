---
title: "Operator&#160;&amp;&amp; (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "&&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&& (Operator) [C#]"
  - "Logischer AND-Operator [C#]"
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Operator&#160;&amp;&amp; (C#-Referenz)
Der bedingte Operator AND \(`&&`\) führt ein logisches AND seiner `bool`\-Operanden aus, wertet den zweiten Operanden aber nur aus, wenn dies erforderlich ist.  
  
## Hinweise  
 Die Operation  
  
```  
x && y  
```  
  
 entspricht der Operation  
  
```  
x & y  
```  
  
 `x`, wenn der Ausnahme, dass `false`ist, wird `y` nicht ausgewertet, weil das Ergebnis der AND\-Operation `false` ist, unabhängig vom Wert von `y` ist.  Dies wird als "Kurzschlussauswertung" bezeichnet.  
  
 Der bedingte Operator AND kann nicht überladen werden, aber Überladungen der regulären logischen Operatoren [true](../../../csharp/language-reference/keywords/true.md) und [false](../../../csharp/language-reference/keywords/false.md) werden, mit gewissen Einschränkungen, auch als Überladung der bedingten logischen Operatoren aufgefasst.  
  
## Beispiel  
 Im folgenden Beispiel wird der bedingte Ausdruck in der zweiten `if`\-Anweisung nur den ersten Operanden aus, da der Operand `false`zurückgibt.  
  
 [!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)