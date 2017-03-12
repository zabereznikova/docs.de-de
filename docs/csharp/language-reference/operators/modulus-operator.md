---
title: "Operator&#160;% (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "%_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "% (Operator) [C#]"
  - "Modulo-Operator [C#]"
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Operator&#160;% (C#-Referenz)
Der `%`\-Operator berechnet werden, nachdem er den Rest ersten Operanden durch seinen zweiten aufgeteilt hat.  Für alle numerischen Typen sind verbleibenden Operatoren vordefiniert.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `%` überladen \(siehe [operator](../../../csharp/language-reference/keywords/operator.md)\).  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#9)]  
  
## Kommentare  
 Beachten Sie die mit dem Typ **double** verbundenen Rundungsfehler.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)