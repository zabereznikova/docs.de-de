---
title: Diagnosetool „dotnet-gcdump“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-gcdump“ installieren und zum Erfassen von Garbage Collector-Speicherabbildern (GC) von .NET-Liveprozessen mithilfe von EventPipe im Zusammenhang mit .NET verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: fe7772eed642daadbd1754627751f58d0ab57b8e
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188568"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Heapanalysetool (dotnet-gcdump)

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher

## <a name="install"></a>Installieren

Es gibt zwei Möglichkeiten, `dotnet-gcdump` herunterzuladen und zu installieren:

- **Globales dotnet-Tool:**

  Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- **Direkter Download:**

  Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:

  | OS  | Plattform |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-gcdump/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64) |

> [!NOTE]
> Sie benötigen eine entsprechende x86-Version des Tools, um `dotnet-gcdump` für eine x86-App verwenden zu können.

## <a name="synopsis"></a>Übersicht

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Beschreibung

Das globale `dotnet-gcdump`-Tool sammelt Garbage Collector-Speicherabbilder (GC) von .NET-Liveprozessen mithilfe von [EventPipe](./eventpipe.md). GC-Speicherabbilder werden durch das Auslösen einer automatischen Speicherbereinigung im Zielprozess, das Aktivieren spezieller Ereignisse und das wiederholte Generieren des Graphs der Objektstämme aus dem Ereignisdatenstrom erstellt. Dieser Prozess ermöglicht das Erfassen von GC-Speicherabbildern während der Prozessausführung mit minimalem Aufwand. Diese Speicherabbilder sind für verschiedene Szenarios nützlich:

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

> [!WARNING]
> Dieser Befehl löst eine (vollständige) Garbage Collection (GC) der Generation 2 aus, um den GC-Heap zu durchlaufen. Dadurch kann die Runtime für längere Zeit unterbrochen werden – insbesondere dann, wenn der GC-Heap groß ist. Verwenden Sie diesen Befehl nicht in leistungsabhängigen Umgebungen, wenn der GC-Heap groß ist.

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

> [!NOTE]
> Unter Linux und macOS erwartet dieser Befehl, dass die Zielanwendung und `dotnet-gcdump` die gleiche `TMPDIR`-Umgebungsvariable verwenden. Andernfalls führt der Befehl zu einem Timeout.

> [!NOTE]
> Wenn Sie mit `dotnet-gcdump` ein Garbage Collection-Speicherabbild erfassen möchten, muss der Befehl vom Rootbenutzer oder dem Benutzer ausgeführt werden, der den Zielprozess ausführt. Andernfalls kann das Tool keine Verbindung mit dem Zielprozess herstellen.

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
