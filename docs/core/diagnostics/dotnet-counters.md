---
title: Diagnosetool „dotnet-counters“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-counter“ installieren und für die Ad-hoc-Integritätsüberwachung und allgemeine Leistungsuntersuchung verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 48e3b038ddb5c9421367612a592c5ba6b9459791
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009546"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="ef099-103">Untersuchen von Leistungsindikatoren (dotnet-counters)</span><span class="sxs-lookup"><span data-stu-id="ef099-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="ef099-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="ef099-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="ef099-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="ef099-105">Install</span></span>

<span data-ttu-id="ef099-106">Es gibt zwei Möglichkeiten, `dotnet-counters` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="ef099-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="ef099-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="ef099-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="ef099-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="ef099-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="ef099-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="ef099-109">**Direct download:**</span></span>

  <span data-ttu-id="ef099-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="ef099-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="ef099-111">OS</span><span class="sxs-lookup"><span data-stu-id="ef099-111">OS</span></span>  | <span data-ttu-id="ef099-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="ef099-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="ef099-113">Windows</span><span class="sxs-lookup"><span data-stu-id="ef099-113">Windows</span></span> | <span data-ttu-id="ef099-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="ef099-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="ef099-115">macOS</span><span class="sxs-lookup"><span data-stu-id="ef099-115">macOS</span></span>   | [<span data-ttu-id="ef099-116">x64</span><span class="sxs-lookup"><span data-stu-id="ef099-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="ef099-117">Linux</span><span class="sxs-lookup"><span data-stu-id="ef099-117">Linux</span></span>   | <span data-ttu-id="ef099-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="ef099-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="ef099-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef099-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="ef099-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef099-120">Description</span></span>

<span data-ttu-id="ef099-121">`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene.</span><span class="sxs-lookup"><span data-stu-id="ef099-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="ef099-122">Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ef099-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="ef099-123">Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.</span><span class="sxs-lookup"><span data-stu-id="ef099-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="ef099-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="ef099-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="ef099-125">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="ef099-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ef099-126">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="ef099-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="ef099-127">Befehle</span><span class="sxs-lookup"><span data-stu-id="ef099-127">Commands</span></span>

| <span data-ttu-id="ef099-128">Befehl</span><span class="sxs-lookup"><span data-stu-id="ef099-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="ef099-129">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="ef099-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="ef099-130">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="ef099-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="ef099-131">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="ef099-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="ef099-132">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="ef099-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="ef099-133">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="ef099-133">dotnet-counters collect</span></span>

<span data-ttu-id="ef099-134">Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.</span><span class="sxs-lookup"><span data-stu-id="ef099-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ef099-135">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef099-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="ef099-136">Optionen</span><span class="sxs-lookup"><span data-stu-id="ef099-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="ef099-137">Dies ist die ID des Prozesses, von dem die Leistungsindikatordaten erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef099-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="ef099-138">Dies ist der Name des Prozesses, von dem die Leistungsindikatordaten erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef099-138">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="ef099-139">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="ef099-139">The name of the diagnostic port to create.</span></span> <span data-ttu-id="ef099-140">Informationen zur Verwendung dieser Option, um die Überwachung von Leistungsindikatoren beim Start der App zu starten, finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="ef099-140">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="ef099-141">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="ef099-141">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="ef099-142">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="ef099-142">A comma-separated list of counters.</span></span> <span data-ttu-id="ef099-143">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef099-143">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="ef099-144">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef099-144">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="ef099-145">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="ef099-145">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="ef099-146">Das zu exportierende Format</span><span class="sxs-lookup"><span data-stu-id="ef099-146">The format to be exported.</span></span> <span data-ttu-id="ef099-147">Derzeit sind die folgenden Formate verfügbar: CSV und JSON.</span><span class="sxs-lookup"><span data-stu-id="ef099-147">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="ef099-148">Der Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="ef099-148">The name of the output file.</span></span>

- <span data-ttu-id="ef099-149">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="ef099-149">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="ef099-150">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef099-150">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="ef099-151">`dotnet-counters` startet einen Prozess mit dem angegebenen Befehl und erfasst die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="ef099-151">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="ef099-152">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="ef099-152">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef099-153">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ef099-153">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="ef099-154">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef099-154">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef099-155">Wenn eine ausführbare .NET-Datei über „dotnet-counters“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mehr mit „stdin/stdout“ interagieren.</span><span class="sxs-lookup"><span data-stu-id="ef099-155">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="ef099-156">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="ef099-156">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="ef099-157">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="ef099-157">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="ef099-158">Wenn Sie „stdin/stdout“ verwenden müssen, können Sie die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef099-158">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="ef099-159">Weitere Informationen finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="ef099-159">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="ef099-160">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ef099-160">Examples</span></span>

- <span data-ttu-id="ef099-161">Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:</span><span class="sxs-lookup"><span data-stu-id="ef099-161">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="ef099-162">Starten Sie `dotnet mvc.dll` als untergeordneten Prozess, und beginnen Sie von Anfang an mit der Erfassung von Runtimeindikatoren und ASP.NET Core-Hostingindikatoren. Speichern Sie sie als JSON-Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ef099-162">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="ef099-163">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="ef099-163">dotnet-counters list</span></span>

<span data-ttu-id="ef099-164">Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="ef099-164">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ef099-165">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef099-165">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="ef099-166">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef099-166">Example</span></span>

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
> <span data-ttu-id="ef099-167">Die `Microsoft.AspNetCore.Hosting`-Leistungsindikatoren werden angezeigt, wenn bestimmte Prozesse identifiziert werden, die diese Leistungsindikatoren unterstützen, etwa wenn eine ASP.NET Core-Anwendung auf dem Hostcomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef099-167">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="ef099-168">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="ef099-168">dotnet-counters monitor</span></span>

<span data-ttu-id="ef099-169">Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.</span><span class="sxs-lookup"><span data-stu-id="ef099-169">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ef099-170">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef099-170">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="ef099-171">Optionen</span><span class="sxs-lookup"><span data-stu-id="ef099-171">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="ef099-172">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ef099-172">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="ef099-173">Dies ist der Name des Prozesses, der überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef099-173">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="ef099-174">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="ef099-174">The name of the diagnostic port to create.</span></span> <span data-ttu-id="ef099-175">Informationen zur Verwendung dieser Option, um die Überwachung von Leistungsindikatoren beim Start der App zu starten, finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="ef099-175">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="ef099-176">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="ef099-176">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="ef099-177">Eine durch Leerzeichen getrennte Liste von Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="ef099-177">A comma-separated list of counters.</span></span> <span data-ttu-id="ef099-178">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef099-178">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="ef099-179">Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef099-179">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="ef099-180">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="ef099-180">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="ef099-181">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**</span><span class="sxs-lookup"><span data-stu-id="ef099-181">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="ef099-182">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef099-182">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="ef099-183">`dotnet-counters` startet einen Prozess mit dem bereitgestellten Befehl und überwacht die angeforderten Metriken.</span><span class="sxs-lookup"><span data-stu-id="ef099-183">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="ef099-184">Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="ef099-184">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef099-185">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ef099-185">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="ef099-186">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef099-186">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef099-187">Wenn eine ausführbare .NET-Datei über „dotnet-counters“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mehr mit „stdin/stdout“ interagieren.</span><span class="sxs-lookup"><span data-stu-id="ef099-187">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="ef099-188">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="ef099-188">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="ef099-189">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="ef099-189">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="ef099-190">Wenn Sie „stdin/stdout“ verwenden müssen, können Sie die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef099-190">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="ef099-191">Weitere Informationen finden Sie unter [Verwenden von Diagnoseports](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="ef099-191">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="ef099-192">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ef099-192">Examples</span></span>

- <span data-ttu-id="ef099-193">Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="ef099-193">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="ef099-194">Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="ef099-194">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="ef099-195">Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="ef099-195">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="ef099-196">Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="ef099-196">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="ef099-197">Starten Sie `my-aspnet-server.exe`, und überwachen Sie die Anzahl der vom Start geladenen Assemblys (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="ef099-197">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ef099-198">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ef099-198">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="ef099-199">Starten Sie `my-aspnet-server.exe` mit `arg1` und `arg2` als Befehlszeilenargumente, und überwachen Sie den Arbeitssatz und die GC-Heapgröße vom Start an (nur .NET 5.0 oder höher):</span><span class="sxs-lookup"><span data-stu-id="ef099-199">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ef099-200">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ef099-200">This works for apps running .NET 5.0 or later only.</span></span>

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

## <a name="dotnet-counters-ps"></a><span data-ttu-id="ef099-201">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="ef099-201">dotnet-counters ps</span></span>

<span data-ttu-id="ef099-202">Mit diesem Befehl wird eine Liste der dotnet-Prozesse angezeigt, die überwacht werden können.</span><span class="sxs-lookup"><span data-stu-id="ef099-202">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ef099-203">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ef099-203">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="ef099-204">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef099-204">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="ef099-205">Verwenden des Diagnoseports</span><span class="sxs-lookup"><span data-stu-id="ef099-205">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ef099-206">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ef099-206">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="ef099-207">Der Diagnoseport ist ein neues Runtimefeature, das in .NET 5 hinzugefügt wurde und es Ihnen ermöglicht, die Überwachung oder Erfassung von Leistungsindikatoren beim Start der App zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef099-207">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="ef099-208">Dies können Sie mit `dotnet-counters` einrichten, indem Sie `dotnet-counters <collect|monitor> -- <command>` wie in den Beispielen oben oder die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef099-208">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="ef099-209">Die Verwendung von `dotnet-counters <collect|monitor> -- <command>` zum Starten der Anwendung als untergeordneter Prozess ist die einfachste Möglichkeit, schnell mit der Überwachung ab dem Start zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ef099-209">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="ef099-210">Wenn Sie allerdings präzisere Kontrolle über die Lebensdauer der überwachten App wünschen (z. B., damit die App nur in den ersten 10 Minuten überwacht und dann weiterhin ausgeführt wird) oder mithilfe der CLI mit der App interagieren müssen, können Sie die Option `--diagnostic-port` verwenden, um sowohl die überwachte Ziel-App als auch `dotnet-counters` zu steuern.</span><span class="sxs-lookup"><span data-stu-id="ef099-210">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="ef099-211">Der folgende Befehl sorgt dafür, dass „dotnet-counters“ einen Diagnosesocket namens `myport.sock` erstellt und auf eine Verbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="ef099-211">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="ef099-212">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ef099-212">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="ef099-213">Starten Sie die Zielanwendung in einer separaten Konsole mit der Umgebungsvariable `DOTNET_DiagnosticPorts`, die Sie auf den Wert in der `dotnet-counters`-Ausgabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="ef099-213">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="ef099-214">Dadurch sollte `dotnet-counters` damit beginnen, Leistungsindikatoren von `my-dotnet-app` zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="ef099-214">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="ef099-215">Das Starten Ihrer App mit `dotnet run` kann sich als problematisch erweisen, da die .NET-CLI viele untergeordnete Prozesse erzeugen kann, bei denen es sich nicht um Ihre App handelt. Diese können vor Ihrer App eine Verbindung mit `dotnet-counters` herstellen, wodurch Ihre App zur Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ef099-215">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="ef099-216">Es wird empfohlen, dass Sie direkt eine eigenständige Version der App oder `dotnet exec` verwenden, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ef099-216">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
