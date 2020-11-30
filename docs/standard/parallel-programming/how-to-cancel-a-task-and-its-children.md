---
title: 'Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente'
description: Erfahren Sie, wie Sie Tasks und deren untergeordnete Elemente in .NET abbrechen. In den gezeigten Beispielen werden die Schritte von der Erstellung eines abbrechbaren Tasks bis hin zur Benachrichtigung über den Abbruch des Tasks beschrieben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 82a71faf3a2390f5bb36dd896cf865f773f54bd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713222"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="b30cb-104">Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente</span><span class="sxs-lookup"><span data-stu-id="b30cb-104">How to: Cancel a Task and Its Children</span></span>

<span data-ttu-id="b30cb-105">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="b30cb-105">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="b30cb-106">Erstellen und Starten einer abbrechbare Aufgabe</span><span class="sxs-lookup"><span data-stu-id="b30cb-106">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="b30cb-107">Übergeben eines Abbruchtokens an den Benutzerdelegaten und optional an die Aufgabeninstanz</span><span class="sxs-lookup"><span data-stu-id="b30cb-107">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="b30cb-108">Erkennen der Abbruchanforderung im Benutzerdelegaten und Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="b30cb-108">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="b30cb-109">Hinzufügen eines optionalen Hinweises, dass die Aufgabe abgebrochen wurde, zum aufrufenden Thread</span><span class="sxs-lookup"><span data-stu-id="b30cb-109">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="b30cb-110">Der aufrufende Thread erzwingt nicht die Beendigung der Aufgabe, er kennzeichnet nur, dass der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="b30cb-110">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="b30cb-111">Wenn die Aufgabe bereits ausgeführt wird, muss der Benutzerdelegat die Anforderung erkennen und entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="b30cb-111">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="b30cb-112">Wenn der Abbruch vor Auführung der Aufgabe angefordert wird, wird der Benutzerdelegat nicht ausgeführt; und das Aufgabenobjekt geht in den abgebrochenen Zustand über.</span><span class="sxs-lookup"><span data-stu-id="b30cb-112">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b30cb-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b30cb-113">Example</span></span>  

 <span data-ttu-id="b30cb-114">In diesem Beispiel wird gezeigt, wie Sie <xref:System.Threading.Tasks.Task> und die zugehörigen untergeordneten Elemente als Reaktion auf eine Abbruchanforderung beenden.</span><span class="sxs-lookup"><span data-stu-id="b30cb-114">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="b30cb-115">Darüber hinaus wird gezeigt, dass beim Beenden eines Benutzerdelegaten durch eine <xref:System.Threading.Tasks.TaskCanceledException> der aufrufende Thread optional die <xref:System.Threading.Tasks.Task.Wait%2A>-Methode oder <xref:System.Threading.Tasks.Task.WaitAll%2A>-Methode verwenden kann, um auf das Ende der Aufgaben zu warten.</span><span class="sxs-lookup"><span data-stu-id="b30cb-115">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="b30cb-116">In diesem Fall müssen Sie einen `try/catch`-Block verwenden, um die Ausnahmen im aufrufenden Thread zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b30cb-116">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="b30cb-117">Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse ist vollständig in das Abbruchmodell integriert, das auf dem <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>-Typ und dem <xref:System.Threading.CancellationToken?displayProperty=nameWithType>-Typ basiert.</span><span class="sxs-lookup"><span data-stu-id="b30cb-117">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="b30cb-118">Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../threading/cancellation-in-managed-threads.md) und [Aufgabenabbruch](task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="b30cb-118">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30cb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b30cb-119">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="b30cb-120">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="b30cb-120">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="b30cb-121">Angefügte und getrennte untergeordnete Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b30cb-121">Attached and Detached Child Tasks</span></span>](attached-and-detached-child-tasks.md)
- [<span data-ttu-id="b30cb-122">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="b30cb-122">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
