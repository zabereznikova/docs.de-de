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
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e83505a36252457d286bc7fbc6bbe442732229a4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="spinlock"></a><span data-ttu-id="bea5e-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="bea5e-102">SpinLock</span></span>
<span data-ttu-id="bea5e-103">Die <xref:System.Threading.SpinLock>-Struktur ist eine Synchronisierungsprimitive auf niedriger Ebene mit gegenseitigem Ausschluss, die die Schleife durchläuft, während sie darauf wartet, eine Sperre abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bea5e-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="bea5e-104">Wenn Wartezeiten auf Mehrkerncomputern kurz und Konflikte minimal sein sollen, bietet <xref:System.Threading.SpinLock> einen Leistungsvorteil gegenüber anderen Arten von Sperren.</span><span class="sxs-lookup"><span data-stu-id="bea5e-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="bea5e-105">Sie sollten <xref:System.Threading.SpinLock> jedoch nur verwenden, wenn Sie durch Profilerstellung bestimmen, dass die <xref:System.Threading.Monitor?displayProperty=nameWithType>- oder <xref:System.Threading.Interlocked>-Methode die Leistung des Programms erheblich beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="bea5e-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="bea5e-106"><xref:System.Threading.SpinLock> könnte das Zeitsegment des Threads selbst dann erzeugen, wenn die Sperre noch nicht abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="bea5e-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="bea5e-107">Dies soll eine Umkehrung der Threadpriorität vermeiden und den Fortschritt des Garbage Collectors aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bea5e-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="bea5e-108">Stellen Sie bei Verwendung von <xref:System.Threading.SpinLock> sicher, dass kein Thread die Sperre für mehr als einen sehr kurzen Zeitraum aufrechterhalten kann, und dass kein Thread blockieren kann, während er die Sperre aufrechterhält.</span><span class="sxs-lookup"><span data-stu-id="bea5e-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="bea5e-109">Da SpinLock ein Werttyp ist, müssen Sie SpinLock explizit als Verweis übergeben, wenn die beiden Kopien auf die gleiche Sperre verweisen sollen.</span><span class="sxs-lookup"><span data-stu-id="bea5e-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="bea5e-110">Weitere Informationen zum Verwenden dieses Typs finden Sie unter <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bea5e-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bea5e-111">Ein Beispiel finden Sie unter [Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="bea5e-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="bea5e-112"><xref:System.Threading.SpinLock> unterstützt einen *Thread*-*Nachverfolgungsmodus*, mit dem Sie während der Entwicklungsphase den Thread nachverfolgen können, der die Sperre zu einem bestimmten Zeitpunkt aufrechterhält.</span><span class="sxs-lookup"><span data-stu-id="bea5e-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="bea5e-113">Der Thread-Nachverfolgungsmodus ist sehr nützlich für das Debuggen, aber Sie sollten ihn in der endgültigen Produktversion des Programms deaktivieren, da er die Leistung beeinträchtigen könnte.</span><span class="sxs-lookup"><span data-stu-id="bea5e-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="bea5e-114">Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="bea5e-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea5e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bea5e-115">See Also</span></span>  
 [<span data-ttu-id="bea5e-116">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="bea5e-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
