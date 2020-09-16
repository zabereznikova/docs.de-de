---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: e97acccbe3bdd577ee600cefb9f1f0528d3c1ac0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538526"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="8a957-103">Welche Diagnosetools sind in .NET Core verfügbar?</span><span class="sxs-lookup"><span data-stu-id="8a957-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="8a957-104">Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="8a957-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="8a957-105">Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="8a957-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="8a957-106">Verwaltete Debugger</span><span class="sxs-lookup"><span data-stu-id="8a957-106">Managed debuggers</span></span>

<span data-ttu-id="8a957-107">[Verwaltete Debugger](managed-debuggers.md) ermöglichen Ihnen die Interaktion mit dem Programm.</span><span class="sxs-lookup"><span data-stu-id="8a957-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="8a957-108">Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="8a957-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="8a957-109">Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="8a957-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="8a957-110">Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8a957-110">Logging and tracing</span></span>

<span data-ttu-id="8a957-111">Die [Protokollierung und Ablaufverfolgung](logging-tracing.md) sind verwandte Techniken.</span><span class="sxs-lookup"><span data-stu-id="8a957-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="8a957-112">Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="8a957-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="8a957-113">In den Dateien werden die Details eines Programms aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8a957-113">The files record the details of what a program does.</span></span> <span data-ttu-id="8a957-114">Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a957-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="8a957-115">In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="8a957-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="8a957-116">Komponententest</span><span class="sxs-lookup"><span data-stu-id="8a957-116">Unit testing</span></span>

<span data-ttu-id="8a957-117">[Komponententests](../testing/index.md) sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software.</span><span class="sxs-lookup"><span data-stu-id="8a957-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="8a957-118">Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="8a957-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="8a957-119">Debuggen von Linux-Abbildern</span><span class="sxs-lookup"><span data-stu-id="8a957-119">Debug Linux dumps</span></span>

<span data-ttu-id="8a957-120">[Debuggen von Linux-Abbildern](debug-linux-dumps.md) erläutert das Sammeln und Analysieren von Abbildern unter Linux.</span><span class="sxs-lookup"><span data-stu-id="8a957-120">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="8a957-121">Globale .NET Core-Diagnosetools</span><span class="sxs-lookup"><span data-stu-id="8a957-121">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="8a957-122">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="8a957-122">dotnet-counters</span></span>

<span data-ttu-id="8a957-123">[dotnet-counters](dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung.</span><span class="sxs-lookup"><span data-stu-id="8a957-123">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="8a957-124">Es überwacht die Werte des Leistungsindikators, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="8a957-124">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="8a957-125">Sie können beispielsweise den CPU-Verbrauch oder die Anzahl ausgelöster Ausnahmen in Ihrer .NET Core-Anwendung überwachen.</span><span class="sxs-lookup"><span data-stu-id="8a957-125">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="8a957-126">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="8a957-126">dotnet-dump</span></span>

<span data-ttu-id="8a957-127">Mit dem Tool [dotnet-dump](dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne nativen Debugger erfassen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="8a957-127">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="8a957-128">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="8a957-128">dotnet-gcdump</span></span>

<span data-ttu-id="8a957-129">Mit dem Tool [dotnet-gcdump](dotnet-gcdump.md) können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.</span><span class="sxs-lookup"><span data-stu-id="8a957-129">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="8a957-130">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="8a957-130">dotnet-trace</span></span>

<span data-ttu-id="8a957-131">.NET Core schließt `EventPipe` ein, worüber Diagnosedaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a957-131">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="8a957-132">Mit dem Tool [dotnet-trace](dotnet-trace.md) können Sie relevante Daten für die Profilerstellung in Ihrer App nutzen. Diese können hilfreich sein, wenn Sie die Ursache für langsame Apps ermitteln müssen.</span><span class="sxs-lookup"><span data-stu-id="8a957-132">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="8a957-133">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="8a957-133">dotnet-symbol</span></span>

<span data-ttu-id="8a957-134">[dotnet-symbol](dotnet-symbol.md) lädt Dateien (Symbole, DAC/DBI, Hostdateien usw.) herunter, die benötigt werden, um ein zentrales Kernabbild oder Miniabbild zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8a957-134">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="8a957-135">Verwenden Sie dieses Tool, wenn Sie Symbole und Module benötigen, um eine auf einem anderen Computer erfasste Abbilddatei zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="8a957-135">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="8a957-136">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="8a957-136">dotnet-sos</span></span>

<span data-ttu-id="8a957-137">[dotnet-sos](dotnet-sos.md) wird verwendet, um die [SOS-Debugerweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) unter Linux oder MacOS (oder unter Windows, wenn ältere Debugtools verwendet werden) zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8a957-137">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="8a957-138">Tutorials zur .NET Core-Diagnose</span><span class="sxs-lookup"><span data-stu-id="8a957-138">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="8a957-139">Debuggen eines Speicherverlusts</span><span class="sxs-lookup"><span data-stu-id="8a957-139">Debug a memory leak</span></span>

<span data-ttu-id="8a957-140">[Tutorial: Debuggen eines Speicherverlusts](debug-memory-leak.md). Hier wird erläutert, wie ein Speicherverlust gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8a957-140">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="8a957-141">Das [dotnet-counters](dotnet-counters.md)-Tool wird zum Bestätigen des Verlusts und das [dotnet-dump](dotnet-dump.md)-Tool zur Diagnose des Verlusts verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a957-141">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="8a957-142">Debuggen einer hohen CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="8a957-142">Debug high CPU usage</span></span>

<span data-ttu-id="8a957-143">[Tutorial: Debuggen einer hohen CPU-Auslastung](debug-highcpu.md). Hier lernen Sie, wie Sie eine hohe CPU-Auslastung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a957-143">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="8a957-144">In diesem Tutorial wird das Tool [dotnet-counters](dotnet-counters.md) verwendet, um eine solche Auslastung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="8a957-144">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="8a957-145">Danach erfahren Sie, wie Sie das [`dotnet-trace`-Hilfsprogramm für Leistungsanalysen](dotnet-trace.md) oder `perf` in Linux verwenden, um das CPU-Auslastungsprofil zu erfassen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a957-145">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="8a957-146">Debuggen eines Deadlocks</span><span class="sxs-lookup"><span data-stu-id="8a957-146">Debug deadlock</span></span>

<span data-ttu-id="8a957-147">[Tutorial: Debuggen eines Deadlocks](debug-deadlock.md). Hier erfahren Sie, wie Sie das Tool [dotnet-dump](dotnet-dump.md) verwenden, um Threads und Sperren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a957-147">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
