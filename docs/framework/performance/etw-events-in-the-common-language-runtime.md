---
title: ETW-Ereignisse in der Common Language Runtime
description: Lesen Sie eine Zusammenfassung und Links zu Ereignissen der Ereignis Ablauf Verfolgung für Windows (ETW) im Common Language Runtime (CLR).
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: aa422dcb7efbc0f6f7f09e09a6c9e44b40ada86b
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309481"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="6d800-103">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6d800-103">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="6d800-104">Die Common Language Runtime (CLR) stellt nützliche Diagnoseinformationen für die Ereignisablaufverfolgung für Windows (ETW) durch eine große Vielfalt von Ereignissen für das Debuggen und die Profilerstellung bereit.</span><span class="sxs-lookup"><span data-stu-id="6d800-104">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="6d800-105">CLR-ETW-Ereignisse nutzen das Windows-ETW-Ablaufverfolgungssystem, um die bestehende Unterstützung für die Profilerstellung und das Debuggen zu erweitern, die von der Common Language Runtime bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6d800-105">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="6d800-106">Weitere Informationen zu etw finden Sie im Artikel [verbessern der Debuggen und Leistungsoptimierung mit etw](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="6d800-106">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="6d800-107">Weitere Informationen zu Xperf finden Sie im Eintrag [Windows Performance Toolkit – Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) im NTDebugging-Blog.</span><span class="sxs-lookup"><span data-stu-id="6d800-107">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="6d800-108">Der .NET Framework 4 oder höher ist für alle in den Ereignis Themen beschriebenen Ereignisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6d800-108">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="6d800-109">Das Betriebssystem „Windows Vista“ ist die mindestens erforderliche Version für den Client, und Windows Server 2008 ist die mindestens erforderliche Version für den Server.</span><span class="sxs-lookup"><span data-stu-id="6d800-109">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d800-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6d800-110">In This Section</span></span>  
 [<span data-ttu-id="6d800-111">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d800-111">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="6d800-112">Beschreibt die Tools und Befehle zum Erfassen und Anzeigen von ETW-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="6d800-112">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="6d800-113">CLR-ETW-Anbieter</span><span class="sxs-lookup"><span data-stu-id="6d800-113">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="6d800-114">Bietet Informationen zu den Runtime- und Rundownanbietern, und wie Sie diese für die ETW-Datensammlung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="6d800-114">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="6d800-115">CLR-ETW-Schlüsselwörter und -Ebenen</span><span class="sxs-lookup"><span data-stu-id="6d800-115">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="6d800-116">Beschreibt die Schlüsselwörter für die Runtime- und Rundownanbieter, die das Filtern der Ereignisse nach Kategorie ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6d800-116">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="6d800-117">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6d800-117">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="6d800-118">Bietet detaillierte Informationen zu CLR-ETW-Ereignissen sowie zu deren Schlüsselwörtern, Ebenen und Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="6d800-118">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d800-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d800-119">See also</span></span>

- [<span data-ttu-id="6d800-120">ETW-Ereignisse in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d800-120">ETW Events in the .NET Framework</span></span>](etw-events.md)
