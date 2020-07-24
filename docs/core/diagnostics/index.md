---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: dc64c03ee9c8cee6a5b3c5cc089b4a1a2c27f84a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924781"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="46874-103">Welche Diagnosetools sind in .NET Core verfügbar?</span><span class="sxs-lookup"><span data-stu-id="46874-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="46874-104">Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="46874-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="46874-105">Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="46874-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="46874-106">Verwaltete Debugger</span><span class="sxs-lookup"><span data-stu-id="46874-106">Managed debuggers</span></span>

<span data-ttu-id="46874-107">[Verwaltete Debugger](managed-debuggers.md) ermöglichen Ihnen die Interaktion mit dem Programm.</span><span class="sxs-lookup"><span data-stu-id="46874-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="46874-108">Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="46874-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="46874-109">Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="46874-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="46874-110">Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46874-110">Logging and tracing</span></span>

<span data-ttu-id="46874-111">Die [Protokollierung und Ablaufverfolgung](logging-tracing.md) sind verwandte Techniken.</span><span class="sxs-lookup"><span data-stu-id="46874-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="46874-112">Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="46874-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="46874-113">In den Dateien werden die Details eines Programms aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="46874-113">The files record the details of what a program does.</span></span> <span data-ttu-id="46874-114">Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46874-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="46874-115">In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="46874-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="46874-116">Komponententest</span><span class="sxs-lookup"><span data-stu-id="46874-116">Unit testing</span></span>

<span data-ttu-id="46874-117">[Komponententests](../testing/index.md) sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software.</span><span class="sxs-lookup"><span data-stu-id="46874-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="46874-118">Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="46874-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="46874-119">Globale .NET Core-dotnet-Diagnosetools</span><span class="sxs-lookup"><span data-stu-id="46874-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="46874-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="46874-120">dotnet-counters</span></span>

<span data-ttu-id="46874-121">[dotnet-counters](dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung.</span><span class="sxs-lookup"><span data-stu-id="46874-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="46874-122">Es überwacht die Werte des Leistungsindikators, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="46874-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="46874-123">Sie können beispielsweise den CPU-Verbrauch oder die Anzahl ausgelöster Ausnahmen in Ihrer .NET Core-Anwendung überwachen.</span><span class="sxs-lookup"><span data-stu-id="46874-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="46874-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="46874-124">dotnet-dump</span></span>

<span data-ttu-id="46874-125">Mit dem Tool [dotnet-dump](dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne nativen Debugger erfassen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="46874-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="46874-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="46874-126">dotnet-trace</span></span>

<span data-ttu-id="46874-127">.NET Core schließt `EventPipe` ein, worüber Diagnosedaten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="46874-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="46874-128">Mit dem Tool [dotnet-trace](dotnet-trace.md) können Sie relevante Daten für die Profilerstellung in Ihrer App nutzen. Diese können hilfreich sein, wenn Sie die Ursache für langsame Apps ermitteln müssen.</span><span class="sxs-lookup"><span data-stu-id="46874-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="46874-129">Tutorials zur .NET Core-Diagnose</span><span class="sxs-lookup"><span data-stu-id="46874-129">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="46874-130">Debuggen eines Speicherverlusts</span><span class="sxs-lookup"><span data-stu-id="46874-130">Debug a memory leak</span></span>

<span data-ttu-id="46874-131">[Tutorial: Debuggen eines Speicherverlusts](debug-memory-leak.md). Hier wird erläutert, wie ein Speicherverlust gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="46874-131">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="46874-132">Das [dotnet-counters](dotnet-counters.md)-Tool wird zum Bestätigen des Verlusts und das [dotnet-dump](dotnet-dump.md)-Tool zur Diagnose des Verlusts verwendet.</span><span class="sxs-lookup"><span data-stu-id="46874-132">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="46874-133">Debuggen einer hohen CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="46874-133">Debug high CPU usage</span></span>

<span data-ttu-id="46874-134">[Tutorial: Debuggen einer hohen CPU-Auslastung](debug-highcpu.md). Hier lernen Sie, wie Sie eine hohe CPU-Auslastung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="46874-134">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="46874-135">In diesem Tutorial wird das Tool [dotnet-counters](dotnet-counters.md) verwendet, um eine solche Auslastung zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="46874-135">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="46874-136">Danach erfahren Sie, wie Sie das [`dotnet-trace`-Hilfsprogramm für Leistungsanalysen](dotnet-trace.md) oder `perf` in Linux verwenden, um das CPU-Auslastungsprofil zu erfassen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46874-136">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="46874-137">Debuggen eines Deadlocks</span><span class="sxs-lookup"><span data-stu-id="46874-137">Debug deadlock</span></span>

<span data-ttu-id="46874-138">[Tutorial: Debuggen eines Deadlocks](debug-deadlock.md). Hier erfahren Sie, wie Sie das Tool [dotnet-dump](dotnet-dump.md) verwenden, um Threads und Sperren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="46874-138">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
