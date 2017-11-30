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
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="72780-102">Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="72780-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="72780-103">Anwendungen, die nicht fortgesetzt werden können, andere Aufgaben während des Wartens auf die Ergebnisse eines asynchronen Vorgangs blockiert, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="72780-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="72780-104">Hauptthread der Anwendung blockiert wird, beim Abschluss eines asynchronen Vorgangs warten, verwenden Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="72780-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="72780-105">Verwenden der <xref:System.IAsyncResult.AsyncWaitHandle%2A> Eigenschaft von der <xref:System.IAsyncResult> zurückgegeben, die für des asynchronen Vorgangs **beginnen** *OperationName* Methode.</span><span class="sxs-lookup"><span data-stu-id="72780-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="72780-106">Dieser Ansatz wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="72780-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="72780-107">Rufen Sie den asynchronen Vorgang **End** *OperationName* Methode.</span><span class="sxs-lookup"><span data-stu-id="72780-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="72780-108">Ein Beispiel für diesen Ansatz finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="72780-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="72780-109">Anwendungen, die eine mehrere oder <xref:System.Threading.WaitHandle> Objekte blockiert, bis ein asynchroner Vorgang abgeschlossen ist in der Regel ruft der **beginnen** *OperationName* -Methode, führen Sie alle Daten, die ausgeführt werden kann ohne die Ergebnisse des Vorgangs und dann blockieren, bis die asynchronen Vorgänge abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="72780-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="72780-110">Eine Anwendung kann für einen einzelnen Vorgang durch Aufrufen einer der Blockieren der <xref:System.Threading.WaitHandle.WaitOne%2A> Methoden mithilfe der <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="72780-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="72780-111">Um auf den Abschluss asynchroner Vorgänge blockiert, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A> Objekte in einem Array und den Aufruf von der <xref:System.Threading.WaitHandle.WaitAll%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="72780-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="72780-112">Zum Blockieren, bis für jede einer Reihe von auf den Abschluss asynchroner Vorgänge, speichern Sie die entsprechenden <xref:System.IAsyncResult.AsyncWaitHandle%2A> Objekte in einem Array und den Aufruf von der <xref:System.Threading.WaitHandle.WaitAny%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="72780-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72780-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72780-113">Example</span></span>  
 <span data-ttu-id="72780-114">Im folgenden Codebeispiel wird veranschaulicht, wie asynchrone Methoden in der DNS-Klasse, Domain Name System-Informationen für einen Benutzer angegebenen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="72780-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="72780-115">Im Beispiel wird veranschaulicht, blockieren mit der <xref:System.Threading.WaitHandle> den asynchronen Vorgang zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="72780-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="72780-116">Beachten Sie, dass `null` (`Nothing` in Visual Basic) übergeben wird, für die <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` und `stateObject` Parameter, da diese nicht erforderlich sind, bei dieser Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="72780-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="72780-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72780-117">See Also</span></span>  
 [<span data-ttu-id="72780-118">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="72780-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="72780-119">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="72780-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
