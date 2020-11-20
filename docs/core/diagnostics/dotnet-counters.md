---
title: dotnet-counters – .NET Core
description: Erfahren Sie, wie Sie das Befehlszeilentool dotnet-counter installieren und verwenden.
ms.date: 02/26/2020
ms.openlocfilehash: 7ff29ad91ad271afd35e3d38a4d748bc79ad6c03
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507253"
---
# <a name="dotnet-counters"></a><span data-ttu-id="aa7fd-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="aa7fd-103">dotnet-counters</span></span>

<span data-ttu-id="aa7fd-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="aa7fd-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="aa7fd-105">Installieren von dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="aa7fd-105">Install dotnet-counters</span></span>

<span data-ttu-id="aa7fd-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="aa7fd-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="aa7fd-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="aa7fd-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="aa7fd-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa7fd-108">Description</span></span>

<span data-ttu-id="aa7fd-109">`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="aa7fd-110">Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="aa7fd-111">Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="aa7fd-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="aa7fd-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="aa7fd-113">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="aa7fd-114">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="aa7fd-115">Befehle</span><span class="sxs-lookup"><span data-stu-id="aa7fd-115">Commands</span></span>

| <span data-ttu-id="aa7fd-116">Befehl</span><span class="sxs-lookup"><span data-stu-id="aa7fd-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="aa7fd-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="aa7fd-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="aa7fd-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="aa7fd-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="aa7fd-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="aa7fd-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="aa7fd-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="aa7fd-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="aa7fd-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="aa7fd-121">dotnet-counters collect</span></span>

<span data-ttu-id="aa7fd-122">Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="aa7fd-123">Übersicht</span><span class="sxs-lookup"><span data-stu-id="aa7fd-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="aa7fd-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="aa7fd-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="aa7fd-125">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="aa7fd-126">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="aa7fd-127">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-127">A comma-separated list of counters.</span></span> <span data-ttu-id="aa7fd-128">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="aa7fd-129">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-129">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="aa7fd-130">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="aa7fd-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="aa7fd-131">Das zu exportierende Format</span><span class="sxs-lookup"><span data-stu-id="aa7fd-131">The format to be exported.</span></span> <span data-ttu-id="aa7fd-132">Derzeit sind die folgenden Formate verfügbar: CSV und JSON.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="aa7fd-133">Der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-133">The name of the output file.</span></span>

- <span data-ttu-id="aa7fd-134">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="aa7fd-134">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="aa7fd-135">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-135">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="aa7fd-136">`dotnet-counters` startet einen Prozess mit dem angegebenen Befehl und erfasst die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-136">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="aa7fd-137">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-137">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

> [!NOTE]
> <span data-ttu-id="aa7fd-138">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-138">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="aa7fd-139">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-139">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="aa7fd-140">Beispiele</span><span class="sxs-lookup"><span data-stu-id="aa7fd-140">Examples</span></span>

- <span data-ttu-id="aa7fd-141">Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="aa7fd-141">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="aa7fd-142">Starten Sie `dotnet mvc.dll` als untergeordneten Prozess, und beginnen Sie von Anfang an mit der Erfassung von Runtimeindikatoren und ASP.NET Core-Hostingindikatoren. Speichern Sie sie als JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="aa7fd-142">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="aa7fd-143">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="aa7fd-143">dotnet-counters list</span></span>

<span data-ttu-id="aa7fd-144">Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-144">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="aa7fd-145">Übersicht</span><span class="sxs-lookup"><span data-stu-id="aa7fd-145">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="aa7fd-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa7fd-146">Example</span></span>

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
> <span data-ttu-id="aa7fd-147">Die `Microsoft.AspNetCore.Hosting`-Leistungsindikatoren werden angezeigt, wenn bestimmte Prozesse identifiziert werden, die diese Leistungsindikatoren unterstützen, etwa wenn eine ASP.NET Core-Anwendung auf dem Hostcomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-147">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="aa7fd-148">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="aa7fd-148">dotnet-counters monitor</span></span>

<span data-ttu-id="aa7fd-149">Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-149">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="aa7fd-150">Übersicht</span><span class="sxs-lookup"><span data-stu-id="aa7fd-150">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="aa7fd-151">Optionen</span><span class="sxs-lookup"><span data-stu-id="aa7fd-151">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="aa7fd-152">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-152">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="aa7fd-153">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-153">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="aa7fd-154">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-154">A comma-separated list of counters.</span></span> <span data-ttu-id="aa7fd-155">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-155">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="aa7fd-156">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-156">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="aa7fd-157">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="aa7fd-157">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="aa7fd-158">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="aa7fd-158">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="aa7fd-159">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-159">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="aa7fd-160">`dotnet-counters` startet einen Prozess mit dem bereitgestellten Befehl und überwacht die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-160">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="aa7fd-161">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-161">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="aa7fd-162">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-162">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="aa7fd-163">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-163">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

### <a name="examples"></a><span data-ttu-id="aa7fd-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="aa7fd-164">Examples</span></span>

- <span data-ttu-id="aa7fd-165">Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="aa7fd-165">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="aa7fd-166">Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="aa7fd-166">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="aa7fd-167">Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-167">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="aa7fd-168">Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="aa7fd-168">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="aa7fd-169">Starten Sie `my-aspnet-server.exe`, und überwachen Sie die Anzahl der vom Start geladenen Assemblys (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="aa7fd-169">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  <span data-ttu-id="aa7fd-170">HINWEIS: Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-170">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="aa7fd-171">Starten Sie `my-aspnet-server.exe` mit `arg1` und `arg2` als Befehlszeilenargumente, und überwachen Sie den Arbeitssatz und die GC-Heapgröße vom Start an (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="aa7fd-171">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  <span data-ttu-id="aa7fd-172">HINWEIS: Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-172">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="aa7fd-173">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="aa7fd-173">dotnet-counters ps</span></span>

<span data-ttu-id="aa7fd-174">Mit diesem Befehl wird eine Liste der dotnet-Prozesse angezeigt, die überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="aa7fd-174">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="aa7fd-175">Übersicht</span><span class="sxs-lookup"><span data-stu-id="aa7fd-175">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="aa7fd-176">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa7fd-176">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
