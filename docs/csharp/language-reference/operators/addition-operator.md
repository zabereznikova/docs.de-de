---
title: "Operator&#160;+ (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+ (Operator) [C#]"
  - "Additionsoperator [C#]"
  - "Verkettungsoperator [C#]"
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operator&#160;+ (C#-Referenz)
Der Operator `+` kann entweder als unärer oder als binärer Operator verwendet werden.  
  
## Hinweise  
 Unäre Operatoren `+` sind für alle numerischen Typen vordefiniert.  Das Ergebnis einer unären `+`\-Operation für einen numerischen Typ ist der Wert des Operanden.  
  
 Der binäre Operator `+` ist für numerische Typen und Zeichenfolgentypen vordefiniert.  Für numerische Typen berechnet **\+** die Summe seiner zwei Operanden.  Wenn mindestens ein Operand den Zeichenfolgentyp aufweist, verkettet \+ die Zeichenfolgenentsprechungen der Operanden.  
  
 Delegattypen stellen ebenfalls den binären Operator `+` bereit, durch den Delegaten miteinander verkettet werden.  
  
 Benutzerdefinierte Typen können die unären Operatoren `+` und die binären Operatoren `+` überladen.  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  
  
## Beispiel  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#28)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Operator](../../../csharp/language-reference/keywords/operator.md)