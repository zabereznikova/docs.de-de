---
title: "Operator&#160;++ (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "++_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "++ (Operator) [C#]"
  - "Inkrementoperator (++) [C#]"
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Operator&#160;++ (C#-Referenz)
Der Inkrementoperator \(`++`\) erhöht seinen Operanden um 1. Der Inkrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `++variable` und `variable++`.  
  
## Hinweise  
 Die erste Form stellt eine Präfixinkrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, nachdem er erhöht worden ist.  
  
 Die zweite Form stellt eine Postfixinkrementoperation dar. Das Ergebnis der Operation ist der Wert des Operanden, bevor er erhöht wird.  
  
 Für alle numerischen Typen und Enumerationstypen sind Inkrementoperatoren vordefiniert. Benutzerdefinierte Typen können den Operator `++` überladen. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen \(enum\) zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#3)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)