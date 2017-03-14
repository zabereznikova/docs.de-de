---
title: "Events of shared WithEvents variables cannot be handled by non-shared methods | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30594"
  - "vbc30594"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30594"
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Events of shared WithEvents variables cannot be handled by non-shared methods
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine mit dem `Shared`\-Modifizierer deklarierte Variable ist eine gemeinsam genutzte Variable.  Eine gemeinsam genutzte Variable kennzeichnet genau einen Speicherort.  Eine mit dem `WithEvents`\-Modifizierer deklarierte Variable gibt an, dass der zur Variablen gehörende Typ die Gruppe von Ereignissen verarbeitet, die von der Variablen ausgelöst werden.  Wenn der Variablen ein Wert zugewiesen wird, hebt die von der `WithEvents`\-Deklaration erstellte Eigenschaft die Zuordnung aller bestehenden Ereignishandler auf und ordnet über die `Add`\-Methode einen neuen Ereignishandler zu.  
  
 **Fehler\-ID:** BC30594  
  
### So beheben Sie diesen Fehler  
  
-   Deklarieren Sie den Ereignishandler als `Shared`.  
  
## Siehe auch  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)