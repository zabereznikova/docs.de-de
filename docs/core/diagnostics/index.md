---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: 3274b72363a3df1dbe1bb29492eedcb134a4f9f2
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982308"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="db1f9-103">Welche Diagnosetools sind in .NET Core verfügbar?</span><span class="sxs-lookup"><span data-stu-id="db1f9-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="db1f9-104">Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="db1f9-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="db1f9-105">Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="db1f9-106">Verwaltete Debugger</span><span class="sxs-lookup"><span data-stu-id="db1f9-106">Managed debuggers</span></span>

<span data-ttu-id="db1f9-107">[Verwaltete Debugger](managed-debuggers.md) ermöglichen Ihnen die Interaktion mit dem Programm.</span><span class="sxs-lookup"><span data-stu-id="db1f9-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="db1f9-108">Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="db1f9-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="db1f9-109">Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="db1f9-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="db1f9-110">Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="db1f9-110">Logging and tracing</span></span>

<span data-ttu-id="db1f9-111">Die [Protokollierung und Ablaufverfolgung](logging-tracing.md) sind verwandte Techniken.</span><span class="sxs-lookup"><span data-stu-id="db1f9-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="db1f9-112">Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="db1f9-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="db1f9-113">In den Dateien werden die Details eines Programms aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="db1f9-113">The files record the details of what a program does.</span></span> <span data-ttu-id="db1f9-114">Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db1f9-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="db1f9-115">In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="db1f9-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="db1f9-116">Komponententest</span><span class="sxs-lookup"><span data-stu-id="db1f9-116">Unit testing</span></span>

<span data-ttu-id="db1f9-117">[Komponententests](../testing/index.md) sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software.</span><span class="sxs-lookup"><span data-stu-id="db1f9-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="db1f9-118">Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="db1f9-119">Sammeln von Diagnosen in Containern</span><span class="sxs-lookup"><span data-stu-id="db1f9-119">Collect diagnostics in containers</span></span>

<span data-ttu-id="db1f9-120">Dieselben Diagnosetools, die in nicht-containerisierten Linux-Umgebungen verwendet werden, können auch verwendet werden, um [Diagnosen in Containern](diagnostics-in-containers.md) zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="db1f9-120">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="db1f9-121">Es sind nur ein paar Nutzungsänderungen erforderlich, um sicherzustellen, dass die Tools in einem Docker-Container funktionieren.</span><span class="sxs-lookup"><span data-stu-id="db1f9-121">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="db1f9-122">Debuggen von Linux-Abbildern</span><span class="sxs-lookup"><span data-stu-id="db1f9-122">Debug Linux dumps</span></span>

<span data-ttu-id="db1f9-123">[Debuggen von Linux-Abbildern](debug-linux-dumps.md) erläutert das Sammeln und Analysieren von Abbildern unter Linux.</span><span class="sxs-lookup"><span data-stu-id="db1f9-123">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="db1f9-124">Globale .NET Core-Diagnosetools</span><span class="sxs-lookup"><span data-stu-id="db1f9-124">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="db1f9-125">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="db1f9-125">dotnet-counters</span></span>

<span data-ttu-id="db1f9-126">[dotnet-counters](dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung.</span><span class="sxs-lookup"><span data-stu-id="db1f9-126">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="db1f9-127">Es überwacht die Werte des Leistungsindikators, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="db1f9-127">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="db1f9-128">Sie können beispielsweise den CPU-Verbrauch oder die Anzahl ausgelöster Ausnahmen in Ihrer .NET Core-Anwendung überwachen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-128">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="db1f9-129">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="db1f9-129">dotnet-dump</span></span>

<span data-ttu-id="db1f9-130">Mit dem Tool [dotnet-dump](dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne nativen Debugger erfassen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="db1f9-130">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="db1f9-131">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="db1f9-131">dotnet-gcdump</span></span>

<span data-ttu-id="db1f9-132">Mit dem Tool [dotnet-gcdump](dotnet-gcdump.md) können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-132">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="db1f9-133">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="db1f9-133">dotnet-trace</span></span>

<span data-ttu-id="db1f9-134">.NET Core schließt `EventPipe` ein, worüber Diagnosedaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="db1f9-134">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="db1f9-135">Mit dem Tool [dotnet-trace](dotnet-trace.md) können Sie relevante Daten für die Profilerstellung in Ihrer App nutzen. Diese können hilfreich sein, wenn Sie die Ursache für langsame Apps ermitteln müssen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-135">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="db1f9-136">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="db1f9-136">dotnet-symbol</span></span>

<span data-ttu-id="db1f9-137">[dotnet-symbol](dotnet-symbol.md) lädt Dateien (Symbole, DAC/DBI, Hostdateien usw.) herunter, die benötigt werden, um ein zentrales Kernabbild oder Miniabbild zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-137">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="db1f9-138">Verwenden Sie dieses Tool, wenn Sie Symbole und Module benötigen, um eine auf einem anderen Computer erfasste Abbilddatei zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-138">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="db1f9-139">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="db1f9-139">dotnet-sos</span></span>

<span data-ttu-id="db1f9-140">[dotnet-sos](dotnet-sos.md) wird verwendet, um die [SOS-Debugerweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) unter Linux oder MacOS (oder unter Windows, wenn ältere Debugtools verwendet werden) zu installieren.</span><span class="sxs-lookup"><span data-stu-id="db1f9-140">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="db1f9-141">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="db1f9-141">PerfCollect</span></span>

<span data-ttu-id="db1f9-142">[Perfcollect](trace-perfcollect-lttng.md) ist ein Bash-Skript, das Sie verwenden können, um Ablaufverfolgungen mit `perf` und `LTTng` für eine ausführlichere Leistungsanalyse von .NET-Apps zu erfassen, die unter Linux-Distributionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="db1f9-142">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="db1f9-143">Tutorials zur .NET Core-Diagnose</span><span class="sxs-lookup"><span data-stu-id="db1f9-143">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="db1f9-144">Debuggen eines Speicherverlusts</span><span class="sxs-lookup"><span data-stu-id="db1f9-144">Debug a memory leak</span></span>

<span data-ttu-id="db1f9-145">[Tutorial: Debuggen eines Speicherverlusts](debug-memory-leak.md). Hier wird erläutert, wie ein Speicherverlust gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="db1f9-145">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="db1f9-146">Das [dotnet-counters](dotnet-counters.md)-Tool wird zum Bestätigen des Verlusts und das [dotnet-dump](dotnet-dump.md)-Tool zur Diagnose des Verlusts verwendet.</span><span class="sxs-lookup"><span data-stu-id="db1f9-146">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="db1f9-147">Debuggen einer hohen CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="db1f9-147">Debug high CPU usage</span></span>

<span data-ttu-id="db1f9-148">[Tutorial: Debuggen einer hohen CPU-Auslastung](debug-highcpu.md). Hier lernen Sie, wie Sie eine hohe CPU-Auslastung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-148">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="db1f9-149">In diesem Tutorial wird das Tool [dotnet-counters](dotnet-counters.md) verwendet, um eine solche Auslastung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-149">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="db1f9-150">Danach erfahren Sie, wie Sie das [`dotnet-trace`-Hilfsprogramm für Leistungsanalysen](dotnet-trace.md) oder `perf` in Linux verwenden, um das CPU-Auslastungsprofil zu erfassen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-150">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="db1f9-151">Debuggen eines Deadlocks</span><span class="sxs-lookup"><span data-stu-id="db1f9-151">Debug deadlock</span></span>

<span data-ttu-id="db1f9-152">[Tutorial: Debuggen eines Deadlocks](debug-deadlock.md). Hier erfahren Sie, wie Sie das Tool [dotnet-dump](dotnet-dump.md) verwenden, um Threads und Sperren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="db1f9-152">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="db1f9-153">Messen der Leistung mithilfe von EventCounters</span><span class="sxs-lookup"><span data-stu-id="db1f9-153">Measure performance using EventCounters</span></span>

<span data-ttu-id="db1f9-154">[Tutorial: Messen der Leistung mithilfe von EventCounters in .NET](event-counter-perf.md) zeigt, wie Sie die <xref:System.Diagnostics.Tracing.EventCounter>-API zum Messen der Leistung in Ihrer .NET-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="db1f9-154">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
