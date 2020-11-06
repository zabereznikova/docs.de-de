---
title: Grundlagen des verwalteten Threadings
description: In diesem Artikel finden Sie Links zu anderen Artikeln über verwaltetes Threading, in denen unter anderem Themen wie Ausnahmen, das Synchronisieren von Daten, Vordergrund- und Hintergrundthreads und lokaler Speicher behandelt werden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: ca3073cca9887265b4bacb4f8dfeb01203f82621
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189133"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="354c2-103">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="354c2-103">Managed threading basics</span></span>

<span data-ttu-id="354c2-104">Die ersten fünf Artikel in diesem Abschnitt sollen Ihnen helfen, zu bestimmen, wann Sie verwaltetes Threading verwenden sollten, und einige grundlegende Features erläutern.</span><span class="sxs-lookup"><span data-stu-id="354c2-104">The first five articles of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="354c2-105">Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threadingobjekte und -funktionen](threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="354c2-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="354c2-106">Die restlichen Artikel in diesem Abschnitt behandeln erweiterte Themen einschließlich der Interaktion verwalteten Threadings mit dem Windows-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="354c2-106">The remaining articles in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="354c2-107">Ab .NET Framework 4 stellen die Task Parallel Library und PLINQ APIs für Task- und Datenparallelität in Multithreadprogrammen bereit.</span><span class="sxs-lookup"><span data-stu-id="354c2-107">Starting with .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="354c2-108">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="354c2-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="354c2-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="354c2-109">In this section</span></span>

 [<span data-ttu-id="354c2-110">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="354c2-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="354c2-111">Erläutert die Vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Threads aus Threadpools verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="354c2-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="354c2-112">Ausnahmen in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="354c2-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="354c2-113">In diesem Artikel wird das Verhalten der Ausnahmefehler in Threads für verschiedene Versionen von .NET beschrieben, insbesondere die Situationen, in denen sie zum Beenden der Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="354c2-113">Describes the behavior of unhandled exceptions in threads for different versions of .NET, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="354c2-114">Datensynchronisierung für Multithreading</span><span class="sxs-lookup"><span data-stu-id="354c2-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="354c2-115">Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="354c2-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="354c2-116">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="354c2-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="354c2-117">Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="354c2-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="354c2-118">Verwaltetes und nicht verwaltetes Threading in Windows</span><span class="sxs-lookup"><span data-stu-id="354c2-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="354c2-119">Beschreibt die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, listet verwaltete Entsprechungen für Windows-Threading-APIs auf und erläutert die Interaktion von COM-Apartments und verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="354c2-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="354c2-120">Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots</span><span class="sxs-lookup"><span data-stu-id="354c2-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="354c2-121">Beschreibt threadbezogene Speichermechanismen.</span><span class="sxs-lookup"><span data-stu-id="354c2-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="354c2-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="354c2-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="354c2-123">Stellt die Referenzdokumentation für die **Thread** -Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="354c2-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="354c2-124">Bietet eine sichere Möglichkeit zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.</span><span class="sxs-lookup"><span data-stu-id="354c2-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="354c2-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="354c2-125">Related sections</span></span>

 [<span data-ttu-id="354c2-126">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="354c2-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="354c2-127">Beschreibt die verwalteten Klassen, die zum Synchronisieren mehrerer Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="354c2-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="354c2-128">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="354c2-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="354c2-129">Beschreibt allgemeine Probleme mit Multithreading und Strategien zur Vermeidung von Problemen.</span><span class="sxs-lookup"><span data-stu-id="354c2-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="354c2-130">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="354c2-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="354c2-131">In diesem Artikel werden die Task Parallel Library und PLINQ beschrieben, die das Erstellen von asynchronen und Multithread-.NET-Anwendungen erheblich vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="354c2-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET applications.</span></span>
