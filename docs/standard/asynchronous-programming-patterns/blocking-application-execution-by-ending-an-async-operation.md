---
title: "Blocking Application Execution by Ending an Async Operation | Microsoft Docs"
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
  - "blocks, asynchronous operations"
  - "AsyncWaitHandle property"
  - "asynchronous programming, blocking applications"
  - "blocking application execution"
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Blocking Application Execution by Ending an Async Operation
Anwendungen, die während des Wartens auf die Ergebnisse asynchroner Operationen keine anderen Aufgaben ausführen können, müssen bis zum Abschluss der Operation blockieren.  Um den Hauptthread der Anwendung zu blockieren, wenn auf den Abschluss einer asynchronen Operation gewartet wird, verwenden Sie eine der folgenden Optionen:  
  
-   Rufen Sie die **Beenden** *OperationName*\-Methode der asynchronen Operation auf.  Diese Vorgehensweise wird in diesem Thema veranschaulicht.  
  
-   Verwenden Sie die <xref:System.IAsyncResult.AsyncWaitHandle%2A>\-Eigenschaft <xref:System.IAsyncResult>, das von der **Begin** *OperationName*\-Methode der asynchronen Operation zurückgegeben wird.  Ein Beispiel zu dieser Vorgehensweise finden Sie unter [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Anwendungen, die die **Beenden** *OperationName*\-Methode verwenden, um zu blockieren, bis ein asynchroner Vorgang abgeschlossen ist, rufen im Normalfall die **Begin** *OperationName*\-Methode auf, führen dann Aufgaben, für die die Ergebnisse der Operation ausgeführt werden kann, aufrufen und dann auf **Beenden** *OperationName*.  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie asynchrone Methoden in der <xref:System.Net.Dns>\-Klasse verwendet werden, um DNS\-Daten für einen vom Benutzer festgelegten Computer abzurufen.  Beachten Sie, dass für den <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback`\-Parameter und den `stateObject`\-Parameter `null` \(`Nothing` in Visual Basic\) übergeben wird, da solche Argumente für diese Vorgehensweise entbehrlich sind.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)