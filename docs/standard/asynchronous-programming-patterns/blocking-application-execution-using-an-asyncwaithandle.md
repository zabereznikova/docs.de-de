---
title: Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 16b5a297c13cd9096548ed489e4994b72a48da67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121425"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle
Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs nicht weiterarbeiten können, werden blockiert, bis der Vorgang abgeschlossen ist. Verwenden Sie eine der folgenden Optionen, um den Hauptthread Ihrer Anwendung zu blockieren, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:  
  
- Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.AsyncWaitHandle%2A> des Ergebnisses <xref:System.IAsyncResult>, das durch die Methode **Begin**_OperationName_ für asynchrone Vorgänge zurückgegeben wird. Dieser Ansatz wird in diesem Thema veranschaulicht.  
  
- Rufen Sie die Methode **End**_OperationName_ für asynchrone Vorgänge auf. Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Anwendungen, die mindestens ein <xref:System.Threading.WaitHandle>-Objekt zum Blockieren verwenden, bis ein asynchroner Vorgang abgeschlossen ist, rufen in der Regel die Methode **Begin**_OperationName_ auf, arbeiten alle Tasks ab, die ohne die Ergebnisse des Vorgangs ausgeführt werden können, und blockieren dann bis alle asynchronen Vorgänge abgeschlossen sind. Eine Anwendung kann für einen einzelnen Vorgang durch Aufrufen einer der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methoden mithilfe von <xref:System.IAsyncResult.AsyncWaitHandle%2A> blockiert werden. Damit die Anwendungsausführung blockiert wird, solange eine Reihe von asynchronen Vorgängen noch nicht abgeschlossen ist, speichern Sie die zugehörigen <xref:System.IAsyncResult.AsyncWaitHandle%2A>-Objekte in einem Array und rufen Sie eine der <xref:System.Threading.WaitHandle.WaitAll%2A>-Methoden auf. Wenn die Anwendungsausführung blockiert werden soll, solange eine beliebige Reihe von asynchronen Vorgängen noch nicht abgeschlossen ist, speichern Sie die zugehörigen <xref:System.IAsyncResult.AsyncWaitHandle%2A>-Objekte in einem Array und rufen Sie eine der <xref:System.Threading.WaitHandle.WaitAny%2A>-Methoden auf.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der DNS-Klasse, um Informationen aus dem Domain Name System für einen benutzerdefinierten Computer abzurufen. Im Beispiel wird veranschaulicht, wie Sie zum Blockieren das mit dem asynchronen Vorgang verknüpfte <xref:System.Threading.WaitHandle> verwenden. Beachten Sie, dass `null` (`Nothing` in Visual Basic) für die Parameter <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` und `stateObject` übergeben wird, da sie bei diesem Ansatz nicht benötigt werden.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
