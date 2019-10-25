---
title: dotnet-trace – .NET Core
description: Installieren und Verwenden des Befehlszeilentools dotnet-trace.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321531"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>Hilfsprogramm zur Ablaufverfolgung für Leistungsanalysen (`dotnet-trace`)

**Dieser Artikel gilt für:** .NET Core 3.0 SDK und neuere Versionen

## <a name="installing-dotnet-trace"></a>Installieren von `dotnet-trace`

Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Übersicht

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>BESCHREIBUNG

Das Tool `dotnet-trace` ist ein plattformübergreifendes globales Befehlszeilenschnittstellen-Tool zum Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler. Es basiert auf der plattformübergreifenden `EventPipe`-Technologie der .NET Core-Runtime. `dotnet-trace` bietet unter Windows, Linux und macOS die gleiche Oberfläche.

## <a name="options"></a>Optionen

- **`--version`**

Zeigt die Version des Hilfsprogramms dotnet-counters an.

- **`-h|--help`**

Zeigt die Hilfe für die Befehlszeile an.

## <a name="commands"></a>Befehle

| Befehl                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace list-processes](#dotnet-trace-list-processes) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Optionen

- **`-p|--process-id <PID>`**

  Der Prozess, von dem die Ablaufverfolgung gesammelt werden soll.

- **`--buffersize <size>`**

  Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest. Standard: 256 MB.

- **`-o|--output <trace-file-path>`**

  Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten. Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.

- **`--providers <list-of-comma-separated-providers>`**

  Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen. Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter. Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat die Konfiguration hier Vorrang vor der impliziten Konfiguration aus dem Profil.

  Diese Liste der Anbieter hat das folgende Format:

  - `Provider[,Provider]`
  - `Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können.

- **`--format <NetTrace|Speedscope>`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Argumente

- **`<input-filename>`**

  Die zu konvertierende Eingabe-Ablaufverfolgungsdatei. Standard: *trace.nettrace*.

### <a name="options"></a>Optionen

- **`--format <NetTrace|Speedscope>`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.

- **`-o|--output <output-filename>`**

  Ausgabedateiname. Die Erweiterung des Zielformats wird hinzugefügt.

## <a name="dotnet-trace-list-processes"></a>dotnet-trace list-processes

Listet die dotnet-Prozesse auf, die verfolgt werden können.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Erfassen einer Ablaufverfolgung mit `dotnet-trace`

- Um Ablaufverfolgungen mithilfe von `dotnet-trace` zu sammeln, müssen Sie zunächst die Prozess-ID (PID) der .NET Core-Anwendung ermitteln, von der Ablaufverfolgungen gesammelt werden sollen.

  - Unter Windows gibt es Optionen wie den Task-Manager oder den Befehl `tasklist`.
  - Unter Linux besteht die triviale Option im Verwenden des Befehls `ps`.

Sie können auch den Befehl [dotnet-trace list-processes](#dotnet-trace-list-processes) verwenden, um die ausgeführten .NET Core-Prozesse zusammen mit ihren PIDs herauszufinden.

- Führen Sie dann den folgenden Befehl aus:

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- Beenden Sie schließlich die Sammlung, indem Sie die Taste `<Enter>` drücken. `dotnet-trace` protokolliert dann keine Ereignisse mehr in der Datei `trace.nettrace`.

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>Anzeigen der aufgezeichneten Ablaufverfolgung von `dotnet-trace`

Unter Windows können `.nettrace`-Dateien genau wie mit ETW oder LTTng gesammelte Ablaufverfolgungen in [PerfView](https://github.com/microsoft/perfview) angezeigt werden. Bei unter Linux gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgung auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.

Sie können die Ablaufverfolgung auch auf einem Linux-Computer anzeigen, indem Sie das Ausgabeformat von `dotnet-trace` in `speedscope` ändern. Sie können das Ausgabedateiformat mit der Option `-f|--format` ändern – mit `-f speedscope` generiert `dotnet-trace` eine `speedscope`-Datei. Derzeit können Sie zwischen `nettrace` (Standardoption) und `speedscope` auswählen. `Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.

> [!NOTE]
> Die .NET Core-Runtime generiert Ablaufverfolgungen im `nettrace`-Format, die nach Abschluss der Ablaufverfolgung in „speedscope“ konvertiert werden (sofern dies angegeben wird). Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>Verwenden von `dotnet-trace` zum Sammeln von Leistungsindikatorwerten über die Zeit

Wenn Sie `EventCounter` für die grundlegende Systemüberwachung in leistungsempfindlichen Umfeldern wie Produktionsumgebungen verwenden und dabei Ablaufverfolgungen sammeln möchten, anstatt sie in Echtzeit zu überwachen, können Sie dies ebenfalls mit `dotnet-trace` erreichen.

Wenn Sie z. B. Laufzeit-Leistungsindikatorwerte sammeln möchten, können Sie den folgenden Befehl verwenden:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Dieser Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Integritätsüberwachung mit geringem Aufwand. Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.

Wenn Sie den Mehraufwand (und die Größe der Ablaufverfolgung) noch weiter reduzieren möchten, können Sie mit dem folgenden Befehl Laufzeitereignisse und den verwalteten Stapelprofiler deaktivieren.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>.NET-Anbieter

Die .NET Core-Runtime unterstützt die folgenden .NET-Anbieter. .NET Core verwendet zum Aktivieren von Ablaufverfolgungen mit `Event Tracing for Windows (ETW)` und `EventPipe` dieselben Schlüsselwörter.

| Anbietername                            | Information |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Runtimeanbieter](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[CLR-Runtime-Schlüsselwörter](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Rundownanbieter](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[CLR-Rundown-Schlüsselwörter](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Aktiviert den Beispielprofiler. |
