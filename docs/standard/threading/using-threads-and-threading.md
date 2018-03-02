---
title: Verwenden von Threads und Threading
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
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5bed13950a29cfa787ef8c9eb2608c6d74dfd49f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="87fc8-102">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="87fc8-102">Using Threads and Threading</span></span>
<span data-ttu-id="87fc8-103">Die Themen in diesem Abschnitt erläutern die Erstellung und Verwaltung von verwalteten Threads, das Übergeben von Daten an verwaltete Threads und Abrufen der Ergebnisse sowie das Zerstören von Threads und Behandeln einer <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="87fc8-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87fc8-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="87fc8-104">In This Section</span></span>  
 [<span data-ttu-id="87fc8-105">Erstellen von Threads und Übergeben von Daten zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="87fc8-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="87fc8-106">Erläutert und veranschaulicht die Erstellung von verwalteten Threads einschließlich der Übergabe von Daten an neue Threads und des Abrufens von Daten.</span><span class="sxs-lookup"><span data-stu-id="87fc8-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="87fc8-107">Anhalten und Fortsetzen von Threads</span><span class="sxs-lookup"><span data-stu-id="87fc8-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="87fc8-108">Erläutert die Auswirkungen des Anhaltens und Fortsetzens verwalteter Threads.</span><span class="sxs-lookup"><span data-stu-id="87fc8-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="87fc8-109">Zerstören von Threads</span><span class="sxs-lookup"><span data-stu-id="87fc8-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="87fc8-110">Erläutert die Konsequenzen der Zerstörung verwalteter Threads und das Behandeln einer <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="87fc8-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="87fc8-111">Scheduling von Threads</span><span class="sxs-lookup"><span data-stu-id="87fc8-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="87fc8-112">Erläutert Threadprioritäten und deren Einfluss auf die Threadplanung.</span><span class="sxs-lookup"><span data-stu-id="87fc8-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87fc8-113">Verweis</span><span class="sxs-lookup"><span data-stu-id="87fc8-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="87fc8-114">Stellt die Referenzdokumentation für die <xref:System.Threading.Thread>-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="87fc8-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="87fc8-115">Enthält die Referenzdokumentation für den <xref:System.Threading.ThreadStart>-Delegaten, der parameterlose Threadprozeduren darstellt.</span><span class="sxs-lookup"><span data-stu-id="87fc8-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="87fc8-116">Bietet eine einfache Möglichkeit, Daten an eine Threadprozedur zu übergeben, allerdings ohne starke Typisierung.</span><span class="sxs-lookup"><span data-stu-id="87fc8-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="87fc8-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="87fc8-117">Related Sections</span></span>  
 [<span data-ttu-id="87fc8-118">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="87fc8-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="87fc8-119">Bietet eine Einführung zu verwaltetem Threading.</span><span class="sxs-lookup"><span data-stu-id="87fc8-119">Provides an introduction to managed threading.</span></span>
