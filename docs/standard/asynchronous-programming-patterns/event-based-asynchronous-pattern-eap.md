---
title: Ereignisbasiertes asynchrones Muster (EAP)
description: Links zu Artikeln zu ereignisbasierten asynchronen Mustern (Event-based Asynchronous Pattern, EAP) in .NET, z. B. zur Implementierung, zu bewährten Methoden und zur Implementierung eines EAP-Clients
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768871"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="484a4-103">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="484a4-103">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="484a4-104">Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="484a4-104">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="484a4-105">Das ereignisbasierte asynchrone Muster gibt Klassen ein Verfahren zum Präsentieren von asynchronem Verhalten vor.</span><span class="sxs-lookup"><span data-stu-id="484a4-105">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="484a4-106">Ab .NET Framework 4 stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit.</span><span class="sxs-lookup"><span data-stu-id="484a4-106">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="484a4-107">Weitere Informationen finden Sie unter [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) und [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="484a4-107">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="484a4-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="484a4-108">In This Section</span></span>

 [<span data-ttu-id="484a4-109">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="484a4-109">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="484a4-110">Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.</span><span class="sxs-lookup"><span data-stu-id="484a4-110">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="484a4-111">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="484a4-111">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-112">Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Funktionen verfügt.</span><span class="sxs-lookup"><span data-stu-id="484a4-112">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="484a4-113">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="484a4-113">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-114">Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Funktionen nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="484a4-114">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="484a4-115">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="484a4-115">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-116">Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>-Musters implementieren sollen, das vom [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell)](asynchronous-programming-model-apm.md) dargestellt wird</span><span class="sxs-lookup"><span data-stu-id="484a4-116">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="484a4-117">How to: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen</span><span class="sxs-lookup"><span data-stu-id="484a4-117">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-118">Beschreibt das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert.</span><span class="sxs-lookup"><span data-stu-id="484a4-118">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="484a4-119">Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="484a4-119">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="484a4-120">How to: Implementieren eines Clients des ereignisbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="484a4-120">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-121">Beschreibt das Erstellen eines Clients, der das ereignisbasierte asynchrone Muster implementiert.</span><span class="sxs-lookup"><span data-stu-id="484a4-121">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="484a4-122">How to: How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)</span><span class="sxs-lookup"><span data-stu-id="484a4-122">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="484a4-123">Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="484a4-123">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="484a4-124">Referenz</span><span class="sxs-lookup"><span data-stu-id="484a4-124">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="484a4-125">Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="484a4-125">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="484a4-126">Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="484a4-126">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="484a4-127">Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="484a4-127">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="484a4-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="484a4-128">Related Sections</span></span>

 [<span data-ttu-id="484a4-129">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="484a4-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="484a4-130">Beschreibt ein Programmiermodell für asynchrone und parallele Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="484a4-130">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="484a4-131">Threading</span><span class="sxs-lookup"><span data-stu-id="484a4-131">Threading</span></span>](../threading/index.md)  
 <span data-ttu-id="484a4-132">Beschreibt Multithreadingfunktionen in .NET.</span><span class="sxs-lookup"><span data-stu-id="484a4-132">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="484a4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="484a4-133">See also</span></span>

- [<span data-ttu-id="484a4-134">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="484a4-134">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="484a4-135">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="484a4-135">Events</span></span>](../events/index.md)
- [<span data-ttu-id="484a4-136">Asynchronous Programming Design Patterns (Entwurfsmuster für die asynchrone Programmierung)</span><span class="sxs-lookup"><span data-stu-id="484a4-136">Asynchronous Programming Design Patterns</span></span>](index.md)
