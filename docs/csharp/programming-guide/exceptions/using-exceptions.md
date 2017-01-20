---
title: "Verwenden von Ausnahmen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/09/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmebehandlung [C#], Informationen über Ausnahmebehandlung"
  - "Ausnahmen [C#], Informationen über Ausnahmen"
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Verwenden von Ausnahmen (C#-Programmierhandbuch)
In C\# werden Fehler, die zur Laufzeit im Programm auftreten, im Programm über sogenannte Ausnahmen übermittelt.  Ausnahmen werden durch Code ausgelöst, der auf einen Fehler trifft, und durch Code abgefangen, der den Fehler korrigieren kann.  Ausnahmen können von der Common Language Runtime \(CLR\) von .NET Framework oder durch Programmcode ausgelöst werden.  Sobald eine Ausnahme ausgelöst wird, wird sie in der Aufrufliste aufwärts weitergeleitet, bis eine `catch`\-Anweisung für die Ausnahme gefunden wird.  Nicht abgefangene Ausnahmen werden von einem generischen Ausnahmehandler des Systems behandelt, der ein Dialogfeld anzeigt.  
  
 Ausnahmen werden durch Klassen dargestellt, die von <xref:System.Exception> abgeleitet sind.  Diese Klasse bestimmt den Typ der Ausnahme und enthält Eigenschaften mit Details über die Ausnahme.  Zum Auslösen einer Ausnahme gehört das Erstellen der Instanz aus einer Klasse, die von einer Ausnahme abgeleitet ist, optional das Konfigurieren von Eigenschaften der Ausnahme und die anschließende Übergabe des Objekts mit dem `throw`\-Schlüsselwort.  Beispiele:  
  
 [!code-cs[csProgGuideExceptions#1](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_1.cs)]  
  
 Nachdem eine Ausnahme ausgelöst wurde, wird über die Laufzeit geprüft, ob die aktuelle Anweisung sich innerhalb eines `try`\-Blocks befindet.  Ist dies der Fall, werden alle `catch`\-Blöcke, die dem `try`\-Block zugeordnet sind, darauf überprüft, ob sie die Ausnahme abfangen können.  `Catch`\-Blöcke geben normalerweise Ausnahmetypen an. Wenn der `catch`\-Block vom gleichen Typ wie die Ausnahme oder wie eine Basisklasse der Ausnahme ist, kann der `catch`\-Block die Methode verarbeiten.  Beispiele:  
  
 [!code-cs[csProgGuideExceptions#2](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_2.cs)]  
  
 Steht die Anweisung, die die Ausnahme auslöst, nicht in einem `try`\-Block, oder hat der `try`\-Block, in dem sie steht, keinen zugehörigen `catch`\-Block, wird die aufrufende Methode über die Laufzeit auf eine `try`\-Anweisung mit `catch`\-Blöcken geprüft.  Die Laufzeit folgt der Aufrufliste auf der Suche nach einem passenden `catch`\-Block.  Nach der Ausführung des `catch`\-Blocks wird die Steuerung an die nächste Anweisung nach diesem `catch`\-Block übergeben.  
  
 Eine `try`\-Anweisung kann mehr als einen `catch`\-Block enthalten.  Die erste `catch`\-Anweisung, die die Ausnahme behandeln kann, wird ausgeführt. Alle nachfolgenden `catch`\-Anweisungen werden ignoriert, unabhängig davon, ob sie kompatibel sind.  Deshalb sollten catch\-Blöcke immer von der spezifischsten \(oder am meisten abgeleiteten\) bis hin zur am wenigsten spezifischen angeordnet werden.  Beispiele:  
  
 [!code-cs[csProgGuideExceptions#3](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_3.cs)]  
  
 Vor Ausführung des `catch`\-Blocks werden alle `finally`\-Blöcke von der Laufzeit untersucht.  Mit `Finally`\-Blöcken kann der Programmierer nicht eindeutige Zustände bereinigen, die ein abgebrochener `try`\-Block hinterlassen hat. Er kann auch externe Ressourcen \(wie z. B. Grafikhandles, Datenbankverbindungen oder Dateistreams\) freigeben, ohne darauf zu warten, dass der Garbage Collector Objekte in der Laufzeit abschließt.  Beispiele:  
  
 [!code-cs[csProgGuideExceptions#4](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/using-exceptions_4.cs)]  
  
 Wenn `WriteByte()` eine Ausnahme auslöst, schlägt der Code im zweiten `try`\-Block, der versucht, die Datei erneut zu öffnen, fehl, wenn `file.Close()` nicht aufgerufen wird. Die Datei bleibt in diesem Fall gesperrt.  Da `finally`\-Blöcke unabhängig vom Auslösen einer Ausnahme ausgeführt werden, kann durch den `finally`\-Block im obigen Beispiel die Datei ordnungsgemäß geschlossen und damit ein Fehler vermieden werden.  
  
 Sollte nach dem Auslösen einer Ausnahme kein passender `catch`\-Block in der Aufrufliste gefunden werden, gibt es drei Möglichkeiten:  
  
-   Befindet sich die Ausnahme innerhalb eines Destruktors, wird der Destruktor abgebrochen und der Basisdestruktor, falls vorhanden, wird aufgerufen.  
  
-   Enthält der Stapel einen statischen Konstruktor oder einen statischen Feldinitialisierer, wird <xref:System.TypeInitializationException> ausgelöst, wobei die ursprüngliche Ausnahme der <xref:System.Exception.InnerException%2A>\-Eigenschaft der neuen Ausnahme zugewiesen wird.  
  
-   Wenn der Anfang des Threads erreicht wird, wird der Thread beendet.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)