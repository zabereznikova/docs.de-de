---
title: dangerousThreadingAPI-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
ms.openlocfilehash: d3fe7d11657c2f9edd1fea7ff639f878f993d6b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174770"
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="fa50e-102">dangerousThreadingAPI-MDA</span><span class="sxs-lookup"><span data-stu-id="fa50e-102">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="fa50e-103">Der `dangerousThreadingAPI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>-Methode für einen anderen Thread als den aktuellen Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fa50e-103">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fa50e-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="fa50e-104">Symptoms</span></span>  
 <span data-ttu-id="fa50e-105">Eine Anwendung reagiert nicht oder bleibt auf unbestimmte Zeit hängen.</span><span class="sxs-lookup"><span data-stu-id="fa50e-105">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="fa50e-106">Die System- oder Anwendungsdaten befinden sich vorübergehend oder selbst nach Herunterfahren der Anwendung in einem unvorhersehbaren Zustand.</span><span class="sxs-lookup"><span data-stu-id="fa50e-106">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="fa50e-107">Einige Vorgänge werden nicht wie erwartet abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fa50e-107">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="fa50e-108">Die Symptome sind aufgrund der Zufälligkeit dieses Problems breit gefächert.</span><span class="sxs-lookup"><span data-stu-id="fa50e-108">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fa50e-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="fa50e-109">Cause</span></span>  
 <span data-ttu-id="fa50e-110">Ein Thread wird von einem anderen Thread mit der <xref:System.Threading.Thread.Suspend%2A>-Methode asynchron angehalten.</span><span class="sxs-lookup"><span data-stu-id="fa50e-110">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="fa50e-111">Es gibt keine Möglichkeit festzustellen, wann ein anderer Thread sicher angehalten werden kann, der sich möglicherweise gerade mitten in einem Vorgang befindet.</span><span class="sxs-lookup"><span data-stu-id="fa50e-111">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="fa50e-112">Das Anhalten eines Threads kann zur Beschädigung von Daten oder Invarianten führen.</span><span class="sxs-lookup"><span data-stu-id="fa50e-112">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="fa50e-113">Befindet sich ein Thread in angehaltenem Zustand und wird nicht mit der <xref:System.Threading.Thread.Resume%2A>-Methode fortgesetzt, kann die Anwendung auf unbestimmte Zeit hängen bleiben und Anwendungsdaten beschädigen.</span><span class="sxs-lookup"><span data-stu-id="fa50e-113">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="fa50e-114">Diese Methoden wurden als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="fa50e-114">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="fa50e-115">Für den Zielthread reservierte Synchronisierungsprimitiven bleiben während der Unterbrechung reserviert.</span><span class="sxs-lookup"><span data-stu-id="fa50e-115">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="fa50e-116">Dies kann zu Deadlocks führen, sollte ein anderer Thread versuchen, die Primitive zu sperren (z.B. der Thread, der <xref:System.Threading.Thread.Suspend%2A> ausführt).</span><span class="sxs-lookup"><span data-stu-id="fa50e-116">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="fa50e-117">In diesem Fall wird das Problem als Deadlock sichtbar.</span><span class="sxs-lookup"><span data-stu-id="fa50e-117">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fa50e-118">Lösung</span><span class="sxs-lookup"><span data-stu-id="fa50e-118">Resolution</span></span>  
 <span data-ttu-id="fa50e-119">Vermeiden Sie Entwürfe, die die Verwendung von <xref:System.Threading.Thread.Suspend%2A> und <xref:System.Threading.Thread.Resume%2A> erfordern.</span><span class="sxs-lookup"><span data-stu-id="fa50e-119">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="fa50e-120">Verwenden Sie für die Zusammenarbeit zwischen Threads Synchronisierungsprimitiven wie beispielsweise <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> oder die C#-Anweisung `lock`.</span><span class="sxs-lookup"><span data-stu-id="fa50e-120">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="fa50e-121">Wenn Sie diese Methoden verwenden müssen, verringern Sie das Zeitfenster, und minimieren Sie die Codemenge, die ausgeführt wird, während sich der Thread in angehaltenem Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="fa50e-121">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fa50e-122">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fa50e-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="fa50e-123">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="fa50e-123">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="fa50e-124">Es werden nur Angaben über problematische Threadoperationen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="fa50e-124">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fa50e-125">Output</span><span class="sxs-lookup"><span data-stu-id="fa50e-125">Output</span></span>  
 <span data-ttu-id="fa50e-126">Der MDA identifiziert die problematische Threadmethode, die zu seiner Aktivierung führte.</span><span class="sxs-lookup"><span data-stu-id="fa50e-126">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fa50e-127">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fa50e-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="fa50e-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa50e-128">Example</span></span>  
 <span data-ttu-id="fa50e-129">Das folgende Codebeispiel veranschaulicht einen Aufruf der <xref:System.Threading.Thread.Suspend%2A>-Methode, der zur Aktivierung des `dangerousThreadingAPI` führt.</span><span class="sxs-lookup"><span data-stu-id="fa50e-129">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa50e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa50e-130">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="fa50e-131">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="fa50e-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fa50e-132">lock-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa50e-132">lock Statement</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
