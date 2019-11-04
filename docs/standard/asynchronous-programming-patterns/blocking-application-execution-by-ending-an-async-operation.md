---
title: Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121330"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="a094f-102">Blockieren der Anwendungsausführung durch Beenden eines asynchronen Vorgangs</span><span class="sxs-lookup"><span data-stu-id="a094f-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="a094f-103">Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs nicht weiterarbeiten können, werden blockiert, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a094f-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="a094f-104">Verwenden Sie eine der folgenden Optionen, um den Hauptthread Ihrer Anwendung zu blockieren, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="a094f-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="a094f-105">Rufen Sie die Methode **End**_OperationName_ für asynchrone Vorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="a094f-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="a094f-106">Dieser Ansatz wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a094f-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="a094f-107">Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.AsyncWaitHandle%2A> des Ergebnisses <xref:System.IAsyncResult>, das durch die Methode **Begin**_OperationName_ für asynchrone Vorgänge zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a094f-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="a094f-108">Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Blockieren der Anwendungsausführung mithilfe von AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="a094f-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="a094f-109">Anwendungen, die die Methode **End**_OperationName_ zum Blockieren verwenden, bis ein asynchroner Vorgang abgeschlossen ist, rufen in der Regel die Methode **Begin**_OperationName_ auf, arbeiten alle Tasks ab, die ohne die Ergebnisse des Vorgangs ausgeführt werden können, und rufen dann die Methode **End**_OperationName_ auf.</span><span class="sxs-lookup"><span data-stu-id="a094f-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a094f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a094f-110">Example</span></span>  
 <span data-ttu-id="a094f-111">Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System für einen benutzerdefinierten Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a094f-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="a094f-112">Beachten Sie, dass `null` (`Nothing` in Visual Basic) für die Parameter <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` und `stateObject` übergeben wird, da diese Argumente bei diesem Ansatz nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a094f-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a094f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a094f-113">See also</span></span>

- [<span data-ttu-id="a094f-114">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="a094f-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="a094f-115">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="a094f-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
