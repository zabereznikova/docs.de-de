---
title: "Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "catch-Blöcke"
  - "Ausnahmen, try/catch-Blöcke"
  - "try/catch-Blöcke"
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block
Tritt eine Ausnahme auf, wird sie an den Stapel übergeben, und jeder **catch**\-Block hat die Möglichkeit, sie zu behandeln.  Wichtig ist die Reihenfolge der **catch**\-Anweisungen.  Setzen Sie **catch**\-Blöcke, die auf spezifische Ausnahmen abzielen, vor diejenigen für allgemeine Ausnahmen. Ansonsten könnte der Compiler einen Fehler melden.  Der richtige **catch**\-Block wird durch Übereinstimmung des Ausnahmetyps mit dem Namen der im **catch**\-Block angegebenen Ausnahme ermittelt.  Gibt es keinen spezifischen **catch**\-Block, wird die Ausnahme von einem allgemeinen **catch**\-Block abgefangen, sofern ein solcher vorhanden ist.  
  
 Im folgenden Beispielcode wird ein try\/catch\-Block verwendet, um eine <xref:System.InvalidCastException> abzufangen.  Es wird eine Klasse namens `Employee` mit der Eigenschaft `Emlevel` \(employee level\) erstellt.  Die Methode `, PromoteEmployee` nimmt ein Objekt an und erhöht die Emlevel\-Eigenschaft.  Die **InvalidCastException**\-Ausnahme tritt dann auf, wenn die <xref:System.DateTime>\-Instanz an die `PromoteEmployee`\-Methode übergeben wird.  
  
## Beispiel  
 [!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
 [!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
 [!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]  
  
 Durch die Common Language Runtime werden Ausnahmen abgefangen, die nicht durch einen **catch\-**Block abgefangen wurden.  Je nach Konfiguration der CLR wird entweder ein Dialogfeld zum Debuggen angezeigt oder das Programm wird beendet und ein Dialogfeld mit Ausnahmeinformationen angezeigt.  Informationen zum Debuggen finden Sie unter [Debuggen und Profilerstellung von Anwendungen](../../../docs/framework/debug-trace-profile/index.md).  
  
## Siehe auch  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Gewusst wie: Explizites Auslösen von Ausnahmen](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Gewusst wie: Verwenden von Finally\-Blöcken](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Exception\-Klasse und Exception\-Eigenschaften](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)