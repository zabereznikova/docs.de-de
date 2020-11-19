---
title: Garbage Collection für .NET
description: Erfahren Sie mehr über die Garbage Collection in .NET. Der Garbage Collector von .NET verwaltet die Belegung und Freigabe von Arbeitsspeicher für die Anwendung.
ms.date: 04/21/2020
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 8b1fad3420778c17656614994684930fcd1b62ca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827775"
---
# <a name="garbage-collection"></a><span data-ttu-id="9ffb3-104">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9ffb3-104">Garbage collection</span></span>

<span data-ttu-id="9ffb3-105">Der Garbage Collector von .NET verwaltet die Belegung und Freigabe von Arbeitsspeicher für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-105">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="9ffb3-106">Bei jedem Erstellen eines neuen Objekts belegt die Common Language Runtime (CLR) Speicher für das Objekt aus dem verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-106">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="9ffb3-107">Solange ein Adressbereich im verwalteten Heap verfügbar ist, reserviert die Laufzeit Arbeitsspeicher für neue Objekte.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-107">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="9ffb3-108">Arbeitsspeicher ist jedoch nicht unendlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-108">However, memory is not infinite.</span></span> <span data-ttu-id="9ffb3-109">Möglicherweise muss mithilfe der Garbage Collection Arbeitsspeicher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-109">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="9ffb3-110">Die Optimierungs-Engine der Garbage Collection bestimmt den besten Zeitpunkt für das Einsammeln anhand der erfolgten Speicherbelegungen.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-110">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="9ffb3-111">Beim Einsammeln durch die Garbage Collection wird nach Objekten im verwalteten Heap gesucht, die nicht mehr von der Anwendung verwendet werden. Anschließend werden die für das Freigeben des Arbeitsspeichers erforderlichen Operationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-111">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ffb3-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9ffb3-112">In this section</span></span>
  
|<span data-ttu-id="9ffb3-113">Titel</span><span class="sxs-lookup"><span data-stu-id="9ffb3-113">Title</span></span>|<span data-ttu-id="9ffb3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ffb3-114">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9ffb3-115">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9ffb3-115">Fundamentals of garbage collection</span></span>](fundamentals.md)|<span data-ttu-id="9ffb3-116">Beschreibt, wie die Garbage Collection funktioniert, wie Objekte auf dem verwalteten Heap zugeordnet werden und erläutert andere Kernkonzepte.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-116">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="9ffb3-117">Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="9ffb3-117">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="9ffb3-118">Beschreibt die Unterschiede zwischen der Garbage Collection auf der Arbeitsstation für Client-Apps und der Garbage Collection auf dem Server für Server-Apps</span><span class="sxs-lookup"><span data-stu-id="9ffb3-118">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="9ffb3-119">Garbage Collection im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="9ffb3-119">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="9ffb3-120">Beschreibt die Garbage Collection im Hintergrund, bei der es sich um die Bereinigung von Objekten der Generationen 0 und 1 handelt, während die Bereinigung für Generation 2 ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="9ffb3-120">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="9ffb3-121">Der Large-Object-Heap</span><span class="sxs-lookup"><span data-stu-id="9ffb3-121">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="9ffb3-122">Beschreibt den Large-Object-Heap (Large Object Heap, LOH) und die Garbage Collection für Large Objects</span><span class="sxs-lookup"><span data-stu-id="9ffb3-122">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="9ffb3-123">Garbage Collection und Leistung</span><span class="sxs-lookup"><span data-stu-id="9ffb3-123">Garbage collection and performance</span></span>](performance.md)|<span data-ttu-id="9ffb3-124">Beschreibt die Leistungsprüfungen, die Sie verwenden können, um Probleme mit der Garbage Collection oder der Leistung zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-124">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="9ffb3-125">Indizierte Auflistungen</span><span class="sxs-lookup"><span data-stu-id="9ffb3-125">Induced collections</span></span>](induced.md)|<span data-ttu-id="9ffb3-126">Beschreibt, wie eine Garbage Collection initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-126">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="9ffb3-127">Latenzmodi</span><span class="sxs-lookup"><span data-stu-id="9ffb3-127">Latency modes</span></span>](latency.md)|<span data-ttu-id="9ffb3-128">Beschreibt die Modi, die das Ausmaß der Garbage Collection bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-128">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="9ffb3-129">Optimierung für freigegebenes Webhosting</span><span class="sxs-lookup"><span data-stu-id="9ffb3-129">Optimization for shared web hosting</span></span>](optimization-for-shared-web-hosting.md)|<span data-ttu-id="9ffb3-130">Beschreibt, wie die Garbage Collection auf Servern, die von mehreren kleinen Websites gemeinsam verwendet werden, optimiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-130">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="9ffb3-131">Garbage-Collection-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="9ffb3-131">Garbage collection notifications</span></span>](notifications.md)|<span data-ttu-id="9ffb3-132">Beschreibt, wie festgestellt werden kann, wann eine vollständige Garbage Collection ansteht und wann sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-132">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="9ffb3-133">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="9ffb3-133">Application domain resource monitoring</span></span>](app-domain-resource-monitoring.md)|<span data-ttu-id="9ffb3-134">Beschreibt, wie die durch eine Anwendungsdomäne verursachte CPU- und Speicherauslastung überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-134">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="9ffb3-135">Schwache Verweise</span><span class="sxs-lookup"><span data-stu-id="9ffb3-135">Weak references</span></span>](weak-references.md)|<span data-ttu-id="9ffb3-136">Beschreibt Funktionen, die dem Garbage Collector ermöglichen, ein Objekt zu sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9ffb3-136">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="9ffb3-137">Referenz</span><span class="sxs-lookup"><span data-stu-id="9ffb3-137">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="9ffb3-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ffb3-138">See also</span></span>

- [<span data-ttu-id="9ffb3-139">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9ffb3-139">Clean up unmanaged resources</span></span>](unmanaged.md)
