---
title: Asynchrone Programmierung mithilfe von Delegaten
ms.date: 03/30/2017
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: 01cdf5acf8f64472c218f35a0b8095aebf8f4571
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716264"
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="c79a9-102">Asynchrone Programmierung mithilfe von Delegaten</span><span class="sxs-lookup"><span data-stu-id="c79a9-102">Asynchronous Programming Using Delegates</span></span>

<span data-ttu-id="c79a9-103">Delegaten bieten die Möglichkeit, synchrone Methoden in asynchroner Weise aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c79a9-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="c79a9-104">Wenn ein Delegat synchron aufgerufen wird, ruft die `Invoke`-Methode die Zielmethode direkt im aktuellen Thread auf.</span><span class="sxs-lookup"><span data-stu-id="c79a9-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="c79a9-105">Wird die `BeginInvoke`-Methode aufgerufen, fügt die Common Language Runtime (CLR) die Anforderung in die Warteschlange ein und kehrt sofort zum Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="c79a9-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="c79a9-106">Die Zielmethode wird in einem Thread asynchron aus dem Threadpool aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c79a9-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="c79a9-107">Der ursprüngliche Thread, der die Anforderung gesendet hat, kann weiterhin parallel zur Zielmethode ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c79a9-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="c79a9-108">Wenn im Aufruf der `BeginInvoke`-Methode eine Rückrufmethode angegeben war, wird die Rückrufmethode aufgerufen, wenn die Zielmethode beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c79a9-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="c79a9-109">In der Rückrufmethode ruft die `EndInvoke`-Methode den Rückgabewert und alle Eingabe-/Ausgabe- oder reinen Ausgabeparameter ab.</span><span class="sxs-lookup"><span data-stu-id="c79a9-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="c79a9-110">Ist beim Aufrufen von `BeginInvoke` keine Rückrufmethode angegeben, kann `EndInvoke` aus dem Thread aufgerufen werden, der `BeginInvoke` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="c79a9-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c79a9-111">Compiler sollten Delegatklassen mit den Methoden `Invoke`, `BeginInvoke` und `EndInvoke` ausgeben und dabei die vom Benutzer angegebene Delegatsignatur verwenden.</span><span class="sxs-lookup"><span data-stu-id="c79a9-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="c79a9-112">Die Methoden `BeginInvoke` und `EndInvoke` sollten als systemeigen dekoriert werden.</span><span class="sxs-lookup"><span data-stu-id="c79a9-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="c79a9-113">Da diese Methoden als systemeigene Methoden gekennzeichnet sind, stellt die CLR die Implementierung automatisch zur Klassenladezeit bereit.</span><span class="sxs-lookup"><span data-stu-id="c79a9-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="c79a9-114">Das Ladeprogramm stellt sicher, dass die Methoden nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="c79a9-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c79a9-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c79a9-115">In This Section</span></span>  

 [<span data-ttu-id="c79a9-116">Asynchrones Aufrufen von synchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="c79a9-116">Calling Synchronous Methods Asynchronously</span></span>](calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="c79a9-117">Erläutert die Verwendung von Delegaten zum asynchronen Aufrufen normaler Methoden und bietet einfache Codebeispiele, in denen die vier Möglichkeiten zum Warten auf die Rückgabe asynchroner Aufrufe gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c79a9-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c79a9-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c79a9-118">Related Sections</span></span>  

 [<span data-ttu-id="c79a9-119">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="c79a9-119">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="c79a9-120">Beschreibt die asynchrone Programmierung in .NET</span><span class="sxs-lookup"><span data-stu-id="c79a9-120">Describes asynchronous programming in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79a9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c79a9-121">See also</span></span>

- <xref:System.Delegate>
