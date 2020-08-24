---
title: dotnet-counters – .NET Core
description: Erfahren Sie, wie Sie das Befehlszeilentool dotnet-counter installieren und verwenden.
ms.date: 02/26/2020
ms.openlocfilehash: 6a4fd92540dbc16173dfa3a10ff9dfaa1f31f7d0
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062898"
---
# <a name="dotnet-counters"></a><span data-ttu-id="001c6-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="001c6-103">dotnet-counters</span></span>

<span data-ttu-id="001c6-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="001c6-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="001c6-105">Installieren von dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="001c6-105">Install dotnet-counters</span></span>

<span data-ttu-id="001c6-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="001c6-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="001c6-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="001c6-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="001c6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="001c6-108">Description</span></span>

<span data-ttu-id="001c6-109">`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene.</span><span class="sxs-lookup"><span data-stu-id="001c6-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="001c6-110">Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="001c6-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="001c6-111">Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.</span><span class="sxs-lookup"><span data-stu-id="001c6-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="001c6-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="001c6-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="001c6-113">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="001c6-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="001c6-114">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="001c6-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="001c6-115">Befehle</span><span class="sxs-lookup"><span data-stu-id="001c6-115">Commands</span></span>

| <span data-ttu-id="001c6-116">Befehl</span><span class="sxs-lookup"><span data-stu-id="001c6-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="001c6-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="001c6-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="001c6-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="001c6-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="001c6-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="001c6-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="001c6-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="001c6-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="001c6-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="001c6-121">dotnet-counters collect</span></span>

<span data-ttu-id="001c6-122">Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.</span><span class="sxs-lookup"><span data-stu-id="001c6-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="001c6-123">Übersicht</span><span class="sxs-lookup"><span data-stu-id="001c6-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="001c6-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="001c6-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="001c6-125">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="001c6-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="001c6-126">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="001c6-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="001c6-127">Eine durch Leerzeichen getrennte Liste von Zählern.</span><span class="sxs-lookup"><span data-stu-id="001c6-127">A space separated list of counters.</span></span> <span data-ttu-id="001c6-128">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="001c6-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="001c6-129">Wenn `provider_name` ohne qualifizierenden `counter_name` verwendet wird, werden alle Indikatoren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="001c6-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="001c6-130">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="001c6-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="001c6-131">Das zu exportierende Format</span><span class="sxs-lookup"><span data-stu-id="001c6-131">The format to be exported.</span></span> <span data-ttu-id="001c6-132">Derzeit sind die folgenden Formate verfügbar: CSV und JSON.</span><span class="sxs-lookup"><span data-stu-id="001c6-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="001c6-133">Der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="001c6-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="001c6-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="001c6-134">Examples</span></span>

- <span data-ttu-id="001c6-135">Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="001c6-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="001c6-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="001c6-136">dotnet-counters list</span></span>

<span data-ttu-id="001c6-137">Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="001c6-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="001c6-138">Übersicht</span><span class="sxs-lookup"><span data-stu-id="001c6-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="001c6-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="001c6-139">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="001c6-140">Die `Microsoft.AspNetCore.Hosting`-Leistungsindikatoren werden angezeigt, wenn bestimmte Prozesse identifiziert werden, die diese Leistungsindikatoren unterstützen, etwa wenn eine ASP.NET Core-Anwendung auf dem Hostcomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="001c6-140">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="001c6-141">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="001c6-141">dotnet-counters monitor</span></span>

<span data-ttu-id="001c6-142">Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.</span><span class="sxs-lookup"><span data-stu-id="001c6-142">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="001c6-143">Übersicht</span><span class="sxs-lookup"><span data-stu-id="001c6-143">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="001c6-144">Optionen</span><span class="sxs-lookup"><span data-stu-id="001c6-144">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="001c6-145">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="001c6-145">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="001c6-146">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="001c6-146">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="001c6-147">Eine durch Leerzeichen getrennte Liste von Zählern.</span><span class="sxs-lookup"><span data-stu-id="001c6-147">A space separated list of counters.</span></span> <span data-ttu-id="001c6-148">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="001c6-148">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="001c6-149">Wenn `provider_name` ohne qualifizierenden `counter_name` verwendet wird, werden alle Indikatoren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="001c6-149">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="001c6-150">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="001c6-150">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="001c6-151">Beispiele</span><span class="sxs-lookup"><span data-stu-id="001c6-151">Examples</span></span>

- <span data-ttu-id="001c6-152">Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="001c6-152">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="001c6-153">Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="001c6-153">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="001c6-154">Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="001c6-154">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="001c6-155">Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="001c6-155">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="001c6-156">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="001c6-156">dotnet-counters ps</span></span>

<span data-ttu-id="001c6-157">Mit diesem Befehl wird eine Liste der dotnet-Prozesse angezeigt, die überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="001c6-157">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="001c6-158">Übersicht</span><span class="sxs-lookup"><span data-stu-id="001c6-158">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="001c6-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="001c6-159">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
