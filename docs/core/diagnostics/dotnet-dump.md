---
title: Diagnosetool „dotnet-dump“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-dump“ installieren und zum Erfassen und Analysieren von Windows- und Linux-Speicherabbildern ohne nativen Debugger verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 84b3796f4ee92880e6d432df606a6addfd2471b0
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189803"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="c2351-103">Hilfsprogramm zum Sammeln und Analysieren von Speicherabbildern (dotnet-dump)</span><span class="sxs-lookup"><span data-stu-id="c2351-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="c2351-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c2351-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="c2351-105">`dotnet-dump` für macOS wird nur mit .NET 5.0 und höheren Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c2351-105">`dotnet-dump` for macOS is only supported with .NET 5.0 and later versions.</span></span>

## <a name="install"></a><span data-ttu-id="c2351-106">Installieren</span><span class="sxs-lookup"><span data-stu-id="c2351-106">Install</span></span>

<span data-ttu-id="c2351-107">Es gibt zwei Möglichkeiten, `dotnet-dump` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="c2351-107">There are two ways to download and install `dotnet-dump`:</span></span>

- <span data-ttu-id="c2351-108">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="c2351-108">**dotnet global tool:**</span></span>

  <span data-ttu-id="c2351-109">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-dump) `dotnet-dump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="c2351-109">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- <span data-ttu-id="c2351-110">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="c2351-110">**Direct download:**</span></span>

  <span data-ttu-id="c2351-111">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="c2351-111">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="c2351-112">OS</span><span class="sxs-lookup"><span data-stu-id="c2351-112">OS</span></span>  | <span data-ttu-id="c2351-113">Plattform</span><span class="sxs-lookup"><span data-stu-id="c2351-113">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="c2351-114">Windows</span><span class="sxs-lookup"><span data-stu-id="c2351-114">Windows</span></span> | <span data-ttu-id="c2351-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="c2351-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span></span> |
  | <span data-ttu-id="c2351-116">macOS</span><span class="sxs-lookup"><span data-stu-id="c2351-116">macOS</span></span>   | [<span data-ttu-id="c2351-117">x64</span><span class="sxs-lookup"><span data-stu-id="c2351-117">x64</span></span>](https://aka.ms/dotnet-dump/osx-x64) |
  | <span data-ttu-id="c2351-118">Linux</span><span class="sxs-lookup"><span data-stu-id="c2351-118">Linux</span></span>   | <span data-ttu-id="c2351-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="c2351-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="c2351-120">Sie benötigen eine entsprechende x86-Version des Tools, um `dotnet-dump` für eine x86-App verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="c2351-120">To use `dotnet-dump` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c2351-121">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2351-121">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="c2351-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2351-122">Description</span></span>

<span data-ttu-id="c2351-123">Mit dem globalen Tool `dotnet-dump` können Sie Windows- und Linux-Speicherabbilder ohne nativen Debugger wie `lldb` unter Linux sammeln und analysieren.</span><span class="sxs-lookup"><span data-stu-id="c2351-123">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="c2351-124">Dieses Tool ist auf Plattformen wie z. B. Alpine Linux wichtig, bei denen kein voll funktionsfähiges Tool `lldb` verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c2351-124">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="c2351-125">Mit dem Tool `dotnet-dump` können Sie SOS-Befehle zum Analysieren von Abstürzen und dem Garbage Collector (GC) ausführen, es handelt sich jedoch nicht um einen nativen Debugger, sodass Elemente wie das Anzeigen von nativen Stapelrahmen nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c2351-125">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="c2351-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2351-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="c2351-127">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-dump“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2351-127">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2351-128">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="c2351-128">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="c2351-129">Befehle</span><span class="sxs-lookup"><span data-stu-id="c2351-129">Commands</span></span>

| <span data-ttu-id="c2351-130">Befehl</span><span class="sxs-lookup"><span data-stu-id="c2351-130">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="c2351-131">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="c2351-131">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="c2351-132">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="c2351-132">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="c2351-133">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="c2351-133">dotnet-dump collect</span></span>

<span data-ttu-id="c2351-134">Erfasst ein Speicherabbild von einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="c2351-134">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c2351-135">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2351-135">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="c2351-136">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2351-136">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2351-137">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="c2351-137">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="c2351-138">Hiermit wird die ID-Nummer des Prozesses angegeben, von dem ein Speicherabbild gesammelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2351-138">Specifies the process ID number to collect a dump from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="c2351-139">Hiermit wird der Name des Prozesses angegeben, von dem ein Speicherabbild gesammelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2351-139">Specifies the name of the process to collect a dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="c2351-140">Gibt den Speicherabbildtyp an, der festlegt, welche Arten von Informationen vom Prozess gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="c2351-140">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="c2351-141">Es gibt drei Typen:</span><span class="sxs-lookup"><span data-stu-id="c2351-141">There are three types:</span></span>

  - <span data-ttu-id="c2351-142">`Full`: Das größte Speicherabbild, das den gesamten Arbeitsspeicher einschließlich der Modulimages enthält</span><span class="sxs-lookup"><span data-stu-id="c2351-142">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="c2351-143">`Heap`: eine große und relativ umfassende Sicherung, die Modullisten, Threadlisten, alle Stapel, Ausnahmeinformationen, Handleinformationen und den gesamten Arbeitsspeicher mit Ausnahme von zugeordneten Images enthält.</span><span class="sxs-lookup"><span data-stu-id="c2351-143">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="c2351-144">`Mini`: eine kleine Sicherung, die Modullisten, Threadlisten, Ausnahmeinformationen und alle Stapel enthält.</span><span class="sxs-lookup"><span data-stu-id="c2351-144">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="c2351-145">Wenn nichts anderes angegeben wird, wird als Standard `Full` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2351-145">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="c2351-146">Der vollständige Pfad und der Dateiname, in den das gesammelte Speicherabbild geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2351-146">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="c2351-147">Wenn nichts angegeben wird, gilt:</span><span class="sxs-lookup"><span data-stu-id="c2351-147">If not specified:</span></span>

  - <span data-ttu-id="c2351-148">Unter Windows ist der Standard *.\dump_JJJJMMTT_HHMMSS.dmp*.</span><span class="sxs-lookup"><span data-stu-id="c2351-148">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="c2351-149">Unter Linux ist der Standard *./core_JJJJMMTT_HHMMSS*.</span><span class="sxs-lookup"><span data-stu-id="c2351-149">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="c2351-150">JJJJMMTT entspricht Jahr/Monat/Tag, und HHMMSS entspricht Stunde/Minute/Sekunde.</span><span class="sxs-lookup"><span data-stu-id="c2351-150">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="c2351-151">Aktiviert die Diagnoseprotokollierung für die Speicherabbildsammlung.</span><span class="sxs-lookup"><span data-stu-id="c2351-151">Enables dump collection diagnostic logging.</span></span>

> [!NOTE]
> <span data-ttu-id="c2351-152">Unter Linux und macOS erwartet dieser Befehl, dass die Zielanwendung und `dotnet-dump` die gleiche `TMPDIR`-Umgebungsvariable verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2351-152">On Linux and macOS, this command expects the target application and `dotnet-dump` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="c2351-153">Andernfalls führt der Befehl zu einem Timeout.</span><span class="sxs-lookup"><span data-stu-id="c2351-153">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="c2351-154">Wenn Sie mit `dotnet-dump` ein Speicherabbild erfassen möchten, muss der Befehl vom Rootbenutzer oder dem Benutzer ausgeführt werden, der den Zielprozess ausführt.</span><span class="sxs-lookup"><span data-stu-id="c2351-154">To collect a dump using `dotnet-dump`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="c2351-155">Andernfalls kann das Tool keine Verbindung mit dem Zielprozess herstellen.</span><span class="sxs-lookup"><span data-stu-id="c2351-155">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="c2351-156">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="c2351-156">dotnet-dump analyze</span></span>

<span data-ttu-id="c2351-157">Startet eine interaktive Shell zum Durchsuchen eines Speicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="c2351-157">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="c2351-158">Die Shell akzeptiert verschiedene [SOS-Befehle](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="c2351-158">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="c2351-159">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2351-159">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="c2351-160">Argumente</span><span class="sxs-lookup"><span data-stu-id="c2351-160">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="c2351-161">Gibt den Pfad zu der Speicherabbilddatei an, die analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2351-161">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="c2351-162">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2351-162">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="c2351-163">Gibt den [Befehl](#analyze-sos-commands) an, der beim Starten in der Shell ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2351-163">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="c2351-164">SOS-Befehle zum Analysieren</span><span class="sxs-lookup"><span data-stu-id="c2351-164">Analyze SOS commands</span></span>

| <span data-ttu-id="c2351-165">Befehl</span><span class="sxs-lookup"><span data-stu-id="c2351-165">Command</span></span>                             | <span data-ttu-id="c2351-166">Funktion</span><span class="sxs-lookup"><span data-stu-id="c2351-166">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="c2351-167">Zeigt alle verfügbaren Befehle an.</span><span class="sxs-lookup"><span data-stu-id="c2351-167">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="c2351-168">Zeigt den angegebenen Befehl an.</span><span class="sxs-lookup"><span data-stu-id="c2351-168">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="c2351-169">Beendet den interaktiven Modus.</span><span class="sxs-lookup"><span data-stu-id="c2351-169">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="c2351-170">Stellt eine Stapelüberwachung ausschließlich für verwalteten Code bereit.</span><span class="sxs-lookup"><span data-stu-id="c2351-170">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="c2351-171">Listet die ausgeführten verwalteten Threads auf.</span><span class="sxs-lookup"><span data-stu-id="c2351-171">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="c2351-172">Zeigt Informationen zu Computern im asynchronen Zustand im Heap der Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="c2351-172">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="c2351-173">Zeigt Details zur Assembly bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-173">Displays details about the assembly at the specified address.</span></span>                                 |
| `dumpclass <arguments>`             | <span data-ttu-id="c2351-174">Zeigt Informationen zu einer `EEClass`-Struktur bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-174">Displays information about the `EEClass` structure at the specified address.</span></span>                  |
| `dumpdelegate <arguments>`          | <span data-ttu-id="c2351-175">Zeigt Informationen zum Delegaten bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-175">Displays information about the delegate at the specified address.</span></span>                             |
| `dumpdomain <arguments>`            | <span data-ttu-id="c2351-176">Zeigt Informationen zu allen AppDomains und allen Assemblys in der angegebenen Domäne an.</span><span class="sxs-lookup"><span data-stu-id="c2351-176">Displays information all the AppDomains and all assemblies within the specified domain.</span></span>       |
| `dumpheap <arguments>`              | <span data-ttu-id="c2351-177">Zeigt Informationen zum Garbage Collector-Heap und Sammlungsstatistiken zu Objekten an.</span><span class="sxs-lookup"><span data-stu-id="c2351-177">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="c2351-178">Zeigt die Microsoft Intermediate Language (MSIL) an, die einer verwalteten Methode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c2351-178">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="c2351-179">Schreibt den Inhalt eines Belastungsprotokolls im Speicher in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="c2351-179">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="c2351-180">Zeigt Informationen zur `MethodDesc`-Struktur bei der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="c2351-180">Displays information about the `MethodDesc` structure at the specified address.</span></span>               |
| `dumpmodule <arguments>`            | <span data-ttu-id="c2351-181">Zeigt Informationen zu einem Modul bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-181">Displays information about the module at the specified address.</span></span>                               |
| `dumpmt <arguments>`                | <span data-ttu-id="c2351-182">Zeigt Informationen zum `MethodTable`-Objekt bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-182">Displays information about the `MethodTable` at the specified address.</span></span>                        |
| `dumpobj <arguments>`               | <span data-ttu-id="c2351-183">Zeigt Informationen zu einem Objekt bei der angegebenen Adresse an</span><span class="sxs-lookup"><span data-stu-id="c2351-183">Displays info about the object at the specified address.</span></span>                                      |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="c2351-184">Zeigt alle innerhalb der Grenzen des aktuellen Stapels gefundenen verwalteten Objekte an.</span><span class="sxs-lookup"><span data-stu-id="c2351-184">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="c2351-185">Zeigt Informationen zu dem von internen Laufzeit-Datenstrukturen verwendeten Prozessspeicher an.</span><span class="sxs-lookup"><span data-stu-id="c2351-185">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="c2351-186">Zeigt alle für den Abschluss registrierten Objekte an.</span><span class="sxs-lookup"><span data-stu-id="c2351-186">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="c2351-187">Zeigt Informationen zu Verweisen auf das Objekt (oder Stämmen) bei der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="c2351-187">Displays info about references (or roots) to the object at the specified address.</span></span>             |
| `gcwhere <arguments>`               | <span data-ttu-id="c2351-188">Zeigt den Speicherort im GC-Heap des übergebenen Arguments an.</span><span class="sxs-lookup"><span data-stu-id="c2351-188">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="c2351-189">Zeigt die `MethodDesc`-Struktur bei der angegebenen Adresse in JIT-Code an</span><span class="sxs-lookup"><span data-stu-id="c2351-189">Displays the `MethodDesc` structure at the specified address in JIT code.</span></span>                     |
| `histclear <arguments>`             | <span data-ttu-id="c2351-190">Gibt alle von der Familie der `hist*`-Befehle verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="c2351-190">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="c2351-191">Initialisiert die SOS-Strukturen aus dem Belastungsprotokoll, die in der zu debuggenden Komponente gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c2351-191">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="c2351-192">Zeigt die Umsetzungen im Garbage Collection-Belastungsprotokoll im Zusammenhang mit `<arguments>` an.</span><span class="sxs-lookup"><span data-stu-id="c2351-192">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="c2351-193">Zeigt alle Protokolleinträge an, die auf das Objekt bei der angegebenen Adresse verweisen</span><span class="sxs-lookup"><span data-stu-id="c2351-193">Displays all the log entries that reference the object at the specified address.</span></span>              |
| `histroot <arguments>`              | <span data-ttu-id="c2351-194">Zeigt Informationen zu sowohl Heraufstufungen als auch Umsetzungen des angegebenen Stamms an.</span><span class="sxs-lookup"><span data-stu-id="c2351-194">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="c2351-195">Zeigt die nativen Module im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="c2351-195">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="c2351-196">Zeigt die Strukturen `MethodTable` und `EEClass` für das Objekt `<argument>` an</span><span class="sxs-lookup"><span data-stu-id="c2351-196">Displays the `MethodTable` and `EEClass` structures for the `<argument>`.</span></span>                     |
| `pe|printexception <arguments>`     | <span data-ttu-id="c2351-197">Zeigt jedes Objekt an, das von der Klasse <xref:System.Exception> für das Objekt `<argument>`abgeleitet wurde</span><span class="sxs-lookup"><span data-stu-id="c2351-197">Displays any object derived from the <xref:System.Exception> class for the `<argument>`.</span></span>      |
| `setsymbolserver <arguments>`       | <span data-ttu-id="c2351-198">Aktiviert die Symbolserverunterstützung.</span><span class="sxs-lookup"><span data-stu-id="c2351-198">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="c2351-199">Zeigt die Informationen zum SyncBlock-Container an.</span><span class="sxs-lookup"><span data-stu-id="c2351-199">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="c2351-200">Legt die ID des aktuellen Threads für die SOS-Befehle fest oder zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="c2351-200">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

> [!NOTE]
> <span data-ttu-id="c2351-201">Weitere Informationen finden Sie unter [SOS-Debuggingerweiterung für .NET](sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="c2351-201">Additional details can be found in [SOS Debugging Extension for .NET](sos-debugging-extension.md).</span></span>

## <a name="using-dotnet-dump"></a><span data-ttu-id="c2351-202">Verwenden von `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="c2351-202">Using `dotnet-dump`</span></span>

<span data-ttu-id="c2351-203">Der erste Schritt besteht im Sammeln eines Speicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="c2351-203">The first step is to collect a dump.</span></span> <span data-ttu-id="c2351-204">Dieser Schritt kann übersprungen werden, wenn bereits ein Kernspeicherabbild generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c2351-204">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="c2351-205">Das Betriebssystem und die integrierte [Speicherabbild-Generierungsfunktion](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) der .NET Core-Runtime können Kernspeicherabbilder erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2351-205">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="c2351-206">Analysieren Sie nun das Kernspeicherabbild mit dem Befehl `analyze`:</span><span class="sxs-lookup"><span data-stu-id="c2351-206">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="c2351-207">Durch diese Aktion wird eine interaktive Sitzung aufgerufen, die Befehle wie die folgenden akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="c2351-207">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="c2351-208">So zeigen Sie einen Ausnahmefehler an, der Ihre App beendet hat</span><span class="sxs-lookup"><span data-stu-id="c2351-208">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="c2351-209">Spezielle Anweisungen für Docker</span><span class="sxs-lookup"><span data-stu-id="c2351-209">Special instructions for Docker</span></span>

<span data-ttu-id="c2351-210">Wenn Sie den Prozess unter Docker ausführen, sind für die Speicherabbildsammlung `SYS_PTRACE`-Funktionen (`--cap-add=SYS_PTRACE` oder `--privileged`) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c2351-210">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="c2351-211">In Linux-Docker-Images des Microsoft .NET Core SDK können einige `dotnet-dump`-Befehle folgende Ausnahme auslösen:</span><span class="sxs-lookup"><span data-stu-id="c2351-211">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="c2351-212">Ausnahmefehler: System.DllNotFoundException: Ausnahme, da die freigegebene Bibliothek „libdl.so“ oder eine ihrer Abhängigkeiten nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c2351-212">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="c2351-213">Um dieses Problem zu umgehen, installieren Sie das Paket „libc6-dev“.</span><span class="sxs-lookup"><span data-stu-id="c2351-213">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2351-214">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2351-214">See also</span></span>

- [<span data-ttu-id="c2351-215">Blog zum Sammeln und Analysieren von Speicherabbildern</span><span class="sxs-lookup"><span data-stu-id="c2351-215">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="c2351-216">Heapanalysetool (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="c2351-216">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
