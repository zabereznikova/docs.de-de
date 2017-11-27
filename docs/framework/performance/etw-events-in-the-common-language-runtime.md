---
title: "ETW-Ereignisse in der Common Language Runtime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8313a6b06387f6fd0a5f95191ea57bdf034c372
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="c314f-102">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c314f-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="c314f-103">Die Common Language Runtime (CLR) stellt nützliche Diagnoseinformationen für die Ereignisablaufverfolgung für Windows (ETW) durch eine große Vielfalt von Ereignissen für das Debuggen und die Profilerstellung bereit.</span><span class="sxs-lookup"><span data-stu-id="c314f-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="c314f-104">CLR-ETW-Ereignisse nutzen das Windows-ETW-Ablaufverfolgungssystem, um die bestehende Unterstützung für die Profilerstellung und das Debuggen zu erweitern, die von der Common Language Runtime bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c314f-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="c314f-105">Weitere Informationen zu ETW finden Sie im Artikel [Improve Debugging and Performance Tuning with ETW (Verbessertes Debugging und Leistungsoptimierung mit ETW)](http://go.microsoft.com/fwlink/?LinkID=161142) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="c314f-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="c314f-106">Weitere Informationen zu Xperf finden Sie im Eintrag [Windows Performance Toolkit – Xperf](http://go.microsoft.com/fwlink/?LinkID=161144) im NTDebugging-Blog.</span><span class="sxs-lookup"><span data-stu-id="c314f-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](http://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="c314f-107">Für alle Ereignisse, die in den Themen zu Ereignissen beschrieben werden, ist [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c314f-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="c314f-108">Das Betriebssystem „Windows Vista“ ist die mindestens erforderliche Version für den Client, und Windows Server 2008 ist die mindestens erforderliche Version für den Server.</span><span class="sxs-lookup"><span data-stu-id="c314f-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c314f-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c314f-109">In This Section</span></span>  
 [<span data-ttu-id="c314f-110">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="c314f-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="c314f-111">Beschreibt die Tools und Befehle zum Erfassen und Anzeigen von ETW-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="c314f-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="c314f-112">CLR ETW Providers (CLR-ETW-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="c314f-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="c314f-113">Bietet Informationen zu den Runtime- und Rundownanbietern, und wie Sie diese für die ETW-Datensammlung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="c314f-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="c314f-114">CLR ETW Keywords and Levels (CLR-ETW-Schlüsselwörter und -Ebenen)</span><span class="sxs-lookup"><span data-stu-id="c314f-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="c314f-115">Beschreibt die Schlüsselwörter für die Runtime- und Rundownanbieter, die das Filtern der Ereignisse nach Kategorie ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c314f-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="c314f-116">CLR ETW Events (CLR-ETW-Ereignisse)</span><span class="sxs-lookup"><span data-stu-id="c314f-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="c314f-117">Bietet detaillierte Informationen zu CLR-ETW-Ereignissen sowie zu deren Schlüsselwörtern, Ebenen und Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="c314f-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c314f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c314f-118">See Also</span></span>  
 [<span data-ttu-id="c314f-119">ETW Events in the .NET Framework (ETW-Ereignisse in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="c314f-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
