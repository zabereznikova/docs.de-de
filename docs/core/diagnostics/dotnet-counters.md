---
title: dotnet-counters – .NET Core
description: Erfahren Sie, wie Sie das Befehlszeilentool dotnet-counter installieren und verwenden.
ms.date: 10/14/2019
ms.openlocfilehash: 399d5908e8ac52bcd4a20c1a819fc6c99f4de2f4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737710"
---
# <a name="dotnet-counters"></a><span data-ttu-id="b2b77-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="b2b77-103">dotnet-counters</span></span>

<span data-ttu-id="b2b77-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="b2b77-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="b2b77-105">Installieren von dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="b2b77-105">Install dotnet-counters</span></span>

<span data-ttu-id="b2b77-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="b2b77-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="b2b77-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b2b77-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="b2b77-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2b77-108">Description</span></span>

<span data-ttu-id="b2b77-109">`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene.</span><span class="sxs-lookup"><span data-stu-id="b2b77-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="b2b77-110">Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="b2b77-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="b2b77-111">Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.</span><span class="sxs-lookup"><span data-stu-id="b2b77-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="b2b77-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="b2b77-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="b2b77-113">Zeigt die Version des Hilfsprogramms dotnet-counters an.</span><span class="sxs-lookup"><span data-stu-id="b2b77-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b2b77-114">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="b2b77-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="b2b77-115">Befehle</span><span class="sxs-lookup"><span data-stu-id="b2b77-115">Commands</span></span>

| <span data-ttu-id="b2b77-116">Befehl</span><span class="sxs-lookup"><span data-stu-id="b2b77-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="b2b77-117">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="b2b77-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="b2b77-118">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="b2b77-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="b2b77-119">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="b2b77-119">dotnet-counters list</span></span>

<span data-ttu-id="b2b77-120">Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="b2b77-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b2b77-121">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b2b77-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="b2b77-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2b77-122">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="b2b77-123">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="b2b77-123">dotnet-counters monitor</span></span>

<span data-ttu-id="b2b77-124">Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.</span><span class="sxs-lookup"><span data-stu-id="b2b77-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="b2b77-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b2b77-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="b2b77-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="b2b77-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="b2b77-127">Die ID des zu überwachenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b2b77-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="b2b77-128">Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.</span><span class="sxs-lookup"><span data-stu-id="b2b77-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="b2b77-129">Eine durch Leerzeichen getrennte Liste von Zählern.</span><span class="sxs-lookup"><span data-stu-id="b2b77-129">A space separated list of counters.</span></span> <span data-ttu-id="b2b77-130">Zähler können in der Form `provider_name[:counter_name]` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b2b77-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="b2b77-131">Wenn `provider_name` ohne qualifizierenden `counter_name` verwendet wird, werden alle Indikatoren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2b77-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="b2b77-132">Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="b2b77-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="b2b77-133">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b2b77-133">Examples</span></span>

- <span data-ttu-id="b2b77-134">Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:</span><span class="sxs-lookup"><span data-stu-id="b2b77-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="b2b77-135">Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="b2b77-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="b2b77-136">Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`.</span><span class="sxs-lookup"><span data-stu-id="b2b77-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="b2b77-137">Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung für sehr häufige Ereignisse mithilfe von EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="b2b77-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
