---
title: Garbage Collection und Leistung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, troubleshooting
- garbage collection, performance
ms.assetid: c203467b-e95c-4ccf-b30b-953eb3463134
ms.openlocfilehash: 833bf46b973988196fea37da18bac9923ecd6dcc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141367"
---
# <a name="garbage-collection-and-performance"></a><span data-ttu-id="e4987-102">Garbage Collection und Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-102">Garbage Collection and Performance</span></span>

<a name="top"></a> <span data-ttu-id="e4987-103">In diesem Thema werden Probleme im Zusammenhang mit Garbage Collection und Speicherauslastung besprochen.</span><span class="sxs-lookup"><span data-stu-id="e4987-103">This topic describes issues related to garbage collection and memory usage.</span></span> <span data-ttu-id="e4987-104">Es werden Probleme beschrieben, die den verwalteten Heap betreffen, und es wird erläutert, wie die Auswirkungen der Garbage Collection auf Ihre Anwendungen minimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e4987-104">It addresses issues that pertain to the managed heap and explains how to minimize the effect of garbage collection on your applications.</span></span> <span data-ttu-id="e4987-105">Jedes Problem bietet Links zu Verfahren, mit denen Sie die Probleme untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="e4987-105">Each issue has links to procedures that you can use to investigate problems.</span></span>

<span data-ttu-id="e4987-106">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="e4987-106">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e4987-107">Tools zur Leistungsanalyse</span><span class="sxs-lookup"><span data-stu-id="e4987-107">Performance Analysis Tools</span></span>](#performance_analysis_tools)

- [<span data-ttu-id="e4987-108">Problembehandlung bei Performanceproblemen</span><span class="sxs-lookup"><span data-stu-id="e4987-108">Troubleshooting Performance Issues</span></span>](#troubleshooting_performance_issues)

- [<span data-ttu-id="e4987-109">Richtlinien für die Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e4987-109">Troubleshooting Guidelines</span></span>](#troubleshooting_guidelines)

- [<span data-ttu-id="e4987-110">Prozeduren zur Leistungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="e4987-110">Performance Check Procedures</span></span>](#performance_check_procedures)

<a name="performance_analysis_tools"></a>

## <a name="performance-analysis-tools"></a><span data-ttu-id="e4987-111">Tools zur Leistungsanalyse</span><span class="sxs-lookup"><span data-stu-id="e4987-111">Performance Analysis Tools</span></span>

<span data-ttu-id="e4987-112">In den folgenden Abschnitten werden Tools beschrieben, die zum Untersuchen von Problemen mit der Speicherauslastung und Garbage Collection verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-112">The following sections describe the tools that are available for investigating memory usage and garbage collection issues.</span></span> <span data-ttu-id="e4987-113">Die [Prozeduren](#performance_check_procedures), die weiter unten in diesem Thema aufgeführt sind, beziehen sich auf diese Tools.</span><span class="sxs-lookup"><span data-stu-id="e4987-113">The [procedures](#performance_check_procedures) provided later in this topic refer to these tools.</span></span>

<a name="perf_counters"></a>

### <a name="memory-performance-counters"></a><span data-ttu-id="e4987-114">Speicherleistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="e4987-114">Memory Performance Counters</span></span>

<span data-ttu-id="e4987-115">Sie können Leistungsindikatoren verwenden, um Leistungsdaten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="e4987-115">You can use performance counters to gather performance data.</span></span> <span data-ttu-id="e4987-116">Anweisungen hierzu finden Sie unter [Laufzeit-Profilerstellung](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span><span class="sxs-lookup"><span data-stu-id="e4987-116">For instructions, see [Runtime Profiling](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span></span> <span data-ttu-id="e4987-117">Die Leistungsindikatorkategorie .NET CLR-Speicher, die in [Leistungsindikatoren in .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md) beschrieben wird, stellt Informationen über den Garbage Collector bereit.</span><span class="sxs-lookup"><span data-stu-id="e4987-117">The .NET CLR Memory category of performance counters, as described in [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md), provides information about the garbage collector.</span></span>

<a name="sos"></a>

### <a name="debugging-with-sos"></a><span data-ttu-id="e4987-118">Debuggen mit SOS</span><span class="sxs-lookup"><span data-stu-id="e4987-118">Debugging with SOS</span></span>

<span data-ttu-id="e4987-119">Sie können den [Windows-Debugger (WinDbg)](/windows-hardware/drivers/debugger/index) verwenden, um Objekte auf dem verwalteten Heap zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e4987-119">You can use the [Windows Debugger (WinDbg)](/windows-hardware/drivers/debugger/index) to inspect objects on the managed heap.</span></span>

<span data-ttu-id="e4987-120">Wenn Sie WinDbg installieren möchten, installieren Sie die Debugtools für Windows über die Seite [Download Debugging Tools for Windows (Herunterladen von Debuggingtools für Windows)](/windows-hardware/drivers/debugger/debugger-download-tools).</span><span class="sxs-lookup"><span data-stu-id="e4987-120">To install WinDbg, install Debugging Tools for Windows from the [Download Debugging Tools for Windows](/windows-hardware/drivers/debugger/debugger-download-tools) page.</span></span>

<a name="etw"></a>

### <a name="garbage-collection-etw-events"></a><span data-ttu-id="e4987-121">Garbage Collection-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="e4987-121">Garbage Collection ETW Events</span></span>

<span data-ttu-id="e4987-122">Die Ereignisablaufverfolgung für Windows (ETW) ist ein Ablaufverfolgungssystem, das die Profilerstellung und das Debugging ergänzt, die von .NET Framework bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e4987-122">Event tracing for Windows (ETW) is a tracing system that supplements the profiling and debugging support provided by the .NET Framework.</span></span> <span data-ttu-id="e4987-123">Ab .NET Framework 4 erfassen [ETW-Ereignisse der Garbage Collection](../../../docs/framework/performance/garbage-collection-etw-events.md) nützliche Informationen für eine statistische Analyse des verwalteten Heaps.</span><span class="sxs-lookup"><span data-stu-id="e4987-123">Starting with the .NET Framework 4, [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md) capture useful information for analyzing the managed heap from a statistical point of view.</span></span> <span data-ttu-id="e4987-124">Beispielsweise liefert das `GCStart_V1`-Ereignis, das ausgelöst wird, sobald eine Garbage Collection durchgeführt wird, die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e4987-124">For example, the `GCStart_V1` event, which is raised when a garbage collection is about to occur, provides the following information:</span></span>

- <span data-ttu-id="e4987-125">Welche Generation von Objekten wird erfasst.</span><span class="sxs-lookup"><span data-stu-id="e4987-125">Which generation of objects is being collected.</span></span>

- <span data-ttu-id="e4987-126">Was hat die Garbage Collection ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e4987-126">What triggered the garbage collection.</span></span>

- <span data-ttu-id="e4987-127">Typ der Garbage Collection (gleichzeitig oder nicht gleichzeitig).</span><span class="sxs-lookup"><span data-stu-id="e4987-127">Type of garbage collection (concurrent or not concurrent).</span></span>

<span data-ttu-id="e4987-128">Die ETW-Ereignisprotokollierung ist effizient und wird keine Leistungsprobleme bei der Garbage Collection maskieren.</span><span class="sxs-lookup"><span data-stu-id="e4987-128">ETW event logging is efficient and will not mask any performance problems associated with garbage collection.</span></span> <span data-ttu-id="e4987-129">Ein Prozess kann seine eigenen Ereignisse zusätzlich zu den ETW-Ereignissen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e4987-129">A process can provide its own events in conjunction with ETW events.</span></span> <span data-ttu-id="e4987-130">Bei der Protokollierung können die Ereignisse der Anwendung und die Garbage Collection-Ereignisse korreliert werden, um zu bestimmen, wie und wann Probleme mit dem Heap auftreten.</span><span class="sxs-lookup"><span data-stu-id="e4987-130">When logged, both the application's events and the garbage collection events can be correlated to determine how and when heap problems occur.</span></span> <span data-ttu-id="e4987-131">Beispielsweise könnte eine Serveranwendung Ereignisse am Anfang und am Ende einer Clientanforderung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e4987-131">For example, a server application could provide events at the start and end of a client request.</span></span>

<a name="profiling_api"></a>

### <a name="the-profiling-api"></a><span data-ttu-id="e4987-132">Die Profilerstellungs-API</span><span class="sxs-lookup"><span data-stu-id="e4987-132">The Profiling API</span></span>

<span data-ttu-id="e4987-133">Die Profilerstellungsschnittstellen der Common Language Runtime (CLR) enthalten ausführliche Informationen zu den Objekten, die von einer Garbage Collection betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-133">The common language runtime (CLR) profiling interfaces provide detailed information about the objects that were affected during garbage collection.</span></span> <span data-ttu-id="e4987-134">Ein Profiler kann benachrichtigt werden, wenn eine Garbage Collection beginnt oder endet.</span><span class="sxs-lookup"><span data-stu-id="e4987-134">A profiler can be notified when a garbage collection starts and ends.</span></span> <span data-ttu-id="e4987-135">Es kann Berichte über die Objekte im verwalteten Heap bereitstellen, einschließlich einer Identifikation von Objekten in jeder Generation.</span><span class="sxs-lookup"><span data-stu-id="e4987-135">It can provide reports about the objects on the managed heap, including an identification of objects in each generation.</span></span> <span data-ttu-id="e4987-136">Weitere Informationen finden Sie unter [Übersicht über die Profilerstellung](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4987-136">For more information, see [Profiling Overview](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span></span>

<span data-ttu-id="e4987-137">Profiler können umfassende Informationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e4987-137">Profilers can provide comprehensive information.</span></span> <span data-ttu-id="e4987-138">Allerdings können komplexe Profiler das Verhalten der Anwendung beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="e4987-138">However, complex profilers can potentially modify an application's behavior.</span></span>

### <a name="application-domain-resource-monitoring"></a><span data-ttu-id="e4987-139">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="e4987-139">Application Domain Resource Monitoring</span></span>

<span data-ttu-id="e4987-140">Ab .NET Framework 4 können Hosts mit der Ressourcenüberwachung für die Anwendungsdomäne (Application domain Resource Monitoring, ARM) die CPU- und Speicherauslastung pro Anwendungsdomäne überwachen.</span><span class="sxs-lookup"><span data-stu-id="e4987-140">Starting with the .NET Framework 4, Application domain resource monitoring (ARM) enables hosts to monitor CPU and memory usage by application domain.</span></span> <span data-ttu-id="e4987-141">Weitere Informationen finden Sie unter [Überwachung von Anwendungsdomänenressourcen](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="e4987-141">For more information, see [Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span></span>

[<span data-ttu-id="e4987-142">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e4987-142">Back to top</span></span>](#top)

<a name="troubleshooting_performance_issues"></a>

## <a name="troubleshooting-performance-issues"></a><span data-ttu-id="e4987-143">Problembehandlung bei Performanceproblemen</span><span class="sxs-lookup"><span data-stu-id="e4987-143">Troubleshooting Performance Issues</span></span>

<span data-ttu-id="e4987-144">Der erste Schritt besteht darin, [zu bestimmen, ob das Problem tatsächlich bei der Garbage Collection liegt](#IsGC).</span><span class="sxs-lookup"><span data-stu-id="e4987-144">The first step is to [determine whether the issue is actually garbage collection](#IsGC).</span></span> <span data-ttu-id="e4987-145">Wenn dies der Fall ist, treffen Sie eine Auswahl in der folgenden Liste, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="e4987-145">If you determine that it is, select from the following list to troubleshoot the problem.</span></span>

- [<span data-ttu-id="e4987-146">Es wird eine Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst</span><span class="sxs-lookup"><span data-stu-id="e4987-146">An out-of-memory exception is thrown</span></span>](#Issue_OOM)

- [<span data-ttu-id="e4987-147">Der Prozess verwendet zu viel Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="e4987-147">The process uses too much memory</span></span>](#Issue_TooMuchMemory)

- [<span data-ttu-id="e4987-148">Der Garbage Collector gibt Objekte nicht schnell genug frei</span><span class="sxs-lookup"><span data-stu-id="e4987-148">The garbage collector does not reclaim objects fast enough</span></span>](#Issue_NotFastEnough)

- [<span data-ttu-id="e4987-149">Der verwaltete Heap ist zu sehr fragmentiert</span><span class="sxs-lookup"><span data-stu-id="e4987-149">The managed heap is too fragmented</span></span>](#Issue_Fragmentation)

- [<span data-ttu-id="e4987-150">Die Pausen der Garbage Collections sind zu lang</span><span class="sxs-lookup"><span data-stu-id="e4987-150">Garbage collection pauses are too long</span></span>](#Issue_LongPauses)

- [<span data-ttu-id="e4987-151">Generation 0 ist zu groß</span><span class="sxs-lookup"><span data-stu-id="e4987-151">Generation 0 is too big</span></span>](#Issue_Gen0)

- [<span data-ttu-id="e4987-152">Die CPU-Auslastung während einer Garbage Collection ist zu hoch</span><span class="sxs-lookup"><span data-stu-id="e4987-152">CPU usage during a garbage collection is too high</span></span>](#Issue_HighCPU)

<a name="Issue_OOM"></a>

### <a name="issue-an-out-of-memory-exception-is-thrown"></a><span data-ttu-id="e4987-153">Problem: Es wird eine Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst</span><span class="sxs-lookup"><span data-stu-id="e4987-153">Issue: An Out-of-Memory Exception Is Thrown</span></span>

<span data-ttu-id="e4987-154">Es gibt zwei legitime Fälle, in denen eine verwaltete <xref:System.OutOfMemoryException> ausgelöst werden kann:</span><span class="sxs-lookup"><span data-stu-id="e4987-154">There are two legitimate cases for a managed <xref:System.OutOfMemoryException> to be thrown:</span></span>

- <span data-ttu-id="e4987-155">Ungenügender virtueller Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e4987-155">Running out of virtual memory.</span></span>

  <span data-ttu-id="e4987-156">Der Garbage Collector belegt Systemspeicher in Segmenten mit einer vordefinierten Größe.</span><span class="sxs-lookup"><span data-stu-id="e4987-156">The garbage collector allocates memory from the system in segments of a pre-determined size.</span></span> <span data-ttu-id="e4987-157">Wenn eine Belegung ein zusätzliches Segment erfordert, jedoch kein freier zusammenhängender Block im virtuellen Arbeitsspeicher des Prozesses vorhanden ist, schlägt die Zuordnung für den verwalteten Heap fehl.</span><span class="sxs-lookup"><span data-stu-id="e4987-157">If an allocation requires an additional segment, but there is no contiguous free block left in the process's virtual memory space, the allocation for the managed heap will fail.</span></span>

- <span data-ttu-id="e4987-158">Ungenügender physischer Arbeitsspeicher für eine Belegung.</span><span class="sxs-lookup"><span data-stu-id="e4987-158">Not having enough physical memory to allocate.</span></span>

|<span data-ttu-id="e4987-159">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-159">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-160">Bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-160">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)<br /><br /> [<span data-ttu-id="e4987-161">Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4987-161">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="e4987-162">Bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-162">Determine whether there is enough physical memory.</span></span>](#Physical)|

<span data-ttu-id="e4987-163">Wenn Sie feststellen, dass die Ausnahme nicht legitim ist, wenden Sie sich mit folgenden Informationen an den Kundenservice und Support von Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e4987-163">If you determine that the exception is not legitimate, contact Microsoft Customer Service and Support with the following information:</span></span>

- <span data-ttu-id="e4987-164">Der Stapel mit der verwalteten Ausnahme aufgrund ungenügenden Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="e4987-164">The stack with the managed out-of-memory exception.</span></span>

- <span data-ttu-id="e4987-165">Vollständiges Speicherabbild.</span><span class="sxs-lookup"><span data-stu-id="e4987-165">Full memory dump.</span></span>

- <span data-ttu-id="e4987-166">Daten, die zeigen, dass es sich nicht um eine legitime Ausnahme aufgrund ungenügenden Arbeitsspeichers handelt, einschließlich Daten, die zeigen, dass virtueller oder physischer Speicher kein Problem darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4987-166">Data that proves that it is not a legitimate out-of-memory exception, including data that shows that virtual or physical memory is not an issue.</span></span>

<a name="Issue_TooMuchMemory"></a>

### <a name="issue-the-process-uses-too-much-memory"></a><span data-ttu-id="e4987-167">Problem: Der Prozess verwendet zu viel Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="e4987-167">Issue: The Process Uses Too Much Memory</span></span>

<span data-ttu-id="e4987-168">Eine häufige Annahme ist, dass die Speicherauslastungsanzeige auf der Registerkarte **Leistung** des Windows Task-Managers anzeigen kann, wann zu viel Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-168">A common assumption is that the memory usage display on the **Performance** tab of Windows Task Manager can indicate when too much memory is being used.</span></span> <span data-ttu-id="e4987-169">Allerdings betrifft diese Anzeige lediglich das Workingset. Sie stellt keine Informationen zur virtuellen Arbeitsspeicherverwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="e4987-169">However, that display pertains to the working set; it does not provide information about virtual memory usage.</span></span>

<span data-ttu-id="e4987-170">Wenn Sie feststellen, dass das Problem durch den verwalteten Heap verursacht wird, müssen Sie den verwalteten Heap über einen bestimmten Zeitraum überwachen, um ein Muster zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e4987-170">If you determine that the issue is caused by the managed heap, you must measure the managed heap over time to determine any patterns.</span></span>

<span data-ttu-id="e4987-171">Wenn Sie feststellen, dass das Problem nicht durch den verwalteten Heap verursacht wird, müssen Sie ein systemeigenes Debugging durchführen.</span><span class="sxs-lookup"><span data-stu-id="e4987-171">If you determine that the problem is not caused by the managed heap, you must use native debugging.</span></span>

|<span data-ttu-id="e4987-172">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-172">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-173">Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4987-173">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="e4987-174">Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert.</span><span class="sxs-lookup"><span data-stu-id="e4987-174">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)<br /><br /> [<span data-ttu-id="e4987-175">Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert.</span><span class="sxs-lookup"><span data-stu-id="e4987-175">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)<br /><br /> [<span data-ttu-id="e4987-176">Bestimmen Sie große Objekte in Generation 2.</span><span class="sxs-lookup"><span data-stu-id="e4987-176">Determine large objects in generation 2.</span></span>](#ExamineGen2)<br /><br /> [<span data-ttu-id="e4987-177">Bestimmen Sie die Verweise auf Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4987-177">Determine references to objects.</span></span>](#ObjRef)|

<a name="Issue_NotFastEnough"></a>

### <a name="issue-the-garbage-collector-does-not-reclaim-objects-fast-enough"></a><span data-ttu-id="e4987-178">Problem: Der Garbage Collector gibt Objekte nicht schnell genug frei</span><span class="sxs-lookup"><span data-stu-id="e4987-178">Issue: The Garbage Collector Does Not Reclaim Objects Fast Enough</span></span>

<span data-ttu-id="e4987-179">Wenn es scheint, als ob Objekte nicht wie erwartet von der Garbage Collection freigegeben werden, müssen Sie ermitteln, ob starke Verweise auf diese Objekte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-179">When it appears as if objects are not being reclaimed as expected for garbage collection, you must determine if there are any strong references to those objects.</span></span>

<span data-ttu-id="e4987-180">Dieses Problem kann auch auftreten, wenn keine Garbage Collection für die Generation durchgeführt wurde, die ein totes Objekt enthält. Dies zeigt an, dass der Finalizer für die inaktiven Objekt nicht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4987-180">You may also encounter this issue if there has been no garbage collection for the generation that contains a dead object, which indicates that the finalizer for the dead object has not been run.</span></span> <span data-ttu-id="e4987-181">Dies ist z. B. möglich, wenn Sie eine Anwendung mit einem Singlethread-Apartment (STA) ausführen und der Thread, der die Warteschlange des Finalizers verwaltet, keinen Aufruf in das Apartment ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="e4987-181">For example, this is possible when you are running a single-threaded apartment (STA) application and the thread that services the finalizer queue cannot call into it.</span></span>

|<span data-ttu-id="e4987-182">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-182">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-183">Überprüfen Sie die Verweise auf Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4987-183">Check references to objects.</span></span>](#ObjRef)<br /><br /> [<span data-ttu-id="e4987-184">Bestimmen Sie, ob ein Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4987-184">Determine whether a finalizer has been run.</span></span>](#Induce)<br /><br /> [<span data-ttu-id="e4987-185">Bestimmen Sie, ob Objekte auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="e4987-185">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)|

<a name="Issue_Fragmentation"></a>

### <a name="issue-the-managed-heap-is-too-fragmented"></a><span data-ttu-id="e4987-186">Problem: Der verwaltete Heap ist zu sehr fragmentiert</span><span class="sxs-lookup"><span data-stu-id="e4987-186">Issue: The Managed Heap Is Too fragmented</span></span>

<span data-ttu-id="e4987-187">Der Fragmentierungsgrad wird als das Verhältnis zwischen freiem Speicherplatz und dem insgesamt belegten Speicher für die Generation berechnet.</span><span class="sxs-lookup"><span data-stu-id="e4987-187">The fragmentation level is calculated as the ratio of free space over the total allocated memory for the generation.</span></span> <span data-ttu-id="e4987-188">Für Generation 2 gelten nicht mehr als 20% als akzeptabler Wert für die Fragmentierung.</span><span class="sxs-lookup"><span data-stu-id="e4987-188">For generation 2, an acceptable level of fragmentation is no more than 20%.</span></span> <span data-ttu-id="e4987-189">Da Generation 2 sehr groß werden kann, ist das Verhältnis der Fragmentierung wichtiger als der absolute Wert.</span><span class="sxs-lookup"><span data-stu-id="e4987-189">Because generation 2 can get very big, the ratio of fragmentation is more important than the absolute value.</span></span>

<span data-ttu-id="e4987-190">Viele freier Speicherplatz in Generation 0 ist kein Problem, da in dieser Generation neue Objekte belegt werden.</span><span class="sxs-lookup"><span data-stu-id="e4987-190">Having lots of free space in generation 0 is not a problem because this is the generation where new objects are allocated.</span></span>

<span data-ttu-id="e4987-191">Fragmentierung tritt immer im Heap für große Objekte auf, da dieser nicht komprimiert ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-191">Fragmentation always occurs in the large object heap because it is not compacted.</span></span> <span data-ttu-id="e4987-192">Freie einander angrenzende Objekte werden immer in einem einzelnen Bereich zusammengefasst, um große Objektanforderungen erfüllen zu können.</span><span class="sxs-lookup"><span data-stu-id="e4987-192">Free objects that are adjacent are naturally collapsed into a single space to satisfy large object allocation requests.</span></span>

<span data-ttu-id="e4987-193">Die Fragmentierung kann in Generation 1 und in Generation 2 zu einem Problem werden.</span><span class="sxs-lookup"><span data-stu-id="e4987-193">Fragmentation can become a problem in generation 1 and generation 2.</span></span> <span data-ttu-id="e4987-194">Wenn diese Generationen nach einer Garbage Collection viel freien Speicherplatz aufweisen, muss die Objektverwendung einer Anwendung möglicherweise angepasst werden, und Sie sollten die Lebensdauer von langfristigen Objekten neu prüfen.</span><span class="sxs-lookup"><span data-stu-id="e4987-194">If these generations have a large amount of free space after a garbage collection, an application's object usage may need modification, and you should consider re-evaluating the lifetime of long-term objects.</span></span>

<span data-ttu-id="e4987-195">Ein übermäßiges Fixieren von Objekten kann die Fragmentierung erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e4987-195">Excessive pinning of objects can increase fragmentation.</span></span> <span data-ttu-id="e4987-196">Wenn die Fragmentierung zu groß ist, wurden eventuell zu viele Objekte fixiert.</span><span class="sxs-lookup"><span data-stu-id="e4987-196">If fragmentation is high, too many objects could be pinned.</span></span>

<span data-ttu-id="e4987-197">Wenn die Fragmentierung des virtuellen Arbeitsspeichers verhindert, dass der Garbage Collector Segmente hinzufügen kann, kann dies eine der folgenden Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="e4987-197">If fragmentation of virtual memory is preventing the garbage collector from adding segments, the causes could be one of the following:</span></span>

- <span data-ttu-id="e4987-198">Häufiges Laden und Entladen von vielen kleinen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="e4987-198">Frequent loading and unloading of many small assemblies.</span></span>

- <span data-ttu-id="e4987-199">Zu viele Verweise auf COM-Objekte bei der Interoperation mit nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e4987-199">Holding too many references to COM objects when interoperating with unmanaged code.</span></span>

- <span data-ttu-id="e4987-200">Erstellung von großen flüchtigen Objekten. Dies zwingt den großen Objektheap, häufig Heapsgmente zu reservieren und wieder freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e4987-200">Creation of large transient objects, which causes the large object heap to allocate and free heap segments frequently.</span></span>

  <span data-ttu-id="e4987-201">Wenn die CLR gehostet wird, kann eine Anwendung anfordern, dass der Garbage Collector seine Segmente beibehält.</span><span class="sxs-lookup"><span data-stu-id="e4987-201">When hosting the CLR, an application can request that the garbage collector retain its segments.</span></span> <span data-ttu-id="e4987-202">Dadurch wird die Häufigkeit von Segmentbelegungen reduziert.</span><span class="sxs-lookup"><span data-stu-id="e4987-202">This reduces the frequency of segment allocations.</span></span> <span data-ttu-id="e4987-203">Dies wird mit dem Flag STARTUP_HOARD_GC_VM in der [STARTUP_FLAGS-Enumeration](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) erreicht.</span><span class="sxs-lookup"><span data-stu-id="e4987-203">This is accomplished by using the STARTUP_HOARD_GC_VM flag in the [STARTUP_FLAGS Enumeration](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>

|<span data-ttu-id="e4987-204">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-204">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-205">Bestimmen Sie den freien Speicherplatz im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="e4987-205">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)<br /><br /> [<span data-ttu-id="e4987-206">Bestimmen Sie die Anzahl der fixierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4987-206">Determine the number of pinned objects.</span></span>](#Pinned)|

<span data-ttu-id="e4987-207">Wenn Sie glauben, dass keine legitime Ursache für die Fragmentierung vorliegt, wenden Sie sich an den Kundenservice und Support von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4987-207">If you think that there is no legitimate cause for the fragmentation, contact Microsoft Customer Service and Support.</span></span>

<a name="Issue_LongPauses"></a>

### <a name="issue-garbage-collection-pauses-are-too-long"></a><span data-ttu-id="e4987-208">Problem: Die Pausen der Garbage Collections sind zu lang</span><span class="sxs-lookup"><span data-stu-id="e4987-208">Issue: Garbage Collection Pauses Are Too Long</span></span>

<span data-ttu-id="e4987-209">Die Garbage Collection arbeitet in verzögerter Echtzeit. Daher muss eine Anwendung gewisse Pausen tolerieren können.</span><span class="sxs-lookup"><span data-stu-id="e4987-209">Garbage collection operates in soft real time, so an application must be able to tolerate some pauses.</span></span> <span data-ttu-id="e4987-210">Ein Kriterium für die verzögerte Echtzeit besteht darin, dass 95% der Vorgänge zeitgenau beendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e4987-210">A criterion for soft real time is that 95% of the operations must finish on time.</span></span>

<span data-ttu-id="e4987-211">Bei der gleichzeitigen Garbage Collection dürfen während einer Garbage Collection verwaltete Threads ausgeführt werden. Dies bedeutet, dass die Pausen sehr klein sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-211">In concurrent garbage collection, managed threads are allowed to run during a collection, which means that pauses are very minimal.</span></span>

<span data-ttu-id="e4987-212">Kurzlebige Garbage Collections (Generationen 0 und 1) dauern nur einige Millisekunden, sodass das Verringern der Pausen normalerweise nicht sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-212">Ephemeral garbage collections (generations 0 and 1) last only a few milliseconds, so decreasing pauses is usually not feasible.</span></span> <span data-ttu-id="e4987-213">Sie können jedoch die Pausen in Garbage Collections der Generation 2 verringern, indem Sie das Muster der Belegungsanforderungen in einer Anwendung anpassen.</span><span class="sxs-lookup"><span data-stu-id="e4987-213">However, you can decrease the pauses in generation 2 collections by changing the pattern of allocation requests by an application.</span></span>

<span data-ttu-id="e4987-214">Eine andere und genauere Methode ist die Verwendung von [ETW-Ereignissen der Garbage Collection](../../../docs/framework/performance/garbage-collection-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="e4987-214">Another, more accurate, method is to use [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md).</span></span> <span data-ttu-id="e4987-215">Sie können die Intervalle der Collections ermitteln, indem Sie die Zeitstempeldifferenzen einer bestimmten Ereignissequenz addieren.</span><span class="sxs-lookup"><span data-stu-id="e4987-215">You can find the timings for collections by adding the time stamp differences for a sequence of events.</span></span> <span data-ttu-id="e4987-216">Die gesamte Collection-Sequenz beinhaltet die Unterbrechung der Ausführungs-Engine, die Garbage Collection selbst und die Wiederaufnahme der Ausführungs-Engine.</span><span class="sxs-lookup"><span data-stu-id="e4987-216">The whole collection sequence includes suspension of the execution engine, the garbage collection itself, and the resumption of the execution engine.</span></span>

<span data-ttu-id="e4987-217">Verwenden Sie [Garbage Collection-Benachrichtigungen](../../../docs/standard/garbage-collection/notifications.md), um zu ermitteln, ob ein Server im Begriff ist, eine Collection der Generation 2 durchzuführen, und ob Umleitungsanforderungen an einen anderen Server die Probleme mit Pausen verringern könnten.</span><span class="sxs-lookup"><span data-stu-id="e4987-217">You can use [Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md) to determine whether a server is about to have a generation 2 collection, and whether rerouting requests to another server could ease any problems with pauses.</span></span>

|<span data-ttu-id="e4987-218">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-218">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-219">Bestimmen Sie die Dauer einer Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e4987-219">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)<br /><br /> [<span data-ttu-id="e4987-220">Ermitteln Sie, was eine Garbage Collection ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e4987-220">Determine what caused a garbage collection.</span></span>](#Triggered)|

<a name="Issue_Gen0"></a>

### <a name="issue-generation-0-is-too-big"></a><span data-ttu-id="e4987-221">Problem: Generation 0 ist zu groß</span><span class="sxs-lookup"><span data-stu-id="e4987-221">Issue: Generation 0 Is Too Big</span></span>

<span data-ttu-id="e4987-222">Generation 0 enthält auf einem 64-Bit-System häufig eine größere Anzahl von Objekten, insbesondere, wenn Sie die Garbage Collection auf dem Server statt der Garbage Collection für die Arbeitsstation verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-222">Generation 0 is likely to have a larger number of objects on a 64-bit system, especially when you use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="e4987-223">Dies liegt daran, dass der Schwellenwert zum Auslösen einer Garbage Collection der Generation 0 in dieser Umgebung höher ist und Collections der Generation 0 viel größer werden können.</span><span class="sxs-lookup"><span data-stu-id="e4987-223">This is because the threshold to trigger a generation 0 garbage collection is higher in these environments, and generation 0 collections can get much bigger.</span></span> <span data-ttu-id="e4987-224">Die Leistung wird verbessert, wenn eine Anwendung mehr Arbeitsspeicher belegt, bevor eine Garbage Collection ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-224">Performance is improved when an application allocates more memory before a garbage collection is triggered.</span></span>

<a name="Issue_HighCPU"></a>

### <a name="issue-cpu-usage-during-a-garbage-collection-is-too-high"></a><span data-ttu-id="e4987-225">Problem: Die CPU-Auslastung während einer Garbage Collection ist zu hoch</span><span class="sxs-lookup"><span data-stu-id="e4987-225">Issue: CPU Usage During a Garbage Collection Is Too High</span></span>

<span data-ttu-id="e4987-226">Die CPU-Auslastung ist während einer Garbage Collection hoch.</span><span class="sxs-lookup"><span data-stu-id="e4987-226">CPU usage will be high during a garbage collection.</span></span> <span data-ttu-id="e4987-227">Wenn sehr viel Prozessorzeit für eine Garbage Collection aufgewendet wird, erfolgen die Collections zu häufig, oder die Collection dauert zu lang.</span><span class="sxs-lookup"><span data-stu-id="e4987-227">If a significant amount of process time is spent in a garbage collection, the number of collections is too frequent or the collection is lasting too long.</span></span> <span data-ttu-id="e4987-228">Eine zu hohe Belegungsrate für Objekte auf dem verwalteten Heap führt zu häufigeren Garbage Collections.</span><span class="sxs-lookup"><span data-stu-id="e4987-228">An increased allocation rate of objects on the managed heap causes garbage collection to occur more frequently.</span></span> <span data-ttu-id="e4987-229">Das Verringern der Belegungsrate verringert die Häufigkeit der Garbage Collections.</span><span class="sxs-lookup"><span data-stu-id="e4987-229">Decreasing the allocation rate reduces the frequency of garbage collections.</span></span>

<span data-ttu-id="e4987-230">Sie können die Belegungsrate mit dem Leistungsindikator `Allocated Bytes/second` überwachen.</span><span class="sxs-lookup"><span data-stu-id="e4987-230">You can monitor allocation rates by using the `Allocated Bytes/second` performance counter.</span></span> <span data-ttu-id="e4987-231">Weitere Informationen finden Sie unter [Leistungsindikatoren in .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="e4987-231">For more information, see [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span></span>

<span data-ttu-id="e4987-232">Die Dauer einer Collection wird wesentlich durch die Anzahl der Objekte bestimmt, die nach der Belegung noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-232">The duration of a collection is primarily a factor of the number of objects that survive after allocation.</span></span> <span data-ttu-id="e4987-233">Der Garbage Collector muss einen sehr großen Speicherbereich durchlaufen, wenn viele freizugebende Objekte verblieben sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-233">The garbage collector must go through a large amount of memory if many objects remain to be collected.</span></span> <span data-ttu-id="e4987-234">Der Aufwand für die Komprimierung der Überlebenden ist sehr zeitintensiv.</span><span class="sxs-lookup"><span data-stu-id="e4987-234">The work to compact the survivors is time-consuming.</span></span> <span data-ttu-id="e4987-235">Um zu bestimmen, wie viele Objekte während einer Collection verarbeitet wurden, legen Sie einen Haltepunkt im Debugger am Ende einer Garbage Collection für eine bestimmte Generation fest.</span><span class="sxs-lookup"><span data-stu-id="e4987-235">To determine how many objects were handled during a collection, set a breakpoint in the debugger at the end of a garbage collection for a specified generation.</span></span>

|<span data-ttu-id="e4987-236">Überprüfen der Leistung</span><span class="sxs-lookup"><span data-stu-id="e4987-236">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="e4987-237">Ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-237">Determine if high CPU usage is caused by garbage collection.</span></span>](#HighCPU)<br /><br /> [<span data-ttu-id="e4987-238">Legen Sie einen Haltepunkt am Ende der Garbage Collection fest.</span><span class="sxs-lookup"><span data-stu-id="e4987-238">Set a breakpoint at the end of garbage collection.</span></span>](#GenBreak)|

[<span data-ttu-id="e4987-239">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e4987-239">Back to top</span></span>](#top)

<a name="troubleshooting_guidelines"></a>

## <a name="troubleshooting-guidelines"></a><span data-ttu-id="e4987-240">Richtlinien für die Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e4987-240">Troubleshooting Guidelines</span></span>

<span data-ttu-id="e4987-241">In diesem Abschnitt werden Richtlinien beschrieben, die Sie zu Beginn der Prüfungen und Analysen berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="e4987-241">This section describes guidelines that you should consider as you begin your investigations.</span></span>

### <a name="workstation-or-server-garbage-collection"></a><span data-ttu-id="e4987-242">Garbage Collection für die Arbeitsstation oder Garbage Collection auf dem Server</span><span class="sxs-lookup"><span data-stu-id="e4987-242">Workstation or Server Garbage Collection</span></span>

<span data-ttu-id="e4987-243">Ermitteln Sie, ob Sie den richtigen Typ der Garbage Collection verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-243">Determine if you are using the correct type of garbage collection.</span></span> <span data-ttu-id="e4987-244">Wenn Ihre Anwendung mehrere Threads und Objektinstanzen verwendet, verwenden Sie die Garbage Collection auf dem Server statt der Garbage Collection für die Arbeitsstation.</span><span class="sxs-lookup"><span data-stu-id="e4987-244">If your application uses multiple threads and object instances, use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="e4987-245">Die Garbage Collection auf dem Server kann in mehreren Threads ausgeführt werden, wohingegen die Garbage Collection für die Arbeitsstation erfordert, dass mehrere Instanzen einer Anwendung eigene Garbage Collection-Threads ausführen, die um die Prozessorzeit konkurrieren.</span><span class="sxs-lookup"><span data-stu-id="e4987-245">Server garbage collection operates on multiple threads, whereas workstation garbage collection requires multiple instances of an application to run their own garbage collection threads and compete for CPU time.</span></span>

<span data-ttu-id="e4987-246">Eine Anwendung mit einer geringen Auslastung, die nur selten im Hintergrund Aufgaben ausführt, z. B. ein Dienst, kann die Garbage Collection für die Arbeitsstation mit deaktivierter gleichzeitiger Garbage Collection verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-246">An application that has a low load and that performs tasks infrequently in the background, such as a service, could use workstation garbage collection with concurrent garbage collection disabled.</span></span>

### <a name="when-to-measure-the-managed-heap-size"></a><span data-ttu-id="e4987-247">Wann sollte die Größe des verwalteten Heaps gemessen werden</span><span class="sxs-lookup"><span data-stu-id="e4987-247">When to Measure the Managed Heap Size</span></span>

<span data-ttu-id="e4987-248">Sofern Sie keinen Profiler verwenden, müssen Sie ein einheitliches Messmuster erzielen, um Leistungsprobleme effektiv bestimmen zu können.</span><span class="sxs-lookup"><span data-stu-id="e4987-248">Unless you are using a profiler, you will have to establish a consistent measuring pattern to effectively diagnose performance issues.</span></span> <span data-ttu-id="e4987-249">Beachten Sie bei der Messplanung die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="e4987-249">Consider the following points to establish a schedule:</span></span>

- <span data-ttu-id="e4987-250">Wenn Sie nach einer Garbage Collection in Generation 2 messen, ist der gesamte verwaltete Heap frei von inaktiven Objekten.</span><span class="sxs-lookup"><span data-stu-id="e4987-250">If you measure after a generation 2 garbage collection, the entire managed heap will be free of garbage (dead objects).</span></span>

- <span data-ttu-id="e4987-251">Wenn Sie sofort nach einer Garbage Collection in Generation 0 messen, wurden die Objekte in den Generationen 1 und 2 noch nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e4987-251">If you measure immediately after a generation 0 garbage collection, the objects in generations 1 and 2 will not be collected yet.</span></span>

- <span data-ttu-id="e4987-252">Wenn Sie direkt vor einer Garbage Collection messen, messen Sie die maximale Belegung vor Beginn der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e4987-252">If you measure immediately before a garbage collection, you will measure as much allocation as possible before the garbage collection starts.</span></span>

- <span data-ttu-id="e4987-253">Das Messen während einer Garbage Collection ist problematisch, da die Garbage Collector-Datenstrukturen sich nicht in einem gültigen Zustand für einen Durchlauf befinden und möglicherweise nicht in der Lage sind, vollständige Ergebnisse zu liefern.</span><span class="sxs-lookup"><span data-stu-id="e4987-253">Measuring during a garbage collection is problematic, because the garbage collector data structures are not in a valid state for traversal and may not be able to give you the complete results.</span></span> <span data-ttu-id="e4987-254">Dieser Fehler ist entwurfsbedingt.</span><span class="sxs-lookup"><span data-stu-id="e4987-254">This is by design.</span></span>

- <span data-ttu-id="e4987-255">Wenn Sie die Garbage Collection für die Arbeitsstation mit gleichzeitiger Garbage Collection verwenden, werden die freigegebenen Objekte nicht komprimiert, sodass die Heapgröße identisch oder größer sein kann (sie kann durch die Fragmentierung größer erscheinen).</span><span class="sxs-lookup"><span data-stu-id="e4987-255">When you are using workstation garbage collection with concurrent garbage collection, the reclaimed objects are not compacted, so the heap size can be the same or larger (fragmentation can make it appear to be larger).</span></span>

- <span data-ttu-id="e4987-256">Die gleichzeitige Garbage Collection in Generation 2 wird verzögert, wenn die Auslastung des physischen Arbeitsspeichers zu hoch ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-256">Concurrent garbage collection on generation 2 is delayed when the physical memory load is too high.</span></span>

<span data-ttu-id="e4987-257">Im folgenden Verfahren wird beschrieben, wie Sie einen Haltepunkt festlegen, sodass Sie den verwalteten Heap messen können.</span><span class="sxs-lookup"><span data-stu-id="e4987-257">The following procedure describes how to set a breakpoint so that you can measure the managed heap.</span></span>

<a name="GenBreak"></a>

#### <a name="to-set-a-breakpoint-at-the-end-of-garbage-collection"></a><span data-ttu-id="e4987-258">So legen Sie einen Haltepunkt am Ende der Garbage Collection fest</span><span class="sxs-lookup"><span data-stu-id="e4987-258">To set a breakpoint at the end of garbage collection</span></span>

- <span data-ttu-id="e4987-259">Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-259">In WinDbg with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="e4987-260">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span><span class="sxs-lookup"><span data-stu-id="e4987-260">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span></span>

  <span data-ttu-id="e4987-261">wobei **GcCondemnedGeneration** auf die gewünschte Generation festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-261">where **GcCondemnedGeneration** is set to the desired generation.</span></span> <span data-ttu-id="e4987-262">Dieser Befehl erfordert private Symbole.</span><span class="sxs-lookup"><span data-stu-id="e4987-262">This command requires private symbols.</span></span>

  <span data-ttu-id="e4987-263">Mit diesem Befehl wird eine Unterbrechung erzwungen, wenn **RestartEE** ausgeführt wird, nachdem die Objekte der Generation 2 für die Garbage Collection freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e4987-263">This command forces a break if **RestartEE** is executed after generation 2 objects have been reclaimed for garbage collection.</span></span>

  <span data-ttu-id="e4987-264">Bei der Garbage Collection auf dem Server ruft nur ein Thread **RestartEE** auf, sodass der Haltepunkt nur einmal während einer Garbage Collection der Generation 2 angelaufen wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-264">In server garbage collection, only one thread calls **RestartEE**, so the breakpoint will occur only once during a generation 2 garbage collection.</span></span>

[<span data-ttu-id="e4987-265">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="e4987-265">Back to top</span></span>](#top)

<a name="performance_check_procedures"></a>

## <a name="performance-check-procedures"></a><span data-ttu-id="e4987-266">Prozeduren zur Leistungsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="e4987-266">Performance Check Procedures</span></span>

<span data-ttu-id="e4987-267">In diesem Abschnitt werden die folgenden Verfahren beschrieben, um die Ursache des Leistungsproblems zu isolieren:</span><span class="sxs-lookup"><span data-stu-id="e4987-267">This section describes the following procedures to isolate the cause of your performance issue:</span></span>

- [<span data-ttu-id="e4987-268">Stellen Sie fest, ob das Problem durch die Garbage Collection verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-268">Determine whether the problem is caused by garbage collection.</span></span>](#IsGC)

- [<span data-ttu-id="e4987-269">Bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-269">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)

- [<span data-ttu-id="e4987-270">Ermitteln Sie, wie viel virtueller Speicher reserviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4987-270">Determine how much virtual memory can be reserved.</span></span>](#GetVM)

- [<span data-ttu-id="e4987-271">Bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-271">Determine whether there is enough physical memory.</span></span>](#Physical)

- [<span data-ttu-id="e4987-272">Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert.</span><span class="sxs-lookup"><span data-stu-id="e4987-272">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)

- [<span data-ttu-id="e4987-273">Bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert.</span><span class="sxs-lookup"><span data-stu-id="e4987-273">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)

- [<span data-ttu-id="e4987-274">Bestimmen Sie große Objekte in Generation 2.</span><span class="sxs-lookup"><span data-stu-id="e4987-274">Determine large objects in generation 2.</span></span>](#ExamineGen2)

- [<span data-ttu-id="e4987-275">Bestimmen Sie die Verweise auf Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4987-275">Determine references to objects.</span></span>](#ObjRef)

- [<span data-ttu-id="e4987-276">Bestimmen Sie, ob ein Finalizer ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4987-276">Determine whether a finalizer has been run.</span></span>](#Induce)

- [<span data-ttu-id="e4987-277">Bestimmen Sie, ob Objekte auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="e4987-277">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)

- [<span data-ttu-id="e4987-278">Bestimmen Sie den freien Speicherplatz im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="e4987-278">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)

- [<span data-ttu-id="e4987-279">Bestimmen Sie die Anzahl der fixierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="e4987-279">Determine the number of pinned objects.</span></span>](#Pinned)

- [<span data-ttu-id="e4987-280">Bestimmen Sie die Dauer einer Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e4987-280">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)

- [<span data-ttu-id="e4987-281">Ermitteln Sie, was eine Garbage Collection ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e4987-281">Determine what triggered a garbage collection.</span></span>](#Triggered)

- [<span data-ttu-id="e4987-282">Ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-282">Determine whether high CPU usage is caused by garbage collection.</span></span>](#HighCPU)

<a name="IsGC"></a>

### <a name="to-determine-whether-the-problem-is-caused-by-garbage-collection"></a><span data-ttu-id="e4987-283">So stellen Sie fest, ob das Problem durch die Garbage Collection verursacht wird</span><span class="sxs-lookup"><span data-stu-id="e4987-283">To determine whether the problem is caused by garbage collection</span></span>

- <span data-ttu-id="e4987-284">Überprüfen Sie die folgenden beiden Leistungsindikatoren für den Arbeitsspeicher:</span><span class="sxs-lookup"><span data-stu-id="e4987-284">Examine the following two memory performance counters:</span></span>

  - <span data-ttu-id="e4987-285">**GC-Zeitdauer in Prozent**.</span><span class="sxs-lookup"><span data-stu-id="e4987-285">**% Time in GC**.</span></span> <span data-ttu-id="e4987-286">Zeigt an, wie viel Prozent der vergangenen Zeit seit dem letzten Garbage Collection-Durchlauf mit der Durchführung der Garbage Collection verbracht wurde.</span><span class="sxs-lookup"><span data-stu-id="e4987-286">Displays the percentage of elapsed time that was spent performing a garbage collection after the last garbage collection cycle.</span></span> <span data-ttu-id="e4987-287">Mit diesem Indikator können Sie bestimmen, ob die Garbage Collection zu viel Zeit benötigt, um Speicherplatz auf dem verwalteten Heap verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e4987-287">Use this counter to determine whether the garbage collector is spending too much time to make managed heap space available.</span></span> <span data-ttu-id="e4987-288">Wenn die für die Garbage Collection aufgewendete Zeit relativ gering ist, kann dies auf ein Ressourcenproblem außerhalb des verwalteten Heaps hindeuten.</span><span class="sxs-lookup"><span data-stu-id="e4987-288">If the time spent in garbage collection is relatively low, that could indicate a resource problem outside the managed heap.</span></span> <span data-ttu-id="e4987-289">Dieser Indikator ist möglicherweise nicht präzise, wenn die gleichzeitige oder die Garbage Collection im Hintergrund aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-289">This counter may not be accurate when concurrent or background garbage collection is involved.</span></span>

  - <span data-ttu-id="e4987-290">**Zugesicherte Bytes gesamt**.</span><span class="sxs-lookup"><span data-stu-id="e4987-290">**# Total committed Bytes**.</span></span> <span data-ttu-id="e4987-291">Zeigt den virtuellen Speicher an, der momentan durch den Garbage Collector belegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-291">Displays the amount of virtual memory currently committed by the garbage collector.</span></span> <span data-ttu-id="e4987-292">Mit diesem Indikator können Sie bestimmen, ob der Garbage Collector einen übermäßig großen Teil des Arbeitsspeichers im Verhältnis zur Anwendung selbst belegt.</span><span class="sxs-lookup"><span data-stu-id="e4987-292">Use this counter to determine whether the memory consumed by the garbage collector is an excessive portion of the memory that your application uses.</span></span>

  <span data-ttu-id="e4987-293">Die meisten Speicherleistungsindikatoren werden am Ende jeder Garbage Collection aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e4987-293">Most of the memory performance counters are updated at the end of each garbage collection.</span></span> <span data-ttu-id="e4987-294">Daher geben sie möglicherweise nicht die aktuellen Bedingungen an, zu denen Sie Informationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="e4987-294">Therefore, they may not reflect the current conditions that you want information about.</span></span>

<a name="OOMIsManaged"></a>

### <a name="to-determine-whether-the-out-of-memory-exception-is-managed"></a><span data-ttu-id="e4987-295">So bestimmen Sie, ob die Ausnahme aufgrund ungenügenden Arbeitsspeichers verwaltet ist</span><span class="sxs-lookup"><span data-stu-id="e4987-295">To determine whether the out-of-memory exception is managed</span></span>

1. <span data-ttu-id="e4987-296">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den Befehl zur Ausgabe von Ausnahmen (**pe**) ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-296">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the print exception (**pe**) command:</span></span>

    <span data-ttu-id="e4987-297">**!pe**</span><span class="sxs-lookup"><span data-stu-id="e4987-297">**!pe**</span></span>

    <span data-ttu-id="e4987-298">Wenn die Ausnahme verwaltet ist, wird <xref:System.OutOfMemoryException> als Ausnahmetyp angezeigt, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e4987-298">If the exception is managed, <xref:System.OutOfMemoryException> is displayed as the exception type, as shown in the following example.</span></span>

    ```console
    Exception object: 39594518
    Exception type: System.OutOfMemoryException
    Message: <none>
    InnerException: <none>
    StackTrace (generated):
    ```

2. <span data-ttu-id="e4987-299">Wenn die Ausgabe keine Ausnahme angibt, müssen Sie ermitteln, welcher Thread die Ausnahme aufgrund ungenügenden Arbeitsspeichers ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e4987-299">If the output does not specify an exception, you have to determine which thread the out-of-memory exception is from.</span></span> <span data-ttu-id="e4987-300">Geben Sie im Debugger den folgenden Befehl ein, um alle Threads mit ihren Aufruflisten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e4987-300">Type the following command in the debugger to show all the threads with their call stacks:</span></span>

    <span data-ttu-id="e4987-301">**~\*kb**</span><span class="sxs-lookup"><span data-stu-id="e4987-301">**~\*kb**</span></span>

    <span data-ttu-id="e4987-302">Der Thread mit dem Stapel, der Ausnahmeaufrufe enthält, wird durch das `RaiseTheException`-Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="e4987-302">The thread with the stack that has exception calls is indicated by the `RaiseTheException` argument.</span></span> <span data-ttu-id="e4987-303">Dies ist das verwaltete Ausnahmeobjekt.</span><span class="sxs-lookup"><span data-stu-id="e4987-303">This is the managed exception object.</span></span>

    ```console
    28adfb44 7923918f 5b61f2b4 00000000 5b61f2b4 mscorwks!RaiseTheException+0xa0
    ```

3. <span data-ttu-id="e4987-304">Sie können den folgenden Befehl verwenden, um geschachtelte Ausnahmen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e4987-304">You can use the following command to dump nested exceptions.</span></span>

    <span data-ttu-id="e4987-305">**!pe -nested**</span><span class="sxs-lookup"><span data-stu-id="e4987-305">**!pe -nested**</span></span>

    <span data-ttu-id="e4987-306">Wenn Sie keine Ausnahmen finden können, stammt die Ausnahme aufgrund ungenügenden Arbeitsspeichers aus nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e4987-306">If you do not find any exceptions, the out-of-memory exception originated from unmanaged code.</span></span>

<a name="GetVM"></a>

### <a name="to-determine-how-much-virtual-memory-can-be-reserved"></a><span data-ttu-id="e4987-307">So ermitteln Sie, wie viel virtueller Speicher reserviert werden kann</span><span class="sxs-lookup"><span data-stu-id="e4987-307">To determine how much virtual memory can be reserved</span></span>

- <span data-ttu-id="e4987-308">Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein, um den größten freien Bereich abzurufen:</span><span class="sxs-lookup"><span data-stu-id="e4987-308">In WinDbg with the SOS debugger extension loaded, type the following command to get the largest free region:</span></span>

  <span data-ttu-id="e4987-309">**!address -summary**</span><span class="sxs-lookup"><span data-stu-id="e4987-309">**!address -summary**</span></span>

  <span data-ttu-id="e4987-310">Der größte freie Bereich wird wie in der folgenden Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-310">The largest free region is displayed as shown in the following output.</span></span>

  ```console
  Largest free region: Base 54000000 - Size 0003A980
  ```

  <span data-ttu-id="e4987-311">In diesem Beispiel ist die Größe des größten freien Bereichs ungefähr 24.000 KB (3A980 als Hexadezimalwert).</span><span class="sxs-lookup"><span data-stu-id="e4987-311">In this example, the size of the largest free region is approximately 24000 KB (3A980 in hexadecimal).</span></span> <span data-ttu-id="e4987-312">Dieser Bereich ist wesentlich kleiner als der Bereich, den die Garbage Collection für ein Segment benötigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-312">This region is much smaller than what the garbage collector needs for a segment.</span></span>

  <span data-ttu-id="e4987-313">Oder</span><span class="sxs-lookup"><span data-stu-id="e4987-313">-or-</span></span>

- <span data-ttu-id="e4987-314">Verwenden Sie den Befehl **vmstat**:</span><span class="sxs-lookup"><span data-stu-id="e4987-314">Use the **vmstat** command:</span></span>

  <span data-ttu-id="e4987-315">**!vmstat**</span><span class="sxs-lookup"><span data-stu-id="e4987-315">**!vmstat**</span></span>

  <span data-ttu-id="e4987-316">Der größte freie Bereich ist der größte Wert in der Spalte MAXIMUM, wie in der folgenden Ausgabe gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-316">The largest free region is the largest value in the MAXIMUM column, as shown in the following output.</span></span>

  ```console
  TYPE        MINIMUM   MAXIMUM     AVERAGE   BLK COUNT   TOTAL
  ~~~~        ~~~~~~~   ~~~~~~~     ~~~~~~~   ~~~~~~~~~~  ~~~~
  Free:
  Small       8K        64K         46K       36          1,671K
  Medium      80K       864K        349K      3           1,047K
  Large       1,384K    1,278,848K  151,834K  12          1,822,015K
  Summary     8K        1,278,848K  35,779K   51          1,824,735K
  ```

<a name="Physical"></a>

### <a name="to-determine-whether-there-is-enough-physical-memory"></a><span data-ttu-id="e4987-317">So bestimmen Sie, ob ausreichend physikalischer Speicher vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="e4987-317">To determine whether there is enough physical memory</span></span>

1. <span data-ttu-id="e4987-318">Starten Sie Windows Task-Manager.</span><span class="sxs-lookup"><span data-stu-id="e4987-318">Start Windows Task Manager.</span></span>

2. <span data-ttu-id="e4987-319">Prüfen Sie auf der Registerkarte **Leistung** den zugesicherten Wert.</span><span class="sxs-lookup"><span data-stu-id="e4987-319">On the **Performance** tab, look at the committed value.</span></span> <span data-ttu-id="e4987-320">(Prüfen Sie unter Windows 7 den Wert **Zugesichert (KB)** in der **Systemgruppe**.)</span><span class="sxs-lookup"><span data-stu-id="e4987-320">(In Windows 7, look at **Commit (KB)** in the **System group**.)</span></span>

    <span data-ttu-id="e4987-321">Wenn **Gesamt** nahe der **Grenze** ist, ist nicht genügend physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4987-321">If the **Total** is close to the **Limit**, you are running low on physical memory.</span></span>

<a name="ManagedHeapCommit"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-is-committing"></a><span data-ttu-id="e4987-322">So bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap zusichert</span><span class="sxs-lookup"><span data-stu-id="e4987-322">To determine how much memory the managed heap is committing</span></span>

- <span data-ttu-id="e4987-323">Verwenden Sie den Speicherleistungsindikator `# Total committed bytes`, um die Anzahl an Bytes abzurufen, die der verwaltete Heap zusichert.</span><span class="sxs-lookup"><span data-stu-id="e4987-323">Use the `# Total committed bytes` memory performance counter to get the number of bytes that the managed heap is committing.</span></span> <span data-ttu-id="e4987-324">Der Garbage Collector sichert nach Bedarf Ausschnitte in einem Segment zu, niemals alle zur selben Zeit.</span><span class="sxs-lookup"><span data-stu-id="e4987-324">The garbage collector commits chunks on a segment as needed, not all at the same time.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e4987-325">Verwenden Sie nicht den Leistungsindikator `# Bytes in all Heaps`, da dieser nicht die tatsächliche Speicherauslastung des verwalteten Heaps angibt.</span><span class="sxs-lookup"><span data-stu-id="e4987-325">Do not use the `# Bytes in all Heaps` performance counter, because it does not represent actual memory usage by the managed heap.</span></span> <span data-ttu-id="e4987-326">Die Größe einer Generation ist in diesem Wert enthalten, und es handelt sich eigentlich um den Schwellenwert, d. h. um die Größe, bei der eine Garbage Collection ausgelöst wird, wenn die Generation mit Objekten gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-326">The size of a generation is included in this value and is actually its threshold size, that is, the size that induces a garbage collection if the generation is filled with objects.</span></span> <span data-ttu-id="e4987-327">Daher ist dieser Wert 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e4987-327">Therefore, this value is usually zero.</span></span>

<a name="ManagedHeapReserve"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-reserves"></a><span data-ttu-id="e4987-328">So bestimmen Sie, wie viel Arbeitsspeicher der verwaltete Heap reserviert</span><span class="sxs-lookup"><span data-stu-id="e4987-328">To determine how much memory the managed heap reserves</span></span>

- <span data-ttu-id="e4987-329">Verwenden Sie den Speicherleistungsindikator `# Total reserved bytes`.</span><span class="sxs-lookup"><span data-stu-id="e4987-329">Use the `# Total reserved bytes` memory performance counter.</span></span>

  <span data-ttu-id="e4987-330">Der Garbage Collector reserviert Speicherplatz in Segmenten. Sie können den Anfang eines Segments ermitteln, indem Sie den Befehl **eeheap** verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-330">The garbage collector reserves memory in segments, and you can determine where a segment starts by using the **eeheap** command.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e4987-331">Obwohl Sie die Größe des Arbeitsspeichers ermitteln können, der vom Garbage Collector für jedes Segment zugewiesen wird, ist die Segmentgröße von der Implementierung abhängig und kann jederzeit geändert werden, auch bei regelmäßigen Updates.</span><span class="sxs-lookup"><span data-stu-id="e4987-331">Although you can determine the amount of memory the garbage collector allocates for each segment, segment size is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="e4987-332">Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen, und es darf in ihr auch nicht versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e4987-332">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

- <span data-ttu-id="e4987-333">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-333">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="e4987-334">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="e4987-334">**!eeheap -gc**</span></span>

  <span data-ttu-id="e4987-335">Daraus ergibt sich folgendes Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e4987-335">The result is as follows.</span></span>

  ```console
  Number of GC Heaps: 2
  ------------------------------
  Heap 0 (002db550)
  generation 0 starts at 0x02abe29c
  generation 1 starts at 0x02abdd08
  generation 2 starts at 0x02ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  02ab0000 02ab0038  02aceff4 0x0001efbc(126908)
  Large object heap starts at 0x0aab0038
    segment    begin allocated     size
  0aab0000 0aab0038  0aab2278 0x00002240(8768)
  Heap Size   0x211fc(135676)
  ------------------------------
  Heap 1 (002dc958)
  generation 0 starts at 0x06ab1bd8
  generation 1 starts at 0x06ab1bcc
  generation 2 starts at 0x06ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  06ab0000 06ab0038  06ab3be4 0x00003bac(15276)
  Large object heap starts at 0x0cab0038
    segment    begin allocated     size
  0cab0000 0cab0038  0cab0048 0x00000010(16)
  Heap Size    0x3bbc(15292)
  ------------------------------
  GC Heap Size   0x24db8(150968)
  ```

  <span data-ttu-id="e4987-336">Die Adressen, die durch "segment" angegeben werden, sind die Startadressen der Segmente.</span><span class="sxs-lookup"><span data-stu-id="e4987-336">The addresses indicated by "segment" are the starting addresses of the segments.</span></span>

<a name="ExamineGen2"></a>

### <a name="to-determine-large-objects-in-generation-2"></a><span data-ttu-id="e4987-337">So bestimmen Sie große Objekte in Generation 2</span><span class="sxs-lookup"><span data-stu-id="e4987-337">To determine large objects in generation 2</span></span>

- <span data-ttu-id="e4987-338">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-338">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="e4987-339">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="e4987-339">**!dumpheap –stat**</span></span>

  <span data-ttu-id="e4987-340">Wenn der verwaltete Heap groß ist, kann die Ausführung von **dumpheap** eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="e4987-340">If the managed heap is big, **dumpheap** may take a while to finish.</span></span>

  <span data-ttu-id="e4987-341">Sie können die Analyse in den letzten Zeilen der Ausgabe beginnen, da diese die Objekte auflisten, die den meisten Platz verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-341">You can start analyzing from the last few lines of the output, because they list the objects that use the most space.</span></span> <span data-ttu-id="e4987-342">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e4987-342">For example:</span></span>

  ```console
  2c6108d4   173712     14591808 DevExpress.XtraGrid.Views.Grid.ViewInfo.GridCellInfo
  00155f80      533     15216804      Free
  7a747c78   791070     15821400 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700930     19626040 System.Collections.Specialized.ListDictionary
  2c64e36c    78644     20762016 DevExpress.XtraEditors.ViewInfo.TextEditViewInfo
  79124228   121143     29064120 System.Object[]
  035f0ee4    81626     35588936 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    40182     90664128 System.Collections.Hashtable+bucket[]
  790fa3e0  3154024    137881448 System.String
  Total 8454945 objects
  ```

  <span data-ttu-id="e4987-343">Das letzte aufgelistete Objekt ist eine Zeichenfolge, die den meisten Platz beansprucht.</span><span class="sxs-lookup"><span data-stu-id="e4987-343">The last object listed is a string and occupies the most space.</span></span> <span data-ttu-id="e4987-344">Sie können Ihre Anwendung überprüfen, um zu ermitteln, wie die Zeichenfolgenobjekte optimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e4987-344">You can examine your application to see how your string objects can be optimized.</span></span> <span data-ttu-id="e4987-345">Um Zeichenfolgen anzuzeigen, die zwischen 150 und 200 Byte groß sind, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-345">To see strings that are between 150 and 200 bytes, type the following:</span></span>

  <span data-ttu-id="e4987-346">**!dumpheap -type System.String -min 150 -max 200**</span><span class="sxs-lookup"><span data-stu-id="e4987-346">**!dumpheap -type System.String -min 150 -max 200**</span></span>

  <span data-ttu-id="e4987-347">Ein Beispielergebnis sieht wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="e4987-347">An example of the results is as follows.</span></span>

  ```console
  Address  MT           Size  Gen
  1875d2c0 790fa3e0      152    2 System.String HighlightNullStyle_Blotter_PendingOrder-11_Blotter_PendingOrder-11
  …
  ```

  <span data-ttu-id="e4987-348">Das Verwenden einer ganzen Zahl anstelle einer Zeichenfolge für eine ID kann effizienter sein.</span><span class="sxs-lookup"><span data-stu-id="e4987-348">Using an integer instead of a string for an ID can be more efficient.</span></span> <span data-ttu-id="e4987-349">Wenn dieselbe Zeichenfolge viele tausend Mal wiederholt wird, sollten Sie eine Internalisierung der Zeichenfolgen in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="e4987-349">If the same string is being repeated thousands of times, consider string interning.</span></span> <span data-ttu-id="e4987-350">Weitere Informationen zur Internalisierung von Zeichenfolgen finden Sie im Referenzthema für die <xref:System.String.Intern%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="e4987-350">For more information about string interning, see the reference topic for the <xref:System.String.Intern%2A?displayProperty=nameWithType> method.</span></span>

<a name="ObjRef"></a>

### <a name="to-determine-references-to-objects"></a><span data-ttu-id="e4987-351">So bestimmen Sie Verweise auf Objekte</span><span class="sxs-lookup"><span data-stu-id="e4987-351">To determine references to objects</span></span>

- <span data-ttu-id="e4987-352">Geben Sie in WinDbg bei geladener SOS-Debuggererweiterung folgenden Befehl ein, um Objektverweise aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="e4987-352">In WinDbg with the SOS debugger extension loaded, type the following command to list references to objects:</span></span>

  <span data-ttu-id="e4987-353">**!gcroot**</span><span class="sxs-lookup"><span data-stu-id="e4987-353">**!gcroot**</span></span>

  `-or-`

- <span data-ttu-id="e4987-354">Um die Verweise für ein bestimmtes Objekt zu ermitteln, geben Sie zusätzlich die Adresse an:</span><span class="sxs-lookup"><span data-stu-id="e4987-354">To determine the references for a specific object, include the address:</span></span>

  <span data-ttu-id="e4987-355">**!gcroot 1c37b2ac**</span><span class="sxs-lookup"><span data-stu-id="e4987-355">**!gcroot 1c37b2ac**</span></span>

  <span data-ttu-id="e4987-356">Die Stammelemente, die in Stapeln gefunden werden, sind möglicherweise falsche positive Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e4987-356">Roots found on stacks may be false positives.</span></span> <span data-ttu-id="e4987-357">Weitere Informationen erhalten Sie mit dem Befehl `!help gcroot`.</span><span class="sxs-lookup"><span data-stu-id="e4987-357">For more information, use the command `!help gcroot`.</span></span>

  ```console
  ebx:Root:19011c5c(System.Windows.Forms.Application+ThreadContext)->
  19010b78(DemoApp.FormDemoApp)->
  19011158(System.Windows.Forms.PropertyStore)->
  … [omitted]
  1c3745ec(System.Data.DataTable)->
  1c3747a8(System.Data.DataColumnCollection)->
  1c3747f8(System.Collections.Hashtable)->
  1c376590(System.Collections.Hashtable+bucket[])->
  1c376c98(System.Data.DataColumn)->
  1c37b270(System.Data.Common.DoubleStorage)->
  1c37b2ac(System.Double[])
  Scan Thread 0 OSTHread 99c
  Scan Thread 6 OSTHread 484
  ```

  <span data-ttu-id="e4987-358">Ein Ausführen des Befehls **gcroot** kann lange dauern.</span><span class="sxs-lookup"><span data-stu-id="e4987-358">The **gcroot** command can take a long time to finish.</span></span> <span data-ttu-id="e4987-359">Jedes Objekt, das nicht von der Garbage Collection freigegeben wurde, ist ein aktives Objekt.</span><span class="sxs-lookup"><span data-stu-id="e4987-359">Any object that is not reclaimed by garbage collection is a live object.</span></span> <span data-ttu-id="e4987-360">Das heißt, dass ein Stamm direkt oder indirekt das Objekt hält, sodass **gcroot** Pfadinformationen zum Objekt zurückgeben sollte.</span><span class="sxs-lookup"><span data-stu-id="e4987-360">This means that some root is directly or indirectly holding onto the object, so **gcroot** should return path information to the object.</span></span> <span data-ttu-id="e4987-361">Sie sollten die zurückgegebenen Diagramme untersuchen und feststellen, warum auf diese Objekte immer noch verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-361">You should examine the graphs returned and see why these objects are still referenced.</span></span>

<a name="Induce"></a>

### <a name="to-determine-whether-a-finalizer-has-been-run"></a><span data-ttu-id="e4987-362">So bestimmen Sie, ob ein Finalizer ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="e4987-362">To determine whether a finalizer has been run</span></span>

- <span data-ttu-id="e4987-363">Führen Sie ein Testprogramm aus, das den folgenden Code enthält:</span><span class="sxs-lookup"><span data-stu-id="e4987-363">Run a test program that contains the following code:</span></span>

  ```csharp
  GC.Collect();
  GC.WaitForPendingFinalizers();
  GC.Collect();
  ```

  <span data-ttu-id="e4987-364">Wenn der Test das Problem behebt, heißt dies, dass der Garbage Collector keine Objekte freigegeben hat, da die Finalizer für diese Objekte unterbrochen wurden.</span><span class="sxs-lookup"><span data-stu-id="e4987-364">If the test resolves the problem, this means that the garbage collector was not reclaiming objects, because the finalizers for those objects had been suspended.</span></span> <span data-ttu-id="e4987-365">Mithilfe der <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType>-Methode können die Finalizer ihre Aufgaben abschließen und das Problem beheben.</span><span class="sxs-lookup"><span data-stu-id="e4987-365">The <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method enables the finalizers to complete their tasks, and fixes the problem.</span></span>

<a name="Finalize"></a>

### <a name="to-determine-whether-there-are-objects-waiting-to-be-finalized"></a><span data-ttu-id="e4987-366">So bestimmen Sie, ob Objekte auf einen Abschluss warten</span><span class="sxs-lookup"><span data-stu-id="e4987-366">To determine whether there are objects waiting to be finalized</span></span>

1. <span data-ttu-id="e4987-367">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-367">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

    <span data-ttu-id="e4987-368">**!finalizequeue**</span><span class="sxs-lookup"><span data-stu-id="e4987-368">**!finalizequeue**</span></span>

    <span data-ttu-id="e4987-369">Prüfen Sie die Anzahl der Objekte, die auf einen Abschluss warten.</span><span class="sxs-lookup"><span data-stu-id="e4987-369">Look at the number of objects that are ready for finalization.</span></span> <span data-ttu-id="e4987-370">Wenn die Zahl hoch ist, müssen Sie überprüfen, weshalb diese Finalizer nicht schnell genug bzw. überhaupt nicht fortgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="e4987-370">If the number is high, you must examine why these finalizers cannot progress at all or cannot progress fast enough.</span></span>

2. <span data-ttu-id="e4987-371">Um eine Ausgabe der Threads abzurufen, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-371">To get an output of threads, type the following command:</span></span>

    <span data-ttu-id="e4987-372">**threads -special**</span><span class="sxs-lookup"><span data-stu-id="e4987-372">**threads -special**</span></span>

    <span data-ttu-id="e4987-373">Dieser Befehl stellt folgende Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="e4987-373">This command provides output such as the following.</span></span>

    ```console
       OSID     Special thread type
    2    cd0    DbgHelper
    3    c18    Finalizer
    4    df0    GC SuspendEE
    ```

    <span data-ttu-id="e4987-374">Der Finalizerthread gibt an, welcher Finalizer, sofern vorhanden, aktuell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-374">The finalizer thread indicates which finalizer, if any, is currently being run.</span></span> <span data-ttu-id="e4987-375">Wenn ein Finalizerthread keine Finalizer ausführt, wartet er auf ein Ereignis, das die Ausführung startet.</span><span class="sxs-lookup"><span data-stu-id="e4987-375">When a finalizer thread is not running any finalizers, it is waiting for an event to tell it to do its work.</span></span> <span data-ttu-id="e4987-376">Der Finalizerthread befindet sich meistens in diesem Zustand, da er mit THREAD_HIGHEST_PRIORITY ausgeführt wird und die Ausführung von Finalizern i. d. R. sehr schnell abschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="e4987-376">Most of the time you will see the finalizer thread in this state because it runs at THREAD_HIGHEST_PRIORITY and is supposed to finish running finalizers, if any, very quickly.</span></span>

<a name="Fragmented"></a>

### <a name="to-determine-the-amount-of-free-space-in-the-managed-heap"></a><span data-ttu-id="e4987-377">So bestimmen Sie den freien Speicherplatz im verwalteten Heap</span><span class="sxs-lookup"><span data-stu-id="e4987-377">To determine the amount of free space in the managed heap</span></span>

- <span data-ttu-id="e4987-378">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-378">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="e4987-379">**!dumpheap -type Free -stat**</span><span class="sxs-lookup"><span data-stu-id="e4987-379">**!dumpheap -type Free -stat**</span></span>

  <span data-ttu-id="e4987-380">Dieser Befehl zeigt die Gesamtgröße aller freien Objekte im verwalteten Heap an, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-380">This command displays the total size of all the free objects on the managed heap, as shown in the following example.</span></span>

  ```console
  total 230 objects
  Statistics:
        MT    Count    TotalSize Class Name
  00152b18      230     40958584      Free
  Total 230 objects
  ```

- <span data-ttu-id="e4987-381">Um den freien Speicherplatz in Generation 0 zu ermitteln, geben Sie den folgenden Befehl ein, um Informationen zum Speicherverbrauch jeder Generation zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e4987-381">To determine the free space in generation 0, type the following command for memory consumption information by generation:</span></span>

  <span data-ttu-id="e4987-382">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="e4987-382">**!eeheap -gc**</span></span>

  <span data-ttu-id="e4987-383">Dieser Befehl zeigt eine Ausgabe ähnlich der folgenden an.</span><span class="sxs-lookup"><span data-stu-id="e4987-383">This command displays output similar to the following.</span></span> <span data-ttu-id="e4987-384">Die letzte Zeile zeigt das kurzlebige Segment an.</span><span class="sxs-lookup"><span data-stu-id="e4987-384">The last line shows the ephemeral segment.</span></span>

  ```console
  Heap 0 (0015ad08)
  generation 0 starts at 0x49521f8c
  generation 1 starts at 0x494d7f64
  generation 2 starts at 0x007f0038
  ephemeral segment allocation context: none
  segment  begin     allocated  size
  00178250 7a80d84c  7a82f1cc   0x00021980(137600)
  00161918 78c50e40  78c7056c   0x0001f72c(128812)
  007f0000 007f0038  047eed28   0x03ffecf0(67103984)
  3a120000 3a120038  3a3e84f8   0x002c84c0(2917568)
  46120000 46120038  49e05d04   0x03ce5ccc(63855820)
  ```

- <span data-ttu-id="e4987-385">Berechnen Sie den Speicherplatz für Generation 0:</span><span class="sxs-lookup"><span data-stu-id="e4987-385">Calculate the space used by generation 0:</span></span>

  <span data-ttu-id="e4987-386">**? 49e05d04-0x49521f8c**</span><span class="sxs-lookup"><span data-stu-id="e4987-386">**? 49e05d04-0x49521f8c**</span></span>

  <span data-ttu-id="e4987-387">Daraus ergibt sich folgendes Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e4987-387">The result is as follows.</span></span> <span data-ttu-id="e4987-388">Generation 0 belegt ungefähr 9 MB.</span><span class="sxs-lookup"><span data-stu-id="e4987-388">Generation 0 is approximately 9 MB.</span></span>

  ```console
  Evaluate expression: 9321848 = 008e3d78
  ```

- <span data-ttu-id="e4987-389">Der folgende Befehl gibt den freien Platz im Bereich der Generation 0 aus:</span><span class="sxs-lookup"><span data-stu-id="e4987-389">The following command dumps the free space within the generation 0 range:</span></span>

  <span data-ttu-id="e4987-390">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span><span class="sxs-lookup"><span data-stu-id="e4987-390">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span></span>

  <span data-ttu-id="e4987-391">Daraus ergibt sich folgendes Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e4987-391">The result is as follows.</span></span>

  ```console
  ------------------------------
  Heap 0
  total 409 objects
  ------------------------------
  Heap 1
  total 0 objects
  ------------------------------
  Heap 2
  total 0 objects
  ------------------------------
  Heap 3
  total 0 objects
  ------------------------------
  total 409 objects
  Statistics:
        MT    Count TotalSize Class Name
  0015a498      409   7296540      Free
  Total 409 objects
  ```

  <span data-ttu-id="e4987-392">Diese Ausgabe zeigt, dass der Bereich der Generation 0 im Heap 9 MB Speicherplatz für Objekte verwendet, von denen 7 MB frei sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-392">This output shows that the generation 0 portion of the heap is using 9 MB of space for objects and has 7 MB free.</span></span> <span data-ttu-id="e4987-393">Diese Analyse zeigt, in welchem Maße Generation 0 zur Fragmentierung beiträgt.</span><span class="sxs-lookup"><span data-stu-id="e4987-393">This analysis shows the extent to which generation 0 contributes to fragmentation.</span></span> <span data-ttu-id="e4987-394">Dieser Anteil des verwendeten Heaps sollte, als Ursache für die Fragmentierung von Langzeitobjekten, von der Gesamtgröße abgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="e4987-394">This amount of heap usage should be discounted from the total amount as the cause of fragmentation by long-term objects.</span></span>

<a name="Pinned"></a>

### <a name="to-determine-the-number-of-pinned-objects"></a><span data-ttu-id="e4987-395">So bestimmen Sie die Anzahl der fixierten Objekte</span><span class="sxs-lookup"><span data-stu-id="e4987-395">To determine the number of pinned objects</span></span>

- <span data-ttu-id="e4987-396">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e4987-396">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="e4987-397">**!gchandles**</span><span class="sxs-lookup"><span data-stu-id="e4987-397">**!gchandles**</span></span>

  <span data-ttu-id="e4987-398">Die angezeigte Statistik beinhaltet die Anzahl der festen Handles, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-398">The statistics displayed includes the number of pinned handles, as the following example shows.</span></span>

  ```console
  GC Handle Statistics:
  Strong Handles:      29
  Pinned Handles:      10
  ```

<a name="TimeInGC"></a>

### <a name="to-determine-the-length-of-time-in-a-garbage-collection"></a><span data-ttu-id="e4987-399">So bestimmen Sie die Dauer einer Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="e4987-399">To determine the length of time in a garbage collection</span></span>

- <span data-ttu-id="e4987-400">Überprüfen Sie den Speicherleistungsindikator `% Time in GC`.</span><span class="sxs-lookup"><span data-stu-id="e4987-400">Examine the `% Time in GC` memory performance counter.</span></span>

  <span data-ttu-id="e4987-401">Der Wert wird anhand eines Samplingintervalls berechnet.</span><span class="sxs-lookup"><span data-stu-id="e4987-401">The value is calculated by using a sample interval time.</span></span> <span data-ttu-id="e4987-402">Da die Indikatoren am Ende jeder Garbage Collection aktualisiert werden, hat die aktuelle Messung den gleichen Wert wie die vorhergehende Messung, wenn während des Intervalls keine Collections aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-402">Because the counters are updated at the end of each garbage collection, the current sample will have the same value as the previous sample if no collections occurred during the interval.</span></span>

  <span data-ttu-id="e4987-403">Die Dauer der Collection wird durch die Multiplikation der Samplingintervalldauer mit dem Prozentwert ermittelt.</span><span class="sxs-lookup"><span data-stu-id="e4987-403">Collection time is obtained by multiplying the sample interval time with the percentage value.</span></span>

  <span data-ttu-id="e4987-404">Die folgenden Daten zeigen vier Messintervalle von 2 Sekunden in einer Messung über 8 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="e4987-404">The following data shows four sampling intervals of two seconds, for an 8-second study.</span></span> <span data-ttu-id="e4987-405">Die Spalten `Gen0`, `Gen1` und `Gen2` zeigen die Anzahl der Garbage Collections, die während dieses Intervalls für diese Generation aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-405">The `Gen0`, `Gen1`, and `Gen2` columns show the number of garbage collections that occurred during that interval for that generation.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2    % Time in GC
          1       9       3       1              10
          2      10       3       1               1
          3      11       3       1               3
          4      11       3       1               3
  ```

  <span data-ttu-id="e4987-406">Diese Informationen geben nicht an, wann die Garbage Collection erfolgt ist, Sie können aber die Anzahl der Garbage Collections ermitteln, die in einem bestimmten Zeitintervall aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e4987-406">This information does not show when the garbage collection occurred, but you can determine the number of garbage collections that occurred in an interval of time.</span></span> <span data-ttu-id="e4987-407">Im schlimmsten Fall wurde die Garbage Collection der zehnten Generation 0 zu Beginn des zweiten Intervalls abgeschlossen und die Garbage Collection der elften Generation 0 zum Ende des fünften Intervalls.</span><span class="sxs-lookup"><span data-stu-id="e4987-407">Assuming the worst case, the tenth generation 0 garbage collection finished at the start of the second interval, and the eleventh generation 0 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="e4987-408">Die Zeit zwischen dem Ende der zehnten und dem Ende der elften Garbage Collection ist ungefähr 2 Sekunden, und der Leistungsindikator zeigt 3%. Daher war die Dauer der elften Garbage Collection der Generation 0 (2 Sekunden \* 3% = 60ms).</span><span class="sxs-lookup"><span data-stu-id="e4987-408">The time between the end of the tenth and the end of the eleventh garbage collection is about 2 seconds, and the performance counter shows 3%, so the duration of the eleventh generation 0 garbage collection was (2 seconds \* 3% = 60ms).</span></span>

  <span data-ttu-id="e4987-409">In diesem Beispiel gibt es 5 Intervalle.</span><span class="sxs-lookup"><span data-stu-id="e4987-409">In this example, there are 5 periods.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2     % Time in GC
          1       9       3       1                3
          2      10       3       1                1
          3      11       4       2                1
          4      11       4       2                1
          5      11       4       2               20
  ```

  <span data-ttu-id="e4987-410">Die zweite Garbage Collection der Generation 2 wurde während des dritten Intervalls gestartet und im fünften Intervall abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e4987-410">The second generation 2 garbage collection started during the third interval and finished at the fifth interval.</span></span> <span data-ttu-id="e4987-411">Im schlimmsten Fall erfolgte die letzte Garbage Collection für eine Collection der Generation 0, die zu Beginn des zweiten Intervalls abgeschlossen wurde, und die Garbage Collection der Generation 2 wurde zum Ende des fünften Intervalls abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e4987-411">Assuming the worst case, the last garbage collection was for a generation 0 collection that finished at the start of the second interval, and the generation 2 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="e4987-412">Daher ist die Zeit zwischen dem Ende der Garbage Collection der Generation 0 und dem Ende der Garbage Collection der Generation 2 4 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="e4987-412">Therefore, the time between the end of the generation 0 garbage collection and the end of the generation 2 garbage collection is 4 seconds.</span></span> <span data-ttu-id="e4987-413">Da der `% Time in GC`-Indikator 20% angibt, beträgt die maximale Zeitdauer, die die Garbage Collection der Generation 2 benötigt haben kann: (4 Sekunden \* 20% = 800ms).</span><span class="sxs-lookup"><span data-stu-id="e4987-413">Because the `% Time in GC` counter is 20%, the maximum amount of time the generation 2 garbage collection could have taken is (4 seconds \* 20% = 800ms).</span></span>

- <span data-ttu-id="e4987-414">Alternativ können Sie die Länge einer Garbage Collection mithilfe der [ETW-Ereignisse der Garbage Collection](../../../docs/framework/performance/garbage-collection-etw-events.md) bestimmen und die Informationen analysieren, um so die Dauer der Garbage Collection zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e4987-414">Alternatively, you can determine the length of a garbage collection by using [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md), and analyze the information to determine the duration of garbage collection.</span></span>

  <span data-ttu-id="e4987-415">Beispielsweise enthalten die folgenden Daten eine Ereignissequenz, die während einer nicht gleichzeitigen Garbage Collection aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-415">For example, the following data shows an event sequence that occurred during a non-concurrent garbage collection.</span></span>

  ```console
  Timestamp    Event name
  513052        GCSuspendEEBegin_V1
  513078        GCSuspendEEEnd
  513090        GCStart_V1
  517890        GCEnd_V1
  517894        GCHeapStats
  517897        GCRestartEEBegin
  517918        GCRestartEEEnd
  ```

  <span data-ttu-id="e4987-416">Das Anhalten des verwalteten Threads dauerte 26us (`GCSuspendEEEnd` - `GCSuspendEEBegin_V1`).</span><span class="sxs-lookup"><span data-stu-id="e4987-416">Suspending the managed thread took 26us (`GCSuspendEEEnd` – `GCSuspendEEBegin_V1`).</span></span>

  <span data-ttu-id="e4987-417">Die tatsächliche Garbage Collection dauerte 4,8ms (`GCEnd_V1` - `GCStart_V1`).</span><span class="sxs-lookup"><span data-stu-id="e4987-417">The actual garbage collection took 4.8ms (`GCEnd_V1` – `GCStart_V1`).</span></span>

  <span data-ttu-id="e4987-418">Das Fortsetzen der verwalteten Threads dauerte 21us (`GCRestartEEEnd` - `GCRestartEEBegin`).</span><span class="sxs-lookup"><span data-stu-id="e4987-418">Resuming the managed threads took 21us (`GCRestartEEEnd` – `GCRestartEEBegin`).</span></span>

  <span data-ttu-id="e4987-419">Die folgende Ausgabe zeigt ein Beispiel für eine Garbage Collection im Hintergrund und enthält Felder für den Prozess, den Thread und das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e4987-419">The following output provides an example for background garbage collection, and includes the process, thread, and event fields.</span></span> <span data-ttu-id="e4987-420">(Es werden nicht alle Daten gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="e4987-420">(Not all data is shown.)</span></span>

  ```console
  timestamp(us)    event name            process    thread    event field
  42504385        GCSuspendEEBegin_V1    Test.exe    4372             1
  42504648        GCSuspendEEEnd         Test.exe    4372
  42504816        GCStart_V1             Test.exe    4372        102019
  42504907        GCStart_V1             Test.exe    4372        102020
  42514170        GCEnd_V1               Test.exe    4372
  42514204        GCHeapStats            Test.exe    4372        102020
  42832052        GCRestartEEBegin       Test.exe    4372
  42832136        GCRestartEEEnd         Test.exe    4372
  63685394        GCSuspendEEBegin_V1    Test.exe    4744             6
  63686347        GCSuspendEEEnd         Test.exe    4744
  63784294        GCRestartEEBegin       Test.exe    4744
  63784407        GCRestartEEEnd         Test.exe    4744
  89931423        GCEnd_V1               Test.exe    4372        102019
  89931464        GCHeapStats            Test.exe    4372
  ```

  <span data-ttu-id="e4987-421">Das `GCStart_V1`-Ereignis bei 42504816 gibt an, dass dies eine Garbage Collection im Hintergrund ist, da das letzte Feld `1` ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-421">The `GCStart_V1` event at 42504816 indicates that this is a background garbage collection, because the last field is `1`.</span></span> <span data-ttu-id="e4987-422">Dies wird Garbage Collection Nr.</span><span class="sxs-lookup"><span data-stu-id="e4987-422">This becomes garbage collection No.</span></span> <span data-ttu-id="e4987-423">102019.</span><span class="sxs-lookup"><span data-stu-id="e4987-423">102019.</span></span>

  <span data-ttu-id="e4987-424">Das `GCStart`-Ereignis tritt auf, weil eine kurzlebige Garbage Collection erforderlich ist, bevor eine Garbage Collection im Hintergrund gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e4987-424">The `GCStart` event occurs because there is a need for an ephemeral garbage collection before you start a background garbage collection.</span></span> <span data-ttu-id="e4987-425">Dies wird Garbage Collection Nr.</span><span class="sxs-lookup"><span data-stu-id="e4987-425">This becomes garbage collection No.</span></span> <span data-ttu-id="e4987-426">102020.</span><span class="sxs-lookup"><span data-stu-id="e4987-426">102020.</span></span>

  <span data-ttu-id="e4987-427">Bei 42514170 wird Garbage Collection Nr.</span><span class="sxs-lookup"><span data-stu-id="e4987-427">At 42514170, garbage collection No.</span></span> <span data-ttu-id="e4987-428">102020 beendet.</span><span class="sxs-lookup"><span data-stu-id="e4987-428">102020 finishes.</span></span> <span data-ttu-id="e4987-429">Die verwalteten Threads werden an diesem Punkt neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="e4987-429">The managed threads are restarted at this point.</span></span> <span data-ttu-id="e4987-430">Dies wird im Thread 4372 abgeschlossen, der diese Garbage Collection im Hintergrund ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="e4987-430">This is completed on thread 4372, which triggered this background garbage collection.</span></span>

  <span data-ttu-id="e4987-431">Im Thread 4744 tritt eine Unterbrechung auf.</span><span class="sxs-lookup"><span data-stu-id="e4987-431">On thread 4744, a suspension occurs.</span></span> <span data-ttu-id="e4987-432">Dies ist das einzige Mal, dass die Garbage Collection im Hintergrund verwaltete Threads anhalten muss.</span><span class="sxs-lookup"><span data-stu-id="e4987-432">This is the only time at which the background garbage collection has to suspend managed threads.</span></span> <span data-ttu-id="e4987-433">Die Dauer beträgt ungefähr 99ms ((63784407-63685394)/1000).</span><span class="sxs-lookup"><span data-stu-id="e4987-433">This duration is approximately 99ms ((63784407-63685394)/1000).</span></span>

  <span data-ttu-id="e4987-434">Das `GCEnd`-Ereignis für die Garbage Collection im Hintergrund wird bei 89931423 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4987-434">The `GCEnd` event for the background garbage collection is at 89931423.</span></span> <span data-ttu-id="e4987-435">Dies bedeutet, dass die Garbage Collection im Hintergrund etwa 47 Sekunden gedauert hat ((89931423-42504816)/1000).</span><span class="sxs-lookup"><span data-stu-id="e4987-435">This means that the background garbage collection lasted for about 47seconds ((89931423-42504816)/1000).</span></span>

  <span data-ttu-id="e4987-436">Während die verwalteten Threads ausgeführt werden, können beliebig viele kurzlebige Garbage Collections stattfinden.</span><span class="sxs-lookup"><span data-stu-id="e4987-436">While the managed threads are running, you can see any number of ephemeral garbage collections occurring.</span></span>

<a name="Triggered"></a>

### <a name="to-determine-what-triggered-a-garbage-collection"></a><span data-ttu-id="e4987-437">So ermitteln Sie, was eine Garbage Collection ausgelöst</span><span class="sxs-lookup"><span data-stu-id="e4987-437">To determine what triggered a garbage collection</span></span>

- <span data-ttu-id="e4987-438">Geben Sie im WinDbg-Debugger oder im Visual Studio-Debugger bei geladener SOS-Debuggererweiterung den folgenden Befehl ein, um alle Threads mit ihren Aufruflisten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e4987-438">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command to show all the threads with their call stacks:</span></span>

  <span data-ttu-id="e4987-439">**~\*kb**</span><span class="sxs-lookup"><span data-stu-id="e4987-439">**~\*kb**</span></span>

  <span data-ttu-id="e4987-440">Dieser Befehl zeigt eine Ausgabe ähnlich der folgenden an.</span><span class="sxs-lookup"><span data-stu-id="e4987-440">This command displays output similar to the following.</span></span>

  ```console
  0012f3b0 79ff0bf8 mscorwks!WKS::GCHeap::GarbageCollect
  0012f454 30002894 mscorwks!GCInterface::CollectGeneration+0xa4
  0012f490 79fa22bd fragment_ni!request.Main(System.String[])+0x48
  ```

  <span data-ttu-id="e4987-441">Wenn die Garbage Collection durch eine Benachrichtigung über unzureichenden Arbeitsspeicher vom Betriebssystem verursacht wurde, sieht die Aufrufliste ähnlich aus, mit dem Unterschied, dass der Thread ein Finalizerthread ist.</span><span class="sxs-lookup"><span data-stu-id="e4987-441">If the garbage collection was caused by a low memory notification from the operating system, the call stack is similar, except that the thread is the finalizer thread.</span></span> <span data-ttu-id="e4987-442">Der Finalizerthread erhält eine asynchrone Benachrichtigung über unzureichenden Arbeitsspeicher und führt die Garbage Collection aus.</span><span class="sxs-lookup"><span data-stu-id="e4987-442">The finalizer thread gets an asynchronous low memory notification and induces the garbage collection.</span></span>

  <span data-ttu-id="e4987-443">Wenn die Garbage Collection durch die Speicherbelegung verursacht wurde, sieht der Stapel wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e4987-443">If the garbage collection was caused by memory allocation, the stack appears as follows:</span></span>

  ```console
  0012f230 7a07c551 mscorwks!WKS::GCHeap::GarbageCollectGeneration
  0012f2b8 7a07cba8 mscorwks!WKS::gc_heap::try_allocate_more_space+0x1a1
  0012f2d4 7a07cefb mscorwks!WKS::gc_heap::allocate_more_space+0x18
  0012f2f4 7a02a51b mscorwks!WKS::GCHeap::Alloc+0x4b
  0012f310 7a02ae4c mscorwks!Alloc+0x60
  0012f364 7a030e46 mscorwks!FastAllocatePrimitiveArray+0xbd
  0012f424 300027f4 mscorwks!JIT_NewArr1+0x148
  000af70f 3000299f fragment_ni!request..ctor(Int32, Single)+0x20c
  0000002a 79fa22bd fragment_ni!request.Main(System.String[])+0x153
  ```

  <span data-ttu-id="e4987-444">Ein Just-In-Time-Hilfsprogramm (`JIT_New*`) ruft schließlich `GCHeap::GarbageCollectGeneration` auf.</span><span class="sxs-lookup"><span data-stu-id="e4987-444">A just-in-time helper (`JIT_New*`) eventually calls `GCHeap::GarbageCollectGeneration`.</span></span> <span data-ttu-id="e4987-445">Wenn Sie feststellen, dass die Garbage Collections der Generation 2 durch Belegungen verursacht werden, müssen Sie ermitteln, welche Objekte von einer Garbage Collection der Generation 2 freigegeben werden und wie sie dies vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="e4987-445">If you determine that generation 2 garbage collections are caused by allocations, you must determine which objects are collected by a generation 2 garbage collection and how to avoid them.</span></span> <span data-ttu-id="e4987-446">Das heißt, Sie müssen den Unterschied zwischen dem Anfang und am Ende einer Garbage Collection der Generation 2 sowie die Objekte bestimmen, welche die Collection der Generation 2 verursacht haben.</span><span class="sxs-lookup"><span data-stu-id="e4987-446">That is, you want to determine the difference between the start and the end of a generation 2 garbage collection, and the objects that caused the generation 2 collection.</span></span>

  <span data-ttu-id="e4987-447">Geben Sie beispielsweise den folgenden Befehl im Debugger ein, um den Anfang einer Collection der Generation 2 anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e4987-447">For example, type the following command in the debugger to show the beginning of a generation 2 collection:</span></span>

  <span data-ttu-id="e4987-448">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="e4987-448">**!dumpheap –stat**</span></span>

  <span data-ttu-id="e4987-449">Beispielausgabe (gekürzt, um die Objekte anzuzeigen, die den meisten Platz benötigen):</span><span class="sxs-lookup"><span data-stu-id="e4987-449">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    31857      9862328 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  00155f80    21248     12256296      Free
  79103b6c   297003     13068132 System.Threading.ReaderWriterLock
  7a747ad4   708732     14174640 System.Collections.Specialized.HybridDictionary
  7a747c78   786498     15729960 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  035f0ee4    89192     38887712 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  7912c444    91616     71887080 System.Double[]
  791242ec    32451     82462728 System.Collections.Hashtable+bucket[]
  790fa3e0  2459154    112128436 System.String
  Total 6471774 objects
  ```

  <span data-ttu-id="e4987-450">Wiederholen Sie den Befehl am Ende der Generation 2:</span><span class="sxs-lookup"><span data-stu-id="e4987-450">Repeat the command at the end of generation 2:</span></span>

  <span data-ttu-id="e4987-451">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="e4987-451">**!dumpheap –stat**</span></span>

  <span data-ttu-id="e4987-452">Beispielausgabe (gekürzt, um die Objekte anzuzeigen, die den meisten Platz benötigen):</span><span class="sxs-lookup"><span data-stu-id="e4987-452">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    26648      9314256 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  79103b6c   296770     13057880 System.Threading.ReaderWriterLock
  7a747ad4   708730     14174600 System.Collections.Specialized.HybridDictionary
  7a747c78   786497     15729940 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  00155f80    13806     34007212      Free
  035f0ee4    89187     38885532 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    32370     82359768 System.Collections.Hashtable+bucket[]
  790fa3e0  2440020    111341808 System.String
  Total 6417525 objects
  ```

  <span data-ttu-id="e4987-453">Die `double[]`-Objekte am Ende der Ausgabe sind verschwunden, das heißt, sie wurden freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e4987-453">The `double[]` objects disappeared from the end of the output, which means that they were collected.</span></span> <span data-ttu-id="e4987-454">Diese Objekte umfassen etwa 70 MB.</span><span class="sxs-lookup"><span data-stu-id="e4987-454">These objects account for approximately 70 MB.</span></span> <span data-ttu-id="e4987-455">Bei den übrigen Objekten gab es kaum Änderungen.</span><span class="sxs-lookup"><span data-stu-id="e4987-455">The remaining objects did not change much.</span></span> <span data-ttu-id="e4987-456">Daher waren diese `double[]`-Objekte der Grund, weshalb diese Garbage Collection der Generation 2 ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4987-456">Therefore, these `double[]` objects were the reason why this generation 2 garbage collection occurred.</span></span> <span data-ttu-id="e4987-457">Der nächster Schritt besteht darin, zu bestimmen, warum die `double[]`-Objekte vorhanden sind und warum sie inaktiv waren.</span><span class="sxs-lookup"><span data-stu-id="e4987-457">Your next step is to determine why the `double[]` objects are there and why they died.</span></span> <span data-ttu-id="e4987-458">Sie können den Codeentwickler fragen, woher diese Objekte stammen, oder Sie können den Befehl **gcroot** verwenden.</span><span class="sxs-lookup"><span data-stu-id="e4987-458">You can ask the code developer where these objects came from, or you can use the **gcroot** command.</span></span>

<a name="HighCPU"></a>

### <a name="to-determine-whether-high-cpu-usage-is-caused-by-garbage-collection"></a><span data-ttu-id="e4987-459">So ermitteln Sie, ob die hohe CPU-Auslastung durch die Garbage Collection verursacht wird</span><span class="sxs-lookup"><span data-stu-id="e4987-459">To determine whether high CPU usage is caused by garbage collection</span></span>

- <span data-ttu-id="e4987-460">Setzen Sie den Wert des Speicherleistungsindikators `% Time in GC` zur Prozesszeit in Beziehung.</span><span class="sxs-lookup"><span data-stu-id="e4987-460">Correlate the `% Time in GC` memory performance counter value with the process time.</span></span>

  <span data-ttu-id="e4987-461">Wenn der `% Time in GC`-Wert zum selben Zeitpunkt einen Spitzenwert erreicht wie die Prozesszeit, dann verursacht die Garbage Collection die hohe CPU-Auslastung.</span><span class="sxs-lookup"><span data-stu-id="e4987-461">If the `% Time in GC` value spikes at the same time as process time, garbage collection is causing a high CPU usage.</span></span> <span data-ttu-id="e4987-462">Erstellen Sie andernfalls ein Profil der Anwendung, um zu ermitteln, wie die hohe Auslastung zustande kommt.</span><span class="sxs-lookup"><span data-stu-id="e4987-462">Otherwise, profile the application to find where the high usage is occurring.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4987-463">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4987-463">See also</span></span>

- [<span data-ttu-id="e4987-464">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="e4987-464">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
