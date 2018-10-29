---
title: ManualResetEvent und ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85d0c5c291743c6daac549e15d479fcf332235c
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452822"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="53c37-102">ManualResetEvent und ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="53c37-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="53c37-103">Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse stellt ein lokales Wait-Handleereignis dar, das manuell zurückgesetzt werden muss, nachdem es signalisiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="53c37-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="53c37-104">Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> dar.</span><span class="sxs-lookup"><span data-stu-id="53c37-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="53c37-105">Weitere Informationen zur Verwendung und zu den Features manueller Reset-Ereignisse finden Sie in der Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="53c37-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="53c37-106">Ein <xref:System.Threading.ManualResetEvent>-Objekt bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="53c37-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="53c37-107">Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="53c37-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="53c37-108">In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie für eine bessere Leistung die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse verwenden, wenn die Wartezeiten als sehr kurz eingeschätzt werden und das Ereignis nicht prozessübergreifend ist.</span><span class="sxs-lookup"><span data-stu-id="53c37-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="53c37-109"><xref:System.Threading.ManualResetEventSlim> verwendet während des Wartens auf die Signalisierung des Ereignisses für kurze Zeit ausgelastete Spinvorgänge.</span><span class="sxs-lookup"><span data-stu-id="53c37-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="53c37-110">Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait-Handles.</span><span class="sxs-lookup"><span data-stu-id="53c37-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="53c37-111">Wenn das Ereignis jedoch nicht innerhalb eines bestimmten Zeitraums signalisiert wird, greift <xref:System.Threading.ManualResetEventSlim> auf einen normalen Wartevorgang mit Ereignishandle zurück.</span><span class="sxs-lookup"><span data-stu-id="53c37-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c37-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53c37-112">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="53c37-113">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="53c37-113">AutoResetEvent</span></span>](autoresetevent.md)  
- [<span data-ttu-id="53c37-114">SpinWait</span><span class="sxs-lookup"><span data-stu-id="53c37-114">SpinWait</span></span>](spinwait.md)  
- [<span data-ttu-id="53c37-115">Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="53c37-115">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)
- [<span data-ttu-id="53c37-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="53c37-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="53c37-117">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="53c37-117">Threading objects and features</span></span>](threading-objects-and-features.md)  
- [<span data-ttu-id="53c37-118">Threading</span><span class="sxs-lookup"><span data-stu-id="53c37-118">Threading</span></span>](index.md)  
