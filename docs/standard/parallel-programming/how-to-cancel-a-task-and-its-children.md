---
title: 'Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 4e0e783a4dfe3bf3a55795d7baef461369d7405a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134208"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="9f5ff-102">Vorgehensweise: Abbrechen einer Aufgabe und ihrer untergeordneten Elemente</span><span class="sxs-lookup"><span data-stu-id="9f5ff-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="9f5ff-103">In diesen Beispielen wird gezeigt, wie Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="9f5ff-103">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="9f5ff-104">Erstellen und Starten einer abbrechbare Aufgabe</span><span class="sxs-lookup"><span data-stu-id="9f5ff-104">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="9f5ff-105">Übergeben eines Abbruchtokens an den Benutzerdelegaten und optional an die Aufgabeninstanz</span><span class="sxs-lookup"><span data-stu-id="9f5ff-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="9f5ff-106">Erkennen der Abbruchanforderung im Benutzerdelegaten und Reagieren auf diese</span><span class="sxs-lookup"><span data-stu-id="9f5ff-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="9f5ff-107">Hinzufügen eines optionalen Hinweises, dass die Aufgabe abgebrochen wurde, zum aufrufenden Thread</span><span class="sxs-lookup"><span data-stu-id="9f5ff-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="9f5ff-108">Der aufrufende Thread erzwingt nicht die Beendigung der Aufgabe, er kennzeichnet nur, dass der Abbruch angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="9f5ff-109">Wenn die Aufgabe bereits ausgeführt wird, muss der Benutzerdelegat die Anforderung erkennen und entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="9f5ff-110">Wenn der Abbruch vor Auführung der Aufgabe angefordert wird, wird der Benutzerdelegat nicht ausgeführt; und das Aufgabenobjekt geht in den abgebrochenen Zustand über.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f5ff-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f5ff-111">Example</span></span>  
 <span data-ttu-id="9f5ff-112">In diesem Beispiel wird gezeigt, wie Sie <xref:System.Threading.Tasks.Task> und die zugehörigen untergeordneten Elemente als Reaktion auf eine Abbruchanforderung beenden.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="9f5ff-113">Darüber hinaus wird gezeigt, dass beim Beenden eines Benutzerdelegaten durch eine <xref:System.Threading.Tasks.TaskCanceledException> der aufrufende Thread optional die <xref:System.Threading.Tasks.Task.Wait%2A>-Methode oder <xref:System.Threading.Tasks.Task.WaitAll%2A>-Methode verwenden kann, um auf das Ende der Aufgaben zu warten.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="9f5ff-114">In diesem Fall müssen Sie einen `try/catch`-Block verwenden, um die Ausnahmen im aufrufenden Thread zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="9f5ff-115">Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Klasse ist vollständig in das Abbruchmodell integriert, das auf dem <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>-Typ und dem <xref:System.Threading.CancellationToken?displayProperty=nameWithType>-Typ basiert.</span><span class="sxs-lookup"><span data-stu-id="9f5ff-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="9f5ff-116">Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) und [Aufgabenabbruch](../../../docs/standard/parallel-programming/task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="9f5ff-116">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) and [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5ff-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f5ff-117">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="9f5ff-118">Aufgabenbasierte asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="9f5ff-118">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [<span data-ttu-id="9f5ff-119">Angefügte und getrennte untergeordnete Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9f5ff-119">Attached and Detached Child Tasks</span></span>](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)
- [<span data-ttu-id="9f5ff-120">Lambdaausdrücke in PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="9f5ff-120">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
