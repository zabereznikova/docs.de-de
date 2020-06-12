---
title: Verwaltetes Threading
description: Hier finden Sie Links zu Artikeln über verwaltetes Threading in .NET, die sich mit den Grundlagen, den bewährten Methoden, den Threadingobjekten und -features, Referenzseiten und mehr befassen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: 570db45138c85c4252967404da4404d434660d69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599749"
---
# <a name="managed-threading"></a><span data-ttu-id="1f5b9-103">Verwaltetes Threading</span><span class="sxs-lookup"><span data-stu-id="1f5b9-103">Managed Threading</span></span>
<span data-ttu-id="1f5b9-104">Unabhängig davon, ob eine Anwendung für einen Computer mit einem oder mehreren Prozessoren entwickelt wurde, sollte sie optimal auf die Interaktion mit einem Benutzer reagieren, auch wenn sie gerade mit anderen Aufgaben befasst ist.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-104">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="1f5b9-105">Die Verwendung verschiedener Ausführungsthreads stellt eine der effektivsten Möglichkeiten dar, eine Anwendung entsprechend reaktionsschnell zu gestalten und gleichzeitig den Prozessor zwischen Benutzerereignissen oder sogar währenddessen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-105">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="1f5b9-106">In diesem Abschnitt werden die grundlegenden Threadingkonzepte eingeführt und insbesondere verwaltete Threadingkonzepte und die Verwendung von verwaltetem Threading ausführlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-106">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f5b9-107">Ab .NET Framework 4 wird die Multithreadprogrammierung durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Tasks anstatt von Threads basiert, erheblich vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-107">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="1f5b9-108">Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f5b9-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f5b9-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1f5b9-109">In This Section</span></span>  
 [<span data-ttu-id="1f5b9-110">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="1f5b9-110">Managed Threading Basics</span></span>](managed-threading-basics.md)  
 <span data-ttu-id="1f5b9-111">Enthält eine Übersicht über das verwaltete Threading und erläutert, in welchen Fällen mehrere Threads verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-111">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="1f5b9-112">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="1f5b9-112">Using Threads and Threading</span></span>](using-threads-and-threading.md)  
 <span data-ttu-id="1f5b9-113">Erklärt das Erstellen, Starten, Anhalten, Fortsetzen und Abbrechen von Threads.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-113">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="1f5b9-114">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="1f5b9-114">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="1f5b9-115">Behandelt Synchronisierungsstufen, die Vermeidung von Deadlock- und Racebedingungen und weitere Threadingprobleme.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-115">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="1f5b9-116">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="1f5b9-116">Threading Objects and Features</span></span>](threading-objects-and-features.md)  
 <span data-ttu-id="1f5b9-117">Beschreibt die verwalteten Klassen, mit denen Sie Threadingaktivitäten sowie die Daten von Objekten, auf die in verschiedenen Threads zugegriffen wird, synchronisieren können, und bietet eine Übersicht über Threadpoolthreads.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-117">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1f5b9-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="1f5b9-118">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="1f5b9-119">Enthält Klassen zum Verwenden und Synchronisieren von verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-119">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="1f5b9-120">Enthält Auflistungsklassen, die sicher mit mehreren Threads verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-120">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="1f5b9-121">Enthält Klassen zum Erstellen und Planen von parallelen Verarbeitungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-121">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f5b9-122">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1f5b9-122">Related Sections</span></span>  
 [<span data-ttu-id="1f5b9-123">Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="1f5b9-123">Application Domains</span></span>](../../framework/app-domains/application-domains.md)  
 <span data-ttu-id="1f5b9-124">Übersicht über Anwendungsdomänen und deren Verwendung durch die Common Language-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-124">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="1f5b9-125">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="1f5b9-125">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)  
 <span data-ttu-id="1f5b9-126">Beschreibt die Leistungsvorteile und den grundlegenden Ablauf der asynchronen E/A.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-126">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 [<span data-ttu-id="1f5b9-127">Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)</span><span class="sxs-lookup"><span data-stu-id="1f5b9-127">Task-based Asynchronous Pattern (TAP)</span></span>](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 <span data-ttu-id="1f5b9-128">Bietet eine Übersicht über das empfohlene Muster für asynchrone Programmierung in .NET.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-128">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="1f5b9-129">Asynchrones Aufrufen von synchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="1f5b9-129">Calling Synchronous Methods Asynchronously</span></span>](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="1f5b9-130">Erläutert das Aufrufen von Methoden für Threadpoolthreads mithilfe der integrierten Features von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-130">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="1f5b9-131">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="1f5b9-131">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="1f5b9-132">Beschreibt die parallelen Programmierbibliotheken, die die Verwendung mehrerer Threads in Anwendungen vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-132">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="1f5b9-133">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="1f5b9-133">Parallel LINQ (PLINQ)</span></span>](../parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="1f5b9-134">Beschreibt ein System zum parallelen Ausführen von Abfragen, um die Vorteile mehrerer Prozessoren zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="1f5b9-134">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
