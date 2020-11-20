---
title: Das Tool „dotnet-trace“ – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: d4175ccad785b21f860044a4fd5d691624ec495e
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507227"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="ff86c-103">dotnet-trace-Hilfsprogramm für Leistungsanalysen</span><span class="sxs-lookup"><span data-stu-id="ff86c-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="ff86c-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="ff86c-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="ff86c-105">Installieren von dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="ff86c-105">Install dotnet-trace</span></span>

<span data-ttu-id="ff86c-106">Installieren Sie das [NuGet-Paket](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` mit dem Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="ff86c-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="ff86c-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff86c-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="ff86c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff86c-108">Description</span></span>

<span data-ttu-id="ff86c-109">Das `dotnet-trace`-Tool:</span><span class="sxs-lookup"><span data-stu-id="ff86c-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="ff86c-110">Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="ff86c-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="ff86c-111">Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="ff86c-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="ff86c-112">Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="ff86c-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="ff86c-113">Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="ff86c-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="ff86c-114">Optionen</span><span class="sxs-lookup"><span data-stu-id="ff86c-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="ff86c-115">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="ff86c-115">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="ff86c-116">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-trace“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff86c-116">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="ff86c-117">Befehle</span><span class="sxs-lookup"><span data-stu-id="ff86c-117">Commands</span></span>

| <span data-ttu-id="ff86c-118">Befehl</span><span class="sxs-lookup"><span data-stu-id="ff86c-118">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="ff86c-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="ff86c-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="ff86c-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="ff86c-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="ff86c-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="ff86c-121">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="ff86c-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="ff86c-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="ff86c-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="ff86c-123">dotnet-trace collect</span></span>

<span data-ttu-id="ff86c-124">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="ff86c-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ff86c-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff86c-125">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="ff86c-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="ff86c-126">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="ff86c-127">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="ff86c-127">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="ff86c-128">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="ff86c-128">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="ff86c-129">Ausführlichkeit von auszugebenden CLR-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-129">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="ff86c-130">Liste der auszugebenden CLR-Laufzeitergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ff86c-130">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="ff86c-131">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="ff86c-131">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="ff86c-132">Der Standardwert ist `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="ff86c-132">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="ff86c-133">Der Name des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff86c-133">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="ff86c-134">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="ff86c-134">The output path for the collected trace data.</span></span> <span data-ttu-id="ff86c-135">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff86c-135">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="ff86c-136">Die ID des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff86c-136">The process id to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="ff86c-137">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="ff86c-137">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="ff86c-138">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-138">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="ff86c-139">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="ff86c-139">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="ff86c-140">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="ff86c-140">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="ff86c-141">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="ff86c-141">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="ff86c-142">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="ff86c-142">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="ff86c-143">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="ff86c-143">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="ff86c-144">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 ausführen)**</span><span class="sxs-lookup"><span data-stu-id="ff86c-144">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="ff86c-145">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="ff86c-145">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="ff86c-146">Das kann beim Diagnostizieren von Problemen hilfreich sein, die am Anfang des Prozesses auftreten, wie Leistungsprobleme beim Start oder Assemblylade- und Binderfehler.</span><span class="sxs-lookup"><span data-stu-id="ff86c-146">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ff86c-147">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ff86c-147">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="ff86c-148">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff86c-148">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="ff86c-149">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="ff86c-149">dotnet-trace convert</span></span>

<span data-ttu-id="ff86c-150">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="ff86c-150">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ff86c-151">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff86c-151">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="ff86c-152">Argumente</span><span class="sxs-lookup"><span data-stu-id="ff86c-152">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="ff86c-153">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="ff86c-153">Input trace file to be converted.</span></span> <span data-ttu-id="ff86c-154">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="ff86c-154">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="ff86c-155">Optionen</span><span class="sxs-lookup"><span data-stu-id="ff86c-155">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="ff86c-156">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="ff86c-156">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="ff86c-157">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="ff86c-157">Output filename.</span></span> <span data-ttu-id="ff86c-158">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ff86c-158">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="ff86c-159">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="ff86c-159">dotnet-trace ps</span></span>

 <span data-ttu-id="ff86c-160">Listet die dotnet-Prozesse auf, aus denen Ablaufverfolgungen erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="ff86c-160">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ff86c-161">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff86c-161">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="ff86c-162">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="ff86c-162">dotnet-trace list-profiles</span></span>

<span data-ttu-id="ff86c-163">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="ff86c-163">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="ff86c-164">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ff86c-164">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="ff86c-165">Sammeln einer Ablaufverfolgung mit dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="ff86c-165">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="ff86c-166">So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="ff86c-166">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="ff86c-167">Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-167">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="ff86c-168">Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff86c-168">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="ff86c-169">Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="ff86c-169">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="ff86c-170">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="ff86c-170">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="ff86c-171">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ff86c-171">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="ff86c-172">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff86c-172">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="ff86c-173">Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an.</span><span class="sxs-lookup"><span data-stu-id="ff86c-173">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="ff86c-174">`dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="ff86c-174">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="ff86c-175">Starten einer untergeordneten Anwendung und Erfassen einer Ablaufverfolgung vom Start mithilfe von „dotnet-trace“</span><span class="sxs-lookup"><span data-stu-id="ff86c-175">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

<span data-ttu-id="ff86c-176">HINWEIS: Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ff86c-176">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="ff86c-177">Manchmal kann es nützlich sein, eine Ablaufverfolgung eines Prozesses vom Start zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-177">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="ff86c-178">Bei Anwendungen mit .NET 5.0 oder höher können Sie dies mithilfe von „dotnet-trace“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-178">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="ff86c-179">Dadurch wird `hello.exe` mit `arg1` und `arg2` als Befehlszeilenargumente gestartet und der Ablauf wird vom Start der Runtime verfolgt:</span><span class="sxs-lookup"><span data-stu-id="ff86c-179">This will launch `hello.exe` with `arg1` and `arg2` as its command line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="ff86c-180">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff86c-180">The preceding command generates output similar to the following:</span></span>

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

<span data-ttu-id="ff86c-181">Sie können das Erfassen der Ablaufverfolgung durch Drücken der Taste `<Enter>` oder `<Ctrl + C>` abbrechen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-181">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="ff86c-182">Dadurch wird auch `hello.exe` beendet.</span><span class="sxs-lookup"><span data-stu-id="ff86c-182">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="ff86c-183">Wenn `hello.exe` über „dotnet-trace“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mit stdin/stdout interagieren.</span><span class="sxs-lookup"><span data-stu-id="ff86c-183">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="ff86c-184">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="ff86c-184">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="ff86c-185">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="ff86c-185">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="ff86c-186">Anzeigen der von dotnet-trace erfassten Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ff86c-186">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="ff86c-187">Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-187">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="ff86c-188">Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ff86c-188">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="ff86c-189">Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="ff86c-189">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="ff86c-190">Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-190">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="ff86c-191">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff86c-191">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="ff86c-192">Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format.</span><span class="sxs-lookup"><span data-stu-id="ff86c-192">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="ff86c-193">Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ff86c-193">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="ff86c-194">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ff86c-194">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="ff86c-195">Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="ff86c-195">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="ff86c-196">`dotnet-trace` kann:</span><span class="sxs-lookup"><span data-stu-id="ff86c-196">`dotnet-trace` can:</span></span>

* <span data-ttu-id="ff86c-197">`EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff86c-197">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="ff86c-198">Beispielsweise in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="ff86c-198">For example, in production.</span></span>
* <span data-ttu-id="ff86c-199">Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ff86c-199">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="ff86c-200">Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ff86c-200">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="ff86c-201">Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="ff86c-201">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="ff86c-202">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="ff86c-202">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="ff86c-203">Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:</span><span class="sxs-lookup"><span data-stu-id="ff86c-203">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="ff86c-204">Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.</span><span class="sxs-lookup"><span data-stu-id="ff86c-204">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="ff86c-205">.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ff86c-205">.NET Providers</span></span>

<span data-ttu-id="ff86c-206">Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="ff86c-206">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="ff86c-207">.NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="ff86c-207">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="ff86c-208">Anbietername</span><span class="sxs-lookup"><span data-stu-id="ff86c-208">Provider name</span></span>                            | <span data-ttu-id="ff86c-209">Information</span><span class="sxs-lookup"><span data-stu-id="ff86c-209">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="ff86c-210">Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="ff86c-210">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="ff86c-211">CLR-Runtime-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ff86c-211">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="ff86c-212">Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="ff86c-212">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="ff86c-213">CLR-Rundown-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ff86c-213">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="ff86c-214">Aktiviert den Beispielprofiler.</span><span class="sxs-lookup"><span data-stu-id="ff86c-214">Enables the sample profiler.</span></span> |
