---
title: dotnet-counters – .NET Core
description: Erfahren Sie, wie Sie das Befehlszeilentool dotnet-counter installieren und verwenden.
ms.date: 02/26/2020
ms.openlocfilehash: dc95297478784ca06fe442a939f8489a40b29da7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147177"
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
| --------------------------------------------------- |
| [dotnet-counters collect](#dotnet-counters-collect) |
| [dotnet-counters list](#dotnet-counters-list)       |
| [dotnet-counters monitor](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a>dotnet-counters collect

Mit diesem Befehl werden regelmäßig counter-Werte gesammelt und zur Nachbearbeitung in das festgelegte Dateiformat exportiert.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Die ID des zu überwachenden Prozesses.

- **`--refresh-interval <SECONDS>`**

  Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.

- **`counter_list <COUNTERS>`**

  Eine durch Leerzeichen getrennte Liste von Zählern. Zähler können in der Form `provider_name[:counter_name]` angegeben werden. Wenn `provider_name` ohne qualifizierenden `counter_name` verwendet wird, werden alle Indikatoren angezeigt. Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).

- **`--format <csv|json>`**

  Diese Option beschreibt das Dateiformat, in das die Werte exportiert werden. Derzeit sind die folgenden Formate verfügbar: CSV und JSON.

- **`-o|--output <output>`**

  Der Name der Ausgabedatei.

### <a name="examples"></a>Beispiele

- Im folgenden Beispiel werden alle counter-Werte mit einem Aktualisierungsintervall von 3 Sekunden erfasst und eine CSV-Ausgabedatei wird erstellt:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
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
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a>dotnet-counters monitor

Zeigt regelmäßig aktualisierte Werte ausgewählter Zähler an.

### <a name="synopsis"></a>Übersicht

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Die ID des zu überwachenden Prozesses.

- **`--refresh-interval <SECONDS>`**

  Die Anzahl von Sekunden, die zwischen Aktualisierungen der angezeigten Indikatoren verstreichen soll.

- **`counter_list <COUNTERS>`**

  Eine durch Leerzeichen getrennte Liste von Zählern. Zähler können in der Form `provider_name[:counter_name]` angegeben werden. Wenn `provider_name` ohne qualifizierenden `counter_name` verwendet wird, werden alle Indikatoren angezeigt. Verwenden Sie zum Ermitteln von Anbieter- und Indikatornamen den Befehl [dotnet-counters list](#dotnet-counters-list).

### <a name="examples"></a>Beispiele

- Überwachen aller Zähler von `System.Runtime` in einem Aktualisierungsintervall von 3 Sekunden:

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

- Überwachen nur der CPU-Auslastung und der GC-Heapgröße von `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Überwachen von `EventCounter`-Werten von benutzerdefinierten `EventSource`. Weitere Informationen finden Sie unter [Tutorial: Messen der Leistung für sehr häufige Ereignisse mithilfe von EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
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
