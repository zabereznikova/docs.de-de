---
title: Das Tool „dotnet-trace“ – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 25178a0e59ce9edb69d15ee761c1b9e56aa5eb3a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517307"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="d2f80-103">dotnet-trace-Hilfsprogramm für Leistungsanalysen</span><span class="sxs-lookup"><span data-stu-id="d2f80-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="d2f80-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d2f80-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="d2f80-105">Installieren von dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d2f80-105">Install dotnet-trace</span></span>

<span data-ttu-id="d2f80-106">Installieren Sie das [NuGet-Paket](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` mit dem Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="d2f80-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="d2f80-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2f80-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="d2f80-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2f80-108">Description</span></span>

<span data-ttu-id="d2f80-109">Das `dotnet-trace`-Tool:</span><span class="sxs-lookup"><span data-stu-id="d2f80-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="d2f80-110">Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="d2f80-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="d2f80-111">Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="d2f80-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="d2f80-112">Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="d2f80-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="d2f80-113">Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="d2f80-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="d2f80-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="d2f80-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d2f80-115">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="d2f80-115">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="d2f80-116">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-trace“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2f80-116">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="d2f80-117">Befehle</span><span class="sxs-lookup"><span data-stu-id="d2f80-117">Commands</span></span>

| <span data-ttu-id="d2f80-118">Befehl</span><span class="sxs-lookup"><span data-stu-id="d2f80-118">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="d2f80-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="d2f80-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="d2f80-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="d2f80-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="d2f80-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d2f80-121">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="d2f80-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="d2f80-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="d2f80-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="d2f80-123">dotnet-trace collect</span></span>

<span data-ttu-id="d2f80-124">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="d2f80-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2f80-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2f80-125">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
```

### <a name="options"></a><span data-ttu-id="d2f80-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="d2f80-126">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="d2f80-127">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="d2f80-127">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="d2f80-128">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="d2f80-128">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="d2f80-129">Ausführlichkeit von auszugebenden CLR-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-129">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="d2f80-130">Liste der auszugebenden CLR-Laufzeitergebnisse.</span><span class="sxs-lookup"><span data-stu-id="d2f80-130">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="d2f80-131">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="d2f80-131">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="d2f80-132">Der Standardwert ist `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="d2f80-132">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="d2f80-133">Der Name des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2f80-133">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="d2f80-134">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="d2f80-134">The output path for the collected trace data.</span></span> <span data-ttu-id="d2f80-135">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2f80-135">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="d2f80-136">Die ID des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2f80-136">The process id to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="d2f80-137">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d2f80-137">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="d2f80-138">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-138">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="d2f80-139">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="d2f80-139">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="d2f80-140">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="d2f80-140">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="d2f80-141">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="d2f80-141">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="d2f80-142">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="d2f80-142">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="d2f80-143">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="d2f80-143">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="d2f80-144">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="d2f80-144">dotnet-trace convert</span></span>

<span data-ttu-id="d2f80-145">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="d2f80-145">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2f80-146">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2f80-146">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="d2f80-147">Argumente</span><span class="sxs-lookup"><span data-stu-id="d2f80-147">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="d2f80-148">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="d2f80-148">Input trace file to be converted.</span></span> <span data-ttu-id="d2f80-149">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="d2f80-149">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="d2f80-150">Optionen</span><span class="sxs-lookup"><span data-stu-id="d2f80-150">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="d2f80-151">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="d2f80-151">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="d2f80-152">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="d2f80-152">Output filename.</span></span> <span data-ttu-id="d2f80-153">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2f80-153">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="d2f80-154">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d2f80-154">dotnet-trace ps</span></span>

 <span data-ttu-id="d2f80-155">Listet die dotnet-Prozesse auf, aus denen Ablaufverfolgungen erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="d2f80-155">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2f80-156">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2f80-156">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="d2f80-157">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="d2f80-157">dotnet-trace list-profiles</span></span>

<span data-ttu-id="d2f80-158">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="d2f80-158">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d2f80-159">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d2f80-159">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="d2f80-160">Sammeln einer Ablaufverfolgung mit dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d2f80-160">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="d2f80-161">So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="d2f80-161">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="d2f80-162">Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-162">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="d2f80-163">Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2f80-163">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="d2f80-164">Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="d2f80-164">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="d2f80-165">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d2f80-165">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="d2f80-166">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d2f80-166">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="d2f80-167">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="d2f80-167">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="d2f80-168">Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an.</span><span class="sxs-lookup"><span data-stu-id="d2f80-168">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="d2f80-169">`dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="d2f80-169">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="d2f80-170">Anzeigen der von dotnet-trace erfassten Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d2f80-170">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="d2f80-171">Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-171">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="d2f80-172">Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d2f80-172">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="d2f80-173">Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="d2f80-173">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="d2f80-174">Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-174">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="d2f80-175">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="d2f80-175">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="d2f80-176">Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format.</span><span class="sxs-lookup"><span data-stu-id="d2f80-176">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="d2f80-177">Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d2f80-177">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="d2f80-178">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d2f80-178">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="d2f80-179">Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="d2f80-179">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="d2f80-180">`dotnet-trace` kann:</span><span class="sxs-lookup"><span data-stu-id="d2f80-180">`dotnet-trace` can:</span></span>

* <span data-ttu-id="d2f80-181">`EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2f80-181">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="d2f80-182">Beispielsweise in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="d2f80-182">For example, in production.</span></span>
* <span data-ttu-id="d2f80-183">Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d2f80-183">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="d2f80-184">Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="d2f80-184">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="d2f80-185">Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="d2f80-185">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="d2f80-186">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="d2f80-186">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="d2f80-187">Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:</span><span class="sxs-lookup"><span data-stu-id="d2f80-187">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="d2f80-188">Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.</span><span class="sxs-lookup"><span data-stu-id="d2f80-188">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="d2f80-189">.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d2f80-189">.NET Providers</span></span>

<span data-ttu-id="d2f80-190">Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="d2f80-190">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="d2f80-191">.NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="d2f80-191">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="d2f80-192">Anbietername</span><span class="sxs-lookup"><span data-stu-id="d2f80-192">Provider name</span></span>                            | <span data-ttu-id="d2f80-193">Information</span><span class="sxs-lookup"><span data-stu-id="d2f80-193">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="d2f80-194">Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="d2f80-194">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="d2f80-195">CLR-Runtime-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d2f80-195">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="d2f80-196">Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="d2f80-196">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="d2f80-197">CLR-Rundown-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d2f80-197">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="d2f80-198">Aktiviert den Beispielprofiler.</span><span class="sxs-lookup"><span data-stu-id="d2f80-198">Enables the sample profiler.</span></span> |
