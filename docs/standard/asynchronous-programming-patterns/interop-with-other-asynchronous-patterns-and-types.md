---
title: Interoperabilität mit anderen asynchronen Mustern und Typen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: f9fe33bb46f0ba78756c4172032dfbaf45d6fc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123981"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="fa5e3-102">Interoperabilität mit anderen asynchronen Mustern und Typen</span><span class="sxs-lookup"><span data-stu-id="fa5e3-102">Interop with Other Asynchronous Patterns and Types</span></span>
<span data-ttu-id="fa5e3-103">Mit .NET Framework 1.0 wurde das <xref:System.IAsyncResult> -Muster vorgestellt, das auch als [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)- oder `Begin/End` -Muster bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-103">The .NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>  <span data-ttu-id="fa5e3-104">Mit .NET Framework 2.0 wurde das [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-104">The .NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  <span data-ttu-id="fa5e3-105">Ab .NET Framework 4 löst das [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) APM und EAP ab. Es bietet aber die Möglichkeit, leicht Migrationsroutinen aus früheren Mustern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-105">Starting with the .NET Framework 4, the [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) supersedes both APM and EAP, but provides the ability to easily build migration routines from the earlier patterns.</span></span>  
  
 <span data-ttu-id="fa5e3-106">In diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-106">In this topic:</span></span>  
  
- <span data-ttu-id="fa5e3-107">[Aufgaben und APM](#APM) ([von APM zu TAP](#ApmToTap) oder [von TAP zu APM](#TapToApm))</span><span class="sxs-lookup"><span data-stu-id="fa5e3-107">[Tasks and APM](#APM) ([from APM to TAP](#ApmToTap) or [from TAP to APM](#TapToApm))</span></span>  
  
- [<span data-ttu-id="fa5e3-108">Aufgaben und EAP</span><span class="sxs-lookup"><span data-stu-id="fa5e3-108">Tasks and EAP</span></span>](#EAP)  
  
- <span data-ttu-id="fa5e3-109">[Aufgaben und Wait-Handles](#WaitHandles) ([von den Wait-Handles zu TAP](#WHToTap) oder [von TAP zu Wait-Handles](#TapToWH))</span><span class="sxs-lookup"><span data-stu-id="fa5e3-109">[Tasks and wait handles](#WaitHandles) ([from wait handles to TAP](#WHToTap) or [from TAP to wait handles](#TapToWH))</span></span>  
  
<a name="APM"></a>   
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="fa5e3-110">Aufgaben und das asynchrone Programmiermodell (Asynchronous Programming Model, APM)</span><span class="sxs-lookup"><span data-stu-id="fa5e3-110">Tasks and the Asynchronous Programming Model (APM)</span></span>  
  
<a name="ApmToTap"></a>   
### <a name="from-apm-to-tap"></a><span data-ttu-id="fa5e3-111">von APM zu TAP</span><span class="sxs-lookup"><span data-stu-id="fa5e3-111">From APM to TAP</span></span>  
 <span data-ttu-id="fa5e3-112">Da das [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) -Muster stark strukturiert ist, lässt sich ganz einfach ein Wrapper für eine APM-Implementierung erstellen, um sie als TAP-Implementierung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-112">Because the [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) pattern is very structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="fa5e3-113">.NET Framework enthält für diese Umwandlung seit .NET Framework 4 Hilfsroutinen in Form von <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>-Methodenüberladungen.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-113">In fact, the .NET Framework, starting with .NET Framework 4, includes helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="fa5e3-114">Betrachten Sie die <xref:System.IO.Stream> -Klasse und ihre Methoden <xref:System.IO.Stream.BeginRead%2A> / <xref:System.IO.Stream.EndRead%2A> , die die APM-Entsprechung zur synchronen <xref:System.IO.Stream.Read%2A> -Methode darstellen:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-114">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="fa5e3-115">Sie können die <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> -Methode verwenden, um wie folgt einen TAP-Wrapper für diese Operation zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-115">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="fa5e3-116">Diese Implementierung entspricht dem Folgenden:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-116">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>   
### <a name="from-tap-to-apm"></a><span data-ttu-id="fa5e3-117">von TAP zu APM</span><span class="sxs-lookup"><span data-stu-id="fa5e3-117">From TAP to APM</span></span>  
 <span data-ttu-id="fa5e3-118">Wenn die vorhandene Infrastruktur das APM-Muster erwartet, sollten Sie auch eine TAP-Implementierung erstellen und diese verwenden, wo eine APM-Implementierung erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-118">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="fa5e3-119">Da Aufgaben kombiniert werden können und die <xref:System.Threading.Tasks.Task> -Klasse <xref:System.IAsyncResult>implementiert, können Sie hierfür eine einfache Hilfsfunktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-119">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="fa5e3-120">Der folgende Code verwendet eine Erweiterung der <xref:System.Threading.Tasks.Task%601> -Klasse, aber Sie können eine fast identische Funktion für nicht generische Aufgaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-120">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="fa5e3-121">Betrachten Sie nun einen Fall, bei dem Sie die folgende TAP-Implementierung haben:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-121">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="fa5e3-122">und Sie möchten diese APM-Implementierung bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-122">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="fa5e3-123">Im folgenden Beispiel wird eine Migration zu APM veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-123">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>   
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="fa5e3-124">Aufgaben und das ereignisbasierte asynchrone Muster (Event-based Asynchronous Pattern, EAP)</span><span class="sxs-lookup"><span data-stu-id="fa5e3-124">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="fa5e3-125">Das Umschließen einer [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) -Implementierung ist komplizierter als das Umschließen eines APM-Musters, da das EAP-Muster selbst mehr Varianten als das APM-Muster aufweist und geringer strukturiert ist.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-125">Wrapping an [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="fa5e3-126">Zur Veranschaulichung umschließt der folgende Code die `DownloadStringAsync` -Methode.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-126">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="fa5e3-127">`DownloadStringAsync` akzeptiert einen URI, löst während des Herunterladens das `DownloadProgressChanged` -Ereignis aus, um mehrere Fortschrittswerte zu berichten, und löst zum Abschluss das `DownloadStringCompleted` -Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-127">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="fa5e3-128">Das Endergebnis ist eine Zeichenfolge, die den Inhalt der Seite am angegebenen URI enthält.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-128">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>   
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="fa5e3-129">Aufgaben und Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="fa5e3-129">Tasks and Wait Handles</span></span>  
  
<a name="WHToTap"></a>   
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="fa5e3-130">von den Wait-Handles zu TAP</span><span class="sxs-lookup"><span data-stu-id="fa5e3-130">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="fa5e3-131">Obwohl Wait-Handles kein asynchrones Muster implementieren, können erfahrene Entwickler die <xref:System.Threading.WaitHandle> -Klasse und die <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> -Methode für asynchrone Benachrichtigungen verwenden, wenn ein Wait-Handle festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-131">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="fa5e3-132">Sie können die <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> -Methode umschließen, um eine aufgabenbasierte Alternative zu jedem synchronen Wartevorgang in einem Wait-Handle zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-132">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="fa5e3-133">Mit dieser Methode können Sie vorhandene <xref:System.Threading.WaitHandle> -Implementierungen in asynchronen Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-133">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="fa5e3-134">Wenn Sie beispielsweise die Anzahl von asynchronen Operationen beschränken möchten, die zu einem bestimmten Zeitpunkt ausgeführt werden, können Sie ein Semaphor ( <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> -Objekt) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-134">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="fa5e3-135">Indem Sie die Anzahl des Semaphors mit *N* initialisieren, zu jedem Zeitpunkt, zu dem ein Vorgang ausgeführt werden soll, auf das Semaphor warten und das Semaphor freigeben, wenn ein Vorgang abgeschlossen ist, können Sie die Anzahl von gleichzeitig ausgeführten Vorgängen auf *N*beschränken.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-135">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore’s count to *N*, waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you’re done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="fa5e3-136">Sie können auch ein asynchrones Semaphor erstellen, das nicht auf Wait-Handles beruht und stattdessen vollständig mit Aufgaben funktioniert.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-136">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="fa5e3-137">Um dies zu erreichen, können Sie Techniken wie die verwenden, die in [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) zum Erstellen von Datenstrukturen auf <xref:System.Threading.Tasks.Task>hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-137">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
<a name="TapToWH"></a>   
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="fa5e3-138">von TAP zu Wait-Handles</span><span class="sxs-lookup"><span data-stu-id="fa5e3-138">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="fa5e3-139">Wie bereits erwähnt, implementiert die <xref:System.Threading.Tasks.Task> -Klasse <xref:System.IAsyncResult>, und diese Implementierung macht die <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> -Eigenschaft verfügbar, die ein Wait-Handle zurückgibt, das festgelegt wird, wenn der <xref:System.Threading.Tasks.Task> abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="fa5e3-139">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="fa5e3-140">Sie können ein <xref:System.Threading.WaitHandle> für <xref:System.Threading.Tasks.Task> abrufen, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fa5e3-140">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="fa5e3-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa5e3-141">See also</span></span>

- <span data-ttu-id="fa5e3-142">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Aufgabenbasiertes asynchrones Muster)</span><span class="sxs-lookup"><span data-stu-id="fa5e3-142">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span>
- [<span data-ttu-id="fa5e3-143">Implementieren des aufgabenbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="fa5e3-143">Implementing the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="fa5e3-144">Nutzen des aufgabenbasierten asynchronen Musters</span><span class="sxs-lookup"><span data-stu-id="fa5e3-144">Consuming the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
