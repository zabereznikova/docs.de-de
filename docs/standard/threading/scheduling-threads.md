---
title: Scheduling von Threads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6bb715c11cc0d9b07e4ea8805ace7680ca92097c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="scheduling-threads"></a><span data-ttu-id="c435d-102">Scheduling von Threads</span><span class="sxs-lookup"><span data-stu-id="c435d-102">Scheduling Threads</span></span>
<span data-ttu-id="c435d-103">Jedem Thread ist eine Threadpriorität zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c435d-103">Every thread has a thread priority assigned to it.</span></span> <span data-ttu-id="c435d-104">Threads, die innerhalb der Common Language Runtime erstellt werden, erhalten anfänglich die Priorität **ThreadPriority.Normal**.</span><span class="sxs-lookup"><span data-stu-id="c435d-104">Threads created within the common language runtime are initially assigned the priority of **ThreadPriority.Normal**.</span></span> <span data-ttu-id="c435d-105">Threads, die außerhalb der Runtime erstellt werden, behalten die Priorität bei, die sie vor dem Eintritt in die verwaltete Umgebung innehatten.</span><span class="sxs-lookup"><span data-stu-id="c435d-105">Threads created outside the runtime retain the priority they had before they entered the managed environment.</span></span> <span data-ttu-id="c435d-106">Sie können die Priorität jedes Threads mithilfe der **Thread.Priority**-Eigenschaft abrufen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="c435d-106">You can get or set the priority of any thread with the **Thread.Priority** property.</span></span>  
  
 <span data-ttu-id="c435d-107">Die Ausführung von Threads wird basierend auf ihrer Priorität geplant.</span><span class="sxs-lookup"><span data-stu-id="c435d-107">Threads are scheduled for execution based on their priority.</span></span> <span data-ttu-id="c435d-108">Auch wenn Threads innerhalb der Runtime ausgeführt werden, weist das Betriebssystem allen Threads Prozessorzeitsegmente zu.</span><span class="sxs-lookup"><span data-stu-id="c435d-108">Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.</span></span> <span data-ttu-id="c435d-109">Die Details des Planungsalgorithmus, der zum Ermitteln der Ausführungsreihenfolge der Threads verwendet wird, variieren je nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="c435d-109">The details of the scheduling algorithm used to determine the order in which threads are executed varies with each operating system.</span></span> <span data-ttu-id="c435d-110">In einigen Betriebssystemen erfolgt die Planung so, dass der Thread mit der höchsten Priorität (aller ausführbaren Threads) immer zuerst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c435d-110">Under some operating systems, the thread with the highest priority (of those threads that can be executed) is always scheduled to run first.</span></span> <span data-ttu-id="c435d-111">Wenn mehrere Threads mit der gleichen Priorität verfügbar sind, durchläuft der Planer diese Threads und weist jedem Thread ein festgelegtes Zeitsegment zu, innerhalb dessen die Ausführung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c435d-111">If multiple threads with the same priority are all available, the scheduler cycles through the threads at that priority, giving each thread a fixed time slice in which to execute.</span></span> <span data-ttu-id="c435d-112">Solange ein Thread mit höherer Priorität für die Ausführung verfügbar ist, werden Threads mit niedrigerer Priorität nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c435d-112">As long as a thread with a higher priority is available to run, lower priority threads do not get to execute.</span></span> <span data-ttu-id="c435d-113">Wenn keine ausführbaren Threads mit einer bestimmten Priorität mehr verfügbar sind, fährt der Planer mit der nächstniedrigeren Priorität fort und plant die Ausführung der Threads mit dieser Priorität.</span><span class="sxs-lookup"><span data-stu-id="c435d-113">When there are no more runnable threads at a given priority, the scheduler moves to the next lower priority and schedules the threads at that priority for execution.</span></span> <span data-ttu-id="c435d-114">Wenn ein Thread mit einer höheren Priorität für die Ausführung verfügbar wird, erhält er Vorrang vor dem Thread mit der niedrigeren Priorität und wird erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c435d-114">If a higher priority thread becomes runnable, the lower priority thread is preempted and the higher priority thread is allowed to execute once again.</span></span> <span data-ttu-id="c435d-115">Darüber hinaus kann das Betriebssystem Threadprioritäten auch dynamisch anpassen, wenn die Benutzeroberfläche einer Anwendung vom Vordergrund in den Hintergrund oder zurück wechselt.</span><span class="sxs-lookup"><span data-stu-id="c435d-115">On top of all that, the operating system can also adjust thread priorities dynamically as an application's user interface is moved between foreground and background.</span></span> <span data-ttu-id="c435d-116">Andere Betriebssysteme können einen anderen Planungsalgorithmus einsetzen.</span><span class="sxs-lookup"><span data-stu-id="c435d-116">Other operating systems might choose to use a different scheduling algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c435d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c435d-117">See Also</span></span>  
 [<span data-ttu-id="c435d-118">Verwenden von Threads und Threading</span><span class="sxs-lookup"><span data-stu-id="c435d-118">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="c435d-119">Verwaltetes und nicht verwaltetes Threading in Windows</span><span class="sxs-lookup"><span data-stu-id="c435d-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
