---
title: dotnet-counters – .NET Core
description: Erfahren Sie, wie Sie das Befehlszeilentool dotnet-counter installieren und verwenden.
ms.date: 02/26/2020
ms.openlocfilehash: 7ff29ad91ad271afd35e3d38a4d748bc79ad6c03
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507253"
---
# <a name="dotnet-counters"></a>dotnet-counters

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

## <a name="install-dotnet-counters"></a>Installieren von dotnet-counters

Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-counters) `dotnet-counters` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a>Übersicht

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Beschreibung

`dotnet-counters` ist ein Leistungsüberwachungstool zur Ad-hoc-Überwachung der Integrität und zur Leistungsuntersuchung auf erster Ebene. Es kann Leistungsindikatorwerte überwachen, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht werden. Beispielsweise können Sie schnell die CPU-Auslastung oder die Rate der ausgelösten Ausnahmen in Ihrer .NET Core-Anwendung überwachen, um nach verdächtigen Werten zu suchen, bevor Sie mit `PerfView` oder `dotnet-trace` eine umfassendere Leistungsuntersuchung durchführen.

## <a name="options"></a>Optionen

- **`--version`**

  Zeigt die Version des Hilfsprogramms dotnet-counters an.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="commands"></a>Befehle

| Befehl                                             |
|-----------------------------------------------------|
| [dotnet-counters collect](#dotnet-counters-collect) |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a>dotnet-counters collect

Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Die ID des zu überwachenden Prozesses.

- **`--refresh-interval <SECONDS>`**

  Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.

- **`--counters <COUNTERS>`**

  Eine durch Leerzeichen getrennte Liste von Indikatoren. Zähler können in der Form `provider_name[:counter_name]` angegeben werden. Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt. Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).

- **`--format <csv|json>`**

  Das zu exportierende Format Derzeit sind die folgenden Formate verfügbar: CSV und JSON.

- **`-o|--output <output>`**

  Der Name der Ausgabedatei.

- **`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**

  Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten. `dotnet-counters` startet einen Prozess mit dem angegebenen Befehl und erfasst die angeforderten Metriken. Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.

> [!NOTE]
> Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden. Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.

### <a name="examples"></a>Beispiele

- Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- Starten Sie `dotnet mvc.dll` als untergeordneten Prozess, und beginnen Sie von Anfang an mit der Erfassung von Runtimeindikatoren und ASP.NET Core-Hostingindikatoren. Speichern Sie sie als JSON-Ausgabe:

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a>dotnet-counters list

Zeigt eine Liste von Zählernamen und -beschreibungen gruppiert nach Anbieter an.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>Beispiel

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> Die `Microsoft.AspNetCore.Hosting`-Leistungsindikatoren werden angezeigt, wenn bestimmte Prozesse identifiziert werden, die diese Leistungsindikatoren unterstützen, etwa wenn eine ASP.NET Core-Anwendung auf dem Hostcomputer ausgeführt wird.

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [--counters] [-- <command>]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Die ID des zu überwachenden Prozesses.

- **`--refresh-interval <SECONDS>`**

  Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.

- **`--counters <COUNTERS>`**

  Eine durch Leerzeichen getrennte Liste von Indikatoren. Zähler können in der Form `provider_name[:counter_name]` angegeben werden. Wenn `provider_name` ohne eine qualifizierende Liste von Indikatoren verwendet wird, werden alle Indikatoren des Anbieters angezeigt. Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).

 **`-- <command>` (nur für Zielanwendungen, die .NET 5.0 oder höher ausführen)**

  Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten. `dotnet-counters` startet einen Prozess mit dem bereitgestellten Befehl und überwacht die angeforderten Metriken. Dies ist bei der Sammlung der Metriken für den Startpfad einer Anwendung oft nützlich und kann verwendet werden, um Probleme kurz vor oder nach dem Haupteinstiegspunkt zu diagnostizieren oder zu überwachen.

  > [!NOTE]
  > Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden. Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.

### <a name="examples"></a>Beispiele

- Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`. Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung mithilfe von EventCounters in .NET Core](event-counter-perf.md).

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- Starten Sie `my-aspnet-server.exe`, und überwachen Sie die Anzahl der vom Start geladenen Assemblys (nur .NET 5.0 oder höher):

  HINWEIS: Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- Starten Sie `my-aspnet-server.exe` mit `arg1` und `arg2` als Befehlszeilenargumente, und überwachen Sie den Arbeitssatz und die GC-Heapgröße vom Start an (nur .NET 5.0 oder höher):

  HINWEIS: Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a>dotnet-counters ps

Mit diesem Befehl wird eine Liste der dotnet-Prozesse angezeigt, die überwacht werden können.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a>Beispiel

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
