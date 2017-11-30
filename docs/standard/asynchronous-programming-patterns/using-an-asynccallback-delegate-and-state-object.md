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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="f2084-102">Verwenden von AsyncCallback-Delegat und Zustandsobjekt</span><span class="sxs-lookup"><span data-stu-id="f2084-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="f2084-103">Bei Verwendung einer <xref:System.AsyncCallback> delegieren, um die Ergebnisse des asynchronen Vorgangs in einem separaten Thread zu verarbeiten, können Sie ein Zustandsobjekt verwenden, um Informationen zwischen den Rückrufen zu übergeben und einem Endergebnis abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f2084-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="f2084-104">In diesem Thema veranschaulicht, die sich durch erweitern das Beispiel in [Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="f2084-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2084-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f2084-105">Example</span></span>  
 <span data-ttu-id="f2084-106">Das folgende Codebeispiel veranschaulicht die Verwendung asynchroner Methoden in der <xref:System.Net.Dns> Klasse Domain Name System (DNS) für den Benutzer angegebenen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f2084-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="f2084-107">In diesem Beispiel definiert und verwendet die `HostRequest` Klasse zum Speichern von Zustandsinformationen.</span><span class="sxs-lookup"><span data-stu-id="f2084-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="f2084-108">Ein `HostRequest` Objekt ruft für jeden vom Benutzer eingegebenen Computernamen erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2084-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="f2084-109">Dieses Objekt wird zum Übergeben der <xref:System.Net.Dns.BeginGetHostByName%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f2084-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="f2084-110">Die `ProcessDnsInformation` aufgerufen wird jedes Mal eine Anforderung abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f2084-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="f2084-111">Die `HostRequest` Objekt abgerufen wird, mit der <xref:System.IAsyncResult.AsyncState%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f2084-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="f2084-112">Die `ProcessDnsInformation` -Methode verwendet die `HostRequest` Objekt zum Speichern der <xref:System.Net.IPHostEntry> von der Anforderung zurückgegebenen oder eine <xref:System.Net.Sockets.SocketException> , die von der Anforderung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f2084-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="f2084-113">Wenn alle Anforderungen abgeschlossen sind, die Anwendung führt eine Iteration durch die `HostRequest` Objekten und zeigt die DNS-Informationen oder <xref:System.Net.Sockets.SocketException> Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="f2084-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="f2084-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2084-114">See Also</span></span>  
 [<span data-ttu-id="f2084-115">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="f2084-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="f2084-116">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="f2084-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="f2084-117">Verwenden eines AsyncCallback-Delegaten zum Beenden einer asynchronen Operation</span><span class="sxs-lookup"><span data-stu-id="f2084-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
