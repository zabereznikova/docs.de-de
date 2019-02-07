---
title: Threadingobjekte und -funktionen
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 745cd1e17e2c06a513c6fdafe8f6b5f464b95d5f
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479658"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="77211-102">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="77211-102">Threading objects and features</span></span>

<span data-ttu-id="77211-103">Zusammen mit der <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse stellt .NET eine Reihe von Klassen bereit, mit denen Sie Multithread-Anwendungen entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="77211-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="77211-104">In den folgenden Artikeln finden Sie eine Übersicht über diese Klassen:</span><span class="sxs-lookup"><span data-stu-id="77211-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="77211-105">Titel</span><span class="sxs-lookup"><span data-stu-id="77211-105">Title</span></span>|<span data-ttu-id="77211-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77211-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="77211-107">Der verwaltete Threadpool</span><span class="sxs-lookup"><span data-stu-id="77211-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="77211-108">Beschreibt die <xref:System.Threading.ThreadPool?displayProperty=nameWithType>-Klasse, die einen Pool von Arbeitsthreads bereitstellt, die von .NET verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="77211-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="77211-109">Timer</span><span class="sxs-lookup"><span data-stu-id="77211-109">Timers</span></span>](timers.md)|<span data-ttu-id="77211-110">Beschreibt .NET-Timer, die in einer Multithreadumgebung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="77211-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="77211-111">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="77211-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="77211-112">Beschreibt Typen, die zum Synchronisieren des Zugriffs auf eine freigegebene Ressource oder zum Steuern von Threadinteraktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="77211-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="77211-113">EventWaitHandle, CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="77211-113">EventWaitHandle, CountdownEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|<span data-ttu-id="77211-114">Beschreibt verwaltete Event-Wait-Handles, die signalisieren und auf Signale warten und zum Synchronisieren von Threadaktivitäten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77211-114">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>|
|[<span data-ttu-id="77211-115">Mutexe</span><span class="sxs-lookup"><span data-stu-id="77211-115">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="77211-116">Beschreibt <xref:System.Threading.Mutex?displayProperty=nameWithType>, das exklusiven Zugriff auf eine freigegebene Ressource gewährt.</span><span class="sxs-lookup"><span data-stu-id="77211-116">Describes <xref:System.Threading.Mutex?displayProperty=nameWithType>, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="77211-117">Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="77211-117">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="77211-118">Beschreibt die <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Klasse, die die Anzahl von Threads einschränkt, die gleichzeitig auf eine freigegebene Ressource oder einen Pool von Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="77211-118">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="77211-119">Barrier</span><span class="sxs-lookup"><span data-stu-id="77211-119">Barrier</span></span>](barrier.md)|<span data-ttu-id="77211-120">Beschreibt <xref:System.Threading.Barrier?displayProperty=nameWithType>-Klasse, die das Barrieremuster für die Koordination von Threads in stufenweise durchgeführten Vorgängen implementiert.</span><span class="sxs-lookup"><span data-stu-id="77211-120">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class that implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="77211-121">SpinLock</span><span class="sxs-lookup"><span data-stu-id="77211-121">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="77211-122">Beschreibt die <xref:System.Threading.SpinLock?displayProperty=nameWithType>-Struktur, die für bestimmte Low-Level-Sperrszenarios eine einfache Alternative zur <xref:System.Threading.Monitor?displayProperty=nameWithType>-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="77211-122">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="77211-123">SpinWait</span><span class="sxs-lookup"><span data-stu-id="77211-123">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="77211-124">Beschreibt die <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Struktur, die Unterstützung für Spin-basierte Wartevorgänge bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="77211-124">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="77211-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77211-125">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="77211-126">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="77211-126">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="77211-127">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="77211-127">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="77211-128">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="77211-128">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="77211-129">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="77211-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
