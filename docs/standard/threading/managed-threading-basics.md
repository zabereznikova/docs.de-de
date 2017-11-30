---
title: Grundlagen des verwalteten Threadings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="550f5-102">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="550f5-102">Managed Threading Basics</span></span>
<span data-ttu-id="550f5-103">Die ersten fünf Themen in diesem Abschnitt sollen Sie bestimmen, wann die verwaltetes threading verwenden, und Erläutern Sie einige grundlegende Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="550f5-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="550f5-104">Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threading und-Features](../../../docs/standard/threading/threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="550f5-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="550f5-105">Der Rest der Themen in diesem Abschnitt behandeln die erweiterte Themen, einschließlich der Interaktion mit dem Windows-Betriebssystem verwaltetes threading.</span><span class="sxs-lookup"><span data-stu-id="550f5-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="550f5-106">In der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], geben Sie die Task Parallel Library und PLINQ APIs für Aufgabe und der Parallelität in Multithreaded-Programmen.</span><span class="sxs-lookup"><span data-stu-id="550f5-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="550f5-107">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="550f5-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="550f5-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="550f5-108">In This Section</span></span>  
 [<span data-ttu-id="550f5-109">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="550f5-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="550f5-110">Erläutert die vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Verwenden von Threads im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="550f5-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="550f5-111">Ausnahmen in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="550f5-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="550f5-112">Beschreibt das Verhalten der nicht behandelten Ausnahmen in Threads für verschiedene Versionen von .NET Framework, insbesondere bei die Situationen in die sie bei Beendigung der Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="550f5-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="550f5-113">Datensynchronisierung für Multithreading</span><span class="sxs-lookup"><span data-stu-id="550f5-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="550f5-114">Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="550f5-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="550f5-115">Zustände von verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="550f5-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="550f5-116">Beschreibt die grundlegenden Threadzustände und erklärt, wie zu ermitteln, ob ein Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="550f5-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="550f5-117">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="550f5-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="550f5-118">Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="550f5-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="550f5-119">Verwaltetes und nicht verwaltetes Threading in Windows</span><span class="sxs-lookup"><span data-stu-id="550f5-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="550f5-120">Beschreibt die Beziehung zwischen verwalteten und nicht verwaltetes threading, verwaltete Entsprechungen für Windows-threading-APIs aufgelistet und die Interaktion von COM-Apartments und verwaltete Threads erläutert.</span><span class="sxs-lookup"><span data-stu-id="550f5-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="550f5-121">Thread.Suspend, Garbage Collection und Sicherungspunkte</span><span class="sxs-lookup"><span data-stu-id="550f5-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="550f5-122">Beschreibt Thread anhalten und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="550f5-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="550f5-123">Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots</span><span class="sxs-lookup"><span data-stu-id="550f5-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="550f5-124">Beschreibt threadbezogene Speichermechanismen.</span><span class="sxs-lookup"><span data-stu-id="550f5-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="550f5-125">Abbruch in verwalteten Threads</span><span class="sxs-lookup"><span data-stu-id="550f5-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="550f5-126">Beschreibt die Funktionsweise der asynchronen oder lang andauernden synchrone Vorgängen kann durch Verwenden eines Abbruchtokens abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="550f5-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="550f5-127">Verweis</span><span class="sxs-lookup"><span data-stu-id="550f5-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="550f5-128">Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="550f5-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="550f5-129">Bietet eine sichere Möglichkeit zum Implementieren multithreading in Verbindung mit Benutzeroberflächenobjekten.</span><span class="sxs-lookup"><span data-stu-id="550f5-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="550f5-130">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="550f5-130">Related Sections</span></span>  
 [<span data-ttu-id="550f5-131">Übersicht über Synchronisierungsprimitiven</span><span class="sxs-lookup"><span data-stu-id="550f5-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="550f5-132">Beschreibt die verwalteten Klassen verwendet, um die Aktivitäten mehrerer Threads zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="550f5-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="550f5-133">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="550f5-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="550f5-134">Beschreibt allgemeine Probleme mit multithreading und Strategien zur Vermeidung von Problemen.</span><span class="sxs-lookup"><span data-stu-id="550f5-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="550f5-135">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="550f5-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="550f5-136">Beschreibt die Task Parallel Library und PLINQ, die asynchrone und mit mehreren Threads .NET Framework-Anwendungen erstellen erheblich vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="550f5-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
