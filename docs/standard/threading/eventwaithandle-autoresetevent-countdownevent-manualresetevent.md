---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f61e614696e731a85a030e34aa4356137d9000d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260148"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="753d4-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="753d4-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="753d4-103">Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten.</span><span class="sxs-lookup"><span data-stu-id="753d4-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="753d4-104">Diese Synchronisierungsereignisse beruhen auf Win32-Wait-Handles und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="753d4-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="753d4-105">Wait-Handles für ein Ereignis sind in vielen Synchronisierungsszenarien nützlich, in denen auch die <xref:System.Threading.Monitor>-Klasse eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="753d4-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="753d4-106">Wait-Handles für ein Ereignis sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>- und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>-Methode, und sie bieten stärkere Kontrolle über die Signalisierung.</span><span class="sxs-lookup"><span data-stu-id="753d4-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="753d4-107">Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="753d4-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="753d4-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="753d4-108">In This Section</span></span>  
 [<span data-ttu-id="753d4-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="753d4-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="753d4-110">Die <xref:System.Threading.EventWaitHandle>-Klasse kann entweder automatische oder manuelle Zurücksetzungsereignisse sowie entweder lokale Ereignisse oder benannte Systemereignisse darstellen.</span><span class="sxs-lookup"><span data-stu-id="753d4-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="753d4-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="753d4-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="753d4-112">Die <xref:System.Threading.AutoResetEvent>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das automatisch zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="753d4-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="753d4-113">ManualResetEvent und ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="753d4-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="753d4-114">Die <xref:System.Threading.ManualResetEvent>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das manuell zurückgesetzt werden muss.</span><span class="sxs-lookup"><span data-stu-id="753d4-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="753d4-115">Die <xref:System.Threading.ManualResetEventSlim>-Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="753d4-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="753d4-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="753d4-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="753d4-117">Die <xref:System.Threading.CountdownEvent>-Klasse bietet eine vereinfachte Möglichkeit zum Implementieren von Fork/Join-Parallelismusmustern in Code, in dem Wait-Handle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="753d4-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="753d4-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="753d4-118">Related Sections</span></span>  
 [<span data-ttu-id="753d4-119">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="753d4-119">Wait Handles</span></span>](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="753d4-120">Die <xref:System.Threading.WaitHandle>-Klasse ist die Basisklasse für die <xref:System.Threading.EventWaitHandle>-, <xref:System.Threading.Semaphore>- und <xref:System.Threading.Mutex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="753d4-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="753d4-121">Sie enthält statische Methoden wie <xref:System.Threading.WaitHandle.SignalAndWait%2A> und <xref:System.Threading.WaitHandle.WaitAll%2A>, die bei der Arbeit mit allen Typen von Wait-Handles hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="753d4-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753d4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="753d4-122">See also</span></span>

- <xref:System.Threading.EventWaitHandle>  
- <xref:System.Threading.WaitHandle>  
- <xref:System.Threading.AutoResetEvent>  
- <xref:System.Threading.ManualResetEvent>  
- [<span data-ttu-id="753d4-123">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="753d4-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="753d4-124">Grundlagen des verwalteten Threadings</span><span class="sxs-lookup"><span data-stu-id="753d4-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
