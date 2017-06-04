---
title: "Blocking Application Execution Using an AsyncWaitHandle | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "asynchronous programming, blocking applications"
  - "stopping asynchronous operations"
  - "blocking application execution"
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Blocking Application Execution Using an AsyncWaitHandle
Anwendungen, die während des Wartens auf die Ergebnisse asynchroner Operationen keine anderen Aufgaben ausführen können, müssen bis zum Abschluss der Operation blockieren.  Um den Hauptthread der Anwendung zu blockieren, wenn auf den Abschluss einer asynchronen Operation gewartet wird, verwenden Sie eine der folgenden Optionen:  
  
-   Verwenden Sie die <xref:System.IAsyncResult.AsyncWaitHandle%2A>\-Eigenschaft <xref:System.IAsyncResult>, das von der **Begin** *OperationName*\-Methode der asynchronen Operation zurückgegeben wird.  Diese Vorgehensweise wird in diesem Thema veranschaulicht.  
  
-   Rufen Sie die **Beenden** *OperationName*\-Methode der asynchronen Operation auf.  Ein Beispiel zu dieser Vorgehensweise finden Sie unter [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Anwendungen, die eine oder mehrere <xref:System.Threading.WaitHandle>\-Objekte verwenden, um zu blockieren, bis ein asynchroner Vorgang abgeschlossen ist, rufen im Normalfall die **Begin** *OperationName*\-Methode auf, führen dann Aufgaben, für die die Ergebnisse der Operation ausgeführt werden kann, und blockieren dann auf, wenn der asynchrone Vorgang abgeschlossen wird.  Eine Anwendung kann die Ausführung einer einzelnen Operation blockieren, indem sie mithilfe des <xref:System.IAsyncResult.AsyncWaitHandle%2A> eine der <xref:System.Threading.WaitHandle.WaitOne%2A>\-Methoden aufruft.  Damit die Anwendung vor Abschluss mehrerer asynchroner Operationen blockiert, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A>\-Objekte in einem Array und rufen eine der <xref:System.Threading.WaitHandle.WaitAll%2A>\-Methoden auf.  Damit die Anwendung vor Abschluss einer einzelnen asynchronen Operation blockiert, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A>\-Objekte in einem Array und rufen eine der <xref:System.Threading.WaitHandle.WaitAny%2A>\-Methoden auf.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie asynchrone Methoden in der DNS\-Klasse verwendet werden, um DNS\-Daten für einen vom Benutzer festgelegten Computer abzurufen.  Im Beispiel wird das Blockieren mit dem der asynchronen Operation zugeordneten <xref:System.Threading.WaitHandle> veranschaulicht.  Beachten Sie, dass für den <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback`\-Parameter und den `stateObject`\-Parameter `null` \(`Nothing` in Visual Basic\)  übergeben wird, da hier beide Parameter entbehrlich sind.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## Siehe auch  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)