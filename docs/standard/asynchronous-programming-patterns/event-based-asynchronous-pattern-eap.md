---
title: Ereignisbasiertes asynchrones Muster (EAP)
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: ee8c90d63478e444b7d25cb7cbb5c969963d7c63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73130941"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="8cfc9-102">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-102">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="8cfc9-103">Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="8cfc9-104">Das ereignisbasierte asynchrone Muster gibt Klassen ein Verfahren zum Präsentieren von asynchronem Verhalten vor.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cfc9-105">Ab .NET Framework 4 stellt die Task Parallel Library ein neues Modell für die asynchrone und parallele Programmierung bereit.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-105">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="8cfc9-106">Weitere Informationen finden Sie unter [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) und [Task-based Asynchronous Pattern (TAP) (Aufgabenbasiertes asynchrones Muster)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="8cfc9-106">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8cfc9-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8cfc9-107">In This Section</span></span>

 [<span data-ttu-id="8cfc9-108">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-108">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="8cfc9-109">Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="8cfc9-110">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="8cfc9-110">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-111">Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Funktionen verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="8cfc9-112">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="8cfc9-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-113">Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Funktionen nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="8cfc9-114">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-115">Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>-Musters implementieren sollen, das vom [Asynchronous Programming Model (APM) (Asynchrones Programmiermodell)](asynchronous-programming-model-apm.md) dargestellt wird</span><span class="sxs-lookup"><span data-stu-id="8cfc9-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="8cfc9-116">Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt</span><span class="sxs-lookup"><span data-stu-id="8cfc9-116">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-117">Beschreibt das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-117">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="8cfc9-118">Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="8cfc9-119">Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="8cfc9-119">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-120">Beschreibt das Erstellen eines Clients, der das ereignisbasierte asynchrone Muster implementiert.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-120">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="8cfc9-121">How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-121">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="8cfc9-122">Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-122">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8cfc9-123">Verweis</span><span class="sxs-lookup"><span data-stu-id="8cfc9-123">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="8cfc9-124">Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-124">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="8cfc9-125">Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-125">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="8cfc9-126">Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-126">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8cfc9-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8cfc9-127">Related Sections</span></span>

 [<span data-ttu-id="8cfc9-128">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-128">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="8cfc9-129">Beschreibt ein Programmiermodell für asynchrone und parallele Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-129">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="8cfc9-130">Threading</span><span class="sxs-lookup"><span data-stu-id="8cfc9-130">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="8cfc9-131">Beschreibt Multithreadingfunktionen in .NET.</span><span class="sxs-lookup"><span data-stu-id="8cfc9-131">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cfc9-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8cfc9-132">See also</span></span>

- [<span data-ttu-id="8cfc9-133">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="8cfc9-133">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="8cfc9-134">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8cfc9-134">Events</span></span>](../events/index.md)
- [<span data-ttu-id="8cfc9-135">Asynchronous Programming Design Patterns (Entwurfsmuster für die asynchrone Programmierung)</span><span class="sxs-lookup"><span data-stu-id="8cfc9-135">Asynchronous Programming Design Patterns</span></span>](index.md)
