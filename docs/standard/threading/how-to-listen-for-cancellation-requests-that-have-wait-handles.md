---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
ms.openlocfilehash: e44b10b88bef61edcf3f547f56b4020740530e26
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279542"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="d98ad-102">Gewusst wie: Lauschen auf Abbruchanforderungen mit Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="d98ad-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="d98ad-103">Wenn eine Methode blockiert wird, während sie auf die Signalisierung eines Ereignisses wartet, kann sie nicht den Wert des Abbruchtokens überprüfen und rechtzeitig reagieren.</span><span class="sxs-lookup"><span data-stu-id="d98ad-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="d98ad-104">Im ersten Beispiel wird gezeigt, wie Sie dieses Problem beheben, wenn Sie mit Ereignissen wie z. B. <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> arbeiten, die das einheitliche Abbruchframework nicht nativ unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d98ad-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="d98ad-105">Das zweite Beispiel zeigt einen einfacheren Ansatz, der <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> verwendet, was den Abbruch unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d98ad-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d98ad-106">Wenn "Nur eigenen Code" aktiviert ist, unterbricht Visual Studio die Ausführung in einigen Fällen in der Zeile, die die Ausnahme auslöst, und eine Fehlermeldung zu einer nicht vom Benutzercode behandelten Ausnahme wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d98ad-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="d98ad-107">Dieser Fehler hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d98ad-107">This error is benign.</span></span> <span data-ttu-id="d98ad-108">Sie können F5 drücken, um den Vorgang fortzusetzen. In diesem Fall wird das in den nachstehenden Beispielen veranschaulichte Ausnahmebehandlungsverhalten angewendet.</span><span class="sxs-lookup"><span data-stu-id="d98ad-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="d98ad-109">Um zu verhindern, dass Visual Studio die Ausführung beim ersten Fehler unterbricht, deaktivieren Sie unter **Extras, Optionen, Debugging, Allgemein** das Kontrollkästchen „Nur eigenen Code“.</span><span class="sxs-lookup"><span data-stu-id="d98ad-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d98ad-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d98ad-110">Example</span></span>  
 <span data-ttu-id="d98ad-111">Im folgenden Beispiel wird mit einem <xref:System.Threading.ManualResetEvent> veranschaulicht, wie Sie Wait-Handles entsperren, die keinen einheitlichen Abbruch unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d98ad-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="d98ad-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d98ad-112">Example</span></span>  
 <span data-ttu-id="d98ad-113">Im folgenden Beispiel wird mit einem <xref:System.Threading.ManualResetEventSlim> veranschaulicht, wie Sie Koordinationsprimitive entsperren, die keinen einheitlichen Abbruch unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d98ad-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="d98ad-114">Der gleiche Ansatz kann mit anderen einfachen Koordinationsprimitiven wie <xref:System.Threading.Semaphore>`Slim` und <xref:System.Threading.CountdownEvent> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d98ad-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="d98ad-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d98ad-115">See also</span></span>

- [<span data-ttu-id="d98ad-116">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="d98ad-116">Cancellation in Managed Threads</span></span>](cancellation-in-managed-threads.md)
