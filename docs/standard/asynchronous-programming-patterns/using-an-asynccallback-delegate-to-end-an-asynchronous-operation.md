---
title: Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
ms.openlocfilehash: 1da6bd95c79b25b5bbf6674cf7e9ef48d19cb708
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677959"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="da8a9-102">Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation</span><span class="sxs-lookup"><span data-stu-id="da8a9-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>

<span data-ttu-id="da8a9-103">Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs weiterarbeiten können, sollten nicht blockiert werden, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="da8a9-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="da8a9-104">Verwenden Sie eine der folgenden Optionen, um Anweisungen weiter auszuführen, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="da8a9-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="da8a9-105">Verwenden Sie ein <xref:System.AsyncCallback>-Delegat, um die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="da8a9-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="da8a9-106">Dieser Ansatz wird in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="da8a9-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="da8a9-107">Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.IsCompleted%2A> des <xref:System.IAsyncResult>-Objekts, das von der Methode **Begin**_OperationName_ für asynchrone Vorgänge zurückgegeben wurde, um zu ermitteln, ob der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="da8a9-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="da8a9-108">Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Abrufen des Status einer asynchronen Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="da8a9-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da8a9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da8a9-109">Example</span></span>  

 <span data-ttu-id="da8a9-110">Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System (DNS) für benutzerspezifische Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="da8a9-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="da8a9-111">In diesem Beispiel wird ein <xref:System.AsyncCallback>-Delegat erstellt, der die Methode `ProcessDnsInformation` referenziert.</span><span class="sxs-lookup"><span data-stu-id="da8a9-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="da8a9-112">Diese Methode wird einmal für jede asynchrone Anforderung von DNS-Informationen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="da8a9-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="da8a9-113">Beachten Sie, dass der vom Benutzer angegebene Host an den Parameter <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="da8a9-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="da8a9-114">Ein Beispiel, das die Definition und Verwendung eines komplexeren Zustandsobjekts demonstriert, finden Sie unter [Verwenden von AsyncCallback-Delegat und Zustandsobjekt](using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="da8a9-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="da8a9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da8a9-115">See also</span></span>

- [<span data-ttu-id="da8a9-116">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="da8a9-116">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="da8a9-117">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="da8a9-117">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="da8a9-118">Aufrufen von asynchronen Methoden unter Verwendung von IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="da8a9-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](calling-asynchronous-methods-using-iasyncresult.md)
- [<span data-ttu-id="da8a9-119">Verwenden von AsyncCallback-Delegat und Zustandsobjekt</span><span class="sxs-lookup"><span data-stu-id="da8a9-119">Using an AsyncCallback Delegate and State Object</span></span>](using-an-asynccallback-delegate-and-state-object.md)
