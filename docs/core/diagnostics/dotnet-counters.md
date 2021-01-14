---
title: Diagnosetool „dotnet-counters“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-counter“ installieren und für die Ad-hoc-Integritätsüberwachung und allgemeine Leistungsuntersuchung verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 44d74cfaca7483b1506fe7ad762818e9b9ed7d63
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058089"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="bcc88-103">Untersuchen von Leistungsindikatoren (dotnet-counters)</span><span class="sxs-lookup"><span data-stu-id="bcc88-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="bcc88-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="bcc88-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="bcc88-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="bcc88-105">Install</span></span>

<span data-ttu-id="bcc88-106">Es gibt zwei Möglichkeiten, `dotnet-counters` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="bcc88-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="bcc88-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="bcc88-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="bcc88-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="bcc88-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="bcc88-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="bcc88-109">**Direct download:**</span></span>

  <span data-ttu-id="bcc88-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="bcc88-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="bcc88-111">OS</span><span class="sxs-lookup"><span data-stu-id="bcc88-111">OS</span></span>  | <span data-ttu-id="bcc88-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="bcc88-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="bcc88-113">Windows</span><span class="sxs-lookup"><span data-stu-id="bcc88-113">Windows</span></span> | <span data-ttu-id="bcc88-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="bcc88-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="bcc88-115">macOS</span><span class="sxs-lookup"><span data-stu-id="bcc88-115">macOS</span></span>   | [<span data-ttu-id="bcc88-116">x64</span><span class="sxs-lookup"><span data-stu-id="bcc88-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="bcc88-117">Linux</span><span class="sxs-lookup"><span data-stu-id="bcc88-117">Linux</span></span>   | <span data-ttu-id="bcc88-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="bcc88-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="bcc88-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bcc88-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="bcc88-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bcc88-120">Description</span></span>

<span data-ttu-id="bcc88-121">`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene.</span><span class="sxs-lookup"><span data-stu-id="bcc88-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="bcc88-122">Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="bcc88-123">Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="bcc88-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="bcc88-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="bcc88-125">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="bcc88-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bcc88-126">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="bcc88-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="bcc88-127">Befehle</span><span class="sxs-lookup"><span data-stu-id="bcc88-127">Commands</span></span>

| <span data-ttu-id="bcc88-128">Befehl</span><span class="sxs-lookup"><span data-stu-id="bcc88-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="bcc88-129">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="bcc88-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="bcc88-130">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="bcc88-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="bcc88-131">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="bcc88-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="bcc88-132">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="bcc88-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="bcc88-133">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="bcc88-133">dotnet-counters collect</span></span>

<span data-ttu-id="bcc88-134">Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.</span><span class="sxs-lookup"><span data-stu-id="bcc88-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bcc88-135">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bcc88-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="bcc88-136">Optionen</span><span class="sxs-lookup"><span data-stu-id="bcc88-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="bcc88-137">Dies ist die ID des Prozesses, von dem die Leistungsindikatordaten erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="bcc88-138">Dies ist der Name des Prozesses, von dem die Leistungsindikatordaten erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-138">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="bcc88-139">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="bcc88-139">The name of the diagnostic port to create.</span></span> <span data-ttu-id="bcc88-140">Informationen zur Verwendung dieser Option, um die Überwachung von Leistungsindikatoren beim Start der App zu starten, finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="bcc88-140">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="bcc88-141">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="bcc88-141">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="bcc88-142">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="bcc88-142">A comma-separated list of counters.</span></span> <span data-ttu-id="bcc88-143">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-143">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="bcc88-144">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcc88-144">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="bcc88-145">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="bcc88-145">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="bcc88-146">Das zu exportierende Format</span><span class="sxs-lookup"><span data-stu-id="bcc88-146">The format to be exported.</span></span> <span data-ttu-id="bcc88-147">Derzeit sind die folgenden Formate verfügbar: CSV und JSON.</span><span class="sxs-lookup"><span data-stu-id="bcc88-147">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="bcc88-148">Der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="bcc88-148">The name of the output file.</span></span>

- <span data-ttu-id="bcc88-149">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="bcc88-149">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="bcc88-150">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="bcc88-150">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="bcc88-151">`dotnet-counters` startet einen Prozess mit dem angegebenen Befehl und erfasst die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="bcc88-151">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="bcc88-152">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-152">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bcc88-153">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-153">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="bcc88-154">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-154">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bcc88-155">Wenn eine ausführbare .NET-Datei über „dotnet-counters“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mehr mit „stdin/stdout“ interagieren.</span><span class="sxs-lookup"><span data-stu-id="bcc88-155">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="bcc88-156">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="bcc88-156">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="bcc88-157">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="bcc88-157">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="bcc88-158">Wenn Sie „stdin/stdout“ verwenden müssen, können Sie die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-158">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="bcc88-159">Weitere Informationen finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="bcc88-159">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="bcc88-160">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bcc88-160">Examples</span></span>

- <span data-ttu-id="bcc88-161">Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="bcc88-161">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="bcc88-162">Starten Sie `dotnet mvc.dll` als untergeordneten Prozess, und beginnen Sie von Anfang an mit der Erfassung von Runtimeindikatoren und ASP.NET Core-Hostingindikatoren. Speichern Sie sie als JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bcc88-162">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="bcc88-163">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="bcc88-163">dotnet-counters list</span></span>

<span data-ttu-id="bcc88-164">Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="bcc88-164">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bcc88-165">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bcc88-165">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="bcc88-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcc88-166">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs per interval
    gen-1-gc-count                               Number of Gen 1 GCs per interval
    gen-2-gc-count                               Number of Gen 2 GCs per interval
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions per interval
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
> <span data-ttu-id="bcc88-167">Die `Microsoft.AspNetCore.Hosting`-Leistungsindikatoren werden angezeigt, wenn bestimmte Prozesse identifiziert werden, die diese Leistungsindikatoren unterstützen, etwa wenn eine ASP.NET Core-Anwendung auf dem Hostcomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bcc88-167">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="bcc88-168">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="bcc88-168">dotnet-counters monitor</span></span>

<span data-ttu-id="bcc88-169">Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.</span><span class="sxs-lookup"><span data-stu-id="bcc88-169">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bcc88-170">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bcc88-170">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="bcc88-171">Optionen</span><span class="sxs-lookup"><span data-stu-id="bcc88-171">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="bcc88-172">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bcc88-172">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="bcc88-173">Dies ist der Name des Prozesses, der überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcc88-173">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="bcc88-174">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="bcc88-174">The name of the diagnostic port to create.</span></span> <span data-ttu-id="bcc88-175">Informationen zur Verwendung dieser Option, um die Überwachung von Leistungsindikatoren beim Start der App zu starten, finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="bcc88-175">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="bcc88-176">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="bcc88-176">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="bcc88-177">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="bcc88-177">A comma-separated list of counters.</span></span> <span data-ttu-id="bcc88-178">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-178">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="bcc88-179">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcc88-179">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="bcc88-180">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="bcc88-180">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="bcc88-181">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="bcc88-181">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="bcc88-182">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="bcc88-182">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="bcc88-183">`dotnet-counters` startet einen Prozess mit dem bereitgestellten Befehl und überwacht die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="bcc88-183">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="bcc88-184">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-184">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bcc88-185">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-185">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="bcc88-186">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-186">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bcc88-187">Wenn eine ausführbare .NET-Datei über „dotnet-counters“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mehr mit „stdin/stdout“ interagieren.</span><span class="sxs-lookup"><span data-stu-id="bcc88-187">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="bcc88-188">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="bcc88-188">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="bcc88-189">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet.</span><span class="sxs-lookup"><span data-stu-id="bcc88-189">If the child process exits before the tool, the tool will exit as well.</span></span> <span data-ttu-id="bcc88-190">Wenn Sie „stdin/stdout“ verwenden müssen, können Sie die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-190">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="bcc88-191">Weitere Informationen finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="bcc88-191">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="bcc88-192">Beispiele</span><span class="sxs-lookup"><span data-stu-id="bcc88-192">Examples</span></span>

- <span data-ttu-id="bcc88-193">Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="bcc88-193">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="bcc88-194">Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="bcc88-194">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="bcc88-195">Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="bcc88-195">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="bcc88-196">Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="bcc88-196">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="bcc88-197">Anzeigen aller bekannten Zähler, die in `dotnet-counters` verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="bcc88-197">View all well-known counters that are available in `dotnet-counters`:</span></span>

  ```console
  > dotnet-counters list

  Showing well-known counters for .NET (Core) version 3.1 only. Specific processes may support additional counters.
  System.Runtime              
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active

  Microsoft.AspNetCore.Hosting
      requests-per-second                Number of requests between update intervals
      total-requests                     Total number of requests
      current-requests                   Current number of requests
      failed-requests                    Failed number of requests
  ```

- <span data-ttu-id="bcc88-198">Anzeigen aller bekannten Zähler, die in `dotnet-counters` für .NET 5-Apps verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="bcc88-198">View all well-known counters that are available in `dotnet-counters` for .NET 5 apps:</span></span>

  ```console
  > dotnet-counters list --runtime-version 5.0

  Showing well-known counters for .NET (Core) version 5.0 only. Specific processes may support additional counters.
  System.Runtime                     
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      poh-size                           POH (Pinned Object Heap) Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      gc-fragmentation                   GC Heap Fragmentation
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active
      il-bytes-jitted                    Total IL bytes jitted
      methods-jitted-count               Number of methods jitted

  Microsoft.AspNetCore.Hosting       
      requests-per-second   Number of requests between update intervals
      total-requests        Total number of requests
      current-requests      Current number of requests
      failed-requests       Failed number of requests

  Microsoft-AspNetCore-Server-Kestrel
      connections-per-second      Number of connections between update intervals
      total-connections           Total Connections
      tls-handshakes-per-second   Number of TLS Handshakes made between update intervals
      total-tls-handshakes        Total number of TLS handshakes made
      current-tls-handshakes      Number of currently active TLS handshakes
      failed-tls-handshakes       Total number of failed TLS handshakes
      current-connections         Number of current connections
      connection-queue-length     Length of Kestrel Connection Queue
      request-queue-length        Length total HTTP request queue

  System.Net.Http                    
      requests-started        Total Requests Started
      requests-started-rate   Number of Requests Started between update intervals
      requests-aborted        Total Requests Aborted
      requests-aborted-rate   Number of Requests Aborted between update intervals
      current-requests        Current Requests
  ```

- <span data-ttu-id="bcc88-199">Starten Sie `my-aspnet-server.exe`, und überwachen Sie die Anzahl der vom Start geladenen Assemblys (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="bcc88-199">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="bcc88-200">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="bcc88-200">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="bcc88-201">Starten Sie `my-aspnet-server.exe` mit `arg1` und `arg2` als Befehlszeilenargumente, und überwachen Sie den Arbeitssatz und die GC-Heapgröße vom Start an (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="bcc88-201">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="bcc88-202">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="bcc88-202">This works for apps running .NET 5.0 or later only.</span></span>

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

## <a name="dotnet-counters-ps"></a><span data-ttu-id="bcc88-203">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="bcc88-203">dotnet-counters ps</span></span>

<span data-ttu-id="bcc88-204">Mit diesem Befehl wird eine Liste der dotnet-Prozesse angezeigt, die überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="bcc88-204">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="bcc88-205">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bcc88-205">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="bcc88-206">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcc88-206">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="bcc88-207">Verwenden des Diagnoseports</span><span class="sxs-lookup"><span data-stu-id="bcc88-207">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="bcc88-208">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="bcc88-208">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="bcc88-209">Der Diagnoseport ist ein neues Runtimefeature, das in .NET 5 hinzugefügt wurde und es Ihnen ermöglicht, die Überwachung oder Erfassung von Leistungsindikatoren beim Start der App zu starten.</span><span class="sxs-lookup"><span data-stu-id="bcc88-209">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="bcc88-210">Dies können Sie mit `dotnet-counters` einrichten, indem Sie `dotnet-counters <collect|monitor> -- <command>` wie in den Beispielen oben oder die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcc88-210">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="bcc88-211">Die Verwendung von `dotnet-counters <collect|monitor> -- <command>` zum Starten der Anwendung als untergeordneter Prozess ist die einfachste Möglichkeit, schnell mit der Überwachung ab dem Start zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-211">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="bcc88-212">Wenn Sie allerdings präzisere Kontrolle über die Lebensdauer der überwachten App wünschen (z. B., damit die App nur in den ersten 10 Minuten überwacht und dann weiterhin ausgeführt wird) oder mithilfe der CLI mit der App interagieren müssen, können Sie die Option `--diagnostic-port` verwenden, um sowohl die überwachte Ziel-App als auch `dotnet-counters` zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bcc88-212">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="bcc88-213">Der folgende Befehl sorgt dafür, dass „dotnet-counters“ einen Diagnosesocket namens `myport.sock` erstellt und auf eine Verbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="bcc88-213">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="bcc88-214">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bcc88-214">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="bcc88-215">Starten Sie die Zielanwendung in einer separaten Konsole mit der Umgebungsvariable `DOTNET_DiagnosticPorts`, die Sie auf den Wert in der `dotnet-counters`-Ausgabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="bcc88-215">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="bcc88-216">Dadurch sollte `dotnet-counters` damit beginnen, Leistungsindikatoren von `my-dotnet-app` zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="bcc88-216">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="bcc88-217">Das Starten Ihrer App mit `dotnet run` kann sich als problematisch erweisen, da die .NET-CLI viele untergeordnete Prozesse erzeugen kann, bei denen es sich nicht um Ihre App handelt. Diese können vor Ihrer App eine Verbindung mit `dotnet-counters` herstellen, wodurch Ihre App zur Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="bcc88-217">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="bcc88-218">Es wird empfohlen, dass Sie direkt eine eigenständige Version der App oder `dotnet exec` verwenden, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="bcc88-218">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
