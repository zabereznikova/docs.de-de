---
title: Barriere
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138150"
---
# <a name="barrier"></a><span data-ttu-id="8b4a6-102">Barriere</span><span class="sxs-lookup"><span data-stu-id="8b4a6-102">Barrier</span></span>

<span data-ttu-id="8b4a6-103">Eine <xref:System.Threading.Barrier?displayProperty=nameWithType> ist eine Synchronisierungsprimitive, die es mehreren (als *Teilnehmer* bezeichneten) Threads ermöglicht, in Phasen gleichzeitig an einem Algorithmus zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-103">A <xref:System.Threading.Barrier?displayProperty=nameWithType> is a synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="8b4a6-104">Jeder Teilnehmer wird ausgeführt, bis er den Barrierepunkt im Code erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="8b4a6-105">Die Barriere stellt das Ende einer Arbeitsphase dar.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="8b4a6-106">Wenn ein Teilnehmer die Barriere erreicht hat, wird er blockiert, bis alle Teilnehmer dieselbe Barriere erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="8b4a6-107">Nachdem alle Teilnehmer die Barriere erreicht haben, können Sie eine Nachphasenaktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="8b4a6-108">Diese Nachphasenaktion kann verwendet werden, um Aktionen über einen einzelnen Thread auszuführen, während alle anderen Threads weiterhin blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="8b4a6-109">Nachdem die Aktion ausgeführt wurde, wird die Blockierung aller Teilnehmer aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="8b4a6-110">Der folgende Codeausschnitt zeigt ein grundlegendes Barrieremuster.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="8b4a6-111">Ein vollständiges Beispiel finden Sie unter [Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="8b4a6-111">For a complete example, see [How to: synchronize concurrent operations with a Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="8b4a6-112">Hinzufügen und Entfernen von Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="8b4a6-112">Adding and removing participants</span></span>

 <span data-ttu-id="8b4a6-113">Wenn Sie eine <xref:System.Threading.Barrier>-Instanz erstellen, geben Sie die Anzahl von Teilnehmern an.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-113">When you create a <xref:System.Threading.Barrier> instance, specify the number of participants.</span></span> <span data-ttu-id="8b4a6-114">Sie können auch jederzeit Teilnehmer dynamisch hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="8b4a6-115">Wenn ein Teilnehmer z.B. seinen Teil des Problems gelöst hat, können Sie das Ergebnis speichern, die Ausführung auf diesem Thread beenden und <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> aufrufen, um die Anzahl von Teilnehmern in der Barriere zu verringern.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="8b4a6-116">Wenn Sie einen Teilnehmer hinzufügen, indem Sie <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType> aufrufen, gibt der Rückgabewert die aktuelle Phasennummer an, die möglicherweise nützlich ist, um die Arbeit des neuen Teilnehmers zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="8b4a6-117">Fehlerhafte Barrieren</span><span class="sxs-lookup"><span data-stu-id="8b4a6-117">Broken barriers</span></span>

 <span data-ttu-id="8b4a6-118">Deadlocks können auftreten, wenn ein Teilnehmer die Barriere nicht erreicht.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="8b4a6-119">Um diese Deadlocks zu vermeiden, verwenden Sie die Überladungen der <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType>-Methode, um ein Timeout und ein Abbruchtoken anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="8b4a6-120">Diese Überladungen geben einen booleschen Wert zurück, den jeder Teilnehmer überprüfen kann, bevor er zur nächsten Phase springt.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="8b4a6-121">Nachphasenausnahmen</span><span class="sxs-lookup"><span data-stu-id="8b4a6-121">Post-phase exceptions</span></span>

 <span data-ttu-id="8b4a6-122">Wenn der Nachphasendelegat eine Ausnahme auslöst, wird diese in ein <xref:System.Threading.BarrierPostPhaseException>-Objekt eingeschlossen, das dann an alle Teilnehmer verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="8b4a6-123">Barriere und ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="8b4a6-123">Barrier versus ContinueWhenAll</span></span>

 <span data-ttu-id="8b4a6-124">Barrieren sind besonders nützlich, wenn die Threads mehrere Phasen in Schleifen ausführen.</span><span class="sxs-lookup"><span data-stu-id="8b4a6-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="8b4a6-125">Wenn Ihr Code nur eine oder zwei Arbeitsphasen erfordert, sollten Sie in Betracht ziehen, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekte mit einer beliebigen Art von implizitem Join zu verwenden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="8b4a6-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="8b4a6-126">Weitere Informationen finden Sie unter [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8b4a6-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4a6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b4a6-127">See also</span></span>

- [<span data-ttu-id="8b4a6-128">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="8b4a6-128">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="8b4a6-129">Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere</span><span class="sxs-lookup"><span data-stu-id="8b4a6-129">How to: synchronize concurrent operations with a Barrier</span></span>](how-to-synchronize-concurrent-operations-with-a-barrier.md)
