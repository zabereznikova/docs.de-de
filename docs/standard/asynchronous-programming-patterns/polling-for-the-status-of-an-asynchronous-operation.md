---
title: "Polling for the Status of an Asynchronous Operation | Microsoft Docs"
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
  - "asynchronous programming, status polling"
  - "polling asynchronous operation status"
  - "status information [.NET Framework], asynchronous operations"
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Polling for the Status of an Asynchronous Operation
Anwendungen, die während des Wartens auf die Ergebnisse asynchroner Operationen noch weitere Aufgaben ausführen können, dürfen nicht bis zum Abschluss der Operation blockieren.  Damit die Ausführung von Aufgaben während des Wartens auf den Abschluss einer asynchronen Methode fortgesetzt wird, verwenden Sie eine der folgenden Optionen:  
  
-   Verwenden Sie die <xref:System.IAsyncResult.IsCompleted%2A>\-Eigenschaft <xref:System.IAsyncResult>, das von der **Begin** *OperationName*\-Methode der asynchronen Operation zurückgegeben wird, um zu bestimmen, ob eine Operation abgeschlossen ist.  Diese Vorgehensweise ist als Abrufen bekannt und wird in diesem Thema veranschaulicht.  
  
-   Verwenden Sie einen <xref:System.AsyncCallback>\-Delegaten, um die Ergebnisse der asynchronen Operation in einem separaten Thread zu verarbeiten.  Ein Beispiel zu dieser Vorgehensweise finden Sie unter [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie asynchrone Methoden in der <xref:System.Net.Dns>\-Klasse verwendet werden, um DNS\-Daten für einen vom Benutzer festgelegten Computer abzurufen.  Im Beispiel werden die asynchrone Operation gestartet und anschließend bis zu deren Abschluss Punkte \("."\) auf die Konsole gedruckt.  Beachten Sie, dass **null** \(**Nothing** in Visual Basic\) für den <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback>\-Parameter und den <xref:System.Object>\-Parameter übergeben wird, da solche Argumente für diese Vorgehensweise nicht erforderlich sind.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)