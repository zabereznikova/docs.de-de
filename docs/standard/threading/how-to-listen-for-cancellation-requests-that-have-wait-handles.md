---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles'
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="0e05a-102">Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="0e05a-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="0e05a-103">Wenn eine Methode blockiert wird, während er auf ein Ereignis signalisiert wird, wartet, nicht den Wert des Abbruchtokens und rechtzeitig reagiert.</span><span class="sxs-lookup"><span data-stu-id="0e05a-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="0e05a-104">Im erste Beispiel wird gezeigt, wie dieses Problem behoben, wenn Sie mit Ereignissen wie z. B. arbeiten <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> , die das einheitliche Abbruchframework nicht systemeigen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0e05a-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="0e05a-105">Das zweite Beispiel zeigt einen einfacheren Ansatz, der verwendet <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, Abbruch unified der unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0e05a-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e05a-106">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e05a-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="0e05a-107">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="0e05a-107">This error is benign.</span></span> <span data-ttu-id="0e05a-108">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="0e05a-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="0e05a-109">Zum verhindern, dass Visual Studio den ersten Fehler unterbricht, deaktivieren Sie das Kontrollkästchen "Nur eigenen Code" unter **Extras, Optionen, Debugging, Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="0e05a-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e05a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e05a-110">Example</span></span>  
 <span data-ttu-id="0e05a-111">Im folgenden Beispiel wird eine <xref:System.Threading.ManualResetEvent> zu veranschaulichen, wie Sie die Blockierung von Wait-Handles, die keine einheitliche Abbruch unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0e05a-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="0e05a-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e05a-112">Example</span></span>  
 <span data-ttu-id="0e05a-113">Im folgenden Beispiel wird eine <xref:System.Threading.ManualResetEventSlim> veranschaulicht, wie Sie die Blockierung der Koordination unified Primitive, die unterstützen Abbruch.</span><span class="sxs-lookup"><span data-stu-id="0e05a-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="0e05a-114">Der gleiche Ansatz kann z. B. mit andere Primitive einfache Koordination verwendet werden <xref:System.Threading.Semaphore> `Slim` und <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="0e05a-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="0e05a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e05a-115">See Also</span></span>  
 [<span data-ttu-id="0e05a-116">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="0e05a-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
