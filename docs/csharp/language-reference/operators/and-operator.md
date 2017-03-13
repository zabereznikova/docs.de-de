---
title: "Operator &amp; (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Bitweiser AND-Operator [C#]"
  - "Und-Operator (&) [C#]"
  - "& (Operator) [C#]"
  - "AND-Operator (&) [C#]"
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Operator &amp; (C#-Referenz)
Der Operator **&** kann entweder als unärer oder als binärer Operator verwendet werden.  
  
## Hinweise  
 Der unäre Operator & gibt die Adresse seines Operanden zurück \(erfordert [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\-Kontext\).  
  
 Binäre Operatoren **&** sind für Ganzzahltypen und `bool` vordefiniert.  Für Ganzzahltypen berechnet & das logische bitweise AND seiner Operanden.  Für `bool`\-Operanden berechnet der Operator & das logische AND seiner Operanden. Dies bedeutet, dass das Ergebnis nur `true` ist, wenn beide Operanden `true` sind.  
  
 Der Operator `&` wertet beide Operanden aus, unabhängig vom Wert des ersten.  Beispiel:  
  
 [!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Benutzerdefinierte Typen können den Operator `&` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)