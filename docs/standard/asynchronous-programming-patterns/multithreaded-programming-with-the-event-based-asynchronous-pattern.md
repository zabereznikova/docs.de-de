---
title: Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6d93e449877456e415ebd4d3490a7df99280e7e5
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="5e0be-102">Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster</span><span class="sxs-lookup"><span data-stu-id="5e0be-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="5e0be-103">Es gibt verschiedene Möglichkeiten, asynchrone Funktionen für Clientcode verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="5e0be-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="5e0be-104">Das ereignisbasierte asynchrone Muster gibt Klassen das empfohlene Verfahren zum Präsentieren von asynchronem Verhalten vor.</span><span class="sxs-lookup"><span data-stu-id="5e0be-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e0be-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5e0be-105">In This Section</span></span>  
 [<span data-ttu-id="5e0be-106">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="5e0be-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="5e0be-107">Beschreibt, wie das ereignisbasierte asynchrone Muster die Vorteile von Multithreadanwendungen bietet und gleichzeitig viele komplexe Aspekte des Multithreaddesigns verbirgt.</span><span class="sxs-lookup"><span data-stu-id="5e0be-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="5e0be-108">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="5e0be-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5e0be-109">Beschreibt das standardisierte Verfahren zum Verpacken einer Klasse, die über asynchrone Funktionen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5e0be-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="5e0be-110">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="5e0be-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5e0be-111">Beschreibt die Anforderungen, die zum Verfügbarmachen asynchroner Funktionen nach dem ereignisbasierten asynchronen Muster erfüllt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="5e0be-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="5e0be-112">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="5e0be-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5e0be-113">Beschreibt, wie Sie ermitteln, ob Sie das ereignisbasierte asynchrone Muster anstelle des <xref:System.IAsyncResult>-Musters implementieren sollen.</span><span class="sxs-lookup"><span data-stu-id="5e0be-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="5e0be-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern (Exemplarische Vorgehensweise: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt)</span><span class="sxs-lookup"><span data-stu-id="5e0be-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5e0be-115">Veranschaulicht das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert.</span><span class="sxs-lookup"><span data-stu-id="5e0be-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="5e0be-116">Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="5e0be-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="5e0be-117">How to: Use Components That Support the Event-based Asynchronous Pattern (Vorgehensweise: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen)</span><span class="sxs-lookup"><span data-stu-id="5e0be-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="5e0be-118">Beschreibt die Verwendung einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e0be-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e0be-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="5e0be-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="5e0be-120">Beschreibt die <xref:System.ComponentModel.AsyncOperation>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="5e0be-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="5e0be-121">Beschreibt die <xref:System.ComponentModel.AsyncOperationManager>-Klasse und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="5e0be-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="5e0be-122">Beschreibt die <xref:System.ComponentModel.BackgroundWorker>-Komponente und enthält Links zu allen Membern.</span><span class="sxs-lookup"><span data-stu-id="5e0be-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0be-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e0be-123">See Also</span></span>  
 [<span data-ttu-id="5e0be-124">Empfohlene Vorgehensweise für das verwaltete Threading</span><span class="sxs-lookup"><span data-stu-id="5e0be-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="5e0be-125">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="5e0be-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="5e0be-126">Multithreading in Komponenten</span><span class="sxs-lookup"><span data-stu-id="5e0be-126">Multithreading in Components</span></span>](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="5e0be-127">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="5e0be-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
