---
title: Threadingobjekte und -funktionen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02f88faab6ddbaa026e73ad61bc63fbe8e5e00ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591325"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="cfedd-102">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="cfedd-102">Threading Objects and Features</span></span>
<span data-ttu-id="cfedd-103">.NET Framework stellt eine Reihe von Objekten bereit, mit denen Sie Multithreadanwendungen erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="cfedd-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="cfedd-104">Verwaltete Threads werden durch die <xref:System.Threading.Thread>-Klasse repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="cfedd-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="cfedd-105">Die <xref:System.Threading.ThreadPool>-Klasse ermöglicht eine einfache Erstellung und Verwaltung von Multithreaded-Hintergrundaufgaben.</span><span class="sxs-lookup"><span data-stu-id="cfedd-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="cfedd-106">Die <xref:System.ComponentModel.BackgroundWorker>-Klasse erfüllt den gleichen Zweck für Aufgaben, die mit der Benutzeroberfläche interagieren.</span><span class="sxs-lookup"><span data-stu-id="cfedd-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="cfedd-107">Die <xref:System.Threading.Timer> -Klasse führt Hintergrundaufgaben in festgelegten Intervallen aus.</span><span class="sxs-lookup"><span data-stu-id="cfedd-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="cfedd-108">Darüber hinaus gibt es eine Reihe von Klassen, die Aktivitäten von Threads synchronisieren. Dazu zählen auch die <xref:System.Threading.Semaphore>- und <xref:System.Threading.EventWaitHandle>-Klasse, die in .NET Framework 2.0 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cfedd-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="cfedd-109">Die Funktionen dieser Klassen werden im Artikel [Übersicht über Synchronisierungsprimitive](../../../docs/standard/threading/overview-of-synchronization-primitives.md) miteinander verglichen.</span><span class="sxs-lookup"><span data-stu-id="cfedd-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfedd-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cfedd-110">In This Section</span></span>  
 [<span data-ttu-id="cfedd-111">Der verwaltete Threadpool</span><span class="sxs-lookup"><span data-stu-id="cfedd-111">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)  
 <span data-ttu-id="cfedd-112">Erläutert die **ThreadPool**-Klasse, mit der Sie einen Thread zum Ausführen einer Aufgabe anfordern können, ohne den Thread in irgendeiner Form selbst verwalten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="cfedd-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 [<span data-ttu-id="cfedd-113">Timer</span><span class="sxs-lookup"><span data-stu-id="cfedd-113">Timers</span></span>](../../../docs/standard/threading/timers.md)  
 <span data-ttu-id="cfedd-114">Hier wird erläutert, wie Sie mit einem **Timer** einen Delegaten angeben, der zu einer bestimmten Zeit aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfedd-114">Explains how to use a **Timer** to specify a delegate to be called at a specified time.</span></span>  
  
 [<span data-ttu-id="cfedd-115">Monitore</span><span class="sxs-lookup"><span data-stu-id="cfedd-115">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 <span data-ttu-id="cfedd-116">Erläutert, wie die **Monitor**-Klasse zum Synchronisieren des Zugriffs auf ein Member oder zum Erstellen eigener Threadverwaltungsarten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfedd-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 [<span data-ttu-id="cfedd-117">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="cfedd-117">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="cfedd-118">Beschreibt die <xref:System.Threading.WaitHandle>-Klasse, die abstrakte Basisklasse für Event-Wait-Handles, Mutexe und Semaphoren, welche die Wartefunktion für mehrere Synchronisierungsereignisse ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="cfedd-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="cfedd-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="cfedd-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="cfedd-120">Beschreibt verwaltete Event-Wait-Handles, die signalisieren und auf Signale warten und zum Synchronisieren von Threadaktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfedd-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 [<span data-ttu-id="cfedd-121">Mutexe</span><span class="sxs-lookup"><span data-stu-id="cfedd-121">Mutexes</span></span>](../../../docs/standard/threading/mutexes.md)  
 <span data-ttu-id="cfedd-122">Erläutert, wie ein <xref:System.Threading.Mutex> zum Synchronisieren des Zugriffs auf ein Objekt oder zum Erstellen eigener Synchronisierungsmechanismen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfedd-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 [<span data-ttu-id="cfedd-123">Interlocked-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="cfedd-123">Interlocked Operations</span></span>](../../../docs/standard/threading/interlocked-operations.md)  
 <span data-ttu-id="cfedd-124">Erläutert, wie mit der <xref:System.Threading.Interlocked>-Klasse ein Wert in einem einzigen Vorgang erhöht oder verringert und gleichzeitig gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="cfedd-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 [<span data-ttu-id="cfedd-125">Lese-/Schreibsperren</span><span class="sxs-lookup"><span data-stu-id="cfedd-125">Reader-Writer Locks</span></span>](../../../docs/standard/threading/reader-writer-locks.md)  
 <span data-ttu-id="cfedd-126">Definiert eine Sperre, die eine Semantik implementiert, die nur einen Schreibvorgang, aber mehrere Lesevorgänge gleichzeitig zulässt.</span><span class="sxs-lookup"><span data-stu-id="cfedd-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 [<span data-ttu-id="cfedd-127">Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="cfedd-127">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <span data-ttu-id="cfedd-128">Beschreibt <xref:System.Threading.Semaphore>-Objekte und erläutert, wie diese zum Steuern des Zugriffs auf begrenzte Ressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfedd-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 [<span data-ttu-id="cfedd-129">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="cfedd-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="cfedd-130">Vergleicht die Funktionen von .NET Framework-Klassen, die zum Sperren und Synchronisieren verwalteter Threads zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="cfedd-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 [<span data-ttu-id="cfedd-131">Barrier</span><span class="sxs-lookup"><span data-stu-id="cfedd-131">Barrier</span></span>](../../../docs/standard/threading/barrier.md)  
 <span data-ttu-id="cfedd-132">Beschreibt <xref:System.Threading.Barrier>-Objekte, die das Barrieremuster für die Koordination von Threads in stufenweise durchgeführten Vorgängen implementieren.</span><span class="sxs-lookup"><span data-stu-id="cfedd-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="cfedd-133">SpinLock</span><span class="sxs-lookup"><span data-stu-id="cfedd-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="cfedd-134">Beschreibt <xref:System.Threading.SpinLock>, eine einfache Alternative zur Monitor-Klasse für bestimmte Low-Level-Szenarien.</span><span class="sxs-lookup"><span data-stu-id="cfedd-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="cfedd-135">SpinWait</span><span class="sxs-lookup"><span data-stu-id="cfedd-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="cfedd-136">Beschreibt <xref:System.Threading.SpinWait>, einen Low-Level-Synchronisierungsprimitiven, der vor dem Initiieren eines kernelbasierten Wartevorgangs Spinvorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="cfedd-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cfedd-137">Referenz</span><span class="sxs-lookup"><span data-stu-id="cfedd-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="cfedd-138">Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cfedd-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="cfedd-139">Aktiviert Hintergrundaufgaben, die mit der Benutzeroberfläche interagieren und über Ereignisse kommunizieren, die auf dem Benutzeroberflächenthread ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="cfedd-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cfedd-140">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cfedd-140">Related Sections</span></span>  
 [<span data-ttu-id="cfedd-141">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="cfedd-141">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="cfedd-142">Beschreibt, wie asynchrone E/A-Abschlussports den Threadpool verwenden, um die Verarbeitung nur bei Abschluss eines E/A-Vorgangs anzufordern.</span><span class="sxs-lookup"><span data-stu-id="cfedd-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="cfedd-143">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="cfedd-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="cfedd-144">Beschreibt die empfohlene Vorgehensweise bei der Multithreadprogrammierung in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und höher.</span><span class="sxs-lookup"><span data-stu-id="cfedd-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
