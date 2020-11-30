---
title: Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle
ms.date: 03/30/2017
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
ms.openlocfilehash: 1e7fc71ef5a4a44b2bb4c039305e06c157c65f75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716160"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="2aa37-102">Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="2aa37-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>

<span data-ttu-id="2aa37-103">Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs nicht weiterarbeiten können, werden blockiert, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2aa37-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="2aa37-104">Verwenden Sie eine der folgenden Optionen, um den Hauptthread Ihrer Anwendung zu blockieren, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="2aa37-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="2aa37-105">Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.AsyncWaitHandle%2A> des Ergebnisses <xref:System.IAsyncResult>, das durch die Methode **Begin**_OperationName_ für asynchrone Vorgänge zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2aa37-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="2aa37-106">Dieser Ansatz wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2aa37-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="2aa37-107">Rufen Sie die Methode **End**_OperationName_ für asynchrone Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="2aa37-107">Call the asynchronous operation's **End**_OperationName_ method.</span></span> <span data-ttu-id="2aa37-108">Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs](blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="2aa37-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="2aa37-109">Anwendungen, die mindestens ein <xref:System.Threading.WaitHandle>-Objekt zum Blockieren verwenden, bis ein asynchroner Vorgang abgeschlossen ist, rufen in der Regel die Methode **Begin**_OperationName_ auf, arbeiten alle Tasks ab, die ohne die Ergebnisse des Vorgangs ausgeführt werden können, und blockieren dann bis alle asynchronen Vorgänge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2aa37-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="2aa37-110">Eine Anwendung kann für einen einzelnen Vorgang durch Aufrufen einer der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methoden mithilfe von <xref:System.IAsyncResult.AsyncWaitHandle%2A> blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="2aa37-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="2aa37-111">Damit die Anwendungsausführung blockiert wird, solange eine Reihe von asynchronen Vorgängen noch nicht abgeschlossen ist, speichern Sie die zugehörigen <xref:System.IAsyncResult.AsyncWaitHandle%2A>-Objekte in einem Array und rufen Sie eine der <xref:System.Threading.WaitHandle.WaitAll%2A>-Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="2aa37-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="2aa37-112">Wenn die Anwendungsausführung blockiert werden soll, solange eine beliebige Reihe von asynchronen Vorgängen noch nicht abgeschlossen ist, speichern Sie die zugehörigen <xref:System.IAsyncResult.AsyncWaitHandle%2A>-Objekte in einem Array und rufen Sie eine der <xref:System.Threading.WaitHandle.WaitAny%2A>-Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="2aa37-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa37-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2aa37-113">Example</span></span>  

 <span data-ttu-id="2aa37-114">Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der DNS-Klasse, um Informationen aus dem Domain Name System für einen benutzerdefinierten Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2aa37-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="2aa37-115">Im Beispiel wird veranschaulicht, wie Sie zum Blockieren das mit dem asynchronen Vorgang verknüpfte <xref:System.Threading.WaitHandle> verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aa37-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="2aa37-116">Beachten Sie, dass `null` (`Nothing` in Visual Basic) für die Parameter <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` und `stateObject` übergeben wird, da sie bei diesem Ansatz nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2aa37-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2aa37-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2aa37-117">See also</span></span>

- [<span data-ttu-id="2aa37-118">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="2aa37-118">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="2aa37-119">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="2aa37-119">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
