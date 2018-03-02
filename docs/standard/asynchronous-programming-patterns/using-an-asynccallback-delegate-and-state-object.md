---
title: Verwenden von AsyncCallback-Delegat und Zustandsobjekt
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
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb0cdc9e98dcaf3c9f9879359eff0b31c8435773
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="dd41e-102">Verwenden von AsyncCallback-Delegat und Zustandsobjekt</span><span class="sxs-lookup"><span data-stu-id="dd41e-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="dd41e-103">Wenn Sie einen <xref:System.AsyncCallback>-Delegaten zur Verarbeitung der Ergebnisse des asynchronen Vorgangs in einem separaten Thread verwenden, können Sie mithilfe eines Statusobjekts Informationen zwischen den Rückrufen übergeben und ein Endergebnis abrufen.</span><span class="sxs-lookup"><span data-stu-id="dd41e-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="dd41e-104">In diesem Thema wird diese Vorgehensweise durch eingehendere Erläuterung des Beispiels unter [Verwenden eines AsyncCallback-Delegaten zum Beenden eines asynchronen Vorgangs](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dd41e-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd41e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd41e-105">Example</span></span>  
 <span data-ttu-id="dd41e-106">Das folgende Codebeispiel demonstriert die Verwendung von asynchronen Methoden in der <xref:System.Net.Dns>-Klasse, um Informationen aus dem Domain Name System (DNS) für benutzerspezifische Computer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="dd41e-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="dd41e-107">In diesem Beispiel wird die `HostRequest`-Klasse zum Speichern von Statusinformationen definiert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd41e-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="dd41e-108">Für jeden vom Benutzer eingegebenen Computernamen wird ein `HostRequest`-Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="dd41e-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="dd41e-109">Dieses Objekt wird an die <xref:System.Net.Dns.BeginGetHostByName%2A>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="dd41e-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="dd41e-110">Bei Abschluss einer Anforderung wird die `ProcessDnsInformation`-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dd41e-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="dd41e-111">Das `HostRequest`-Objekt wird mithilfe der <xref:System.IAsyncResult.AsyncState%2A>-Eigenschaft abgerufen.</span><span class="sxs-lookup"><span data-stu-id="dd41e-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="dd41e-112">Die `ProcessDnsInformation`-Methode verwendet das `HostRequest`-Objekt, um die von der Anforderung zurückgegebene <xref:System.Net.IPHostEntry>-Klasse oder eine von der Anforderung ausgelöste <xref:System.Net.Sockets.SocketException>-Klasse zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dd41e-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="dd41e-113">Wenn alle Anforderungen abgeschlossen sind, durchläuft die Anwendung die `HostRequest`-Objekte und zeigt die DNS-Informationen oder die Fehlermeldung <xref:System.Net.Sockets.SocketException> an.</span><span class="sxs-lookup"><span data-stu-id="dd41e-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="dd41e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd41e-114">See Also</span></span>  
 [<span data-ttu-id="dd41e-115">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="dd41e-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="dd41e-116">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="dd41e-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="dd41e-117">Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation</span><span class="sxs-lookup"><span data-stu-id="dd41e-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
