---
title: "Function evaluation is disabled because a previous function evaluation timed out | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30957"
  - "vbc30957"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30957"
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Function evaluation is disabled because a previous function evaluation timed out
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.Wenn Sie die Funktionsauswertung wieder aktivieren möchten, starten Sie den Einzelschrittdurchlauf oder das Debuggen erneut  
  
 Im Visual Studio\-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.  
  
 Zu den möglichen Gründen für das Timeout eines Prozeduraufrufs zählt eine *Endlosschleife*.  Weitere Informationen finden Sie unter [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Eine besondere Variante einer Endlosschleife stellt die *Rekursion* dar.  Weitere Informationen finden Sie unter [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Fehler\-ID:** BC30957  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie nach Möglichkeit die vorherige Funktionsevaluierung und die Ursache für das Timeout.  Andernfalls kann dieser Fehler erneut auftreten.  
  
2.  Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.  
  
## Siehe auch  
 [Debuggen in Visual Studio](/visual-studio/debugger/debugging-in-visual-studio)   
 [Navigieren im Code mit dem Debugger](/visual-studio/debugger/navigating-through-code-with-the-debugger)   
 [Ausdrücke in Visual Basic](../Topic/Expressions%20in%20Visual%20Basic.md)