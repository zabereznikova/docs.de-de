---
title: "Out of stack space (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID28"
dev_langs: 
  - "VB"
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Out of stack space (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, dessen Kapazität entsprechend den Anforderungen des ausgeführten Programms dynamisch vergrößert und verkleinert wird.  Die Grenzen wurden überschritten.  
  
### So beheben Sie diesen Fehler  
  
1.  Prüfen Sie, ob Prozeduren nicht zu tief geschachtelt sind.  
  
2.  Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß abgeschlossen werden.  
  
3.  Falls lokale Variablen mehr Speicherplatz beanspruchen, als verfügbar ist, versuchen Sie, einige Variablen auf Modulebene zu deklarieren.  Sie können auch alle Variablen in der Prozedur als statisch deklarieren, indem Sie den Schlüsselwörtern `Property`, `Sub` oder `Function` die `Static`\-Anweisung voranstellen.  Oder Sie verwenden die `Static`\-Anweisung, um einzelne statische Variablen innerhalb von Prozeduren zu deklarieren.  
  
4.  Definieren Sie einige der Zeichenfolgen mit fester Länge als Zeichenfolgen mit variabler Länge. Zeichenfolgen mit fester Länge benötigen mehr Stapelspeicher als Zeichenfolgen mit variabler Länge.  Sie können die Zeichenfolge auch auf Modulebene definieren; dort erfordert sie keinen Stapelspeicher.  
  
5.  Überprüfen Sie die Anzahl geschachtelter `DoEvents`\-Funktionsaufrufe, indem Sie die auf dem Stapel aktiven Prozeduren mithilfe des Dialogfelds `Calls` anzeigen.  
  
6.  Vergewissern Sie sich, dass Sie keine Ereigniskette verursacht haben, indem Sie ein Ereignis ausgelöst haben, durch das eine bereits auf dem Stapel befindliche Ereignisprozedur aufgerufen wird.  Eine Ereigniskette ist mit einem nicht abgeschlossenen rekursiven Prozeduraufruf vergleichbar, jedoch schwieriger zu erkennen, da der Aufruf durch [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] anstatt explizit im Code erfolgt.  Verwenden Sie das Dialogfeld `Calls`, um die auf dem Stapel aktiven Prozeduren anzuzeigen.  
  
## Siehe auch  
 [Fenster "Arbeitsspeicher"](/visual-studio/debugger/memory-windows)