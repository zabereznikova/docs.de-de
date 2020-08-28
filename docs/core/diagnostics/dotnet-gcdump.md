---
title: dotnet-gcdump (.NET Core)
description: Hier erfahren Sie mehr über das Installieren und Verwenden des Befehlszeilentools „dotnet-gcdump“.
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656650"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a><span data-ttu-id="c2583-103">Heapanalysetool (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="c2583-103">Heap analysis tool (dotnet-gcdump)</span></span>

<span data-ttu-id="c2583-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="c2583-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

## <a name="install-dotnet-gcdump"></a><span data-ttu-id="c2583-105">Installieren von dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="c2583-105">Install dotnet-gcdump</span></span>

<span data-ttu-id="c2583-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="c2583-106">To install the latest release version of the `dotnet-gcdump` [NuGet package](https://www.nuget.org/packages/dotnet-gcdump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a><span data-ttu-id="c2583-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2583-107">Synopsis</span></span>

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="c2583-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2583-108">Description</span></span>

<span data-ttu-id="c2583-109">Mit dem globalen Tool `dotnet-gcdump` können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.</span><span class="sxs-lookup"><span data-stu-id="c2583-109">The `dotnet-gcdump` global tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span> <span data-ttu-id="c2583-110">Dabei wird die EventPipe-Technologie verwendet, bei der es sich um eine plattformübergreifende Alternative zur Ereignisablaufverfolgung für Windows handelt.</span><span class="sxs-lookup"><span data-stu-id="c2583-110">It uses the EventPipe technology, which is a cross-platform alternative to ETW on Windows.</span></span> <span data-ttu-id="c2583-111">GC-Speicherabbilder werden durch das Auslösen einer automatischen Speicherbereinigung im Zielprozess, das Aktivieren spezieller Ereignisse und das wiederholte Generieren des Graphs der Objektstämme aus dem Ereignisdatenstrom erstellt.</span><span class="sxs-lookup"><span data-stu-id="c2583-111">GC dumps are created by triggering a GC in the target process, turning on special events, and regenerating the graph of object roots from the event stream.</span></span> <span data-ttu-id="c2583-112">Dieser Prozess ermöglicht das Erfassen von GC-Speicherabbildern während der Prozessausführung mit minimalem Aufwand.</span><span class="sxs-lookup"><span data-stu-id="c2583-112">This process allows for GC dumps to be collected while the process is running and with minimal overhead.</span></span> <span data-ttu-id="c2583-113">Diese Speicherabbilder sind für verschiedene Szenarios nützlich:</span><span class="sxs-lookup"><span data-stu-id="c2583-113">These dumps are useful for several scenarios:</span></span>

- <span data-ttu-id="c2583-114">Vergleichen der Anzahl von Objekten auf dem Heap zu verschiedenen Zeitpunkten</span><span class="sxs-lookup"><span data-stu-id="c2583-114">Comparing the number of objects on the heap at several points in time.</span></span>
- <span data-ttu-id="c2583-115">Analysieren des Stamms von Objekten (Beantwortung von Fragen wie „Was verweist noch auf diesen Typ?“)</span><span class="sxs-lookup"><span data-stu-id="c2583-115">Analyzing roots of objects (answering questions like, "what still has a reference to this type?").</span></span>
- <span data-ttu-id="c2583-116">Erfassen allgemeiner Statistiken über die Anzahl von Objekten auf dem Heap</span><span class="sxs-lookup"><span data-stu-id="c2583-116">Collecting general statistics about the counts of objects on the heap.</span></span>

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a><span data-ttu-id="c2583-117">Anzeigen des von dotnet-gcdump erfassten GC-Speicherabbilds</span><span class="sxs-lookup"><span data-stu-id="c2583-117">View the GC dump captured from dotnet-gcdump</span></span>

<span data-ttu-id="c2583-118">Unter Windows können `.gcdump`-Dateien zur Analyse in [PerfView](https://github.com/microsoft/perfview) oder in Visual Studio angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c2583-118">On Windows, `.gcdump` files can be viewed in [PerfView](https://github.com/microsoft/perfview) for analysis or in Visual Studio.</span></span> <span data-ttu-id="c2583-119">Derzeit gibt es keine Möglichkeit, eine `.gcdump`-Datei auf anderen Plattformen als Windows zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c2583-119">Currently, There is no way of opening a `.gcdump` on non-Windows platforms.</span></span>

<span data-ttu-id="c2583-120">Sie können mehrere `.gcdump`-Dateien erfassen und gleichzeitig in Visual Studio öffnen, um sie zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c2583-120">You can collect multiple `.gcdump`s and open them simultaneously in Visual Studio to get a comparison experience.</span></span>

## <a name="options"></a><span data-ttu-id="c2583-121">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c2583-121">Options</span></span>

- **`--version`**

  <span data-ttu-id="c2583-122">Hiermit wird die Version des `dotnet-gcdump`-Hilfsprogramms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2583-122">Displays the version of the `dotnet-gcdump` utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2583-123">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="c2583-123">Shows command-line help.</span></span>

## `dotnet-gcdump collect`

<span data-ttu-id="c2583-124">Hiermit wird ein GC-Speicherabbild aus einem derzeit laufenden Prozess erfasst.</span><span class="sxs-lookup"><span data-stu-id="c2583-124">Collects a GC dump from a currently running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c2583-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2583-125">Synopsis</span></span>

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a><span data-ttu-id="c2583-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2583-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2583-127">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="c2583-127">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="c2583-128">Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2583-128">The process ID to collect the GC dump from.</span></span>

- **`-o|--output <gcdump-file-path>`**

  <span data-ttu-id="c2583-129">Dies ist der Pfad, in den erfasste GC-Speicherabbilder geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c2583-129">The path where collected GC dumps should be written.</span></span> <span data-ttu-id="c2583-130">Der Standardwert ist *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span><span class="sxs-lookup"><span data-stu-id="c2583-130">Defaults to *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.</span></span>

- **`-v|--verbose`**

  <span data-ttu-id="c2583-131">Hiermit wird das Protokoll während der Erfassung des GC-Speicherabbilds ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2583-131">Output the log while collecting the GC dump.</span></span>

- **`-t|--timeout <timeout>`**

  <span data-ttu-id="c2583-132">Hiermit wird die Erfassung des GC-Speicherabbilds angehalten, wenn diese länger als eine bestimmte Anzahl von Sekunden dauert.</span><span class="sxs-lookup"><span data-stu-id="c2583-132">Give up on collecting the GC dump if it takes longer than this many seconds.</span></span> <span data-ttu-id="c2583-133">Der Standardwert ist 30.</span><span class="sxs-lookup"><span data-stu-id="c2583-133">The default value is 30.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="c2583-134">Dies ist der Name des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2583-134">The name of the process to collect the GC dump from.</span></span>

## `dotnet-gcdump ps`

<span data-ttu-id="c2583-135">Hiermit werden die dotnet-Prozesse aufgelistet, für die GC-Speicherabbilder erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="c2583-135">Lists the dotnet processes that GC dumps can be collected for.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c2583-136">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2583-136">Synopsis</span></span>

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

<span data-ttu-id="c2583-137">Hiermit wird ein Bericht aus einem zuvor generierten GC-Speicherabbild oder aus einem laufenden Prozess generiert und in `stdout` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2583-137">Generate a report from a previously generated GC dump or from a running process, and write to `stdout`.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c2583-138">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c2583-138">Synopsis</span></span>

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a><span data-ttu-id="c2583-139">Optionen</span><span class="sxs-lookup"><span data-stu-id="c2583-139">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="c2583-140">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="c2583-140">Shows command-line help.</span></span>

- **`-p|--process-id <pid>`**

  <span data-ttu-id="c2583-141">Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2583-141">The process ID to collect the GC dump from.</span></span>

- **`-t|--report-type <HeapStat>`**

  <span data-ttu-id="c2583-142">Dies ist der Typ des zu generierenden Berichts.</span><span class="sxs-lookup"><span data-stu-id="c2583-142">The type of report to generate.</span></span> <span data-ttu-id="c2583-143">Verfügbare Optionen: HeapStat (Standard)</span><span class="sxs-lookup"><span data-stu-id="c2583-143">Available options: heapstat (default).</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="c2583-144">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="c2583-144">Troubleshoot</span></span>

- <span data-ttu-id="c2583-145">In der gcdump-Datei sind keine Typinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2583-145">There is no type information in the gcdump.</span></span>

   <span data-ttu-id="c2583-146">Vor .NET Core 3.1 gab es ein Problem, bei dem ein Typcache zwischen gcdump-Dateien nicht gelöscht wurde, wenn diese mit EventPipe aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="c2583-146">Prior to .NET Core 3.1, there was an issue where a type cache was not cleared between gcdumps when they were invoked with EventPipe.</span></span> <span data-ttu-id="c2583-147">Dies führte dazu, dass die Ereignisse, die zum Bestimmen der Typinformationen benötigt werden, für die zweite und nachfolgende gcdump-Dateien nicht gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c2583-147">This resulted in the events needed for determining type information not being sent for the second and subsequent gcdumps.</span></span> <span data-ttu-id="c2583-148">Dieses Problem wurde in .NET Core 3.1-preview2 behoben.</span><span class="sxs-lookup"><span data-stu-id="c2583-148">This was fixed in .NET Core 3.1-preview2.</span></span>

- <span data-ttu-id="c2583-149">COM- und statische Typen sind nicht im GC-Speicherabbild enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2583-149">COM and static types aren't in the GC dump.</span></span>

   <span data-ttu-id="c2583-150">Vor .NET Core 3.1-preview2 gab es ein Problem, bei dem statische und COM-Typen nicht gesendet wurden, wenn das GC-Speicherabbild über EventPipe aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c2583-150">Prior to .NET Core 3.1-preview2, there was an issue where static and COM types weren't sent when the GC dump was invoked via EventPipe.</span></span> <span data-ttu-id="c2583-151">Dieses Problem wurde in .NET Core 3.1-preview2 behoben.</span><span class="sxs-lookup"><span data-stu-id="c2583-151">This has been fixed in .NET Core 3.1-preview2.</span></span>
