---
title: 'Gewusst wie: Registrieren von Rückrufen für Abbruchanforderungen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: 87ba1ab9ac095c733a53f766d00ebb7530a8d9c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137998"
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="2fff8-102">Gewusst wie: Registrieren von Rückrufen für Abbruchanforderungen</span><span class="sxs-lookup"><span data-stu-id="2fff8-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="2fff8-103">Im folgenden Beispiel wird gezeigt, wie Sie einen Delegaten registrieren, der aufgerufen wird, wenn eine <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>-Eigenschaft aufgrund eines Aufrufs von <xref:System.Threading.CancellationTokenSource.Cancel%2A> für das Objekt, das das Token erstellt hat, den Wert „true“ aufweist.</span><span class="sxs-lookup"><span data-stu-id="2fff8-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="2fff8-104">Verwenden Sie dieses Verfahren zum Abbrechen asynchroner Vorgänge, die das einheitliche Abbruchframework nicht systemeigen unterstützen, und für das Aufheben der Sperre von Methoden, die möglicherweise auf den Abschluss eines asynchronen Vorgangs warten.</span><span class="sxs-lookup"><span data-stu-id="2fff8-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fff8-105">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fff8-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="2fff8-106">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="2fff8-106">This error is benign.</span></span> <span data-ttu-id="2fff8-107">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="2fff8-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="2fff8-108">Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="2fff8-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fff8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fff8-109">Example</span></span>  
 <span data-ttu-id="2fff8-110">Im folgenden Beispiel wird die <xref:System.Net.WebClient.CancelAsync%2A>-Methode als aufzurufende Methode registriert, wenn durch das Abbruchtoken der Abbruch angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="2fff8-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="2fff8-111">Wenn der Abbruch zum Zeitpunkt der Rückrufregistrierung bereits angefordert wurde, wird der Rückruf trotzdem garantiert aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2fff8-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="2fff8-112">In diesem speziellen Fall bleibt die <xref:System.Net.WebClient.CancelAsync%2A>-Methode wirkungslos, wenn kein asynchroner Vorgang ausgeführt wird. Das Aufrufen der Methode ist daher immer sicher.</span><span class="sxs-lookup"><span data-stu-id="2fff8-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fff8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fff8-113">See also</span></span>

- [<span data-ttu-id="2fff8-114">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="2fff8-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
