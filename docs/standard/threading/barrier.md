---
title: Barriere (.NET Framework)
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
helpviewer_keywords: synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a8111cc9f2798ff96be8b128f22a75d21b441178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="barrier-net-framework"></a><span data-ttu-id="d6a21-102">Barriere (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="d6a21-102">Barrier (.NET Framework)</span></span>
<span data-ttu-id="d6a21-103">Ein *Barriere* ist eine benutzerdefinierte Synchronisierungsprimitive, die mehrere Threads ermöglicht (bekannt als *Teilnehmer*) in Phasen gleichzeitig an einem Algorithmus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d6a21-103">A *barrier* is a user-defined synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="d6a21-104">Jeder Teilnehmer wird ausgeführt, bis er den Barrierepunkt im Code erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="d6a21-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="d6a21-105">Die Barriere stellt das Ende einer Arbeitsphase dar.</span><span class="sxs-lookup"><span data-stu-id="d6a21-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="d6a21-106">Wenn ein Teilnehmer die Barriere erreicht hat, wird er blockiert, bis alle Teilnehmer dieselbe Barriere erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="d6a21-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="d6a21-107">Nachdem alle Teilnehmer die Barriere erreicht haben, können Sie eine Nachphasenaktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d6a21-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="d6a21-108">Diese Nachphasenaktion kann verwendet werden, um Aktionen über einen einzelnen Thread auszuführen, während alle anderen Threads weiterhin blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="d6a21-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="d6a21-109">Nachdem die Aktion ausgeführt wurde, wird die Blockierung aller Teilnehmer aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d6a21-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="d6a21-110">Der folgende Codeausschnitt zeigt ein grundlegendes Barrieremuster.</span><span class="sxs-lookup"><span data-stu-id="d6a21-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="d6a21-111">Ein vollständiges Beispiel finden Sie unter [Vorgehensweise: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="d6a21-111">For a complete example, see [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="d6a21-112">Hinzufügen und Entfernen von Teilnehmern</span><span class="sxs-lookup"><span data-stu-id="d6a21-112">Adding and Removing Participants</span></span>  
 <span data-ttu-id="d6a21-113">Wenn Sie eine <xref:System.Threading.Barrier>-Instanz erstellen, geben Sie die Anzahl von Teilnehmern an.</span><span class="sxs-lookup"><span data-stu-id="d6a21-113">When you create a <xref:System.Threading.Barrier>, specify the number of participants.</span></span> <span data-ttu-id="d6a21-114">Sie können auch jederzeit Teilnehmer dynamisch hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="d6a21-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="d6a21-115">Z. B. wenn ein Teilnehmer seinen Teil des Problems löst, Sie können das Ergebnis speichern, beenden die Ausführung auf, der thread, und rufen Sie <xref:System.Threading.Barrier.RemoveParticipant%2A> um die Anzahl der Teilnehmer die Barriere zu verringern.</span><span class="sxs-lookup"><span data-stu-id="d6a21-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="d6a21-116">Wenn Sie einen Teilnehmer hinzufügen, indem Sie <xref:System.Threading.Barrier.AddParticipant%2A> aufrufen, gibt der Rückgabewert die aktuelle Phasennummer an, die möglicherweise nützlich ist, um die Arbeit des neuen Teilnehmers zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d6a21-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="d6a21-117">Fehlerhafte Barrieren</span><span class="sxs-lookup"><span data-stu-id="d6a21-117">Broken Barriers</span></span>  
 <span data-ttu-id="d6a21-118">Deadlocks können auftreten, wenn ein Teilnehmer die Barriere nicht erreicht.</span><span class="sxs-lookup"><span data-stu-id="d6a21-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="d6a21-119">Um diese Deadlocks zu vermeiden, verwenden Sie die Überladungen der <xref:System.Threading.Barrier.SignalAndWait%2A>-Methode, um ein Timeout und ein Abbruchtoken anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6a21-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="d6a21-120">Diese Überladungen geben einen booleschen Wert zurück, den jeder Teilnehmer überprüfen kann, bevor er zur nächsten Phase springt.</span><span class="sxs-lookup"><span data-stu-id="d6a21-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="d6a21-121">Nachphasenausnahmen</span><span class="sxs-lookup"><span data-stu-id="d6a21-121">Post-Phase Exceptions</span></span>  
 <span data-ttu-id="d6a21-122">Wenn der Nachphasendelegat eine Ausnahme auslöst, wird diese in ein <xref:System.Threading.BarrierPostPhaseException>-Objekt eingeschlossen, das dann an alle Teilnehmer verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="d6a21-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="d6a21-123">Barriere und ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="d6a21-123">Barrier Versus ContinueWhenAll</span></span>  
 <span data-ttu-id="d6a21-124">Barrieren sind besonders nützlich, wenn die Threads mehrere Phasen in Schleifen ausführen.</span><span class="sxs-lookup"><span data-stu-id="d6a21-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="d6a21-125">Wenn Ihr Code nur eine oder zwei Arbeitsphasen erfordert, sollten Sie in Betracht ziehen, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>-Objekte mit einer beliebigen Art von implizitem Join zu verwenden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="d6a21-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 <span data-ttu-id="d6a21-126">Weitere Informationen finden Sie unter [Verketten von Aufgaben mithilfe von Fortsetzungsaufgaben](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="d6a21-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6a21-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6a21-127">See Also</span></span>  
 [<span data-ttu-id="d6a21-128">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="d6a21-128">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="d6a21-129">Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere</span><span class="sxs-lookup"><span data-stu-id="d6a21-129">How to: Synchronize Concurrent Operations with a Barrier</span></span>](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
