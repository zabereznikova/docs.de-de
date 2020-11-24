---
title: Garbage Collection-Benachrichtigungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: c91712b9d25221f1ffd9e9e980c420be32e2379a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831181"
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="16012-102">Garbage Collection-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="16012-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="16012-103">Es gibt Situationen, in denen eine vollständige Garbage Collection (d.h. eine Garbage Collection der Generation 2) der Common Language Runtime die Leistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="16012-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="16012-104">Dies kann vor allem bei Servern, die eine hohe Zahl an Anforderungen verarbeiten, ein Problem sein; in diesem Fall kann eine lange Garbage Collection einen Anforderungstimeout verursachen. Um eine vollständige Garbage Collection im Rahmen eines kritischen Zeitraums zu verhindern, können Sie benachrichtigt werden, wenn eine vollständige Garbage Collection bevorsteht, und Maßnahmen ergreifen, um die Workload auf eine andere Serverinstanz umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="16012-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="16012-105">Sie können auch selbst eine Garbage Collection auslösen, vorausgesetzt, dass die aktuelle Serverinstanz keine Anforderungen verarbeiten muss.</span><span class="sxs-lookup"><span data-stu-id="16012-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="16012-106">Die <xref:System.GC.RegisterForFullGCNotification%2A>-Methode registriert, dass eine Benachrichtigung ausgelöst werden soll, wenn die Runtime erkennt, dass eine vollständige Garbage Collection ansteht.</span><span class="sxs-lookup"><span data-stu-id="16012-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="16012-107">Diese Benachrichtigung besteht aus zwei Teilen: Der eine Teil wird gesendet, wenn die vollständige Garbage Collection ansteht, und der andere Teil, wenn die vollständige Garbage Collection abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="16012-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="16012-108">Nur blockierende Garbage Collections lösen Benachrichtigungen aus.</span><span class="sxs-lookup"><span data-stu-id="16012-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="16012-109">Wenn das [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)-Konfigurationselement aktiviert ist, lösen Garbage Collections im Hintergrund keine Benachrichtigungen aus.</span><span class="sxs-lookup"><span data-stu-id="16012-109">When the [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="16012-110">Um zu bestimmen, wann eine Benachrichtigung ausgelöst wurde, verwenden Sie die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="16012-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="16012-111">In der Regel verwenden Sie diese Methoden in einer `while`-Schleife, um fortlaufend eine <xref:System.GCNotificationStatus>-Enumeration abzurufen, die den Status der Benachrichtigung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="16012-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="16012-112">Wenn dieser Wert <xref:System.GCNotificationStatus.Succeeded> ist, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="16012-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
- <span data-ttu-id="16012-113">Als Antwort auf eine mit der <xref:System.GC.WaitForFullGCApproach%2A>-Methode erhaltene Benachrichtigung können Sie die Workload umleiten und möglicherweise selbst eine Garbage Collection auslösen.</span><span class="sxs-lookup"><span data-stu-id="16012-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
- <span data-ttu-id="16012-114">Als Antwort auf eine mit der <xref:System.GC.WaitForFullGCComplete%2A>-Methode erhaltene Benachrichtigung können Sie die aktuelle Serverinstanz erneut zur Verarbeitung von Anforderungen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="16012-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="16012-115">Sie können auch Informationen sammeln.</span><span class="sxs-lookup"><span data-stu-id="16012-115">You can also gather information.</span></span> <span data-ttu-id="16012-116">Beispielsweise können Sie mit der <xref:System.GC.CollectionCount%2A>-Methode die Anzahl der Sammlungen erfassen.</span><span class="sxs-lookup"><span data-stu-id="16012-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="16012-117">Die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode sind für die Zusammenarbeit konzipiert.</span><span class="sxs-lookup"><span data-stu-id="16012-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="16012-118">Die Verwendung der einen ohne die andere kann zu unvorhersehbaren Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="16012-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="16012-119">Vollständige Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="16012-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="16012-120">Die Runtime löst eine vollständige Garbage Collection aus, wenn eines der folgenden Szenarien zutrifft:</span><span class="sxs-lookup"><span data-stu-id="16012-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
- <span data-ttu-id="16012-121">Genügend Arbeitsspeicher wurde in Generation 2 heraufgestuft, um die nächste Generation 2-Garbage Collection auszulösen.</span><span class="sxs-lookup"><span data-stu-id="16012-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="16012-122">Genügend Arbeitsspeicher wurde in den großen Objektheap heraufgestuft, um die nächste Generation 2-Garbage Collection auszulösen.</span><span class="sxs-lookup"><span data-stu-id="16012-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="16012-123">Eine Generation 1-Garbage Collection wird aufgrund anderer Faktoren zu einer Generation 2-Garbage Collection eskaliert.</span><span class="sxs-lookup"><span data-stu-id="16012-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="16012-124">Die Schwellenwerte, die Sie in der <xref:System.GC.RegisterForFullGCNotification%2A>-Methode angeben, gelten für die ersten beiden Szenarien.</span><span class="sxs-lookup"><span data-stu-id="16012-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="16012-125">Allerdings erhalten Sie im ersten Szenario die Benachrichtigung nicht immer genau dann, wenn die von Ihnen angegebenen Schwellenwerte auftreten. Dafür gibt es zwei Gründe:</span><span class="sxs-lookup"><span data-stu-id="16012-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
- <span data-ttu-id="16012-126">Die Runtime überprüft (leistungsbedingt) nicht jede kleine Objektzuordnung.</span><span class="sxs-lookup"><span data-stu-id="16012-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
- <span data-ttu-id="16012-127">Nur Generation 1-Garbage Collections stufen Arbeitsspeicher in Generation 2 herauf.</span><span class="sxs-lookup"><span data-stu-id="16012-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="16012-128">Das dritte Szenario trägt auch zur Ungewissheit bei, wann Sie die Benachrichtigung erhalten.</span><span class="sxs-lookup"><span data-stu-id="16012-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="16012-129">Obwohl dies keine Garantie ist, ist es eine gute Möglichkeit, die Auswirkungen einer ungünstigen vollständigen Garbage Collection zu verringern, indem Sie die Anforderungen während dieser Zeit umleiten oder die Garbage Collection zu einem günstigeren Zeitpunkt selbst auslösen.</span><span class="sxs-lookup"><span data-stu-id="16012-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="16012-130">Schwellenwertparameter für die Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="16012-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="16012-131">Die <xref:System.GC.RegisterForFullGCNotification%2A>-Methode verfügt über zwei Parameter zur Angabe der Schwellenwerte der Objekte der Generation 2 und des großen Objektheaps.</span><span class="sxs-lookup"><span data-stu-id="16012-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="16012-132">Wenn diese Werte erfüllt sind, sollte eine Garbage Collection-Benachrichtigung ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="16012-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="16012-133">In der folgenden Tabelle werden diese Parameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16012-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="16012-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="16012-134">Parameter</span></span>|<span data-ttu-id="16012-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16012-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="16012-136">Eine Zahl zwischen 1 und 99, die auf der Grundlage der in Generation 2 heraufgestuften Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="16012-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="16012-137">Eine Zahl zwischen 1 und 99, die auf der Grundlage der dem großen Objektheap zugeordneten Objekte angibt, wann die Benachrichtigung ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="16012-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="16012-138">Wenn Sie einen zu hohen Wert angeben, besteht eine hohe Wahrscheinlichkeit, dass Sie eine Benachrichtigung erhalten, aber die Wartezeit vor dem Auslösen der Garbage Collection durch die Runtime könnte zu lang sein.</span><span class="sxs-lookup"><span data-stu-id="16012-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="16012-139">Wenn Sie eine Garbage Collection selbst auslösen, können Sie vielleicht mehr Objekte freigegeben, als wenn die Runtime die Garbage Collection auslösen würde.</span><span class="sxs-lookup"><span data-stu-id="16012-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="16012-140">Wenn Sie einen zu niedrigen Wert angeben, könnte die Runtime die Garbage Collection auslösen, bevor Sie benachrichtigt werden können.</span><span class="sxs-lookup"><span data-stu-id="16012-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16012-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16012-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="16012-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16012-142">Description</span></span>  
 <span data-ttu-id="16012-143">Im folgenden Beispiel verarbeitet eine Gruppe von Servern eingehende Webanforderungen.</span><span class="sxs-lookup"><span data-stu-id="16012-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="16012-144">Um die Workload der Verarbeitung von Anforderungen zu simulieren, werden Bytearrays einer <xref:System.Collections.Generic.List%601>-Sammlung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="16012-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="16012-145">Jeder Server wird für eine Garbage Collection-Benachrichtigung registriert und startet dann einen Thread auf der `WaitForFullGCProc`-Benutzermethode, um kontinuierlich die <xref:System.GCNotificationStatus> -Enumeration zu überwachen, die von der <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="16012-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="16012-146">Die <xref:System.GC.WaitForFullGCApproach%2A>- und <xref:System.GC.WaitForFullGCComplete%2A>-Methode rufen ihre jeweiligen Benutzermethoden zur Ereignisbehandlung auf, wenn eine Benachrichtigung ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="16012-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
- `OnFullGCApproachNotify`  
  
     <span data-ttu-id="16012-147">Diese Methode ruft die `RedirectRequests`-Benutzermethode auf, die den Server, der Anforderungen in die Warteschlange setzt, anweist, das Senden von Anforderungen an den Server anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="16012-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="16012-148">Dies wird durch Festlegen der Variablen auf Klassenebene `bAllocate` auf `false` simuliert, sodass keine weiteren Objekte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="16012-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="16012-149">Als Nächstes wird die `FinishExistingRequests`-Benutzermethode aufgerufen, um die Verarbeitung der ausstehenden Serveranforderungen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="16012-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="16012-150">Dies wird durch Löschen der <xref:System.Collections.Generic.List%601>-Sammlung simuliert.</span><span class="sxs-lookup"><span data-stu-id="16012-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="16012-151">Zum Schluss wird eine Garbage Collection ausgelöst, da die Arbeitslast gering ist.</span><span class="sxs-lookup"><span data-stu-id="16012-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
- `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="16012-152">Diese Methode ruft die Benutzermethode `AcceptRequests` auf, um das Akzeptieren von Anforderungen fortzusetzen, da der Server nicht mehr für eine vollständige Garbage Collection anfällig ist.</span><span class="sxs-lookup"><span data-stu-id="16012-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="16012-153">Diese Aktion wird durch Festlegung der `bAllocate`-Variablen auf `true` simuliert, sodass das Hinzufügen von Objekten zur <xref:System.Collections.Generic.List%601>-Sammlung fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="16012-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="16012-154">Der folgende Code enthält die `Main`-Methode des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="16012-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="16012-155">Der folgende Code enthält die `WaitForFullGCProc`-Benutzermethode, die eine kontinuierliche while-Schleife zum Überprüfen auf Garbage Collection-Benachrichtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="16012-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="16012-156">Der folgende Code enthält die `OnFullGCApproachNotify`-Methode gemäß Aufruf durch die</span><span class="sxs-lookup"><span data-stu-id="16012-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="16012-157">`WaitForFullGCProc` -Methode.</span><span class="sxs-lookup"><span data-stu-id="16012-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="16012-158">Der folgende Code enthält die `OnFullGCApproachComplete`-Methode gemäß Aufruf durch die</span><span class="sxs-lookup"><span data-stu-id="16012-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="16012-159">`WaitForFullGCProc` -Methode.</span><span class="sxs-lookup"><span data-stu-id="16012-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="16012-160">Der folgende Code enthält die Benutzermethoden, die durch die `OnFullGCApproachNotify`- und `OnFullGCCompleteNotify`-Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16012-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="16012-161">Die Benutzermethoden leiten Anforderungen um, schließen vorhandene Anforderungen ab und setzen dann Anforderungen fort, nachdem eine vollständige Garbage Collection aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="16012-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="16012-162">Das gesamte Codebeispiel lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16012-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="16012-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16012-163">See also</span></span>

- [<span data-ttu-id="16012-164">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="16012-164">Garbage Collection</span></span>](index.md)
