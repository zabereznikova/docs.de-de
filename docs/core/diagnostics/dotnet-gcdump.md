---
title: Diagnosetool „dotnet-gcdump“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-gcdump“ installieren und zum Erfassen von Garbage Collector-Speicherabbildern (GC) von .NET-Liveprozessen mithilfe von EventPipe im Zusammenhang mit .NET verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 02e1a7c5d86b582289672a027464aefd67a6f490
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593369"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="f25eb-103">Heapanalysetool (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="f25eb-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="f25eb-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="f25eb-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="f25eb-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="f25eb-105">Install</span></span>

<span data-ttu-id="f25eb-106">Es gibt zwei Möglichkeiten, `dotnet-gcdump` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="f25eb-106">There are two ways to download and install `dotnet-gcdump`:</span></span>

- <span data-ttu-id="f25eb-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="f25eb-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="f25eb-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="f25eb-108">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- <span data-ttu-id="f25eb-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="f25eb-109">**Direct download:**</span></span>

  <span data-ttu-id="f25eb-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="f25eb-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="f25eb-111">OS</span><span class="sxs-lookup"><span data-stu-id="f25eb-111">OS</span></span>  | <span data-ttu-id="f25eb-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="f25eb-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="f25eb-113">Windows</span><span class="sxs-lookup"><span data-stu-id="f25eb-113">Windows</span></span> | <span data-ttu-id="f25eb-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="f25eb-114">[x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64)</span></span> |
  | <span data-ttu-id="f25eb-115">macOS</span><span class="sxs-lookup"><span data-stu-id="f25eb-115">macOS</span></span>   | [<span data-ttu-id="f25eb-116">x64</span><span class="sxs-lookup"><span data-stu-id="f25eb-116">x64</span></span>](https://aka.ms/dotnet-gcdump/osx-x64) |
  | <span data-ttu-id="f25eb-117">Linux</span><span class="sxs-lookup"><span data-stu-id="f25eb-117">Linux</span></span>   | <span data-ttu-id="f25eb-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="f25eb-118">[x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="f25eb-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f25eb-119">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="f25eb-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f25eb-120">Description</span></span>

<span data-ttu-id="f25eb-121">Das globale `dotnet-gcdump`-Tool sammelt Garbage Collector-Speicherabbilder (GC) von .NET-Liveprozessen mithilfe von [EventPipe](./eventpipe.md).</span><span class="sxs-lookup"><span data-stu-id="f25eb-121">The `dotnet-gcdump` global tool collects GC (Garbage Collector) dumps of live .NET processes using [EventPipe](./eventpipe.md).</span></span> <span data-ttu-id="f25eb-122">GC-Speicherabbilder werden durch das Auslösen einer automatischen Speicherbereinigung im Zielprozess, das Aktivieren spezieller Ereignisse und das wiederholte Generieren des Graphs der Objektstämme aus dem Ereignisdatenstrom erstellt.</span><span class="sxs-lookup"><span data-stu-id="f25eb-122">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="f25eb-123">Dieser Prozess ermöglicht das Erfassen von GC-Speicherabbildern während der Prozessausführung mit minimalem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="f25eb-123">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="f25eb-124">Diese Speicherabbilder sind für verschiedene Szenarios nützlich:</span><span class="sxs-lookup"><span data-stu-id="f25eb-124">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="f25eb-125">Vergleichen der Anzahl von Objekten auf dem Heap zu verschiedenen Zeitpunkten</span><span class="sxs-lookup"><span data-stu-id="f25eb-125">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="f25eb-126">Analysieren des Stamms von Objekten (Beantwortung von Fragen wie „Was verweist noch auf diesen Typ?“)</span><span class="sxs-lookup"><span data-stu-id="f25eb-126">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="f25eb-127">Erfassen allgemeiner Statistiken über die Anzahl von Objekten auf dem Heap</span><span class="sxs-lookup"><span data-stu-id="f25eb-127">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="f25eb-128">Anzeigen des von dotnet-gcdump erfassten GC-Speicherabbilds</span><span class="sxs-lookup"><span data-stu-id="f25eb-128">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="f25eb-129">Unter Windows können `.gcdump`-Dateien zur Analyse in [PerfView](https://github.com/microsoft/perfview) oder in Visual Studio angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f25eb-129">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="f25eb-130">Derzeit gibt es keine Möglichkeit, eine `.gcdump`-Datei auf anderen Plattformen als Windows zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f25eb-130">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="f25eb-131">Sie können mehrere `.gcdump`-Dateien erfassen und gleichzeitig in Visual Studio öffnen, um sie zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f25eb-131">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="f25eb-132">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f25eb-132">Options</span></span>

- **`--version`**

  <span data-ttu-id="f25eb-133">Hiermit wird die Version des `dotnet-gcdump`-Hilfsprogramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f25eb-133">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="f25eb-134">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="f25eb-134">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="f25eb-135">Hiermit wird ein GC-Speicherabbild aus einem derzeit laufenden Prozess erfasst.</span><span class="sxs-lookup"><span data-stu-id="f25eb-135">Collects a GC dump from a currently running process.</span></span>

> [!WARNING]
> <span data-ttu-id="f25eb-136">Dieser Befehl löst eine (vollständige) Garbage Collection (GC) der Generation 2 aus, um den GC-Heap zu durchlaufen. Dadurch kann die Runtime für längere Zeit unterbrochen werden – insbesondere dann, wenn der GC-Heap groß ist.</span><span class="sxs-lookup"><span data-stu-id="f25eb-136">To walk the GC heap, this command triggers a generation 2 (full) garbage collection, which can suspend the runtime for a long time, especially when the GC heap is large.</span></span> <span data-ttu-id="f25eb-137">Verwenden Sie diesen Befehl nicht in leistungsabhängigen Umgebungen, wenn der GC-Heap groß ist.</span><span class="sxs-lookup"><span data-stu-id="f25eb-137">Don't use this command in performance-sensitive environments when the GC heap is large.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f25eb-138">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f25eb-138">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="f25eb-139">Optionen</span><span class="sxs-lookup"><span data-stu-id="f25eb-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f25eb-140">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="f25eb-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="f25eb-141">Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="f25eb-141">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="f25eb-142">Dies ist der Pfad, in den erfasste GC-Speicherabbilder geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f25eb-142">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="f25eb-143">Der Standardwert ist *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="f25eb-143">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="f25eb-144">Hiermit wird das Protokoll während der Erfassung des GC-Speicherabbilds ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f25eb-144">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="f25eb-145">Hiermit wird die Erfassung des GC-Speicherabbilds angehalten, wenn diese länger als eine bestimmte Anzahl von Sekunden dauert.</span><span class="sxs-lookup"><span data-stu-id="f25eb-145">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="f25eb-146">Der Standardwert ist 30.</span><span class="sxs-lookup"><span data-stu-id="f25eb-146">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="f25eb-147">Dies ist der Name des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="f25eb-147">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="f25eb-148">Hiermit werden die dotnet-Prozesse aufgelistet, für die GC-Speicherabbilder erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="f25eb-148">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f25eb-149">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f25eb-149">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="f25eb-150">Hiermit wird ein Bericht aus einem zuvor generierten GC-Speicherabbild oder aus einem laufenden Prozess generiert und in `stdout` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f25eb-150">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f25eb-151">Übersicht</span><span class="sxs-lookup"><span data-stu-id="f25eb-151">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="f25eb-152">Optionen</span><span class="sxs-lookup"><span data-stu-id="f25eb-152">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f25eb-153">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="f25eb-153">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="f25eb-154">Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="f25eb-154">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="f25eb-155">Dies ist der Typ des zu generierenden Berichts.</span><span class="sxs-lookup"><span data-stu-id="f25eb-155">The type of report to generate.</span></span> <span data-ttu-id="f25eb-156">Verfügbare Optionen: HeapStat (Standard)</span><span class="sxs-lookup"><span data-stu-id="f25eb-156">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="f25eb-157">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f25eb-157">Troubleshoot</span></span>

- <span data-ttu-id="f25eb-158">In der gcdump-Datei sind keine Typinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f25eb-158">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="f25eb-159">Vor .NET Core 3.1 gab es ein Problem, bei dem ein Typcache zwischen gcdump-Dateien nicht gelöscht wurde, wenn diese mit EventPipe aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="f25eb-159">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="f25eb-160">Dies führte dazu, dass die Ereignisse, die zum Bestimmen der Typinformationen benötigt werden, für die zweite und nachfolgende gcdump-Dateien nicht gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f25eb-160">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="f25eb-161">Dieses Problem wurde in .NET Core 3.1-preview2 behoben.</span><span class="sxs-lookup"><span data-stu-id="f25eb-161">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="f25eb-162">COM- und statische Typen sind nicht im GC-Speicherabbild enthalten.</span><span class="sxs-lookup"><span data-stu-id="f25eb-162">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="f25eb-163">Vor .NET Core 3.1-preview2 gab es ein Problem, bei dem statische und COM-Typen nicht gesendet wurden, wenn das GC-Speicherabbild über EventPipe aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="f25eb-163">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="f25eb-164">Dieses Problem wurde in .NET Core 3.1-preview2 behoben.</span><span class="sxs-lookup"><span data-stu-id="f25eb-164">This has been fixed in .NET Core 3.1-preview2.</span></span>
