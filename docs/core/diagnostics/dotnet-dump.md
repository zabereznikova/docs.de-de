---
title: dotnet-dump – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-dump.
ms.date: 10/14/2019
ms.openlocfilehash: e008dcfc734a8742c495ea32a7a149c9a55c54c6
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598109"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="54361-103">Hilfsprogramm zum Sammeln und Analysieren von Speicherabbildern (dotnet-dump)</span><span class="sxs-lookup"><span data-stu-id="54361-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="54361-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="54361-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="54361-105">`dotnet-dump` wird unter macOS nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54361-105">`dotnet-dump` isn't supported on macOS.</span></span>

## <a name="install-dotnet-dump"></a><span data-ttu-id="54361-106">Installieren von dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="54361-106">Install dotnet-dump</span></span>

<span data-ttu-id="54361-107">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-dump) `dotnet-dump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="54361-107">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a><span data-ttu-id="54361-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="54361-108">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="54361-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54361-109">Description</span></span>

<span data-ttu-id="54361-110">Mit dem globalen Tool `dotnet-dump` können Sie Windows- und Linux-Speicherabbilder ohne nativen Debugger wie `lldb` unter Linux sammeln und analysieren.</span><span class="sxs-lookup"><span data-stu-id="54361-110">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="54361-111">Dieses Tool ist auf Plattformen wie z. B. Alpine Linux wichtig, bei denen kein voll funktionsfähiges Tool `lldb` verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="54361-111">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="54361-112">Mit dem Tool `dotnet-dump` können Sie SOS-Befehle zum Analysieren von Abstürzen und dem Garbage Collector (GC) ausführen, es handelt sich jedoch nicht um einen nativen Debugger, sodass Elemente wie das Anzeigen von nativen Stapelrahmen nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="54361-112">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="54361-113">Optionen</span><span class="sxs-lookup"><span data-stu-id="54361-113">Options</span></span>

- **`--version`**

  <span data-ttu-id="54361-114">Mit dieser Option wird die Version des Hilfsprogramms „dotnet-dump“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54361-114">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="54361-115">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="54361-115">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="54361-116">Befehle</span><span class="sxs-lookup"><span data-stu-id="54361-116">Commands</span></span>

| <span data-ttu-id="54361-117">Befehl</span><span class="sxs-lookup"><span data-stu-id="54361-117">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="54361-118">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="54361-118">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="54361-119">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="54361-119">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="54361-120">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="54361-120">dotnet-dump collect</span></span>

<span data-ttu-id="54361-121">Erfasst ein Speicherabbild von einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="54361-121">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="54361-122">Übersicht</span><span class="sxs-lookup"><span data-stu-id="54361-122">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="54361-123">Optionen</span><span class="sxs-lookup"><span data-stu-id="54361-123">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="54361-124">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="54361-124">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="54361-125">Gibt die ID-Nummer des Prozesses an, von dem ein Speicherabbild gesammelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="54361-125">Specifies the process ID number to collect a memory dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="54361-126">Gibt den Speicherabbildtyp an, der festlegt, welche Arten von Informationen vom Prozess gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="54361-126">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="54361-127">Es gibt drei Typen:</span><span class="sxs-lookup"><span data-stu-id="54361-127">There are three types:</span></span>

  - <span data-ttu-id="54361-128">`Full`: Das größte Speicherabbild, das den gesamten Arbeitsspeicher einschließlich der Modulimages enthält</span><span class="sxs-lookup"><span data-stu-id="54361-128">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="54361-129">`Heap`: eine große und relativ umfassende Sicherung, die Modullisten, Threadlisten, alle Stapel, Ausnahmeinformationen, Handleinformationen und den gesamten Arbeitsspeicher mit Ausnahme von zugeordneten Images enthält.</span><span class="sxs-lookup"><span data-stu-id="54361-129">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="54361-130">`Mini`: eine kleine Sicherung, die Modullisten, Threadlisten, Ausnahmeinformationen und alle Stapel enthält.</span><span class="sxs-lookup"><span data-stu-id="54361-130">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="54361-131">Wenn nichts anderes angegeben wird, wird als Standard `Full` verwendet.</span><span class="sxs-lookup"><span data-stu-id="54361-131">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="54361-132">Der vollständige Pfad und der Dateiname, in den das gesammelte Speicherabbild geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="54361-132">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="54361-133">Wenn nichts angegeben wird, gilt:</span><span class="sxs-lookup"><span data-stu-id="54361-133">If not specified:</span></span>

  - <span data-ttu-id="54361-134">Unter Windows ist der Standard *.\dump_JJJJMMTT_HHMMSS.dmp*.</span><span class="sxs-lookup"><span data-stu-id="54361-134">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="54361-135">Unter Linux ist der Standard *./core_JJJJMMTT_HHMMSS*.</span><span class="sxs-lookup"><span data-stu-id="54361-135">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="54361-136">JJJJMMTT entspricht Jahr/Monat/Tag, und HHMMSS entspricht Stunde/Minute/Sekunde.</span><span class="sxs-lookup"><span data-stu-id="54361-136">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="54361-137">Aktiviert die Diagnoseprotokollierung für die Speicherabbildsammlung.</span><span class="sxs-lookup"><span data-stu-id="54361-137">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="54361-138">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="54361-138">dotnet-dump analyze</span></span>

<span data-ttu-id="54361-139">Startet eine interaktive Shell zum Durchsuchen eines Speicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="54361-139">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="54361-140">Die Shell akzeptiert verschiedene [SOS-Befehle](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="54361-140">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="54361-141">Übersicht</span><span class="sxs-lookup"><span data-stu-id="54361-141">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="54361-142">Argumente</span><span class="sxs-lookup"><span data-stu-id="54361-142">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="54361-143">Gibt den Pfad zu der Speicherabbilddatei an, die analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="54361-143">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="54361-144">Optionen</span><span class="sxs-lookup"><span data-stu-id="54361-144">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="54361-145">Gibt den [Befehl](#analyze-sos-commands) an, der beim Starten in der Shell ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="54361-145">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="54361-146">SOS-Befehle zum Analysieren</span><span class="sxs-lookup"><span data-stu-id="54361-146">Analyze SOS commands</span></span>

| <span data-ttu-id="54361-147">Befehl</span><span class="sxs-lookup"><span data-stu-id="54361-147">Command</span></span>                             | <span data-ttu-id="54361-148">Funktion</span><span class="sxs-lookup"><span data-stu-id="54361-148">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="54361-149">Zeigt alle verfügbaren Befehle an.</span><span class="sxs-lookup"><span data-stu-id="54361-149">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="54361-150">Zeigt den angegebenen Befehl an.</span><span class="sxs-lookup"><span data-stu-id="54361-150">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="54361-151">Beendet den interaktiven Modus.</span><span class="sxs-lookup"><span data-stu-id="54361-151">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="54361-152">Stellt eine Stapelüberwachung ausschließlich für verwalteten Code bereit.</span><span class="sxs-lookup"><span data-stu-id="54361-152">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="54361-153">Listet die ausgeführten verwalteten Threads auf.</span><span class="sxs-lookup"><span data-stu-id="54361-153">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="54361-154">Zeigt Informationen zu Computern im asynchronen Zustand im Heap der Garbage Collection an.</span><span class="sxs-lookup"><span data-stu-id="54361-154">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="54361-155">Zeigt Details zu einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="54361-155">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="54361-156">Zeigt Informationen zu einer EE-Klassenstruktur an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-156">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="54361-157">Zeigt Informationen zu einem Delegaten an.</span><span class="sxs-lookup"><span data-stu-id="54361-157">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="54361-158">Zeigt Informationen zu allen AppDomains und allen Assemblys in den Domänen an.</span><span class="sxs-lookup"><span data-stu-id="54361-158">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="54361-159">Zeigt Informationen zum Garbage Collector-Heap und Sammlungsstatistiken zu Objekten an.</span><span class="sxs-lookup"><span data-stu-id="54361-159">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="54361-160">Zeigt die Microsoft Intermediate Language (MSIL) an, die einer verwalteten Methode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="54361-160">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="54361-161">Schreibt den Inhalt eines Belastungsprotokolls im Speicher in die angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="54361-161">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="54361-162">Zeigt Informationen zu einer MethodDesc-Struktur an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-162">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="54361-163">Zeigt Informationen zu einer EE-Modulstruktur an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-163">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="54361-164">Zeigt Informationen zu einer Methodentabelle bei der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-164">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="54361-165">Zeigt Informationen zu einem Objekt an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-165">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="54361-166">Zeigt alle innerhalb der Grenzen des aktuellen Stapels gefundenen verwalteten Objekte an.</span><span class="sxs-lookup"><span data-stu-id="54361-166">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="54361-167">Zeigt Informationen zu dem von internen Laufzeit-Datenstrukturen verwendeten Prozessspeicher an.</span><span class="sxs-lookup"><span data-stu-id="54361-167">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="54361-168">Zeigt alle für den Abschluss registrierten Objekte an.</span><span class="sxs-lookup"><span data-stu-id="54361-168">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="54361-169">Zeigt Informationen zu Verweisen auf ein Objekt (oder Stämmen eines Objekts) an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="54361-169">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="54361-170">Zeigt den Speicherort im GC-Heap des übergebenen Arguments an.</span><span class="sxs-lookup"><span data-stu-id="54361-170">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="54361-171">Zeigt die MethodDesc-Struktur an der angegebenen Adresse in JIT-Code an.</span><span class="sxs-lookup"><span data-stu-id="54361-171">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="54361-172">Gibt alle von der Familie der `hist*`-Befehle verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="54361-172">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="54361-173">Initialisiert die SOS-Strukturen aus dem Belastungsprotokoll, die in der zu debuggenden Komponente gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="54361-173">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="54361-174">Zeigt die Umsetzungen im Garbage Collection-Belastungsprotokoll im Zusammenhang mit `<arguments>` an.</span><span class="sxs-lookup"><span data-stu-id="54361-174">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="54361-175">Zeigt alle Protokolleinträge an, die auf ein Objekt bei der angegebenen Adresse verweisen.</span><span class="sxs-lookup"><span data-stu-id="54361-175">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="54361-176">Zeigt Informationen zu sowohl Heraufstufungen als auch Umsetzungen des angegebenen Stamms an.</span><span class="sxs-lookup"><span data-stu-id="54361-176">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="54361-177">Zeigt die nativen Module im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="54361-177">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="54361-178">Zeigt die MethodTable-Struktur und die EEClass-Struktur für `<argument>` an.</span><span class="sxs-lookup"><span data-stu-id="54361-178">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="54361-179">Zeigt ein Objekt an, das von der Ausnahmeklasse an der Adresse `<argument>` abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="54361-179">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="54361-180">Aktiviert die Symbolserverunterstützung.</span><span class="sxs-lookup"><span data-stu-id="54361-180">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="54361-181">Zeigt die Informationen zum SyncBlock-Container an.</span><span class="sxs-lookup"><span data-stu-id="54361-181">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="54361-182">Legt die ID des aktuellen Threads für die SOS-Befehle fest oder zeigt diese an.</span><span class="sxs-lookup"><span data-stu-id="54361-182">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="54361-183">Verwenden von `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="54361-183">Using `dotnet-dump`</span></span>

<span data-ttu-id="54361-184">Der erste Schritt besteht im Sammeln eines Speicherabbilds.</span><span class="sxs-lookup"><span data-stu-id="54361-184">The first step is to collect a dump.</span></span> <span data-ttu-id="54361-185">Dieser Schritt kann übersprungen werden, wenn bereits ein Kernspeicherabbild generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="54361-185">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="54361-186">Das Betriebssystem und die integrierte [Speicherabbild-Generierungsfunktion](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) der .NET Core-Runtime können Kernspeicherabbilder erstellen.</span><span class="sxs-lookup"><span data-stu-id="54361-186">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="54361-187">Analysieren Sie nun das Kernspeicherabbild mit dem Befehl `analyze`:</span><span class="sxs-lookup"><span data-stu-id="54361-187">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="54361-188">Durch diese Aktion wird eine interaktive Sitzung aufgerufen, die Befehle wie die folgenden akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="54361-188">This action brings up an interactive session that accepts commands like:</span></span>

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

<span data-ttu-id="54361-189">So zeigen Sie einen Ausnahmefehler an, der Ihre App beendet hat</span><span class="sxs-lookup"><span data-stu-id="54361-189">To see an unhandled exception that killed your app:</span></span>

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

## <a name="special-instructions-for-docker"></a><span data-ttu-id="54361-190">Spezielle Anweisungen für Docker</span><span class="sxs-lookup"><span data-stu-id="54361-190">Special instructions for Docker</span></span>

<span data-ttu-id="54361-191">Wenn Sie den Prozess unter Docker ausführen, sind für die Speicherabbildsammlung `SYS_PTRACE`-Funktionen (`--cap-add=SYS_PTRACE` oder `--privileged`) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="54361-191">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="54361-192">In Linux-Docker-Images des Microsoft .NET Core SDK können einige `dotnet-dump`-Befehle folgende Ausnahme auslösen:</span><span class="sxs-lookup"><span data-stu-id="54361-192">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="54361-193">Ausnahmefehler: System.DllNotFoundException: Ausnahme, da die freigegebene Bibliothek „libdl.so“ oder eine ihrer Abhängigkeiten nicht geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="54361-193">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="54361-194">Um dieses Problem zu umgehen, installieren Sie das Paket „libc6-dev“.</span><span class="sxs-lookup"><span data-stu-id="54361-194">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="54361-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54361-195">See also</span></span>

- [<span data-ttu-id="54361-196">Blog zum Sammeln und Analysieren von Speicherabbildern</span><span class="sxs-lookup"><span data-stu-id="54361-196">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="54361-197">Heapanalysetool (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="54361-197">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
