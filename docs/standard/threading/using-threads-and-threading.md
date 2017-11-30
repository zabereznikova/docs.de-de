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
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80eb4c3bb98acdd1f83dbf5bcf57b2f7b295742b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="5b0e7-102">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="5b0e7-102">Using Threads and Threading</span></span>
<span data-ttu-id="5b0e7-103">Die Themen in diesem Abschnitt erläutert die Erstellung und Verwaltung von verwalteten Threads, die zum Übergeben von Daten an verwaltete Threads und Abrufen von Ergebnissen und das Zerstören von Threads und Behandeln einer <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b0e7-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b0e7-104">In This Section</span></span>  
 [<span data-ttu-id="5b0e7-105">Erstellen von Threads und Übergeben von Daten zur Startzeit</span><span class="sxs-lookup"><span data-stu-id="5b0e7-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="5b0e7-106">Erläutert und veranschaulicht die Erstellung von verwalteten Threads, einschließlich der Übergabe von Daten für neue Threads und zum Abrufen von Daten.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="5b0e7-107">Anhalten und Fortsetzen von Threads</span><span class="sxs-lookup"><span data-stu-id="5b0e7-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="5b0e7-108">Erläutert die Auswirkungen des Anhaltens und fortsetzens verwaltete Threads an.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="5b0e7-109">Zerstören von Threads</span><span class="sxs-lookup"><span data-stu-id="5b0e7-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="5b0e7-110">Erläutert die Konsequenzen der Zerstörung verwaltete Threads und zum Behandeln einer <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="5b0e7-111">Scheduling von Threads</span><span class="sxs-lookup"><span data-stu-id="5b0e7-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="5b0e7-112">Erläutert Threadprioritäten und deren Threadplanung Einfluss auf.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5b0e7-113">Verweis</span><span class="sxs-lookup"><span data-stu-id="5b0e7-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="5b0e7-114">Enthält die Referenzdokumentation für die <xref:System.Threading.Thread> Klasse, die einen verwalteten Thread darstellt, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="5b0e7-115">Enthält die Referenzdokumentation für die <xref:System.Threading.ThreadStart> Delegat, parameterlosen Threadprozeduren darstellt.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="5b0e7-116">Bietet eine einfache Möglichkeit, Daten an eine Threadprozedur übergeben allerdings ohne starke Typisierung.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5b0e7-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5b0e7-117">Related Sections</span></span>  
 [<span data-ttu-id="5b0e7-118">Threads and Threading (Threads und Threading)</span><span class="sxs-lookup"><span data-stu-id="5b0e7-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="5b0e7-119">Bietet eine Einführung zum verwalteten threading.</span><span class="sxs-lookup"><span data-stu-id="5b0e7-119">Provides an introduction to managed threading.</span></span>
