---
title: 'Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait'
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="817c2-102">Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait</span><span class="sxs-lookup"><span data-stu-id="817c2-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="817c2-103">Das folgende Beispiel zeigt, wie Sie eine <xref:System.Threading.SpinWait?displayProperty=nameWithType> Objekt implementiert einen zweiphasigen Wartevorgang.</span><span class="sxs-lookup"><span data-stu-id="817c2-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="817c2-104">In der ersten Phase werden die Synchronisierungsobjekt eine `Latch`, für einige Zyklen Spinvorgänge, während er überprüft, ob die Sperre verfügbar geworden ist.</span><span class="sxs-lookup"><span data-stu-id="817c2-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="817c2-105">In der zweiten Phase, wenn die Sperre verfügbar ist, wird die `Wait` Methodenrückgabe ohne Verwendung der <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> warten; ausführen, andernfalls `Wait` den Wartevorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="817c2-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="817c2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="817c2-106">Example</span></span>  
 <span data-ttu-id="817c2-107">Dieses Beispiel zeigt eine sehr grundlegende Implementierung einer Latch Synchronisierung primitive.</span><span class="sxs-lookup"><span data-stu-id="817c2-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="817c2-108">Sie können diese Datenstruktur verwenden, wenn die Wartezeiten voraussichtlich sehr kurz sind.</span><span class="sxs-lookup"><span data-stu-id="817c2-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="817c2-109">In diesem Beispiel wird nur zu Demonstrationszwecken.</span><span class="sxs-lookup"><span data-stu-id="817c2-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="817c2-110">Wenn Sie in Ihrem Programm Latch-Funktionalität benötigen, erwägen Sie <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="817c2-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="817c2-111">Der Latch verwendet die <xref:System.Threading.SpinWait> Objekt nur bis zum nächsten Aufruf von festliegen installiertem `SpinOnce` bewirkt, dass die <xref:System.Threading.SpinWait> die Zeitscheibe des Threads bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="817c2-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="817c2-112">An diesem Punkt wird der Latch bewirkt, dass einen eigene Kontextwechsel durch Aufrufen von <xref:System.Threading.WaitHandle.WaitOne%2A> auf die <xref:System.Threading.ManualResetEvent> und im weiteren Verlauf des Timeoutwerts übergeben.</span><span class="sxs-lookup"><span data-stu-id="817c2-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="817c2-113">Die Protokollausgabe wird gezeigt, wie oft der Latch Leistung zu erhöhen, indem Sie ohne die Sperre konnte die <xref:System.Threading.ManualResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="817c2-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817c2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="817c2-114">See Also</span></span>  
 [<span data-ttu-id="817c2-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="817c2-115">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="817c2-116">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="817c2-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
