---
title: Garbage Collection
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
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
ms.openlocfilehash: 0038f4ba28c7ea3e7be4502a71026a2b3ad47829
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120991"
---
# <a name="garbage-collection"></a><span data-ttu-id="6d885-102">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6d885-102">Garbage Collection</span></span>
<span data-ttu-id="6d885-103">Der Garbage Collector von .NET verwaltet die Belegung und Freigabe von Arbeitsspeicher für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6d885-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="6d885-104">Bei jedem Erstellen eines neuen Objekts belegt die Common Language Runtime (CLR) Speicher für das Objekt aus dem verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="6d885-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="6d885-105">Solange ein Adressbereich im verwalteten Heap verfügbar ist, reserviert die Laufzeit Arbeitsspeicher für neue Objekte.</span><span class="sxs-lookup"><span data-stu-id="6d885-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="6d885-106">Arbeitsspeicher ist jedoch nicht unendlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6d885-106">However, memory is not infinite.</span></span> <span data-ttu-id="6d885-107">Möglicherweise muss mithilfe der Garbage Collection Arbeitsspeicher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d885-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="6d885-108">Die Optimierungs-Engine der Garbage Collection bestimmt den besten Zeitpunkt für das Einsammeln anhand der erfolgten Speicherbelegungen.</span><span class="sxs-lookup"><span data-stu-id="6d885-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="6d885-109">Beim Einsammeln durch die Garbage Collection wird nach Objekten im verwalteten Heap gesucht, die nicht mehr von der Anwendung verwendet werden. Anschließend werden die für das Freigeben des Arbeitsspeichers erforderlichen Operationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d885-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="6d885-110">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6d885-110">Related Topics</span></span>  
  
|<span data-ttu-id="6d885-111">Titel</span><span class="sxs-lookup"><span data-stu-id="6d885-111">Title</span></span>|<span data-ttu-id="6d885-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d885-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6d885-113">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6d885-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="6d885-114">Beschreibt, wie die Garbage Collection funktioniert, wie Objekte auf dem verwalteten Heap zugeordnet werden und erläutert andere Kernkonzepte.</span><span class="sxs-lookup"><span data-stu-id="6d885-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="6d885-115">Garbage Collection und Leistung</span><span class="sxs-lookup"><span data-stu-id="6d885-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="6d885-116">Beschreibt die Leistungsprüfungen, die Sie verwenden können, um Probleme mit der Garbage Collection oder der Leistung zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="6d885-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="6d885-117">Induzierte Sammlungen</span><span class="sxs-lookup"><span data-stu-id="6d885-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="6d885-118">Beschreibt, wie eine Garbage Collection initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="6d885-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="6d885-119">Latenzmodi</span><span class="sxs-lookup"><span data-stu-id="6d885-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="6d885-120">Beschreibt die Modi, die das Ausmaß der Garbage Collection bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6d885-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="6d885-121">Optimierung für freigegebenes Webhosting</span><span class="sxs-lookup"><span data-stu-id="6d885-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="6d885-122">Beschreibt, wie die Garbage Collection auf Servern, die von mehreren kleinen Websites gemeinsam verwendet werden, optimiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d885-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="6d885-123">Garbage Collection-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="6d885-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="6d885-124">Beschreibt, wie festgestellt werden kann, wann eine vollständige Garbage Collection ansteht und wann sie abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6d885-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="6d885-125">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="6d885-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="6d885-126">Beschreibt, wie die durch eine Anwendungsdomäne verursachte CPU- und Speicherauslastung überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="6d885-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="6d885-127">Schwache Verweise</span><span class="sxs-lookup"><span data-stu-id="6d885-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="6d885-128">Beschreibt Funktionen, die dem Garbage Collector ermöglichen, ein Objekt zu sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="6d885-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="6d885-129">Referenz</span><span class="sxs-lookup"><span data-stu-id="6d885-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="6d885-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d885-130">See also</span></span>

- [<span data-ttu-id="6d885-131">Bereinigen von nicht verwalteten Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6d885-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
