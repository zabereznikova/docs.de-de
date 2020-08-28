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
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Heapanalysetool (dotnet-gcdump)

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher

## <a name="install-dotnet-gcdump"></a>Installieren von dotnet-gcdump

Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a>Übersicht

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Beschreibung

Mit dem globalen Tool `dotnet-gcdump` können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen. Dabei wird die EventPipe-Technologie verwendet, bei der es sich um eine plattformübergreifende Alternative zur Ereignisablaufverfolgung für Windows handelt. GC-Speicherabbilder werden durch das Auslösen einer automatischen Speicherbereinigung im Zielprozess, das Aktivieren spezieller Ereignisse und das wiederholte Generieren des Graphs der Objektstämme aus dem Ereignisdatenstrom erstellt. Dieser Prozess ermöglicht das Erfassen von GC-Speicherabbildern während der Prozessausführung mit minimalem Aufwand. Diese Speicherabbilder sind für verschiedene Szenarios nützlich:

- Vergleichen der Anzahl von Objekten auf dem Heap zu verschiedenen Zeitpunkten
- Analysieren des Stamms von Objekten (Beantwortung von Fragen wie „Was verweist noch auf diesen Typ?“)
- Erfassen allgemeiner Statistiken über die Anzahl von Objekten auf dem Heap

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a>Anzeigen des von dotnet-gcdump erfassten GC-Speicherabbilds

Unter Windows können `.gcdump`-Dateien zur Analyse in [PerfView](https://github.com/microsoft/perfview) oder in Visual Studio angezeigt werden. Derzeit gibt es keine Möglichkeit, eine `.gcdump`-Datei auf anderen Plattformen als Windows zu öffnen.

Sie können mehrere `.gcdump`-Dateien erfassen und gleichzeitig in Visual Studio öffnen, um sie zu vergleichen.

## <a name="options"></a>Tastatur

- **`--version`**

  Hiermit wird die Version des `dotnet-gcdump`-Hilfsprogramms angezeigt.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## `dotnet-gcdump collect`

Hiermit wird ein GC-Speicherabbild aus einem derzeit laufenden Prozess erfasst.

### <a name="synopsis"></a>Übersicht

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a>Optionen

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

- **`-p|--process-id <pid>`**

  Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.

- **`-o|--output <gcdump-file-path>`**

  Dies ist der Pfad, in den erfasste GC-Speicherabbilder geschrieben werden sollen. Der Standardwert ist *.\\YYYYMMDD\_HHMMSS\_\<pid>.gcdump*.

- **`-v|--verbose`**

  Hiermit wird das Protokoll während der Erfassung des GC-Speicherabbilds ausgegeben.

- **`-t|--timeout <timeout>`**

  Hiermit wird die Erfassung des GC-Speicherabbilds angehalten, wenn diese länger als eine bestimmte Anzahl von Sekunden dauert. Der Standardwert ist 30.

- **`-n|--name <name>`**

  Dies ist der Name des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.

## `dotnet-gcdump ps`

Hiermit werden die dotnet-Prozesse aufgelistet, für die GC-Speicherabbilder erfasst werden können.

### <a name="synopsis"></a>Übersicht

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

Hiermit wird ein Bericht aus einem zuvor generierten GC-Speicherabbild oder aus einem laufenden Prozess generiert und in `stdout` geschrieben.

### <a name="synopsis"></a>Übersicht

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a>Optionen

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

- **`-p|--process-id <pid>`**

  Dies ist die ID des Prozesses, von dem das GC-Speicherabbild erfasst werden soll.

- **`-t|--report-type <HeapStat>`**

  Dies ist der Typ des zu generierenden Berichts. Verfügbare Optionen: HeapStat (Standard)

## <a name="troubleshoot"></a>Problembehandlung

- In der gcdump-Datei sind keine Typinformationen enthalten.

   Vor .NET Core 3.1 gab es ein Problem, bei dem ein Typcache zwischen gcdump-Dateien nicht gelöscht wurde, wenn diese mit EventPipe aufgerufen wurden. Dies führte dazu, dass die Ereignisse, die zum Bestimmen der Typinformationen benötigt werden, für die zweite und nachfolgende gcdump-Dateien nicht gesendet wurden. Dieses Problem wurde in .NET Core 3.1-preview2 behoben.

- COM- und statische Typen sind nicht im GC-Speicherabbild enthalten.

   Vor .NET Core 3.1-preview2 gab es ein Problem, bei dem statische und COM-Typen nicht gesendet wurden, wenn das GC-Speicherabbild über EventPipe aufgerufen wurde. Dieses Problem wurde in .NET Core 3.1-preview2 behoben.
