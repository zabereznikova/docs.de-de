---
title: "Gewusst wie: Verwenden von Finally-Bl&#246;cken | Microsoft Docs"
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
  - "ArgumentOutOfRangeException-Klasse"
  - "Ausnahmen, finally-Blöcke"
  - "Ausnahmen, try/catch-Blöcke"
  - "finally-Blöcke"
  - "try/catch-Blöcke"
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Verwenden von Finally-Bl&#246;cken
Beim Auftreten einer Ausnahme wird die Ausführung beendet und die Kontrolle an den nächsten Ausnahmehandler übergeben.  Häufig werden dadurch Codezeilen, die sonst immer aufgerufen werden, nicht ausgeführt.  Einige Aufgaben zur Systembereinigung, wie z. B. Schließen einer Datei, müssen immer ausgeführt werden, selbst wenn eine Ausnahme ausgelöst wurde.  Dies kann durch Verwenden eines **finally**\-Blocks erreicht werden.  Ein **finally**\-Block wird immer ausgeführt, unabhängig vom Auslösen einer Ausnahme.  
  
 Im folgenden Beispielcode wird ein try\/catch\-Block verwendet, um eine <xref:System.ArgumentOutOfRangeException> abzufangen.  Durch die `Main`\-Methode werden zwei Arrays erstellt, und es wird der Versuch unternommen, ein Array in das andere zu kopieren.  Die Aktion generiert eine **ArgumentOutOfRangeException**\-Ausnahme. Der Fehler wird auf der Konsole ausgegeben.  Der **finally**\-Block wird unabhängig vom Ausgang des Kopiervorgangs ausgeführt.  
  
## Beispiel  
 [!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
 [!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
 [!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  
  
## Siehe auch  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Gewusst wie: Explizites Auslösen von Ausnahmen](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)