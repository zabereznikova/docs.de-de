---
title: Thread.Suspend, Garbage Collection und Sicherungspunkte
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3af01167fe97b701bdb0c7bc37af02d8e8a77c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004178"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="1b686-102">Thread.Suspend, Garbage Collection und Sicherungspunkte</span><span class="sxs-lookup"><span data-stu-id="1b686-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="1b686-103">Beim Aufruf von <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> in einem Thread hält das System fest, dass eine Threadunterbrechung angefordert wurde, und ermöglicht vor dem Unterbrechen des Threads dessen Ausführung bis zu einem sicheren Punkt.</span><span class="sxs-lookup"><span data-stu-id="1b686-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="1b686-104">Ein sicherer Punkt für einen Thread ist ein Punkt in seiner Ausführung, an dem eine Garbage Collection durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b686-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="1b686-105">Sobald ein sicherer Punkt erreicht ist, garantiert die Runtime, dass der unterbrochene Thread in verwaltetem Code nicht weiter fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="1b686-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="1b686-106">Ein außerhalb von verwaltetem Code ausgeführter Thread ist stets sicher für die Garbage Collection, und dessen Ausführung wird fortgeführt, bis er versucht, die Ausführung von verwaltetem Code fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1b686-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b686-107">Um eine Garbage Collection auszuführen, muss die Runtime alle Threads mit Ausnahme des Threads, der die Collection durchführt, unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="1b686-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="1b686-108">Jeder Thread muss an einen sicheren Punkt gebracht werden, bevor er unterbrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b686-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b686-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b686-109">See also</span></span>

- <xref:System.Threading.Thread>  
- <xref:System.GC>  
- [<span data-ttu-id="1b686-110">Threading</span><span class="sxs-lookup"><span data-stu-id="1b686-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="1b686-111">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="1b686-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
