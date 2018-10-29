---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583151"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="d6ef7-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="d6ef7-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>

<span data-ttu-id="d6ef7-103">Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="d6ef7-104">Diese Synchronisierungsereignisse beruhen auf Wait-Handles des Betriebssystems und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-104">These synchronization events are based on operating system wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
<span data-ttu-id="d6ef7-105">Wait-Handles für ein Ereignis sind in vielen Synchronisierungsszenarien nützlich, in denen auch die <xref:System.Threading.Monitor>-Klasse eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="d6ef7-106">Wait-Handles für ein Ereignis sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>- und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>-Methode, und sie bieten stärkere Kontrolle über die Signalisierung.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="d6ef7-107">Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6ef7-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d6ef7-108">In this section</span></span>

 [<span data-ttu-id="d6ef7-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="d6ef7-109">EventWaitHandle</span></span>](eventwaithandle.md)  
 <span data-ttu-id="d6ef7-110">Die <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>-Klasse kann entweder automatische oder manuelle Zurücksetzungsereignisse sowie entweder lokale Ereignisse oder benannte Systemereignisse darstellen.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-110">The <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="d6ef7-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="d6ef7-111">AutoResetEvent</span></span>](autoresetevent.md)  
 <span data-ttu-id="d6ef7-112">Die <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das automatisch zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-112">The <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="d6ef7-113">ManualResetEvent und ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="d6ef7-113">ManualResetEvent and ManualResetEventSlim</span></span>](manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="d6ef7-114">Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das manuell zurückgesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-114">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="d6ef7-115">Die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-115">The <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="d6ef7-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="d6ef7-116">CountdownEvent</span></span>](countdownevent.md)  
 <span data-ttu-id="d6ef7-117">Die <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>-Klasse bietet eine vereinfachte Möglichkeit zum Implementieren von Fork/Join-Parallelismusmustern in Code, in dem Wait-Handle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6ef7-117">The <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d6ef7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6ef7-118">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [<span data-ttu-id="d6ef7-119">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="d6ef7-119">Threading objects and features</span></span>](threading-objects-and-features.md)
- <span data-ttu-id="d6ef7-120">[Managed Threading Basics](managed-threading-basics.md) (Grundlagen des verwalteten Threadings)</span><span class="sxs-lookup"><span data-stu-id="d6ef7-120">[Managed threading basics](managed-threading-basics.md)</span></span>
