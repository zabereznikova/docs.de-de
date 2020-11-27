---
title: dangerousThreadingAPI-MDA
description: Überprüfen Sie den-MDA ("dangerousThreadingAPI Managed Debug Assistant"), der aktiviert wird, wenn "Thread. Suspend" in einem anderen Thread als dem aktuellen Thread aufgerufen wird.
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
ms.openlocfilehash: 707e3e339cb8a692f862afc15328eef53f0547e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286083"
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="13d2a-103">dangerousThreadingAPI-MDA</span><span class="sxs-lookup"><span data-stu-id="13d2a-103">dangerousThreadingAPI MDA</span></span>

<span data-ttu-id="13d2a-104">Der `dangerousThreadingAPI`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>-Methode für einen anderen Thread als den aktuellen Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="13d2a-104">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="13d2a-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="13d2a-105">Symptoms</span></span>  

 <span data-ttu-id="13d2a-106">Eine Anwendung reagiert nicht oder bleibt auf unbestimmte Zeit hängen.</span><span class="sxs-lookup"><span data-stu-id="13d2a-106">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="13d2a-107">Die System- oder Anwendungsdaten befinden sich vorübergehend oder selbst nach Herunterfahren der Anwendung in einem unvorhersehbaren Zustand.</span><span class="sxs-lookup"><span data-stu-id="13d2a-107">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="13d2a-108">Einige Vorgänge werden nicht wie erwartet abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="13d2a-108">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="13d2a-109">Die Symptome sind aufgrund der Zufälligkeit dieses Problems breit gefächert.</span><span class="sxs-lookup"><span data-stu-id="13d2a-109">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="13d2a-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="13d2a-110">Cause</span></span>  

 <span data-ttu-id="13d2a-111">Ein Thread wird von einem anderen Thread mit der <xref:System.Threading.Thread.Suspend%2A>-Methode asynchron angehalten.</span><span class="sxs-lookup"><span data-stu-id="13d2a-111">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="13d2a-112">Es gibt keine Möglichkeit festzustellen, wann ein anderer Thread sicher angehalten werden kann, der sich möglicherweise gerade mitten in einem Vorgang befindet.</span><span class="sxs-lookup"><span data-stu-id="13d2a-112">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="13d2a-113">Das Anhalten eines Threads kann zur Beschädigung von Daten oder Invarianten führen.</span><span class="sxs-lookup"><span data-stu-id="13d2a-113">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="13d2a-114">Befindet sich ein Thread in angehaltenem Zustand und wird nicht mit der <xref:System.Threading.Thread.Resume%2A>-Methode fortgesetzt, kann die Anwendung auf unbestimmte Zeit hängen bleiben und Anwendungsdaten beschädigen.</span><span class="sxs-lookup"><span data-stu-id="13d2a-114">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="13d2a-115">Diese Methoden wurden als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="13d2a-115">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="13d2a-116">Für den Zielthread reservierte Synchronisierungsprimitiven bleiben während der Unterbrechung reserviert.</span><span class="sxs-lookup"><span data-stu-id="13d2a-116">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="13d2a-117">Dies kann zu Deadlocks führen, sollte ein anderer Thread versuchen, die Primitive zu sperren (z.B. der Thread, der <xref:System.Threading.Thread.Suspend%2A> ausführt).</span><span class="sxs-lookup"><span data-stu-id="13d2a-117">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="13d2a-118">In diesem Fall wird das Problem als Deadlock sichtbar.</span><span class="sxs-lookup"><span data-stu-id="13d2a-118">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="13d2a-119">Lösung</span><span class="sxs-lookup"><span data-stu-id="13d2a-119">Resolution</span></span>  

 <span data-ttu-id="13d2a-120">Vermeiden Sie Entwürfe, die die Verwendung von <xref:System.Threading.Thread.Suspend%2A> und <xref:System.Threading.Thread.Resume%2A> erfordern.</span><span class="sxs-lookup"><span data-stu-id="13d2a-120">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="13d2a-121">Verwenden Sie für die Zusammenarbeit zwischen Threads Synchronisierungsprimitiven wie beispielsweise <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> oder die C#-Anweisung `lock`.</span><span class="sxs-lookup"><span data-stu-id="13d2a-121">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="13d2a-122">Wenn Sie diese Methoden verwenden müssen, verringern Sie das Zeitfenster, und minimieren Sie die Codemenge, die ausgeführt wird, während sich der Thread in angehaltenem Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="13d2a-122">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="13d2a-123">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="13d2a-123">Effect on the Runtime</span></span>  

 <span data-ttu-id="13d2a-124">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="13d2a-124">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="13d2a-125">Es werden nur Angaben über problematische Threadoperationen gemeldet.</span><span class="sxs-lookup"><span data-stu-id="13d2a-125">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="13d2a-126">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="13d2a-126">Output</span></span>  

 <span data-ttu-id="13d2a-127">Der MDA identifiziert die problematische Threadmethode, die zu seiner Aktivierung führte.</span><span class="sxs-lookup"><span data-stu-id="13d2a-127">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="13d2a-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="13d2a-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="13d2a-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13d2a-129">Example</span></span>  

 <span data-ttu-id="13d2a-130">Das folgende Codebeispiel veranschaulicht einen Aufruf der <xref:System.Threading.Thread.Suspend%2A>-Methode, der zur Aktivierung des `dangerousThreadingAPI` führt.</span><span class="sxs-lookup"><span data-stu-id="13d2a-130">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13d2a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13d2a-131">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="13d2a-132">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="13d2a-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="13d2a-133">lock-Anweisung</span><span class="sxs-lookup"><span data-stu-id="13d2a-133">lock Statement</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
