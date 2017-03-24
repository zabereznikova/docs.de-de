---
title: "Gewusst wie: Ausf&#252;hren von Bereinigungscode mit finally (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ausnahmebehandlung [C#], try/finally-Block"
  - "Ausnahmen [C#], try/finally-Block"
  - "try/finally-Blöcke [C#]"
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Gewusst wie: Ausf&#252;hren von Bereinigungscode mit finally (C#-Programmierhandbuch)
Mit einer `finally`\-Anweisung soll sichergestellt werden, dass die notwendige Bereinigung von Objekten sofort erfolgt, auch wenn eine Ausnahme ausgelöst wird. Die zu bereinigenden Objekte enthalten in der Regel externe Ressourcen.  Ein Beispiel für eine solche Bereinigung ist der Aufruf von <xref:System.IO.Stream.Close%2A> für einen <xref:System.IO.FileStream> sofort nach der Verwendung, anstatt zu warten, dass das Objekt in die Garbage Collection der Common Language Runtime aufgenommen wird:  
  
 [!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## Beispiel  
 Um den vorherigen Code in eine `try-catch-finally`\-Anweisung umzuwandeln, wird der Bereinigungscode wie folgt vom Arbeitscode getrennt.  
  
 [!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 Da eine Ausnahme innerhalb eines `try`\-Blocks jederzeit vor dem `OpenWrite()`\-Aufruf auftreten oder der `OpenWrite()`\-Aufruf selbst fehlschlagen kann, ist nicht garantiert, dass die Datei geöffnet ist, wenn versucht wird, sie zu schließen.  Der `finally`\-Block fügt eine Prüfung hinzu, um sicherzustellen, dass das <xref:System.IO.FileStream>\-Objekt vor dem Aufruf der <xref:System.IO.Stream.Close%2A>\-Methode nicht `null` ist.  Ohne die `null`\-Prüfung löst der `finally`\-Block möglicherweise eine eigene <xref:System.NullReferenceException> aus. Das Auslösen von Ausnahmen in `finally`\-Blöcken sollte jedoch möglichst vermieden werden.  
  
 Auch zum Schließen von Datenbankverbindungen sind `finally`\-Blöcke gut geeignet.  Da die Anzahl der zulässigen Verbindungen zum Datenbankserver manchmal begrenzt ist, ist es wichtig, Datenbankverbindungen zu schnell wie möglich zu schließen.  Wenn der Fall eintritt, dass vor dem Schließen einer Verbindung eine Ausnahme ausgelöst wird, liegt eine weitere Situation vor, in der es günstiger ist, den `finally`\-Block zu verwenden, als auf die Garbage Collection zu warten.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)