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
ms.openlocfilehash: 7602a61a4403b7ab85015876823aa41e250b23de
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863308"
---
# <a name="autoresetevent"></a><span data-ttu-id="d7390-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="d7390-102">AutoResetEvent</span></span>
<span data-ttu-id="d7390-103">Die <xref:System.Threading.AutoResetEvent>-Klasse stellt ein lokales Wait-Handleereignis dar, das, sofern es den Zustand „signalisiert“ aufweist, automatisch zurückgesetzt wird, nachdem ein einzelner wartender Thread freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d7390-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="d7390-104">Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle> dar.</span><span class="sxs-lookup"><span data-stu-id="d7390-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="d7390-105">Informationen zur Verwendung und zu den Features von Ereignissen für automatisches Zurücksetzen finden Sie in der Dokumentation zu [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="d7390-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="d7390-106">Ein <xref:System.Threading.AutoResetEvent>-Objekt wird nach der Freigabe eines einzelnen wartenden Threads vom System automatisch auf den Zustand „nicht signalisiert“ zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d7390-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="d7390-107">Wenn sich keine Threads in Warteposition befinden, verbleibt das Ereignisobjekt im signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="d7390-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="d7390-108"><xref:System.Threading.AutoResetEvent> entspricht einem Win32-`CreateEvent`-Aufruf, wobei `false` für das `bManualReset`-Argument angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7390-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="d7390-109">Ein Beispiel, in dem <xref:System.Threading.AutoResetEvent> verwendet wird, finden Sie unter <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="d7390-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7390-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7390-110">See also</span></span>

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [<span data-ttu-id="d7390-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="d7390-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="d7390-112">Threading</span><span class="sxs-lookup"><span data-stu-id="d7390-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="d7390-113">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="d7390-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="d7390-114">Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="d7390-114">Wait Handles</span></span>](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
