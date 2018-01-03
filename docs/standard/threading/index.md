---
title: Verwaltetes Threading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 43fe5f9d193de3f48abfc0d91e01a70ee601a651
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="managed-threading"></a><span data-ttu-id="973ab-102">Verwaltetes Threading</span><span class="sxs-lookup"><span data-stu-id="973ab-102">Managed Threading</span></span>
<span data-ttu-id="973ab-103">Unabhängig davon, ob eine Anwendung für einen Computer mit einem oder mehreren Prozessoren entwickelt wurde, sollte sie optimal auf die Interaktion mit einem Benutzer reagieren, auch wenn sie gerade mit anderen Aufgaben befasst ist.</span><span class="sxs-lookup"><span data-stu-id="973ab-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="973ab-104">Die Verwendung verschiedener Ausführungsthreads stellt eine der effektivsten Möglichkeiten dar, eine Anwendung entsprechend reaktionsschnell zu gestalten und gleichzeitig den Prozessor zwischen Benutzerereignissen oder sogar währenddessen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="973ab-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="973ab-105">In diesem Abschnitt werden die grundlegenden Threadingkonzepte eingeführt und insbesondere verwaltete Threadingkonzepte und die Verwendung von verwaltetem Threading ausführlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="973ab-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="973ab-106">Beginnend mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurde die Multithreadprogrammierung durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Aufgaben anstatt von Threads basiert, erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="973ab-106">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="973ab-107">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="973ab-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="973ab-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="973ab-108">In This Section</span></span>  
 [<span data-ttu-id="973ab-109">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="973ab-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="973ab-110">Enthält eine Übersicht über das verwaltete Threading und erläutert, in welchen Fällen mehrere Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="973ab-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="973ab-111">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="973ab-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="973ab-112">Erklärt das Erstellen, Starten, Anhalten, Fortsetzen und Abbrechen von Threads.</span><span class="sxs-lookup"><span data-stu-id="973ab-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="973ab-113">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="973ab-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="973ab-114">Behandelt Synchronisierungsstufen, die Vermeidung von Deadlock- und Racebedingungen, Einzel- und Multiprozessorcomputer und weitere Threadingprobleme.</span><span class="sxs-lookup"><span data-stu-id="973ab-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, single-processor and multiprocessor computers, and other threading issues.</span></span>  
  
 [<span data-ttu-id="973ab-115">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="973ab-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="973ab-116">Beschreibt die verwalteten Klassen, mit denen Sie Threadingaktivitäten sowie die Daten von Objekten, auf die in verschiedenen Threads zugegriffen wird, synchronisieren können, und bietet eine Übersicht über Threadpoolthreads.</span><span class="sxs-lookup"><span data-stu-id="973ab-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="973ab-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="973ab-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="973ab-118">Enthält Klassen zum Verwenden und Synchronisieren von verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="973ab-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="973ab-119">Enthält Auflistungsklassen, die sicher mit mehreren Threads verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="973ab-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="973ab-120">Enthält Klassen zum Erstellen und Planen von parallelen Verarbeitungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="973ab-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="973ab-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="973ab-121">Related Sections</span></span>  
 [<span data-ttu-id="973ab-122">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="973ab-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="973ab-123">Übersicht über Anwendungsdomänen und deren Verwendung durch die Common Language-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="973ab-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="973ab-124">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="973ab-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="973ab-125">Beschreibt die Leistungsvorteile und den grundlegenden Ablauf der asynchronen E/A.</span><span class="sxs-lookup"><span data-stu-id="973ab-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="973ab-126">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="973ab-126">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="973ab-127">Übersicht über asynchrones Programmieren.</span><span class="sxs-lookup"><span data-stu-id="973ab-127">Provides an overview of asynchronous programming.</span></span>  
  
 [<span data-ttu-id="973ab-128">Asynchrones Aufrufen von synchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="973ab-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="973ab-129">Erläutert das Aufrufen von Methoden für Threadpoolthreads mithilfe der integrierten Features von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="973ab-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="973ab-130">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="973ab-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="973ab-131">Beschreibt die parallelen Programmierbibliotheken, die die Verwendung mehrerer Threads in Anwendungen vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="973ab-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="973ab-132">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="973ab-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 <span data-ttu-id="973ab-133">Beschreibt ein System zum parallelen Ausführen von Abfragen, um die Vorteile mehrerer Prozessoren zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="973ab-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
