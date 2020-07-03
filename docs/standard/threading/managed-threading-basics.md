---
title: Grundlagen des verwalteten Threadings
description: In diesem Artikel finden Sie Links zu anderen Artikeln über verwaltetes Threading, in denen unter anderem Themen wie Ausnahmen, das Synchronisieren von Daten, Vordergrund- und Hintergrundthreads und lokaler Speicher behandelt werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: d4a4ceabf29bd0f6f537e59ba477f9da686b1ef5
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769092"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="b5af9-103">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="b5af9-103">Managed threading basics</span></span>

<span data-ttu-id="b5af9-104">Die ersten fünf Themen in diesem Abschnitt sollen Ihnen helfen, zu bestimmen, wann Sie verwaltetes Threading verwenden sollten, und einige grundlegende Funktionen erläutern.</span><span class="sxs-lookup"><span data-stu-id="b5af9-104">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="b5af9-105">Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threadingobjekte und -funktionen](threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="b5af9-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="b5af9-106">Bei den übrigen Themen in diesem Abschnitt handelt es sich um erweiterte Themen einschließlich der Interaktion verwalteten Threadings mit dem Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="b5af9-106">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5af9-107">In .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs für Aufgaben- und Datenparallelität in Multithreadprogrammen bereit.</span><span class="sxs-lookup"><span data-stu-id="b5af9-107">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="b5af9-108">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="b5af9-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5af9-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b5af9-109">In this section</span></span>

 [<span data-ttu-id="b5af9-110">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="b5af9-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="b5af9-111">Erläutert die Vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Threads aus Threadpools verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="b5af9-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="b5af9-112">Ausnahmen in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="b5af9-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="b5af9-113">Beschreibt das Verhalten der nicht behandelten Ausnahmen in Threads für verschiedene Versionen von .NET Framework, insbesondere die Situationen, in denen sie zum Beenden der Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="b5af9-113">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="b5af9-114">Datensynchronisierung für Multithreading</span><span class="sxs-lookup"><span data-stu-id="b5af9-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="b5af9-115">Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5af9-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="b5af9-116">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="b5af9-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="b5af9-117">Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="b5af9-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="b5af9-118">Verwaltetes und nicht verwaltetes Threading in Windows</span><span class="sxs-lookup"><span data-stu-id="b5af9-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="b5af9-119">Beschreibt die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, listet verwaltete Entsprechungen für Windows-Threading-APIs auf und erläutert die Interaktion von COM-Apartments und verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="b5af9-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="b5af9-120">Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots</span><span class="sxs-lookup"><span data-stu-id="b5af9-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="b5af9-121">Beschreibt threadbezogene Speichermechanismen.</span><span class="sxs-lookup"><span data-stu-id="b5af9-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b5af9-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="b5af9-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="b5af9-123">Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5af9-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="b5af9-124">Bietet eine sichere Möglichkeit zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.</span><span class="sxs-lookup"><span data-stu-id="b5af9-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b5af9-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b5af9-125">Related sections</span></span>

 [<span data-ttu-id="b5af9-126">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="b5af9-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="b5af9-127">Beschreibt die verwalteten Klassen, die zum Synchronisieren mehrerer Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5af9-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="b5af9-128">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="b5af9-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="b5af9-129">Beschreibt allgemeine Probleme mit Multithreading und Strategien zur Vermeidung von Problemen.</span><span class="sxs-lookup"><span data-stu-id="b5af9-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="b5af9-130">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="b5af9-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="b5af9-131">Beschreibt Task Parallel Library und PLINQ, die das Erstellen von asynchronen und Multithreaded-.NET Framework-Anwendungen erheblich vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b5af9-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
