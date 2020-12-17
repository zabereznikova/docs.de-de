---
title: Diagnosetool „dotnet-trace“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-trace“ installieren und mithilfe der .NET-Komponente „EventPipe“ zum Erfassen von .NET-Ablaufverfolgungen in Bezug auf einen laufenden Prozesses ohne den nativen Profiler verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 868ce7828eee6bd7f2101d5d6a65c7f7bf87fe24
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009533"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="b1b8d-103">dotnet-trace-Hilfsprogramm für Leistungsanalysen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="b1b8d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="b1b8d-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="b1b8d-105">Install</span></span>

<span data-ttu-id="b1b8d-106">Es gibt zwei Möglichkeiten, `dotnet-trace` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="b1b8d-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="b1b8d-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="b1b8d-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="b1b8d-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="b1b8d-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="b1b8d-109">**Direct download:**</span></span>

  <span data-ttu-id="b1b8d-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="b1b8d-111">OS</span><span class="sxs-lookup"><span data-stu-id="b1b8d-111">OS</span></span>  | <span data-ttu-id="b1b8d-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="b1b8d-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="b1b8d-113">Windows</span><span class="sxs-lookup"><span data-stu-id="b1b8d-113">Windows</span></span> | <span data-ttu-id="b1b8d-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="b1b8d-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="b1b8d-115">macOS</span><span class="sxs-lookup"><span data-stu-id="b1b8d-115">macOS</span></span>   | [<span data-ttu-id="b1b8d-116">x64</span><span class="sxs-lookup"><span data-stu-id="b1b8d-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="b1b8d-117">Linux</span><span class="sxs-lookup"><span data-stu-id="b1b8d-117">Linux</span></span>   | <span data-ttu-id="b1b8d-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="b1b8d-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="b1b8d-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1b8d-119">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="b1b8d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1b8d-120">Description</span></span>

<span data-ttu-id="b1b8d-121">Das `dotnet-trace`-Tool:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-121">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="b1b8d-122">Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-122">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="b1b8d-123">Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-123">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="b1b8d-124">Es basiert auf der Komponente [`EventPipe`](./eventpipe.md) der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-124">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="b1b8d-125">Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-125">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="b1b8d-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="b1b8d-127">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-127">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="b1b8d-128">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-trace“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-128">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="b1b8d-129">Befehle</span><span class="sxs-lookup"><span data-stu-id="b1b8d-129">Commands</span></span>

| <span data-ttu-id="b1b8d-130">Befehl</span><span class="sxs-lookup"><span data-stu-id="b1b8d-130">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="b1b8d-131">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="b1b8d-131">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="b1b8d-132">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="b1b8d-132">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="b1b8d-133">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="b1b8d-133">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="b1b8d-134">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="b1b8d-134">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="b1b8d-135">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="b1b8d-135">dotnet-trace collect</span></span>

<span data-ttu-id="b1b8d-136">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-136">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1b8d-137">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1b8d-137">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="b1b8d-138">Optionen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-138">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="b1b8d-139">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-139">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="b1b8d-140">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-140">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="b1b8d-141">Ausführlichkeit von auszugebenden CLR-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-141">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="b1b8d-142">Liste der auszugebenden CLR-Laufzeitergebnisse.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-142">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="b1b8d-143">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-143">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="b1b8d-144">Der Standardwert ist `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-144">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="b1b8d-145">Der Name des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-145">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="b1b8d-146">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-146">The name of the diagnostic port to create.</span></span> <span data-ttu-id="b1b8d-147">Informationen dazu, wie Sie diese Option zum Erfassen einer Überwachung ab dem App-Start verwenden, finden Sie unter [Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start](#use-diagnostic-port-to-collect-a-trace-from-app-startup).</span><span class="sxs-lookup"><span data-stu-id="b1b8d-147">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="b1b8d-148">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-148">The output path for the collected trace data.</span></span> <span data-ttu-id="b1b8d-149">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-149">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="b1b8d-150">Dies ist die Prozess-ID, von der die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-150">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="b1b8d-151">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-151">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="b1b8d-152">Die folgenden Profile sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-152">The following profiles are available:</span></span>

 | <span data-ttu-id="b1b8d-153">Profil</span><span class="sxs-lookup"><span data-stu-id="b1b8d-153">Profile</span></span> | <span data-ttu-id="b1b8d-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1b8d-154">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="b1b8d-155">Nützlich für die Nachverfolgung der CPU-Auslastung und allgemeine .NET-Laufzeitinformationen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-155">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="b1b8d-156">Dies ist die Standardoption, wenn kein Profil oder Anbieter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-156">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="b1b8d-157">Verfolgt GC-Sammlungen und Beispielobjektzuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-157">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="b1b8d-158">Verfolgt GC-Sammlungen nur mit sehr geringem Mehraufwand nach.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-158">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="b1b8d-159">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-159">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="b1b8d-160">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-160">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="b1b8d-161">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-161">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="b1b8d-162">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-162">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="b1b8d-163">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-163">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="b1b8d-164">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-164">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="b1b8d-165">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 ausführen)**</span><span class="sxs-lookup"><span data-stu-id="b1b8d-165">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="b1b8d-166">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-166">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="b1b8d-167">Das kann beim Diagnostizieren von Problemen hilfreich sein, die am Anfang des Prozesses auftreten, wie Leistungsprobleme beim Start oder Assemblylade- und Binderfehler.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-167">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b1b8d-168">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-168">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="b1b8d-169">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-169">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="b1b8d-170">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="b1b8d-170">dotnet-trace convert</span></span>

<span data-ttu-id="b1b8d-171">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-171">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1b8d-172">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1b8d-172">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="b1b8d-173">Argumente</span><span class="sxs-lookup"><span data-stu-id="b1b8d-173">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="b1b8d-174">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-174">Input trace file to be converted.</span></span> <span data-ttu-id="b1b8d-175">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-175">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="b1b8d-176">Optionen</span><span class="sxs-lookup"><span data-stu-id="b1b8d-176">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="b1b8d-177">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-177">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="b1b8d-178">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-178">Output filename.</span></span> <span data-ttu-id="b1b8d-179">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-179">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="b1b8d-180">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="b1b8d-180">dotnet-trace ps</span></span>

 <span data-ttu-id="b1b8d-181">Listet die dotnet-Prozesse auf, aus denen Ablaufverfolgungen erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-181">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1b8d-182">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1b8d-182">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="b1b8d-183">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="b1b8d-183">dotnet-trace list-profiles</span></span>

<span data-ttu-id="b1b8d-184">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-184">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b1b8d-185">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b1b8d-185">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="b1b8d-186">Sammeln einer Ablaufverfolgung mit dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="b1b8d-186">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="b1b8d-187">So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-187">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="b1b8d-188">Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-188">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="b1b8d-189">Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-189">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="b1b8d-190">Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-190">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="b1b8d-191">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="b1b8d-191">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="b1b8d-192">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-192">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="b1b8d-193">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-193">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="b1b8d-194">Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-194">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="b1b8d-195">`dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-195">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="b1b8d-196">Starten einer untergeordneten Anwendung und Erfassen einer Ablaufverfolgung vom Start mithilfe von „dotnet-trace“</span><span class="sxs-lookup"><span data-stu-id="b1b8d-196">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1b8d-197">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-197">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="b1b8d-198">Manchmal kann es nützlich sein, eine Ablaufverfolgung eines Prozesses vom Start zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-198">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="b1b8d-199">Bei Anwendungen mit .NET 5.0 oder höher können Sie dies mithilfe von „dotnet-trace“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-199">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="b1b8d-200">Dadurch wird `hello.exe` mit `arg1` und `arg2` als Befehlszeilenargumenten gestartet, und der Ablauf wird vom Start der Runtime verfolgt:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-200">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="b1b8d-201">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-201">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="b1b8d-202">Sie können das Erfassen der Ablaufverfolgung durch Drücken der Taste `<Enter>` oder `<Ctrl + C>` abbrechen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-202">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="b1b8d-203">Dadurch wird auch `hello.exe` beendet.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-203">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b8d-204">Wenn `hello.exe` über „dotnet-trace“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mit stdin/stdout interagieren.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-204">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="b1b8d-205">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-205">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="b1b8d-206">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-206">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="b1b8d-207">Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start</span><span class="sxs-lookup"><span data-stu-id="b1b8d-207">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b1b8d-208">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-208">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="b1b8d-209">Der Diagnoseport ist ein neues Runtimefeature, das in .NET 5 hinzugefügt wurde und es Ihnen ermöglicht, die Ablaufverfolgung beim Start der App zu starten.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-209">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="b1b8d-210">Dies können Sie mit `dotnet-trace` einrichten, indem Sie `dotnet-trace collect -- <command>` wie in den Beispielen oben oder die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-210">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="b1b8d-211">Die Verwendung von `dotnet-trace <collect|monitor> -- <command>` zum Starten der Anwendung als untergeordneter Prozess ist die einfachste Möglichkeit, schnell mit der Überwachung ab dem Start zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-211">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="b1b8d-212">Wenn Sie allerdings präzisere Kontrolle über die Lebensdauer der überwachten App wünschen (z. B., damit die App nur in den ersten 10 Minuten überwacht und dann weiterhin ausgeführt wird) oder mithilfe der CLI mit der App interagieren müssen, können Sie die Option `--diagnostic-port` verwenden, um sowohl die überwachte Ziel-App als auch `dotnet-trace` zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-212">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="b1b8d-213">Der folgende Befehl sorgt dafür, dass `dotnet-trace` einen Diagnosesocket namens `myport.sock` erstellt und auf eine Verbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-213">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="b1b8d-214">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-214">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="b1b8d-215">Starten Sie die Zielanwendung in einer separaten Konsole mit der Umgebungsvariable `DOTNET_DiagnosticPorts`, die Sie auf den Wert in der `dotnet-trace`-Ausgabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-215">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="b1b8d-216">Dadurch sollte `dotnet-trace` die Ablaufverfolgung für `my-dotnet-app` starten können:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-216">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="b1b8d-217">Das Starten Ihrer App mit `dotnet run` kann sich als problematisch erweisen, da die .NET-CLI viele untergeordnete Prozesse erzeugen kann, bei denen es sich nicht um Ihre App handelt. Diese können vor Ihrer App eine Verbindung mit `dotnet-trace` herstellen, wodurch Ihre App zur Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-217">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="b1b8d-218">Es wird empfohlen, dass Sie direkt eine eigenständige Version der App oder `dotnet exec` verwenden, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-218">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="b1b8d-219">Anzeigen der von dotnet-trace erfassten Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b1b8d-219">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="b1b8d-220">Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-220">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="b1b8d-221">Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-221">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="b1b8d-222">Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-222">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="b1b8d-223">Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-223">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="b1b8d-224">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-224">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b8d-225">Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-225">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="b1b8d-226">Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-226">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="b1b8d-227">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-227">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="b1b8d-228">Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="b1b8d-228">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="b1b8d-229">`dotnet-trace` kann:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-229">`dotnet-trace` can:</span></span>

* <span data-ttu-id="b1b8d-230">`EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-230">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="b1b8d-231">Beispielsweise in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-231">For example, in production.</span></span>
* <span data-ttu-id="b1b8d-232">Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-232">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="b1b8d-233">Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-233">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="b1b8d-234">Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-234">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="b1b8d-235">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-235">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="b1b8d-236">Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:</span><span class="sxs-lookup"><span data-stu-id="b1b8d-236">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="b1b8d-237">Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-237">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="b1b8d-238">.NET-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b1b8d-238">.NET Providers</span></span>

<span data-ttu-id="b1b8d-239">Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-239">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="b1b8d-240">.NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-240">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="b1b8d-241">Anbietername</span><span class="sxs-lookup"><span data-stu-id="b1b8d-241">Provider name</span></span>                            | <span data-ttu-id="b1b8d-242">Information</span><span class="sxs-lookup"><span data-stu-id="b1b8d-242">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="b1b8d-243">Runtimeanbieter</span><span class="sxs-lookup"><span data-stu-id="b1b8d-243">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="b1b8d-244">CLR-Runtime-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b1b8d-244">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="b1b8d-245">Rundownanbieter</span><span class="sxs-lookup"><span data-stu-id="b1b8d-245">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="b1b8d-246">CLR-Rundown-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b1b8d-246">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="b1b8d-247">Aktiviert den Beispielprofiler.</span><span class="sxs-lookup"><span data-stu-id="b1b8d-247">Enables the sample profiler.</span></span> |
