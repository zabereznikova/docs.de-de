---
title: Asynchrone Programmierung mithilfe von Delegaten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e84c004c8efc58c6d6ad55674470bec13fc0bab8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="f3472-102">Asynchrone Programmierung mithilfe von Delegaten</span><span class="sxs-lookup"><span data-stu-id="f3472-102">Asynchronous Programming Using Delegates</span></span>
<span data-ttu-id="f3472-103">Delegaten bieten die Möglichkeit, synchrone Methoden in asynchroner Weise aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f3472-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="f3472-104">Wenn ein Delegat synchron aufgerufen wird, ruft die `Invoke`-Methode die Zielmethode direkt im aktuellen Thread auf.</span><span class="sxs-lookup"><span data-stu-id="f3472-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="f3472-105">Wird die `BeginInvoke`-Methode aufgerufen, fügt die Common Language Runtime (CLR) die Anforderung in die Warteschlange ein und kehrt sofort zum Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="f3472-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="f3472-106">Die Zielmethode wird in einem Thread asynchron aus dem Threadpool aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f3472-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="f3472-107">Der ursprüngliche Thread, der die Anforderung gesendet hat, kann weiterhin parallel zur Zielmethode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3472-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="f3472-108">Wenn im Aufruf der `BeginInvoke`-Methode eine Rückrufmethode angegeben war, wird die Rückrufmethode aufgerufen, wenn die Zielmethode beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f3472-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="f3472-109">In der Rückrufmethode ruft die `EndInvoke`-Methode den Rückgabewert und alle Eingabe-/Ausgabe- oder reinen Ausgabeparameter ab.</span><span class="sxs-lookup"><span data-stu-id="f3472-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="f3472-110">Ist beim Aufrufen von `BeginInvoke` keine Rückrufmethode angegeben, kann `EndInvoke` aus dem Thread aufgerufen werden, der `BeginInvoke` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f3472-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f3472-111">Compiler sollten Delegatklassen mit den Methoden `Invoke`, `BeginInvoke` und `EndInvoke` ausgeben und dabei die vom Benutzer angegebene Delegatsignatur verwenden.</span><span class="sxs-lookup"><span data-stu-id="f3472-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="f3472-112">Die Methoden `BeginInvoke` und `EndInvoke` sollten als systemeigen dekoriert werden.</span><span class="sxs-lookup"><span data-stu-id="f3472-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="f3472-113">Da diese Methoden als systemeigene Methoden gekennzeichnet sind, stellt die CLR die Implementierung automatisch zur Klassenladezeit bereit.</span><span class="sxs-lookup"><span data-stu-id="f3472-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="f3472-114">Das Ladeprogramm stellt sicher, dass die Methoden nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f3472-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3472-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f3472-115">In This Section</span></span>  
 [<span data-ttu-id="f3472-116">Asynchrones Aufrufen von synchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="f3472-116">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="f3472-117">Erläutert die Verwendung von Delegaten zum asynchronen Aufrufen normaler Methoden und bietet einfache Codebeispiele, in denen die vier Möglichkeiten zum Warten auf die Rückgabe asynchroner Aufrufe gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f3472-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f3472-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f3472-118">Related Sections</span></span>  
 [<span data-ttu-id="f3472-119">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="f3472-119">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="f3472-120">Beschreibt asynchrone Programmierung mit .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3472-120">Describes asynchronous programming with the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3472-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3472-121">See Also</span></span>  
 <xref:System.Delegate>
