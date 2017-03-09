---
title: "Error Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
helpviewer_keywords: 
  - "exceptions, types"
  - "errors [Visual Basic], types"
  - "errors [Visual Basic], logic"
  - "errors [Visual Basic], syntax"
  - "logic errors, Visual Basic"
  - "run-time errors, types of errors"
  - "syntax errors, Visual Basic"
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Error Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] werden Fehler \(auch *Ausnahmen* genannt\) in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und Logikfehler.  
  
## Syntaxfehler  
 *Syntaxfehler* sind Fehler, die bei der Eingabe des Codes entstehen.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] überprüft den Code bereits während der Eingabe im Fenster **Code\-Editor** und weist Sie auf Fehler hin, z. B. Tippfehler in einem reservierten Wort oder falsch verwendete Sprachelemente.  Syntaxfehler stellen den häufigsten Fehlertyp dar.  Sie können in der Codierungsumgebung sofort problemlos behoben werden.  
  
> [!NOTE]
>  Die `Option Explicit`\-Anweisung ist ein Mittel zur Vermeidung von Syntaxfehlern.  Sie bewirkt, dass alle in einer Anwendung zu verwendenden Variablen im Voraus deklariert werden müssen.  Deshalb lassen sich Tippfehler sofort erkennen und beheben, wenn diese Variablen im Code verwendet werden.  
  
## Laufzeitfehler  
 *Laufzeitfehler* treten erst nach der Kompilierung und Ausführung des Codes auf.  Dazu gehört scheinbar fehlerloser Code, der zwar frei von Syntaxfehlern ist, aber sich nicht ausführen lässt.  Beispiel: Sie schreiben eine korrekte Codezeile zum Öffnen einer Datei.  Wenn die Datei jedoch beschädigt ist, kann die Anwendung die `Open`\-Funktion nicht ausführen, und die Ausführung wird beendet.  Die meisten Laufzeitfehler lassen sich durch erneutes Schreiben des fehlerhaften Codes beheben. Kompilieren Sie ihn anschließend neu, und führen Sie ihn nochmals aus.  
  
## Logische Fehler  
 *Logische Fehler* treten während der Arbeit mit der Anwendung auf.  Meistens handelt es sich hierbei um unbeabsichtigte oder unerwartete Ergebnisse in Reaktion auf Benutzeraktionen.  Eine falsch angeschlagene Taste oder ein anderer äußerer Einfluss können z. B. dazu führen, dass die Anwendung innerhalb erwarteter Parameter nicht mehr läuft oder ganz beendet wird.  Logikfehler sind generell am schwersten zu beheben, da nicht immer nachvollziehbar ist, wodurch sie ausgelöst werden.  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Debugger – Grundlagen](/visual-studio/debugger/debugger-basics)