---
title: 'Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock'
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="51218-102">Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock</span><span class="sxs-lookup"><span data-stu-id="51218-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="51218-103">Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="51218-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51218-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51218-104">Example</span></span>  
 <span data-ttu-id="51218-105">In diesem Beispiel der kritische Abschnitt führt eine minimale Menge an Arbeit, wodurch einen guten Kandidat für eine <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="51218-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="51218-106">Erhöhen die Arbeit eine kleine Menge verbessert die Leistung von der <xref:System.Threading.SpinLock> im Vergleich zu standard-Sperre.</span><span class="sxs-lookup"><span data-stu-id="51218-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="51218-107">Ab einem bestimmten Punkt wird ein SpinLock jedoch aufwändiger als eine Standardsperre.</span><span class="sxs-lookup"><span data-stu-id="51218-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="51218-108">Mit der neuen Parallelitätsprofilerstellungsfunktion in den Profilerstellungstools können Sie feststellen, welcher Sperrentyp in Ihrem Programm die bessere Leistung bietet.</span><span class="sxs-lookup"><span data-stu-id="51218-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="51218-109">Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="51218-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="51218-110"><xref:System.Threading.SpinLock>kann nützlich sein, wenn eine Sperre für eine freigegebene Ressource ist nicht für aufrechterhalten werden als sehr lange.</span><span class="sxs-lookup"><span data-stu-id="51218-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="51218-111">In solchen Fällen wird auf Multikerncomputern möglicherweise ein effizientes Verhalten erzielt, wenn der blockierte Thread einige Spinzyklen ausführt, bis die Sperre aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="51218-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="51218-112">Durch die Spinzyklen wird der Thread nicht blockiert, was zu einer hohen CPU-Auslastung führt.</span><span class="sxs-lookup"><span data-stu-id="51218-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="51218-113"><xref:System.Threading.SpinLock>wird unter bestimmten Bedingungen auf der logischen Prozessoren oder die Umkehrung der Priorität auf Systemen mit Hyperthreading gewissen stoppt.</span><span class="sxs-lookup"><span data-stu-id="51218-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="51218-114">Dieses Beispiel verwendet die <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> -Klasse, die benutzersynchronisierung für Multithreadzugriff erfordert.</span><span class="sxs-lookup"><span data-stu-id="51218-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="51218-115">In Anwendungen, die auf .NET Framework, Version 4 abzielen, eine andere Möglichkeit ist die Verwendung der <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, dem alle Benutzersperren nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="51218-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="51218-116">Beachten Sie die Verwendung von `false` (`False` in Visual Basic) im Aufruf von <xref:System.Threading.SpinLock.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="51218-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="51218-117">Dieser Ansatz bietet die beste Leistung.</span><span class="sxs-lookup"><span data-stu-id="51218-117">This provides the best performance.</span></span> <span data-ttu-id="51218-118">Geben Sie bei IA64-Architekturen `true` (`True`) an, um die Arbeitsspeicherumgrenzung zu verwenden. Dadurch werden die Schreibpuffer geleert, um sicherzustellen, dass die Sperre jetzt verfügbar ist und andere Threads beendet werden können.</span><span class="sxs-lookup"><span data-stu-id="51218-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51218-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51218-119">See Also</span></span>  
 [<span data-ttu-id="51218-120">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="51218-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
