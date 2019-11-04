---
title: Grundlagen des verwalteten Threadings
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: bec769043ab630b37609bed12302ceff5b90474a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139226"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="ec1a6-102">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="ec1a6-102">Managed threading basics</span></span>

<span data-ttu-id="ec1a6-103">Die ersten fünf Themen in diesem Abschnitt sollen Ihnen helfen, zu bestimmen, wann Sie verwaltetes Threading verwenden sollten, und einige grundlegende Funktionen erläutern.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-103">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="ec1a6-104">Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threadingobjekte und -funktionen](../../../docs/standard/threading/threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a6-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="ec1a6-105">Bei den übrigen Themen in diesem Abschnitt handelt es sich um erweiterte Themen einschließlich der Interaktion verwalteten Threadings mit dem Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec1a6-106">In .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs für Aufgaben- und Datenparallelität in Multithreadprogrammen bereit.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-106">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="ec1a6-107">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="ec1a6-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec1a6-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ec1a6-108">In this section</span></span>

 [<span data-ttu-id="ec1a6-109">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="ec1a6-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="ec1a6-110">Erläutert die Vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Threads aus Threadpools verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="ec1a6-111">Ausnahmen in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="ec1a6-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="ec1a6-112">Beschreibt das Verhalten der nicht behandelten Ausnahmen in Threads für verschiedene Versionen von .NET Framework, insbesondere die Situationen, in denen sie zum Beenden der Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="ec1a6-113">Datensynchronisierung für Multithreading</span><span class="sxs-lookup"><span data-stu-id="ec1a6-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="ec1a6-114">Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="ec1a6-115">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="ec1a6-115">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="ec1a6-116">Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-116">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="ec1a6-117">Verwaltetes und nicht verwaltetes Threading in Windows</span><span class="sxs-lookup"><span data-stu-id="ec1a6-117">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="ec1a6-118">Beschreibt die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, listet verwaltete Entsprechungen für Windows-Threading-APIs auf und erläutert die Interaktion von COM-Apartments und verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-118">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="ec1a6-119">Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots</span><span class="sxs-lookup"><span data-stu-id="ec1a6-119">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="ec1a6-120">Beschreibt threadbezogene Speichermechanismen.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-120">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ec1a6-121">Referenz</span><span class="sxs-lookup"><span data-stu-id="ec1a6-121">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="ec1a6-122">Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-122">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="ec1a6-123">Bietet eine sichere Möglichkeit zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-123">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ec1a6-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ec1a6-124">Related sections</span></span>

 [<span data-ttu-id="ec1a6-125">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="ec1a6-125">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="ec1a6-126">Beschreibt die verwalteten Klassen, die zum Synchronisieren mehrerer Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-126">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="ec1a6-127">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="ec1a6-127">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="ec1a6-128">Beschreibt allgemeine Probleme mit Multithreading und Strategien zur Vermeidung von Problemen.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-128">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="ec1a6-129">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="ec1a6-129">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="ec1a6-130">Beschreibt Task Parallel Library und PLINQ, die das Erstellen von asynchronen und Multithreaded-.NET Framework-Anwendungen erheblich vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ec1a6-130">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
