---
title: Diagnosetool „dotnet-trace“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-trace“ installieren und mithilfe der .NET-Komponente „EventPipe“ zum Erfassen von .NET-Ablaufverfolgungen in Bezug auf einen laufenden Prozesses ohne den nativen Profiler verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 93698882e94f58eda84abebc277e1eacfe22a3da
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189700"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="46b69-103">dotnet-trace-Hilfsprogramm für Leistungsanalysen</span><span class="sxs-lookup"><span data-stu-id="46b69-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="46b69-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="46b69-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="46b69-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="46b69-105">Install</span></span>

<span data-ttu-id="46b69-106">Es gibt zwei Möglichkeiten, `dotnet-trace` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="46b69-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="46b69-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="46b69-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="46b69-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="46b69-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="46b69-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="46b69-109">**Direct download:**</span></span>

  <span data-ttu-id="46b69-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="46b69-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="46b69-111">OS</span><span class="sxs-lookup"><span data-stu-id="46b69-111">OS</span></span>  | <span data-ttu-id="46b69-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="46b69-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="46b69-113">Windows</span><span class="sxs-lookup"><span data-stu-id="46b69-113">Windows</span></span> | <span data-ttu-id="46b69-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="46b69-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="46b69-115">macOS</span><span class="sxs-lookup"><span data-stu-id="46b69-115">macOS</span></span>   | [<span data-ttu-id="46b69-116">x64</span><span class="sxs-lookup"><span data-stu-id="46b69-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="46b69-117">Linux</span><span class="sxs-lookup"><span data-stu-id="46b69-117">Linux</span></span>   | <span data-ttu-id="46b69-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="46b69-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="46b69-119">Sie benötigen eine entsprechende x86-Version des Tools, um `dotnet-trace` für eine x86-App verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="46b69-119">To use `dotnet-trace` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="46b69-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b69-120">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="46b69-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46b69-121">Description</span></span>

<span data-ttu-id="46b69-122">Das `dotnet-trace`-Tool:</span><span class="sxs-lookup"><span data-stu-id="46b69-122">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="46b69-123">Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.</span><span class="sxs-lookup"><span data-stu-id="46b69-123">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="46b69-124">Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.</span><span class="sxs-lookup"><span data-stu-id="46b69-124">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="46b69-125">Es basiert auf der Komponente [`EventPipe`](./eventpipe.md) der .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="46b69-125">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="46b69-126">Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.</span><span class="sxs-lookup"><span data-stu-id="46b69-126">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="46b69-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="46b69-127">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="46b69-128">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="46b69-128">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="46b69-129">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-trace“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46b69-129">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="46b69-130">Befehle</span><span class="sxs-lookup"><span data-stu-id="46b69-130">Commands</span></span>

| <span data-ttu-id="46b69-131">Befehl</span><span class="sxs-lookup"><span data-stu-id="46b69-131">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="46b69-132">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="46b69-132">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="46b69-133">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="46b69-133">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="46b69-134">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="46b69-134">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="46b69-135">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="46b69-135">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="46b69-136">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="46b69-136">dotnet-trace collect</span></span>

<span data-ttu-id="46b69-137">Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.</span><span class="sxs-lookup"><span data-stu-id="46b69-137">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="46b69-138">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b69-138">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="46b69-139">Optionen</span><span class="sxs-lookup"><span data-stu-id="46b69-139">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="46b69-140">Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest.</span><span class="sxs-lookup"><span data-stu-id="46b69-140">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="46b69-141">Standard: 256 MB.</span><span class="sxs-lookup"><span data-stu-id="46b69-141">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="46b69-142">Ausführlichkeit von auszugebenden CLR-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="46b69-142">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="46b69-143">Diese Option generiert eine Liste der zu aktivierenden Schlüsselwörter für CLR-Anbieter, die durch `+`-Zeichen getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="46b69-143">A list of CLR runtime provider keywords to enable separated by `+` signs.</span></span> <span data-ttu-id="46b69-144">Mit dieser einfachen Zuordnung können Sie Schlüsselwörter für Ereignisse über Zeichenfolgenaliase anstelle von Hexadezimalwerten angeben.</span><span class="sxs-lookup"><span data-stu-id="46b69-144">This is a simple mapping that lets you specify event keywords via string aliases rather than their hex values.</span></span> <span data-ttu-id="46b69-145">`dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` fordert beispielsweise die gleichen Ereignisse wie `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational` an.</span><span class="sxs-lookup"><span data-stu-id="46b69-145">For example, `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` requests the same set of events as `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`.</span></span> <span data-ttu-id="46b69-146">Die folgende Tabelle ist eine Liste der verfügbaren Schlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="46b69-146">The table below shows the list of available keywords:</span></span>

  | <span data-ttu-id="46b69-147">Zeichenfolgenalias des Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="46b69-147">Keyword String Alias</span></span> | <span data-ttu-id="46b69-148">Hexadezimalwert des Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="46b69-148">Keyword Hex Value</span></span> |
  | ------------ | ------------------- |
  | `gc` | `0x1` |
  | `gchandle` | `0x2` |
  | `fusion` | `0x4` |
  | `loader` | `0x8` |
  | `jit` | `0x10` |
  | `ngen` | `0x20` |
  | `startenumeration` | `0x40` |
  | `endenumeration` | `0x80` |
  | `security` | `0x400` |
  | `appdomainresourcemanagement` | `0x800` |
  | `jittracing` | `0x1000` |
  | `interop` | `0x2000` |
  | `contention` | `0x4000` |
  | `exception` | `0x8000` |
  | `threading` | `0x10000` |
  | `jittedmethodiltonativemap` | `0x20000` |
  | `overrideandsuppressngenevents` | `0x40000` |
  | `type` | `0x80000` |
  | `gcheapdump` | `0x100000` |
  | `gcsampledobjectallocationhigh` | `0x200000` |
  | `gcheapsurvivalandmovement` | `0x400000` |
  | `gcheapcollect` | `0x800000` |
  | `gcheapandtypenames` | `0x1000000` |
  | `gcsampledobjectallocationlow` | `0x2000000` |
  | `perftrack` | `0x20000000` |
  | `stack` | `0x40000000` |
  | `threadtransfer` | `0x80000000` |
  | `debugger` | `0x100000000` |
  | `monitoring` | `0x200000000` |
  | `codesymbols` | `0x400000000` |
  | `eventsource` | `0x800000000` |
  | `compilation` | `0x1000000000` |
  | `compilationdiagnostic` | `0x2000000000` |
  | `methoddiagnostic` | `0x4000000000` |
  | `typediagnostic` | `0x8000000000` |

  <span data-ttu-id="46b69-149">Weitere Informationen zu CLR-Anbietern finden Sie in der [Referenzdokumentation zu .NET-Runtimeanbietern](../../fundamentals/diagnostics/runtime-events.md).</span><span class="sxs-lookup"><span data-stu-id="46b69-149">You can read about the CLR provider more in detail on the [.NET runtime provider reference documentation](../../fundamentals/diagnostics/runtime-events.md).</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="46b69-150">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="46b69-150">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="46b69-151">Der Standardwert ist `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="46b69-151">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="46b69-152">Der Name des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="46b69-152">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="46b69-153">Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports.</span><span class="sxs-lookup"><span data-stu-id="46b69-153">The name of the diagnostic port to create.</span></span> <span data-ttu-id="46b69-154">Informationen dazu, wie Sie diese Option zum Erfassen einer Überwachung ab dem App-Start verwenden, finden Sie unter [Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start](#use-diagnostic-port-to-collect-a-trace-from-app-startup).</span><span class="sxs-lookup"><span data-stu-id="46b69-154">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="46b69-155">Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten.</span><span class="sxs-lookup"><span data-stu-id="46b69-155">The output path for the collected trace data.</span></span> <span data-ttu-id="46b69-156">Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.</span><span class="sxs-lookup"><span data-stu-id="46b69-156">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="46b69-157">Dies ist die Prozess-ID, von der die Ablaufverfolgung erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="46b69-157">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="46b69-158">Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="46b69-158">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="46b69-159">Die folgenden Profile sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="46b69-159">The following profiles are available:</span></span>

 | <span data-ttu-id="46b69-160">Profil</span><span class="sxs-lookup"><span data-stu-id="46b69-160">Profile</span></span> | <span data-ttu-id="46b69-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46b69-161">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="46b69-162">Nützlich für die Nachverfolgung der CPU-Auslastung und allgemeine .NET-Laufzeitinformationen.</span><span class="sxs-lookup"><span data-stu-id="46b69-162">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="46b69-163">Dies ist die Standardoption, wenn kein Profil oder Anbieter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="46b69-163">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="46b69-164">Verfolgt GC-Sammlungen und Beispielobjektzuordnungen.</span><span class="sxs-lookup"><span data-stu-id="46b69-164">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="46b69-165">Verfolgt GC-Sammlungen nur mit sehr geringem Mehraufwand nach.</span><span class="sxs-lookup"><span data-stu-id="46b69-165">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="46b69-166">Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46b69-166">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="46b69-167">Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter.</span><span class="sxs-lookup"><span data-stu-id="46b69-167">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="46b69-168">Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.</span><span class="sxs-lookup"><span data-stu-id="46b69-168">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="46b69-169">Diese Liste der Anbieter hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="46b69-169">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="46b69-170">`Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="46b69-170">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="46b69-171">`KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="46b69-171">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="46b69-172">**`-- <command>` (nur für Zielanwendungen, die .NET 5.0 ausführen)**</span><span class="sxs-lookup"><span data-stu-id="46b69-172">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="46b69-173">Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten.</span><span class="sxs-lookup"><span data-stu-id="46b69-173">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="46b69-174">Das kann beim Diagnostizieren von Problemen hilfreich sein, die am Anfang des Prozesses auftreten, wie Leistungsprobleme beim Start oder Assemblylade- und Binderfehler.</span><span class="sxs-lookup"><span data-stu-id="46b69-174">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="46b69-175">Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="46b69-175">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="46b69-176">Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b69-176">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-177">Das Beenden der Überwachung dauert bei großen Anwendungen möglicherweise lang (bis zu mehrere Minuten).</span><span class="sxs-lookup"><span data-stu-id="46b69-177">Stopping the trace may take a long time (up to minutes) for large applications.</span></span> <span data-ttu-id="46b69-178">Die Runtime muss den Typcache für den gesamten verwalteten Code senden, der bei der Überwachung erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="46b69-178">The runtime needs to send over the type cache for all managed code that was captured in the trace.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-179">Unter Linux und macOS erwartet dieser Befehl, dass die Zielanwendung und `dotnet-trace` die gleiche `TMPDIR`-Umgebungsvariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b69-179">On Linux and macOS, this command expects the target application and `dotnet-trace` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="46b69-180">Andernfalls führt der Befehl zu einem Timeout.</span><span class="sxs-lookup"><span data-stu-id="46b69-180">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-181">Wenn Sie mit `dotnet-trace` eine Überwachung erfassen möchten, muss der Befehl vom Rootbenutzer oder dem Benutzer ausgeführt werden, der den Zielprozess ausführt.</span><span class="sxs-lookup"><span data-stu-id="46b69-181">To collect a trace using `dotnet-trace`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="46b69-182">Andernfalls kann das Tool keine Verbindung mit dem Zielprozess herstellen.</span><span class="sxs-lookup"><span data-stu-id="46b69-182">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="46b69-183">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="46b69-183">dotnet-trace convert</span></span>

<span data-ttu-id="46b69-184">Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="46b69-184">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="46b69-185">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b69-185">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="46b69-186">Argumente</span><span class="sxs-lookup"><span data-stu-id="46b69-186">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="46b69-187">Die zu konvertierende Eingabe-Ablaufverfolgungsdatei.</span><span class="sxs-lookup"><span data-stu-id="46b69-187">Input trace file to be converted.</span></span> <span data-ttu-id="46b69-188">Standard: *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="46b69-188">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="46b69-189">Optionen</span><span class="sxs-lookup"><span data-stu-id="46b69-189">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="46b69-190">Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.</span><span class="sxs-lookup"><span data-stu-id="46b69-190">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="46b69-191">Ausgabedateiname.</span><span class="sxs-lookup"><span data-stu-id="46b69-191">Output filename.</span></span> <span data-ttu-id="46b69-192">Die Erweiterung des Zielformats wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="46b69-192">Extension of target format will be added.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-193">Das Konvertieren von `nettrace`-Dateien in `chromium`- oder `speedscope`-Dateien kann nicht rückgängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="46b69-193">Converting `nettrace` files to `chromium` or `speedscope` files is irreversible.</span></span> <span data-ttu-id="46b69-194">`speedscope`- und `chromium`-Dateien enthalten nicht alle Informationen, die zum Rekonstruieren von `nettrace`-Dateien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="46b69-194">`speedscope` and `chromium` files don't have all the information necessary to reconstruct `nettrace` files.</span></span> <span data-ttu-id="46b69-195">Mit dem `convert`-Befehl bleibt die ursprüngliche `nettrace`-Datei jedoch erhalten. Löschen Sie daher diese Datei nicht, wenn Sie beabsichtigen, sie später irgendwann zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="46b69-195">However, the `convert` command preserves the original `nettrace` file, so don't delete this file if you plan to open it in the future.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="46b69-196">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="46b69-196">dotnet-trace ps</span></span>

 <span data-ttu-id="46b69-197">Listet die dotnet-Prozesse auf, aus denen Ablaufverfolgungen erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="46b69-197">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="46b69-198">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b69-198">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="46b69-199">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="46b69-199">dotnet-trace list-profiles</span></span>

<span data-ttu-id="46b69-200">Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.</span><span class="sxs-lookup"><span data-stu-id="46b69-200">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="46b69-201">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46b69-201">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="46b69-202">Sammeln einer Ablaufverfolgung mit dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="46b69-202">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="46b69-203">So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="46b69-203">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="46b69-204">Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="46b69-204">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="46b69-205">Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b69-205">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="46b69-206">Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="46b69-206">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="46b69-207">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="46b69-207">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="46b69-208">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="46b69-208">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="46b69-209">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="46b69-209">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="46b69-210">Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an.</span><span class="sxs-lookup"><span data-stu-id="46b69-210">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="46b69-211">`dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="46b69-211">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="46b69-212">Starten einer untergeordneten Anwendung und Erfassen einer Ablaufverfolgung vom Start mithilfe von „dotnet-trace“</span><span class="sxs-lookup"><span data-stu-id="46b69-212">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46b69-213">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="46b69-213">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="46b69-214">Manchmal kann es nützlich sein, eine Ablaufverfolgung eines Prozesses vom Start zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="46b69-214">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="46b69-215">Bei Anwendungen mit .NET 5.0 oder höher können Sie dies mithilfe von „dotnet-trace“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="46b69-215">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="46b69-216">Dadurch wird `hello.exe` mit `arg1` und `arg2` als Befehlszeilenargumenten gestartet, und der Ablauf wird vom Start der Runtime verfolgt:</span><span class="sxs-lookup"><span data-stu-id="46b69-216">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="46b69-217">Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="46b69-217">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="46b69-218">Sie können das Erfassen der Ablaufverfolgung durch Drücken der Taste `<Enter>` oder `<Ctrl + C>` abbrechen.</span><span class="sxs-lookup"><span data-stu-id="46b69-218">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="46b69-219">Dadurch wird auch `hello.exe` beendet.</span><span class="sxs-lookup"><span data-stu-id="46b69-219">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-220">Wenn `hello.exe` über „dotnet-trace“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mit stdin/stdout interagieren.</span><span class="sxs-lookup"><span data-stu-id="46b69-220">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="46b69-221">Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.</span><span class="sxs-lookup"><span data-stu-id="46b69-221">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="46b69-222">Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="46b69-222">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="46b69-223">Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start</span><span class="sxs-lookup"><span data-stu-id="46b69-223">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="46b69-224">Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="46b69-224">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="46b69-225">Der Diagnoseport ist ein neues Runtimefeature, das in .NET 5 hinzugefügt wurde und es Ihnen ermöglicht, die Ablaufverfolgung beim Start der App zu starten.</span><span class="sxs-lookup"><span data-stu-id="46b69-225">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="46b69-226">Dies können Sie mit `dotnet-trace` einrichten, indem Sie `dotnet-trace collect -- <command>` wie in den Beispielen oben oder die Option `--diagnostic-port` verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b69-226">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="46b69-227">Die Verwendung von `dotnet-trace <collect|monitor> -- <command>` zum Starten der Anwendung als untergeordneter Prozess ist die einfachste Möglichkeit, schnell mit der Überwachung ab dem Start zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="46b69-227">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="46b69-228">Wenn Sie allerdings präzisere Kontrolle über die Lebensdauer der überwachten App wünschen (z. B., damit die App nur in den ersten 10 Minuten überwacht und dann weiterhin ausgeführt wird) oder mithilfe der CLI mit der App interagieren müssen, können Sie die Option `--diagnostic-port` verwenden, um sowohl die überwachte Ziel-App als auch `dotnet-trace` zu steuern.</span><span class="sxs-lookup"><span data-stu-id="46b69-228">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="46b69-229">Der folgende Befehl sorgt dafür, dass `dotnet-trace` einen Diagnosesocket namens `myport.sock` erstellt und auf eine Verbindung wartet.</span><span class="sxs-lookup"><span data-stu-id="46b69-229">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="46b69-230">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="46b69-230">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="46b69-231">Starten Sie die Zielanwendung in einer separaten Konsole mit der Umgebungsvariable `DOTNET_DiagnosticPorts`, die Sie auf den Wert in der `dotnet-trace`-Ausgabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="46b69-231">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="46b69-232">Dadurch sollte `dotnet-trace` die Ablaufverfolgung für `my-dotnet-app` starten können:</span><span class="sxs-lookup"><span data-stu-id="46b69-232">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="46b69-233">Das Starten Ihrer App mit `dotnet run` kann sich als problematisch erweisen, da die .NET-CLI viele untergeordnete Prozesse erzeugen kann, bei denen es sich nicht um Ihre App handelt. Diese können vor Ihrer App eine Verbindung mit `dotnet-trace` herstellen, wodurch Ihre App zur Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="46b69-233">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="46b69-234">Es wird empfohlen, dass Sie direkt eine eigenständige Version der App oder `dotnet exec` verwenden, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="46b69-234">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="46b69-235">Anzeigen der von dotnet-trace erfassten Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46b69-235">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="46b69-236">Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46b69-236">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="46b69-237">Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird.</span><span class="sxs-lookup"><span data-stu-id="46b69-237">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="46b69-238">Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="46b69-238">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="46b69-239">Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen.</span><span class="sxs-lookup"><span data-stu-id="46b69-239">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="46b69-240">`Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="46b69-240">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="46b69-241">Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format.</span><span class="sxs-lookup"><span data-stu-id="46b69-241">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="46b69-242">Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="46b69-242">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="46b69-243">Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="46b69-243">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="46b69-244">Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit</span><span class="sxs-lookup"><span data-stu-id="46b69-244">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="46b69-245">`dotnet-trace` kann:</span><span class="sxs-lookup"><span data-stu-id="46b69-245">`dotnet-trace` can:</span></span>

* <span data-ttu-id="46b69-246">`EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="46b69-246">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="46b69-247">Beispielsweise in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="46b69-247">For example, in production.</span></span>
* <span data-ttu-id="46b69-248">Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="46b69-248">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="46b69-249">Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="46b69-249">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="46b69-250">Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="46b69-250">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="46b69-251">Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.</span><span class="sxs-lookup"><span data-stu-id="46b69-251">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="46b69-252">Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:</span><span class="sxs-lookup"><span data-stu-id="46b69-252">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="46b69-253">Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.</span><span class="sxs-lookup"><span data-stu-id="46b69-253">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a><span data-ttu-id="46b69-254">Vermeiden der Eingabe langer Befehle mithilfe der .rsp-Datei</span><span class="sxs-lookup"><span data-stu-id="46b69-254">Use .rsp file to avoid typing long commands</span></span>

<span data-ttu-id="46b69-255">Sie können `dotnet-trace` mit einer `.rsp`-Datei starten, die die zu übergebenden Argumente enthält.</span><span class="sxs-lookup"><span data-stu-id="46b69-255">You can launch `dotnet-trace` with an `.rsp` file that contains the arguments to pass.</span></span> <span data-ttu-id="46b69-256">Dies kann hilfreich sein, wenn Sie Anbieter aktivieren, die lange Argumente erwarten, oder wenn Sie eine Shellumgebung verwenden, die Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="46b69-256">This can be useful when enabling providers that expect lengthy arguments or when using a shell environment that strips characters.</span></span>

<span data-ttu-id="46b69-257">Es kann z. B. mühsam sein, den folgenden Anbieter bei jeder gewünschten Überwachung komplett tippen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="46b69-257">For example, the following provider can be cumbersome to type out each time you want to trace:</span></span>

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="46b69-258">Darüber hinaus enthält das Argument im vorherigen Beispiel `"`.</span><span class="sxs-lookup"><span data-stu-id="46b69-258">In addition, the previous example contains `"` as part of the argument.</span></span> <span data-ttu-id="46b69-259">Da Anführungszeichen nicht von jeder Shell gleich behandelt werden, können bei der Verwendung unterschiedlicher Shells verschiedene Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="46b69-259">Because quotes are not handled equally by each shell, you may experience various issues when using different shells.</span></span> <span data-ttu-id="46b69-260">Beispielsweise unterscheidet sich der Befehl, der in `zsh` eingegeben werden muss, von dem in `cmd`.</span><span class="sxs-lookup"><span data-stu-id="46b69-260">For example, the command to enter in `zsh` is different to the command in `cmd`.</span></span>

<span data-ttu-id="46b69-261">Statt den Befehl jedes Mal zu tippen, können Sie den folgenden Text in einer Datei mit dem Namen `myprofile.rsp` speichern.</span><span class="sxs-lookup"><span data-stu-id="46b69-261">Instead of typing this each time, you can save the following text into a file called `myprofile.rsp`.</span></span>

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="46b69-262">Wenn Sie `myprofile.rsp` gespeichert haben, können Sie `dotnet-trace` mit dieser Konfiguration über den folgenden Befehl öffnen:</span><span class="sxs-lookup"><span data-stu-id="46b69-262">Once you've saved `myprofile.rsp`, you can launch `dotnet-trace` with this configuration using the following command:</span></span>

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a><span data-ttu-id="46b69-263">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46b69-263">See also</span></span>

- [<span data-ttu-id="46b69-264">Bekannte Ereignisanbieter in .NET</span><span class="sxs-lookup"><span data-stu-id="46b69-264">Well-known event providers from .NET</span></span>](well-known-event-providers.md)
