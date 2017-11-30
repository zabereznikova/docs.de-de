---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a><span data-ttu-id="e1941-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="e1941-102">SpinLock</span></span>
<span data-ttu-id="e1941-103">Die <xref:System.Threading.SpinLock> Struktur ist eine auf niedriger Ebene, die gegenseitigen Ausschluss Synchronisierungsprimitive, die stößt, während er darauf wartet, eine Sperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e1941-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="e1941-104">Auf Mehrkerncomputern Wartezeiten kurz, und wenn Konflikte minimal, ist zu erwarten sind <xref:System.Threading.SpinLock> bieten eine bessere Leistung als andere Arten von Sperren.</span><span class="sxs-lookup"><span data-stu-id="e1941-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="e1941-105">Wir empfehlen jedoch die Verwendung <xref:System.Threading.SpinLock> nur wenn Sie bestimmen, indem die profilerstellung, die die <xref:System.Threading.Monitor?displayProperty=nameWithType> Methode oder die <xref:System.Threading.Interlocked> Methoden sind erheblich verlangsamt die Leistung des Programms.</span><span class="sxs-lookup"><span data-stu-id="e1941-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="e1941-106"><xref:System.Threading.SpinLock>die Zeitscheibe des Threads kann erhalten, selbst wenn er noch nicht auf die Sperre abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="e1941-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="e1941-107">Dies geschieht Threadpriorität zu vermeiden und die Garbage collection Fortschritte zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1941-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="e1941-108">Bei Verwendung einer <xref:System.Threading.SpinLock>, stellen Sie sicher, dass kein Thread die Sperre für mehr als einen sehr kurzen Zeitraum aufnehmen kann, und kein Thread blockieren kann, während er die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="e1941-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="e1941-109">Da SpinLock ein Werttyp ist, müssen Sie explizit übergeben als Verweis, wenn Sie, die beiden Kopien zum Verweisen auf die gleiche Sperre beabsichtigen.</span><span class="sxs-lookup"><span data-stu-id="e1941-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="e1941-110">Weitere Informationen zur Verwendung dieses Typs finden Sie unter <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1941-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e1941-111">Ein Beispiel finden Sie unter [wie: Verwenden von SpinLock für die Synchronisierung auf niedriger Ebene](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e1941-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="e1941-112"><xref:System.Threading.SpinLock>unterstützt eine *Thread*-*nachverfolgen* Modus, in dem Sie verfolgen, den Thread, der die Sperre zu einem bestimmten Zeitpunkt während der Entwicklungsphase verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e1941-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="e1941-113">Modus zum Nachverfolgen von Threads ist sehr nützlich für das Debuggen, aber es wird empfohlen, dass Sie in der Releaseversion des Programms deaktivieren, da es die Leistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="e1941-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="e1941-114">Weitere Informationen finden Sie unter [How to: Enable Thread-Tracking-Modus in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="e1941-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1941-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1941-115">See Also</span></span>  
 [<span data-ttu-id="e1941-116">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="e1941-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
