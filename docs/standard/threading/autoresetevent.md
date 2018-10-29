---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 519776b5c1c237deb520476384495b8dd96a4e39
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201305"
---
# <a name="autoresetevent"></a><span data-ttu-id="8f6fb-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="8f6fb-102">AutoResetEvent</span></span>
<span data-ttu-id="8f6fb-103">Die <xref:System.Threading.AutoResetEvent>-Klasse stellt ein lokales Wait-Handleereignis dar, das, sofern es den Zustand „signalisiert“ aufweist, automatisch zurückgesetzt wird, nachdem ein einzelner wartender Thread freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8f6fb-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="8f6fb-104">Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle> dar.</span><span class="sxs-lookup"><span data-stu-id="8f6fb-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="8f6fb-105">Informationen zur Verwendung und zu den Features von Ereignissen für automatisches Zurücksetzen finden Sie in der Dokumentation zu [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="8f6fb-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="8f6fb-106">Ein <xref:System.Threading.AutoResetEvent>-Objekt wird nach der Freigabe eines einzelnen wartenden Threads vom System automatisch auf den Zustand „nicht signalisiert“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f6fb-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="8f6fb-107">Wenn sich keine Threads in Warteposition befinden, verbleibt das Ereignisobjekt im signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="8f6fb-107">If no threads are waiting, the event object's state remains signaled.</span></span>
  
 <span data-ttu-id="8f6fb-108">Ein Beispiel, in dem <xref:System.Threading.AutoResetEvent> verwendet wird, finden Sie unter <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="8f6fb-108">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6fb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f6fb-109">See also</span></span>

- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="8f6fb-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="8f6fb-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="8f6fb-111">Threadingobjekte und -funktionen</span><span class="sxs-lookup"><span data-stu-id="8f6fb-111">Threading objects and features</span></span>](threading-objects-and-features.md)  
- [<span data-ttu-id="8f6fb-112">Threading</span><span class="sxs-lookup"><span data-stu-id="8f6fb-112">Threading</span></span>](index.md)  
