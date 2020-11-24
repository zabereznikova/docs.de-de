---
title: 'Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 0a8ece86d71823eb78a9ebbec661722f0e249790
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819720"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a><span data-ttu-id="60503-102">Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait</span><span class="sxs-lookup"><span data-stu-id="60503-102">How to: Use SpinWait to Implement a Two-Phase Wait Operation</span></span>
<span data-ttu-id="60503-103">Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Objekt einen zweiphasigen Wartevorgang implementieren.</span><span class="sxs-lookup"><span data-stu-id="60503-103">The following example shows how to use a <xref:System.Threading.SpinWait?displayProperty=nameWithType> object to implement a two-phase wait operation.</span></span> <span data-ttu-id="60503-104">In der ersten Phase rotiert das Synchronisierungsobjekt, ein `Latch`, für einige Zyklen und überprüft dabei, ob die Sperre verfügbar geworden ist.</span><span class="sxs-lookup"><span data-stu-id="60503-104">In the first phase, the synchronization object, a `Latch`, spins for a few cycles while it checks whether the lock has become available.</span></span> <span data-ttu-id="60503-105">Wenn in der zweiten Phase die Sperre verfügbar wird, erfolgt die Rückgabe der `Wait`-Methode ohne Verwendung von <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> zur Ausführung des Wartevorgangs; andernfalls führt `Wait` den Wartevorgang aus.</span><span class="sxs-lookup"><span data-stu-id="60503-105">In the second phase, if the lock becomes available, then the `Wait` method returns without using the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> to perform its wait; otherwise, `Wait` performs the wait.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60503-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60503-106">Example</span></span>  
 <span data-ttu-id="60503-107">Dieses Beispiel zeigt eine sehr grundlegende Implementierung einer Latchsynchronisierungsprimitiven.</span><span class="sxs-lookup"><span data-stu-id="60503-107">This example shows a very basic implementation of a Latch synchronization primitive.</span></span> <span data-ttu-id="60503-108">Sie können diese Datenstruktur verwenden, wenn die Wartezeiten voraussichtlich sehr kurz sind.</span><span class="sxs-lookup"><span data-stu-id="60503-108">You can use this data structure when wait times are expected to be very short.</span></span> <span data-ttu-id="60503-109">Das Beispiel dient nur der Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="60503-109">This example is for demonstration purposes only.</span></span> <span data-ttu-id="60503-110">Wenn Sie in Ihrem Programm Latchfunktionalität benötigen, erwägen Sie die Verwendung von <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="60503-110">If you require latch-type functionality in your program, consider using <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 <span data-ttu-id="60503-111">Der Latch verwendet das <xref:System.Threading.SpinWait>-Objekt für Schleifendurchläufe, bis der nächste Aufruf von `SpinOnce` veranlasst, dass <xref:System.Threading.SpinWait> das Zeitsegment des Threads bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="60503-111">The latch uses the <xref:System.Threading.SpinWait> object to spin in place only until the next call to `SpinOnce` causes the <xref:System.Threading.SpinWait> to yield the time slice of the thread.</span></span> <span data-ttu-id="60503-112">An diesem Punkt bewirkt der Latch seinen eigenen Kontextwechsel durch Aufruf von <xref:System.Threading.WaitHandle.WaitOne%2A> in <xref:System.Threading.ManualResetEvent> und Übergabe des Rests des Timeoutwerts.</span><span class="sxs-lookup"><span data-stu-id="60503-112">At that point, the latch causes its own context switch by calling <xref:System.Threading.WaitHandle.WaitOne%2A> on the <xref:System.Threading.ManualResetEvent> and passing in the remainder of the time-out value.</span></span>  
  
 <span data-ttu-id="60503-113">Die Protokollausgabe zeigt, wie oft der Latch die Leistung durch Aktivieren der Sperre ohne Verwendung von <xref:System.Threading.ManualResetEvent> erhöhen konnte.</span><span class="sxs-lookup"><span data-stu-id="60503-113">The logging output shows how often the Latch was able to increase performance by acquiring the lock without using the <xref:System.Threading.ManualResetEvent>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60503-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60503-114">See also</span></span>

- [<span data-ttu-id="60503-115">SpinWait</span><span class="sxs-lookup"><span data-stu-id="60503-115">SpinWait</span></span>](spinwait.md)
- [<span data-ttu-id="60503-116">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="60503-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)
