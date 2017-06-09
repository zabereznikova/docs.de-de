---
title: "Gewusst wie: Explizites Ausl&#246;sen von Ausnahmen | Microsoft Docs"
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
  - "Ausnahmen, Auslösen"
  - "Ausnahmen, try/catch-Blöcke"
  - "FileNotFoundException-Klasse"
  - "Implizites Auslösen von Ausnahmen"
  - "try/catch-Blöcke"
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Explizites Ausl&#246;sen von Ausnahmen
Mit der `throw`\-Anweisung können Sie eine Ausnahme explizit auslösen.  Mit der `throw`\-Anweisung können Sie auch eine abgefangene Ausnahme erneut auslösen.  Es ist sinnvoll, einer erneut ausgelösten Ausnahme Informationen hinzuzufügen, um mehr Informationen für das Debuggen bereitstellen zu können.  
  
 Im folgenden Beispielcode wird ein try\/catch\-Block verwendet, um eine mögliche <xref:System.IO.FileNotFoundException> abzufangen.  Auf den try\-Block folgt ein catch\-Block, der die <xref:System.IO.FileNotFoundException> abfängt und eine Meldung an die Konsole ausgibt, wenn die Textdatei nicht gefunden wurde.  Als Nächstes folgt eine throw\-Anweisung, die eine neue <xref:System.IO.FileNotFoundException> auslöst und Textinformationen zur Ausnahme hinzufügt.  
  
## Beispiel  
 [!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
 [!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  
  
## Siehe auch  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Gewusst wie: Verwenden von Finally\-Blöcken](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)