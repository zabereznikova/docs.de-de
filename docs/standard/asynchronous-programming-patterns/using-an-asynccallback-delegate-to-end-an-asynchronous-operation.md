---
title: "Using an AsyncCallback Delegate to End an Asynchronous Operation | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "AsyncCallback delegate"
  - "stopping asynchronous operations"
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Using an AsyncCallback Delegate to End an Asynchronous Operation
Anwendungen, die während des Wartens auf die Ergebnisse asynchroner Operationen noch weitere Aufgaben ausführen können, dürfen nicht bis zum Abschluss der Operation blockieren.  Damit die Ausführung von Aufgaben während des Wartens auf den Abschluss einer asynchronen Methode fortgesetzt wird, verwenden Sie eine der folgenden Optionen:  
  
-   Verwenden Sie einen <xref:System.AsyncCallback>\-Delegaten, um die Ergebnisse der asynchronen Operation in einem separaten Thread zu verarbeiten.  Diese Vorgehensweise wird in diesem Thema veranschaulicht.  
  
-   Verwenden Sie die <xref:System.IAsyncResult.IsCompleted%2A>\-Eigenschaft <xref:System.IAsyncResult>, das von der **Begin** *OperationName*\-Methode der asynchronen Operation zurückgegeben wird, um zu bestimmen, ob eine Operation abgeschlossen ist.  Ein Beispiel zu dieser Vorgehensweise finden Sie unter [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie asynchrone Methoden in der <xref:System.Net.Dns>\-Klasse verwendet werden, um DNS\-Daten für Computer abzurufen, die vom Benutzer festgelegt wurden.  In diesem Beispiel wird ein <xref:System.AsyncCallback>\-Delegat erstellt, der auf die `ProcessDnsInformation`\-Methode verweist.  Diese Methode wird für jede asynchrone Anforderung von DNS\-Informationen einmal aufgerufen.  
  
 Beachten Sie, dass der vom Benutzer angegebene Host an den <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object>\-Parameter übergeben wird.  Ein Beispiel, in dem das Definieren und Verwenden eines komplexeren Zustandsobjekts veranschaulicht wird, finden Sie unter [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Calling Asynchronous Methods Using IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)   
 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)