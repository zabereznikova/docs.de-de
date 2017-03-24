---
title: "Operator&#160;-- (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "--_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-- (Operator) [C#]"
  - "Dekrementoperator (--) [C#]"
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Operator&#160;-- (C#-Referenz)
Der Dekrementoperator \(`--`\) verringert seinen Operanden um 1.  Der Dekrementoperator kann vor oder hinter seinem Operanden auftreten: `--variable` und `variable--`.  Die erste Form stellt eine Präfixdekrementoperation dar.  Das Ergebnis der Operation ist der Wert des Operanden, nachdem er vermindert worden ist.  Die zweite Form stellt eine Postfixdekrementoperation dar.  Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.  
  
## Hinweise  
 Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.  
  
 Benutzerdefinierte Typen können den Operator `--` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)