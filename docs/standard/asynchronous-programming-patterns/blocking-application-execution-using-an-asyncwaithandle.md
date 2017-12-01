---
title: "Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle
Anwendungen, die nicht fortgesetzt werden können, andere Aufgaben während des Wartens auf die Ergebnisse eines asynchronen Vorgangs blockiert, bis der Vorgang abgeschlossen ist. Hauptthread der Anwendung blockiert wird, beim Abschluss eines asynchronen Vorgangs warten, verwenden Sie eine der folgenden Optionen:  
  
-   Verwenden der <xref:System.IAsyncResult.AsyncWaitHandle%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode. Dieser Ansatz wird in diesem Thema veranschaulicht.  
  
-   Rufen Sie den asynchronen Vorgang **End** *OperationName* Methode. Ein Beispiel für diesen Ansatz finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Anwendungen, die eine mehrere oder <xref:System.Threading.WaitHandle> Objekte blockiert, bis ein asynchroner Vorgang abgeschlossen ist in der Regel ruft der **beginnen** *OperationName* -Methode, führen Sie alle Daten, die ausgeführt werden kann ohne die Ergebnisse des Vorgangs und dann blockieren, bis die asynchronen Vorgänge abgeschlossen ist. Eine Anwendung kann für einen einzelnen Vorgang durch Aufrufen einer der Blockieren der <xref:System.Threading.WaitHandle.WaitOne%2A> Methoden mithilfe der <xref:System.IAsyncResult.AsyncWaitHandle%2A>. Um auf den Abschluss asynchroner Vorgänge blockiert, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A> Objekte in einem Array und den Aufruf von der <xref:System.Threading.WaitHandle.WaitAll%2A> Methoden. Zum Blockieren, bis für jede einer Reihe von auf den Abschluss asynchroner Vorgänge, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A> Objekte in einem Array und den Aufruf von der <xref:System.Threading.WaitHandle.WaitAny%2A> Methoden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie asynchrone Methoden in der DNS-Klasse, Domain Name System-Informationen für einen Benutzer angegebenen Computer abgerufen. Im Beispiel wird veranschaulicht, blockieren mit der <xref:System.Threading.WaitHandle> den asynchronen Vorgang zugeordnet. Beachten Sie, dass `null` (`Nothing` in Visual Basic) übergeben wird, für die <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` und `stateObject` Parameter, da diese nicht erforderlich sind, bei dieser Vorgehensweise.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Ereignisbasiertes asynchrones Muster (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
