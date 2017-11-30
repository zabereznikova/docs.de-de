---
title: 'Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf'
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="f61f3-102">Gewusst wie: Lauschen auf Abbruchanforderungen durch Abruf</span><span class="sxs-lookup"><span data-stu-id="f61f3-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="f61f3-103">Das folgende Beispiel zeigt eine Möglichkeit, die Benutzercode ein Abbruchtoken, das in regelmäßigen Abständen, um festzustellen, ob ein Abbruch angefordert wurde, von dem aufrufenden Thread abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f61f3-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="f61f3-104">Dieses Beispiel verwendet die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> aufweisen, aber das gleiche Muster gilt für asynchrone Vorgänge, die direkt über erstellt die <xref:System.Threading.ThreadPool?displayProperty=nameWithType> Typ oder die <xref:System.Threading.Thread?displayProperty=nameWithType> Typ.</span><span class="sxs-lookup"><span data-stu-id="f61f3-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f61f3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f61f3-105">Example</span></span>  
 <span data-ttu-id="f61f3-106">Abruf erfordert eine Art von Schleifen oder Rekursionen Code, der den Wert des booleschen Werts in regelmäßigen Abständen zu lesen, kann <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f61f3-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="f61f3-107">Bei Verwendung der <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> und Warten auf die Aufgabe im aufrufenden Thread abgeschlossen, können Sie mithilfe der <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> -Methode auf, überprüfen Sie die Eigenschaft und die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f61f3-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="f61f3-108">Mithilfe dieser Methode zu verwenden, stellen Sie sicher, dass die richtige Ausnahme, als Antwort auf eine Anforderung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f61f3-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="f61f3-109">Bei Verwendung einer <xref:System.Threading.Tasks.Task>, besser als manuell auszulösen ist beim Aufrufen dieser Methode eine <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="f61f3-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="f61f3-110">Wenn Sie keine Ausnahme auslösen, können Sie nur überprüfen Sie die Eigenschaft und von der Methode zurückgegeben wird, wenn die Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="f61f3-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="f61f3-111">Aufrufen von <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> ist äußerst schnell und führt bedeutenden Aufwand in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="f61f3-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="f61f3-112">Beim Aufrufen <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, Sie müssen nur explizit der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft, wenn Sie andere Vorgänge als Reaktion auf den Abbruch neben dem Auslösen der Ausnahme ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f61f3-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="f61f3-113">In diesem Beispiel sehen Sie, dass der Code tatsächlich zweimal auf die Eigenschaft zugreift: einmal in der expliziten Zugriff und erneut in die <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f61f3-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="f61f3-114">Da jedoch das Act des Lesens der <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> Eigenschaft nur eine flüchtige read-Anweisung pro Zugriff, die doppelte Zugriff ist nicht im Hinblick auf Leistung signifikant.</span><span class="sxs-lookup"><span data-stu-id="f61f3-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="f61f3-115">Dennoch ist es besser, manuell auslösen, sondern rufen Sie die Methode der <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="f61f3-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f61f3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f61f3-116">See Also</span></span>  
 [<span data-ttu-id="f61f3-117">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="f61f3-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
