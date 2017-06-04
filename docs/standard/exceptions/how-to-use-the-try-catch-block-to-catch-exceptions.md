---
title: "Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen | Microsoft Docs"
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
  - "Ausnahmen, try/catch-Blöcke"
  - "try-Blöcke"
  - "try/catch-Blöcke"
  - "catch-Blöcke"
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden des Try-Catch-Blocks zum Abfangen von Ausnahmen
Fügen Sie Codeabschnitte, die Ausnahmen auslösen könnten, in einen **try**\-Block ein und Code, der Ausnahmen behandelt, in einen **catch**\-Block.  Ein **catch**\-Block ist eine Folge von Anweisungen, die mit dem Schlüsselwort **catch** beginnen, gefolgt von einem Ausnahmetyp und einer auszuführenden Aktion.  
  
> [!NOTE]
>  Fast jede Codezeile kann eine Ausnahme verursachen, vor allem solche, die von der Common Language Runtime ausgelöst werden, wie z. B. die Ausnahmen <xref:System.OutOfMemoryException> und <xref:System.StackOverflowException>.  Bei den meisten Anwendungen kommen solche Ausnahmen selten vor, aber Sie sollten darauf achten, wenn Sie Bibliotheken für andere Benutzer schreiben.  Wann es ratsam ist, Code in einen try\-Block einzusetzen, erfahren Sie unter [Empfohlene Vorgehensweise für die Ausnahmebehandlung](../../../docs/standard/exceptions/best-practices-for-exceptions.md).  
  
 Im folgenden Beispielcode wird ein **try\/catch**\-Block verwendet, um gegebenenfalls Ausnahmen abzufangen.  Die `Main`\-Methode enthält einen **try**\-Block mit einer **StreamReader**\-Anweisung, mit der die Textdatei `data.txt` geöffnet und eine Zeichenfolge aus der Datei geschrieben wird.  Auf den **try**\-Block folgt ein **catch**\-Block, der alle vom **try**\-Block gelieferten Ausnahmen abfängt.  
  
## Beispiel  
 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  
  
 Dieses Beispiel veranschaulicht eine grundlegende **catch**\-Anweisung, die in der Lage ist, jede Ausnahme abzufangen.  Im Allgemeinen ist es jedoch besserer Programmierstil, einen spezifischen Ausnahmetyp abzufangen, anstatt die grundlegende **catch** \-Anweisung zu verwenden.  Weitere Informationen über das Abfangen spezifischer Ausnahmen finden Sie unter [Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md).  
  
## Siehe auch  
 [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Gewusst wie: Explizites Auslösen von Ausnahmen](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Gewusst wie: Erstellen benutzerdefinierter Ausnahmen](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Gewusst wie: Verwenden von Finally\-Blöcken](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)