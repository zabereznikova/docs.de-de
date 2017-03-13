---
title: "Operator&#160;| (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "|_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "| (Operator) [C#]"
  - "Binärer Operator (|) [C#]"
  - "Bitweiser OR-Operator [C#]"
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Operator&#160;| (C#-Referenz)
Binär        `|`  Operatoren sind für Ganzzahltypen und `bool` vordefiniert.  Für Ganzzahltypen  `|`berechnet das bitweise OR seiner Operanden.  Für `bool`\-Operanden berechnet der Operator  `|` das logische OR seiner Operanden. Dies bedeutet, dass das Ergebnis nur `false` ist, wenn beide Operanden `false` sind.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator          `|` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Beispiel  
 [!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)