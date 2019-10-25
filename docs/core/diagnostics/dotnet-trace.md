---
title: dotnet-trace – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321531"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a><span data-ttu-id="25ad9-103">Hilfsprogramm zur Ablaufverfolgung für Leistungsanalysen (`dotnet-trace`)</span><span class="sxs-lookup"><span data-stu-id="25ad9-103">Trace for performance analysis utility (`dotnet-trace`)</span></span>

<span data-ttu-id="25ad9-104">**Dieser Artikel gilt für:** .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="25ad9-104">**This article applies to:** .NET Core 3.0 SDK and later versions</span></span>

## <a name="installing-dotnet-trace"></a><span data-ttu-id="25ad9-105">Installieren von `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="25ad9-105">Installing `dotnet-trace`</span></span>

<span data-ttu-id="25ad9-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="25ad9-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="25ad9-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="25ad9-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="25ad9-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25ad9-108">Description</span></span>

<span data-ttu-id="25ad9-109">Das Tool `dotnet-trace` ist ein plattformübergreifendes globales Befehlszeilenschnittstellen-Tool zum Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="25ad9-109">The `dotnet-trace` tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process without any native profiler involved.</span></span> <span data-ttu-id="25ad9-110">Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="25ad9-110">It's built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span> <span data-ttu-id="25ad9-111">`dotnet-trace` bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="25ad9-111">`dotnet-trace` delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="25ad9-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="25ad9-112">Options</span></span>

- **`--version`**

<span data-ttu-id="25ad9-113">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="25ad9-113">Display the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

<span data-ttu-id="25ad9-114">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="25ad9-114">Show command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="25ad9-115">Befehle</span><span class="sxs-lookup"><span data-stu-id="25ad9-115">Commands</span></span>

| <span data-ttu-id="25ad9-116">Befehl</span><span class="sxs-lookup"><span data-stu-id="25ad9-116">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="25ad9-117">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="25ad9-117">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="25ad9-118">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="25ad9-118">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="25ad9-119">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="25ad9-119">dotnet-trace list-processes</span></span>](#dotnet-trace-list-processes) |
| [<span data-ttu-id="25ad9-120">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="25ad9-120">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="25ad9-121">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="25ad9-121">dotnet-trace collect</span></span>

<span data-ttu-id="25ad9-122">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="25ad9-122">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="25ad9-123">Übersicht</span><span class="sxs-lookup"><span data-stu-id="25ad9-123">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="25ad9-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="25ad9-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="25ad9-125">Der Prozess, von dem die Ablaufverfolgung gesammelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="25ad9-125">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="25ad9-126">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="25ad9-126">Sets the size of the in-memory circular buffer in megabytes.</span></span> <span data-ttu-id="25ad9-127">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="25ad9-127">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="25ad9-128">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="25ad9-128">The output path for the collected trace data.</span></span> <span data-ttu-id="25ad9-129">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="25ad9-129">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="25ad9-130">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25ad9-130">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="25ad9-131">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="25ad9-131">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="25ad9-132">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat die Konfiguration hier Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="25ad9-132">If there's any inconsistency for a particular provider, the configuration here takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="25ad9-133">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="25ad9-133">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="25ad9-134">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="25ad9-134">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="25ad9-135">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="25ad9-135">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="25ad9-136">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="25ad9-136">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="25ad9-137">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="25ad9-137">Sets the output format for the trace file conversion.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="25ad9-138">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="25ad9-138">dotnet-trace convert</span></span>

<span data-ttu-id="25ad9-139">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="25ad9-139">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="25ad9-140">Übersicht</span><span class="sxs-lookup"><span data-stu-id="25ad9-140">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="25ad9-141">Argumente</span><span class="sxs-lookup"><span data-stu-id="25ad9-141">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="25ad9-142">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="25ad9-142">Input trace file to be converted.</span></span> <span data-ttu-id="25ad9-143">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="25ad9-143">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="25ad9-144">Optionen</span><span class="sxs-lookup"><span data-stu-id="25ad9-144">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="25ad9-145">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="25ad9-145">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="25ad9-146">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="25ad9-146">Output filename.</span></span> <span data-ttu-id="25ad9-147">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="25ad9-147">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-list-processes"></a><span data-ttu-id="25ad9-148">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="25ad9-148">dotnet-trace list-processes</span></span>

<span data-ttu-id="25ad9-149">Listet die dotnet-Prozesse auf, die verfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="25ad9-149">Lists dotnet processes that can be traced.</span></span>

### <a name="synopsis"></a><span data-ttu-id="25ad9-150">Übersicht</span><span class="sxs-lookup"><span data-stu-id="25ad9-150">Synopsis</span></span>

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="25ad9-151">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="25ad9-151">dotnet-trace list-profiles</span></span>

<span data-ttu-id="25ad9-152">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="25ad9-152">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="25ad9-153">Übersicht</span><span class="sxs-lookup"><span data-stu-id="25ad9-153">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="25ad9-154">Erfassen einer Ablaufverfolgung mit `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="25ad9-154">Collect a trace with `dotnet-trace`</span></span>

- <span data-ttu-id="25ad9-155">Um Ablaufverfolgungen mithilfe von `dotnet-trace` zu sammeln, müssen Sie zunächst die Prozess-ID (PID) der .NET Core-Anwendung ermitteln, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25ad9-155">To collect traces using `dotnet-trace`, you'll need to first, find out the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="25ad9-156">Unter Windows gibt es Optionen wie den Task-Manager oder den Befehl `tasklist`.</span><span class="sxs-lookup"><span data-stu-id="25ad9-156">On Windows, there are options such as using the task manager or the `tasklist` command.</span></span>
  - <span data-ttu-id="25ad9-157">Unter Linux besteht die triviale Option im Verwenden des Befehls `ps`.</span><span class="sxs-lookup"><span data-stu-id="25ad9-157">On Linux, the trivial option could be using `ps` command.</span></span>

<span data-ttu-id="25ad9-158">Sie können auch den Befehl [dotnet-trace list-processes](#dotnet-trace-list-processes) verwenden, um die ausgeführten .NET Core-Prozesse zusammen mit ihren PIDs herauszufinden.</span><span class="sxs-lookup"><span data-stu-id="25ad9-158">You may also use the [dotnet-trace list-processes](#dotnet-trace-list-processes) command to find out what .NET Core processes are running, along with their PIDs.</span></span>

- <span data-ttu-id="25ad9-159">Führen Sie dann den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="25ad9-159">Then, run the following command:</span></span>

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- <span data-ttu-id="25ad9-160">Beenden Sie schließlich die Sammlung, indem Sie die Taste `<Enter>` drücken. `dotnet-trace` protokolliert dann keine Ereignisse mehr in der Datei `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="25ad9-160">Finally, stop collection by pressing the `<Enter>` key, and `dotnet-trace` will finish logging events to `trace.nettrace` file.</span></span>

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="25ad9-161">Anzeigen der aufgezeichneten Ablaufverfolgung von `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="25ad9-161">Viewing the trace captured from `dotnet-trace`</span></span>

<span data-ttu-id="25ad9-162">Unter Windows können `.nettrace`-Dateien genau wie mit ETW oder LTTng gesammelte Ablaufverfolgungen in [PerfView](https://github.com/microsoft/perfview) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="25ad9-162">On Windows, `.nettrace` files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis, just like traces collected with ETW or LTTng.</span></span> <span data-ttu-id="25ad9-163">Bei unter Linux gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgung auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="25ad9-163">For traces collected on Linux, you can move the trace to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="25ad9-164">Sie können die Ablaufverfolgung auch auf einem Linux-Computer anzeigen, indem Sie das Ausgabeformat von `dotnet-trace` in `speedscope` ändern.</span><span class="sxs-lookup"><span data-stu-id="25ad9-164">You may also view the trace on a Linux machine by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="25ad9-165">Sie können das Ausgabedateiformat mit der Option `-f|--format` ändern – mit `-f speedscope` generiert `dotnet-trace` eine `speedscope`-Datei.</span><span class="sxs-lookup"><span data-stu-id="25ad9-165">You can change the output file format using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` to produce a `speedscope` file.</span></span> <span data-ttu-id="25ad9-166">Derzeit können Sie zwischen `nettrace` (Standardoption) und `speedscope` auswählen.</span><span class="sxs-lookup"><span data-stu-id="25ad9-166">You can currently choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="25ad9-167">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="25ad9-167">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="25ad9-168">Die .NET Core-Runtime generiert Ablaufverfolgungen im `nettrace`-Format, die nach Abschluss der Ablaufverfolgung in „speedscope“ konvertiert werden (sofern dies angegeben wird).</span><span class="sxs-lookup"><span data-stu-id="25ad9-168">The .NET Core runtime generates traces in the `nettrace` format, and they're converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="25ad9-169">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="25ad9-169">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="25ad9-170">Verwenden von `dotnet-trace` zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="25ad9-170">Using `dotnet-trace` to collect counter values over time</span></span>

<span data-ttu-id="25ad9-171">Wenn Sie `EventCounter` für die grundlegende Systemüberwachung in leistungsempfindlichen Umfeldern wie Produktionsumgebungen verwenden und dabei Ablaufverfolgungen sammeln möchten, anstatt sie in Echtzeit zu überwachen, können Sie dies ebenfalls mit `dotnet-trace` erreichen.</span><span class="sxs-lookup"><span data-stu-id="25ad9-171">If you're trying to use `EventCounter` for basic health monitoring in  performance-sensitive settings like production environments and you want to collect traces instead of watching them in real time, you can do that with `dotnet-trace` as well.</span></span>

<span data-ttu-id="25ad9-172">Wenn Sie z. B. Laufzeit-Leistungsindikatorwerte sammeln möchten, können Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="25ad9-172">For example, if you want to collect runtime performance counter values, you can use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="25ad9-173">Dieser Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Integritätsüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="25ad9-173">This command tells the runtime counters to be reported once every second for lightweight health monitoring.</span></span> <span data-ttu-id="25ad9-174">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="25ad9-174">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows you to collect a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="25ad9-175">Wenn Sie den Mehraufwand (und die Größe der Ablaufverfolgung) noch weiter reduzieren möchten, können Sie mit dem folgenden Befehl Laufzeitereignisse und den verwalteten Stapelprofiler deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="25ad9-175">If you want to disable runtime events to reduce the overhead (and trace size) even further, you can use the following command to disable runtime events and managed stack profiler.</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a><span data-ttu-id="25ad9-176">.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="25ad9-176">.NET Providers</span></span>

<span data-ttu-id="25ad9-177">Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="25ad9-177">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="25ad9-178">.NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="25ad9-178">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="25ad9-179">Anbietername</span><span class="sxs-lookup"><span data-stu-id="25ad9-179">Provider name</span></span>                            | <span data-ttu-id="25ad9-180">Information</span><span class="sxs-lookup"><span data-stu-id="25ad9-180">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="25ad9-181">Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="25ad9-181">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="25ad9-182">CLR-Runtime-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25ad9-182">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="25ad9-183">Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="25ad9-183">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="25ad9-184">CLR-Rundown-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25ad9-184">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="25ad9-185">Aktiviert den Beispielprofiler.</span><span class="sxs-lookup"><span data-stu-id="25ad9-185">Enables the sample profiler.</span></span> |
