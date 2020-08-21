---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: ae3b9a1961f331c9cdea786bd5fe06b7bfa10927
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558113"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="75512-103">Welche Diagnosetools sind in .NET Core verfügbar?</span><span class="sxs-lookup"><span data-stu-id="75512-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="75512-104">Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="75512-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="75512-105">Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="75512-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="75512-106">Verwaltete Debugger</span><span class="sxs-lookup"><span data-stu-id="75512-106">Managed debuggers</span></span>

<span data-ttu-id="75512-107">[Verwaltete Debugger](managed-debuggers.md) ermöglichen Ihnen die Interaktion mit dem Programm.</span><span class="sxs-lookup"><span data-stu-id="75512-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="75512-108">Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="75512-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="75512-109">Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="75512-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="75512-110">Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="75512-110">Logging and tracing</span></span>

<span data-ttu-id="75512-111">Die [Protokollierung und Ablaufverfolgung](logging-tracing.md) sind verwandte Techniken.</span><span class="sxs-lookup"><span data-stu-id="75512-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="75512-112">Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="75512-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="75512-113">In den Dateien werden die Details eines Programms aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="75512-113">The files record the details of what a program does.</span></span> <span data-ttu-id="75512-114">Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75512-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="75512-115">In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="75512-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="75512-116">Komponententest</span><span class="sxs-lookup"><span data-stu-id="75512-116">Unit testing</span></span>

<span data-ttu-id="75512-117">[Komponententests](../testing/index.md) sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software.</span><span class="sxs-lookup"><span data-stu-id="75512-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="75512-118">Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="75512-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="75512-119">Globale .NET Core-dotnet-Diagnosetools</span><span class="sxs-lookup"><span data-stu-id="75512-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="75512-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="75512-120">dotnet-counters</span></span>

<span data-ttu-id="75512-121">[dotnet-counters](dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung.</span><span class="sxs-lookup"><span data-stu-id="75512-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="75512-122">Es überwacht die Werte des Leistungsindikators, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="75512-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="75512-123">Sie können beispielsweise den CPU-Verbrauch oder die Anzahl ausgelöster Ausnahmen in Ihrer .NET Core-Anwendung überwachen.</span><span class="sxs-lookup"><span data-stu-id="75512-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="75512-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="75512-124">dotnet-dump</span></span>

<span data-ttu-id="75512-125">Mit dem Tool [dotnet-dump](dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne nativen Debugger erfassen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="75512-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="75512-126">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="75512-126">dotnet-gcdump</span></span>

<span data-ttu-id="75512-127">Mit dem Tool [dotnet-gcdump](dotnet-gcdump.md) können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.</span><span class="sxs-lookup"><span data-stu-id="75512-127">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="75512-128">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="75512-128">dotnet-trace</span></span>

<span data-ttu-id="75512-129">.NET Core schließt `EventPipe` ein, worüber Diagnosedaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75512-129">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="75512-130">Mit dem Tool [dotnet-trace](dotnet-trace.md) können Sie relevante Daten für die Profilerstellung in Ihrer App nutzen. Diese können hilfreich sein, wenn Sie die Ursache für langsame Apps ermitteln müssen.</span><span class="sxs-lookup"><span data-stu-id="75512-130">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="75512-131">Tutorials zur .NET Core-Diagnose</span><span class="sxs-lookup"><span data-stu-id="75512-131">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="75512-132">Debuggen eines Speicherverlusts</span><span class="sxs-lookup"><span data-stu-id="75512-132">Debug a memory leak</span></span>

<span data-ttu-id="75512-133">[Tutorial: Debuggen eines Speicherverlusts](debug-memory-leak.md). Hier wird erläutert, wie ein Speicherverlust gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="75512-133">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="75512-134">Das [dotnet-counters](dotnet-counters.md)-Tool wird zum Bestätigen des Verlusts und das [dotnet-dump](dotnet-dump.md)-Tool zur Diagnose des Verlusts verwendet.</span><span class="sxs-lookup"><span data-stu-id="75512-134">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="75512-135">Debuggen einer hohen CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="75512-135">Debug high CPU usage</span></span>

<span data-ttu-id="75512-136">[Tutorial: Debuggen einer hohen CPU-Auslastung](debug-highcpu.md). Hier lernen Sie, wie Sie eine hohe CPU-Auslastung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="75512-136">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="75512-137">In diesem Tutorial wird das Tool [dotnet-counters](dotnet-counters.md) verwendet, um eine solche Auslastung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="75512-137">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="75512-138">Danach erfahren Sie, wie Sie das [`dotnet-trace`-Hilfsprogramm für Leistungsanalysen](dotnet-trace.md) oder `perf` in Linux verwenden, um das CPU-Auslastungsprofil zu erfassen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75512-138">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="75512-139">Debuggen eines Deadlocks</span><span class="sxs-lookup"><span data-stu-id="75512-139">Debug deadlock</span></span>

<span data-ttu-id="75512-140">[Tutorial: Debuggen eines Deadlocks](debug-deadlock.md). Hier erfahren Sie, wie Sie das Tool [dotnet-dump](dotnet-dump.md) verwenden, um Threads und Sperren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="75512-140">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
