---
title: Abrufen des Status einer asynchronen Operation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
ms.openlocfilehash: c4e8e7c66551e0a240eaa873513c3975703af946
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830310"
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a><span data-ttu-id="1be4d-102">Abrufen des Status einer asynchronen Operation</span><span class="sxs-lookup"><span data-stu-id="1be4d-102">Polling for the Status of an Asynchronous Operation</span></span>
<span data-ttu-id="1be4d-103">Anwendungen, die während des Wartens auf die Ergebnisse eines asynchronen Vorgangs weiterarbeiten können, sollten nicht blockiert werden, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1be4d-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="1be4d-104">Verwenden Sie eine der folgenden Optionen, um Anweisungen weiter auszuführen, während Sie darauf warten, dass ein asynchroner Vorgang abgeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="1be4d-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="1be4d-105">Verwenden Sie die Eigenschaft <xref:System.IAsyncResult.IsCompleted%2A> des <xref:System.IAsyncResult>-Objekts, das von der Methode **Begin**_OperationName_ für asynchrone Vorgänge zurückgegeben wurde, um zu ermitteln, ob der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1be4d-105">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method to determine whether the operation has completed.</span></span> <span data-ttu-id="1be4d-106">Dieser Ansatz wird als Abruf bezeichnet und in diesem Thema veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1be4d-106">This approach is known as polling and is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="1be4d-107">Verwenden Sie ein <xref:System.AsyncCallback>-Delegat, um die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1be4d-107">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="1be4d-108">Ein Beispiel zur Veranschaulichung dieses Ansatzes finden Sie unter [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="1be4d-108">For an example that demonstrates this approach, see [Using an AsyncCallback Delegate to End an Asynchronous Operation](using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1be4d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1be4d-109">Example</span></span>  
 <span data-ttu-id="1be4d-110">Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System für einen benutzerdefinierten Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1be4d-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="1be4d-111">Dieses Beispiel startet den asynchronen Vorgang und gibt dann Punkte („.“) in der Konsole aus, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1be4d-111">This example starts the asynchronous operation and then prints periods (".") at the console until the operation is complete.</span></span> <span data-ttu-id="1be4d-112">Beachten Sie, dass **NULL** (**Nichts** in Visual Basic) für die Parameter <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> und <xref:System.Object> übergeben wird, da diese Argumente bei diesem Ansatz nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="1be4d-112">Note that **null** (**Nothing** in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.AsyncCallback> and <xref:System.Object> parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1be4d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1be4d-113">See also</span></span>

- [<span data-ttu-id="1be4d-114">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="1be4d-114">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="1be4d-115">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="1be4d-115">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
