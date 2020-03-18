---
title: Das Tool „dotnet-trace“ – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: b19b159636fbf57fa2d461b398fcf9234aab491c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76737650"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="e1e22-103">dotnet-trace-Hilfsprogramm für Leistungsanalysen</span><span class="sxs-lookup"><span data-stu-id="e1e22-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="e1e22-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="e1e22-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="e1e22-105">Installieren von dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="e1e22-105">Install dotnet-trace</span></span>

<span data-ttu-id="e1e22-106">Installieren Sie das [NuGet-Paket](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` mit dem Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="e1e22-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="e1e22-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1e22-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="e1e22-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1e22-108">Description</span></span>

<span data-ttu-id="e1e22-109">Das `dotnet-trace`-Tool:</span><span class="sxs-lookup"><span data-stu-id="e1e22-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="e1e22-110">Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="e1e22-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="e1e22-111">Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="e1e22-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="e1e22-112">Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="e1e22-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="e1e22-113">Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="e1e22-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="e1e22-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="e1e22-114">Options</span></span>

- **`--version`**

  <span data-ttu-id="e1e22-115">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="e1e22-115">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e1e22-116">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="e1e22-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="e1e22-117">Befehle</span><span class="sxs-lookup"><span data-stu-id="e1e22-117">Commands</span></span>

| <span data-ttu-id="e1e22-118">Befehl</span><span class="sxs-lookup"><span data-stu-id="e1e22-118">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="e1e22-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="e1e22-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="e1e22-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="e1e22-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="e1e22-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="e1e22-121">dotnet-trace ps</span></span>](#dotnet-trace-ps) |
| [<span data-ttu-id="e1e22-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="e1e22-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="e1e22-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="e1e22-123">dotnet-trace collect</span></span>

<span data-ttu-id="e1e22-124">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="e1e22-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e1e22-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1e22-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="e1e22-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="e1e22-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="e1e22-127">Der Prozess, von dem die Ablaufverfolgung gesammelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1e22-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="e1e22-128">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="e1e22-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="e1e22-129">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="e1e22-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="e1e22-130">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="e1e22-130">The output path for the collected trace data.</span></span> <span data-ttu-id="e1e22-131">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1e22-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="e1e22-132">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1e22-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="e1e22-133">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e1e22-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="e1e22-134">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="e1e22-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="e1e22-135">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="e1e22-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="e1e22-136">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="e1e22-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="e1e22-137">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="e1e22-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="e1e22-138">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="e1e22-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="e1e22-139">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="e1e22-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="e1e22-140">Der Standardwert ist `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="e1e22-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="e1e22-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="e1e22-141">dotnet-trace convert</span></span>

<span data-ttu-id="e1e22-142">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="e1e22-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e1e22-143">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1e22-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="e1e22-144">Argumente</span><span class="sxs-lookup"><span data-stu-id="e1e22-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="e1e22-145">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="e1e22-145">Input trace file to be converted.</span></span> <span data-ttu-id="e1e22-146">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="e1e22-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="e1e22-147">Optionen</span><span class="sxs-lookup"><span data-stu-id="e1e22-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="e1e22-148">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="e1e22-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="e1e22-149">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="e1e22-149">Output filename.</span></span> <span data-ttu-id="e1e22-150">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1e22-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="e1e22-151">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="e1e22-151">dotnet-trace ps</span></span>

<span data-ttu-id="e1e22-152">Listet anfügbare dotnet-Prozesse auf.</span><span class="sxs-lookup"><span data-stu-id="e1e22-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e1e22-153">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1e22-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="e1e22-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="e1e22-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="e1e22-155">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="e1e22-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="e1e22-156">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1e22-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="e1e22-157">Sammeln einer Ablaufverfolgung mit dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="e1e22-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="e1e22-158">So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="e1e22-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="e1e22-159">Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1e22-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="e1e22-160">Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1e22-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="e1e22-161">Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="e1e22-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="e1e22-162">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="e1e22-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="e1e22-163">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e1e22-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="e1e22-164">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e1e22-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="e1e22-165">Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an.</span><span class="sxs-lookup"><span data-stu-id="e1e22-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="e1e22-166">`dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="e1e22-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="e1e22-167">Anzeigen der von dotnet-trace erfassten Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e1e22-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="e1e22-168">Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e1e22-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="e1e22-169">Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e1e22-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="e1e22-170">Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="e1e22-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="e1e22-171">Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen.</span><span class="sxs-lookup"><span data-stu-id="e1e22-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="e1e22-172">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="e1e22-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="e1e22-173">Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format.</span><span class="sxs-lookup"><span data-stu-id="e1e22-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="e1e22-174">Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e1e22-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="e1e22-175">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e1e22-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="e1e22-176">Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="e1e22-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="e1e22-177">`dotnet-trace` kann:</span><span class="sxs-lookup"><span data-stu-id="e1e22-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="e1e22-178">`EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1e22-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="e1e22-179">Beispielsweise in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="e1e22-179">For example, in production.</span></span>
* <span data-ttu-id="e1e22-180">Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e1e22-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="e1e22-181">Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="e1e22-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="e1e22-182">Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="e1e22-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="e1e22-183">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="e1e22-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="e1e22-184">Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:</span><span class="sxs-lookup"><span data-stu-id="e1e22-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="e1e22-185">Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.</span><span class="sxs-lookup"><span data-stu-id="e1e22-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="e1e22-186">.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e1e22-186">.NET Providers</span></span>

<span data-ttu-id="e1e22-187">Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e1e22-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="e1e22-188">.NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="e1e22-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="e1e22-189">Anbietername</span><span class="sxs-lookup"><span data-stu-id="e1e22-189">Provider name</span></span>                            | <span data-ttu-id="e1e22-190">Information</span><span class="sxs-lookup"><span data-stu-id="e1e22-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="e1e22-191">Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="e1e22-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="e1e22-192">CLR-Runtime-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e1e22-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="e1e22-193">Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="e1e22-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="e1e22-194">CLR-Rundown-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e1e22-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="e1e22-195">Aktiviert den Beispielprofiler.</span><span class="sxs-lookup"><span data-stu-id="e1e22-195">Enables the sample profiler.</span></span> |
