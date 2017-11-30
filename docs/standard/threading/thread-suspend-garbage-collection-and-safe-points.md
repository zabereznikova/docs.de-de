---
title: "Thread.Suspend, Garbage Collection und Sicherungspunkte"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="798ba-102">Thread.Suspend, Garbage Collection und Sicherungspunkte</span><span class="sxs-lookup"><span data-stu-id="798ba-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="798ba-103">Beim Aufruf <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> in einem Thread im System fest, dass eine Threadunterbrechung wurde angefordert, und dem Thread ermöglicht ausgeführt, bis er einem sicheren Zeitpunkt erreicht hat, vor dem Anhalten des Threads.</span><span class="sxs-lookup"><span data-stu-id="798ba-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="798ba-104">Einem sicheren Zeitpunkt für einen Thread ist ein Verwaltungspunkt in seiner Ausführung Garbage Collection durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="798ba-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="798ba-105">Nach einem sicheren Zeitpunkt erreicht wird, garantiert die Common Language Runtime an, dass der unterbrochene Thread in verwaltetem Code nicht weiteren fortgesetzt tätigt.</span><span class="sxs-lookup"><span data-stu-id="798ba-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="798ba-106">Ein Thread für die Ausführung außerhalb von verwaltetem Code ist sicherer, für die Garbagecollection und dessen Ausführung wird fortgeführt, bis er versucht, die Ausführung von verwaltetem Code fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="798ba-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="798ba-107">Um eine Garbagecollection auszuführen, muss die Common Language Runtime alle Threads mit Ausnahme des Threads, die mit der Durchführung der Collection angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="798ba-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="798ba-108">Jeder Thread muss an einem sicheren Zeitpunkt gebracht werden, bevor es angehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="798ba-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798ba-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="798ba-109">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [<span data-ttu-id="798ba-110">Threading</span><span class="sxs-lookup"><span data-stu-id="798ba-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="798ba-111">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="798ba-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
