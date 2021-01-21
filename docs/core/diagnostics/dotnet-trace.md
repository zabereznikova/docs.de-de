---
title: Diagnosetool „dotnet-trace“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-trace“ installieren und mithilfe der .NET-Komponente „EventPipe“ zum Erfassen von .NET-Ablaufverfolgungen in Bezug auf einen laufenden Prozesses ohne den nativen Profiler verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: 93698882e94f58eda84abebc277e1eacfe22a3da
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189700"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>dotnet-trace-Hilfsprogramm für Leistungsanalysen

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

## <a name="install"></a>Installieren

Es gibt zwei Möglichkeiten, `dotnet-trace` herunterzuladen und zu installieren:

- **Globales dotnet-Tool:**

  Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- **Direkter Download:**

  Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:

  | OS  | Plattform |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-trace/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64) |

> [!NOTE]
> Sie benötigen eine entsprechende x86-Version des Tools, um `dotnet-trace` für eine x86-App verwenden zu können.

## <a name="synopsis"></a>Übersicht

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Beschreibung

Das `dotnet-trace`-Tool:

* Bei diesem Tool handelt es sich um ein plattformübergreifendes .NET Core-Tool.
* Es ermöglicht das Sammeln von .NET Core-Ablaufverfolgungen eines ausgeführten Prozesses ohne nativen Profiler.
* Es basiert auf der Komponente [`EventPipe`](./eventpipe.md) der .NET Core-Runtime.
* Das Tool bietet unter Windows, Linux und macOS die gleiche Oberfläche.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

- **`--version`**

  Mit dieser Option wird die Version des Hilfsprogramms „dotnet-trace“ angezeigt.

## <a name="commands"></a>Befehle

| Befehl                                                   |
|-----------------------------------------------------------|
| [dotnet-trace collect](#dotnet-trace-collect)             |
| [dotnet-trace convert](#dotnet-trace-convert)             |
| [dotnet-trace ps](#dotnet-trace-ps)                       |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Sammelt eine Diagnoseablaufverfolgung von einem ausgeführten Prozess.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a>Optionen

- **`--buffersize <size>`**

  Legt die Größe des Ringpuffers im Arbeitsspeicher in Megabyte fest. Standard: 256 MB.

- **`--clreventlevel <clreventlevel>`**

  Ausführlichkeit von auszugebenden CLR-Ereignissen.

- **`--clrevents <clrevents>`**

  Diese Option generiert eine Liste der zu aktivierenden Schlüsselwörter für CLR-Anbieter, die durch `+`-Zeichen getrennt wird. Mit dieser einfachen Zuordnung können Sie Schlüsselwörter für Ereignisse über Zeichenfolgenaliase anstelle von Hexadezimalwerten angeben. `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` fordert beispielsweise die gleichen Ereignisse wie `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational` an. Die folgende Tabelle ist eine Liste der verfügbaren Schlüsselwörter:

  | Zeichenfolgenalias des Schlüsselworts | Hexadezimalwert des Schlüsselworts |
  | ------------ | ------------------- |
  | `gc` | `0x1` |
  | `gchandle` | `0x2` |
  | `fusion` | `0x4` |
  | `loader` | `0x8` |
  | `jit` | `0x10` |
  | `ngen` | `0x20` |
  | `startenumeration` | `0x40` |
  | `endenumeration` | `0x80` |
  | `security` | `0x400` |
  | `appdomainresourcemanagement` | `0x800` |
  | `jittracing` | `0x1000` |
  | `interop` | `0x2000` |
  | `contention` | `0x4000` |
  | `exception` | `0x8000` |
  | `threading` | `0x10000` |
  | `jittedmethodiltonativemap` | `0x20000` |
  | `overrideandsuppressngenevents` | `0x40000` |
  | `type` | `0x80000` |
  | `gcheapdump` | `0x100000` |
  | `gcsampledobjectallocationhigh` | `0x200000` |
  | `gcheapsurvivalandmovement` | `0x400000` |
  | `gcheapcollect` | `0x800000` |
  | `gcheapandtypenames` | `0x1000000` |
  | `gcsampledobjectallocationlow` | `0x2000000` |
  | `perftrack` | `0x20000000` |
  | `stack` | `0x40000000` |
  | `threadtransfer` | `0x80000000` |
  | `debugger` | `0x100000000` |
  | `monitoring` | `0x200000000` |
  | `codesymbols` | `0x400000000` |
  | `eventsource` | `0x800000000` |
  | `compilation` | `0x1000000000` |
  | `compilationdiagnostic` | `0x2000000000` |
  | `methoddiagnostic` | `0x4000000000` |
  | `typediagnostic` | `0x8000000000` |

  Weitere Informationen zu CLR-Anbietern finden Sie in der [Referenzdokumentation zu .NET-Runtimeanbietern](../../fundamentals/diagnostics/runtime-events.md).

- **`--format {Chromium|NetTrace|Speedscope}`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest. Der Standardwert ist `NetTrace`.

- **`-n, --name <name>`**

  Der Name des Prozesses, von dem die Ablaufverfolgung erfasst werden soll.

- **`--diagnostic-port <path-to-port>`**

  Hierbei handelt es sich um den Namen des zu erstellenden Diagnoseports. Informationen dazu, wie Sie diese Option zum Erfassen einer Überwachung ab dem App-Start verwenden, finden Sie unter [Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start](#use-diagnostic-port-to-collect-a-trace-from-app-startup).

- **`-o|--output <trace-file-path>`**

  Der Ausgabepfad für die gesammelten Ablaufverfolgungsdaten. Wenn dieser Wert nicht angegeben ist, wird standardmäßig `trace.nettrace` verwendet.

- **`-p|--process-id <PID>`**

  Dies ist die Prozess-ID, von der die Ablaufverfolgung erfasst werden soll.

- **`--profile <profile-name>`**

  Ein benannter vordefinierter Satz von Anbieterkonfigurationen, mit dem gängige Ablaufverfolgungsszenarien kurz und präzise angegeben werden können. Die folgenden Profile sind verfügbar:

 | Profil | Beschreibung |
 |---------|-------------|
 |`cpu-sampling`|Nützlich für die Nachverfolgung der CPU-Auslastung und allgemeine .NET-Laufzeitinformationen. Dies ist die Standardoption, wenn kein Profil oder Anbieter angegeben wird.|
 |`gc-verbose`|Verfolgt GC-Sammlungen und Beispielobjektzuordnungen.|
 |`gc-collect`|Verfolgt GC-Sammlungen nur mit sehr geringem Mehraufwand nach.|

- **`--providers <list-of-comma-separated-providers>`**

  Eine durch Trennzeichen getrennte Liste von `EventPipe`-Anbietern, die aktiviert werden sollen. Diese Anbieter ergänzen die durch `--profile <profile-name>` implizierten Anbieter. Wenn für einen bestimmten Anbieter eine Inkonsistenz vorliegt, hat diese Konfiguration Vorrang vor der impliziten Konfiguration aus dem Profil.

  Diese Liste der Anbieter hat das folgende Format:

  - `Provider[,Provider]`
  - `Provider` hat das Format: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` hat das Format: `[key1=value1][;key2=value2]`.

- **`-- <command>` (nur für Zielanwendungen, die .NET 5.0 ausführen)**

  Nach den Sammlungskonfigurationsparametern kann der Benutzer `--` gefolgt von einem Befehl anfügen, um eine .NET-Anwendung mit mindestens Common Language Runtime 5.0 zu starten. Das kann beim Diagnostizieren von Problemen hilfreich sein, die am Anfang des Prozesses auftreten, wie Leistungsprobleme beim Start oder Assemblylade- und Binderfehler.

  > [!NOTE]
  > Wenn Sie diese Option verwenden, wird der erste Prozess von .NET 5.0 überwacht, der mit dem Tool kommuniziert, d. h. der Befehl erfasst nur die erste Anwendung, wenn mehrere .NET-Anwendungen gestartet werden. Sie sollten daher diese Option für eigenständige Anwendungen oder die Option `dotnet exec <app.dll>` verwenden.

> [!NOTE]
> Das Beenden der Überwachung dauert bei großen Anwendungen möglicherweise lang (bis zu mehrere Minuten). Die Runtime muss den Typcache für den gesamten verwalteten Code senden, der bei der Überwachung erfasst wurde.

> [!NOTE]
> Unter Linux und macOS erwartet dieser Befehl, dass die Zielanwendung und `dotnet-trace` die gleiche `TMPDIR`-Umgebungsvariable verwenden. Andernfalls führt der Befehl zu einem Timeout.

> [!NOTE]
> Wenn Sie mit `dotnet-trace` eine Überwachung erfassen möchten, muss der Befehl vom Rootbenutzer oder dem Benutzer ausgeführt werden, der den Zielprozess ausführt. Andernfalls kann das Tool keine Verbindung mit dem Zielprozess herstellen.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Konvertiert `nettrace`-Ablaufverfolgungen in alternative Formate zur Verwendung mit alternativen Tools für die Ablaufverfolgungsanalyse.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a>Argumente

- **`<input-filename>`**

  Die zu konvertierende Eingabe-Ablaufverfolgungsdatei. Standard: *trace.nettrace*.

### <a name="options"></a>Optionen

- **`--format <Chromium|NetTrace|Speedscope>`**

  Legt das Ausgabeformat für die Konvertierung der Ablaufverfolgungsdatei fest.

- **`-o|--output <output-filename>`**

  Ausgabedateiname. Die Erweiterung des Zielformats wird hinzugefügt.

> [!NOTE]
> Das Konvertieren von `nettrace`-Dateien in `chromium`- oder `speedscope`-Dateien kann nicht rückgängig gemacht werden. `speedscope`- und `chromium`-Dateien enthalten nicht alle Informationen, die zum Rekonstruieren von `nettrace`-Dateien erforderlich sind. Mit dem `convert`-Befehl bleibt die ursprüngliche `nettrace`-Datei jedoch erhalten. Löschen Sie daher diese Datei nicht, wenn Sie beabsichtigen, sie später irgendwann zu öffnen.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

 Listet die dotnet-Prozesse auf, aus denen Ablaufverfolgungen erfasst werden können.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Listet vordefinierte Ablaufverfolgungsprofile mit einer Beschreibung der Anbieter und Filter in den einzelnen Profilen auf.

### <a name="synopsis"></a>Übersicht

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Sammeln einer Ablaufverfolgung mit dotnet-trace

So sammeln Sie Ablaufverfolgungen mit `dotnet-trace`:

- Ermitteln Sie die Prozess-ID (PID) der .NET Core-Anwendung, von der Ablaufverfolgungen gesammelt werden sollen.

  - Unter Windows können Sie z. B. den Task-Manager oder den `tasklist`-Befehl verwenden.
  - Verwenden Sie unter Linux beispielsweise den `ps`-Befehl.
  - [dotnet-trace ps](#dotnet-trace-ps)

- Führen Sie den folgenden Befehl aus:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Halten Sie den Sammelvorgang durch Drücken der `<Enter>`-Taste an. `dotnet-trace` beendet das Protokollieren von Ereignissen in der Datei *trace.nettrace*.

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a>Starten einer untergeordneten Anwendung und Erfassen einer Ablaufverfolgung vom Start mithilfe von „dotnet-trace“

> [!IMPORTANT]
> Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.

Manchmal kann es nützlich sein, eine Ablaufverfolgung eines Prozesses vom Start zu erfassen. Bei Anwendungen mit .NET 5.0 oder höher können Sie dies mithilfe von „dotnet-trace“ ausführen.

Dadurch wird `hello.exe` mit `arg1` und `arg2` als Befehlszeilenargumenten gestartet, und der Ablauf wird vom Start der Runtime verfolgt:

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

Der oben gezeigte Befehl generiert eine Ausgabe ähnlich der folgenden:

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

Sie können das Erfassen der Ablaufverfolgung durch Drücken der Taste `<Enter>` oder `<Ctrl + C>` abbrechen. Dadurch wird auch `hello.exe` beendet.

> [!NOTE]
> Wenn `hello.exe` über „dotnet-trace“ gestartet wird, werden die Eingaben/Ausgaben umgeleitet, und Sie können nicht mit stdin/stdout interagieren.
> Wenn Sie das Tool über STRG+C oder SIGTERM beenden, werden sowohl das Tool als auch der untergeordnete Prozess sicher beendet.
> Wenn der untergeordnete Prozess vor dem Tool beendet wird, wird das Tool ebenfalls beendet, und die Ablaufverfolgung sollte sicher angezeigt werden können.

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a>Verwenden von Diagnoseports zum Erfassen einer Überwachung ab dem App-Start

  > [!IMPORTANT]
  > Das funktioniert nur bei Anwendungen mit .NET 5.0 oder höher.

Der Diagnoseport ist ein neues Runtimefeature, das in .NET 5 hinzugefügt wurde und es Ihnen ermöglicht, die Ablaufverfolgung beim Start der App zu starten. Dies können Sie mit `dotnet-trace` einrichten, indem Sie `dotnet-trace collect -- <command>` wie in den Beispielen oben oder die Option `--diagnostic-port` verwenden.

Die Verwendung von `dotnet-trace <collect|monitor> -- <command>` zum Starten der Anwendung als untergeordneter Prozess ist die einfachste Möglichkeit, schnell mit der Überwachung ab dem Start zu beginnen.

Wenn Sie allerdings präzisere Kontrolle über die Lebensdauer der überwachten App wünschen (z. B., damit die App nur in den ersten 10 Minuten überwacht und dann weiterhin ausgeführt wird) oder mithilfe der CLI mit der App interagieren müssen, können Sie die Option `--diagnostic-port` verwenden, um sowohl die überwachte Ziel-App als auch `dotnet-trace` zu steuern.

1. Der folgende Befehl sorgt dafür, dass `dotnet-trace` einen Diagnosesocket namens `myport.sock` erstellt und auf eine Verbindung wartet.

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    Ausgabe:

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. Starten Sie die Zielanwendung in einer separaten Konsole mit der Umgebungsvariable `DOTNET_DiagnosticPorts`, die Sie auf den Wert in der `dotnet-trace`-Ausgabe festlegen.

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    Dadurch sollte `dotnet-trace` die Ablaufverfolgung für `my-dotnet-app` starten können:

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > Das Starten Ihrer App mit `dotnet run` kann sich als problematisch erweisen, da die .NET-CLI viele untergeordnete Prozesse erzeugen kann, bei denen es sich nicht um Ihre App handelt. Diese können vor Ihrer App eine Verbindung mit `dotnet-trace` herstellen, wodurch Ihre App zur Laufzeit angehalten wird. Es wird empfohlen, dass Sie direkt eine eigenständige Version der App oder `dotnet exec` verwenden, um die Anwendung zu starten.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Anzeigen der von dotnet-trace erfassten Ablaufverfolgung

Unter Windows können *.nettrace*-Dateien in [PerfView](https://github.com/microsoft/perfview) für die Analyse angezeigt werden: Bei auf anderen Plattformen gesammelten Ablaufverfolgungen können Sie die Ablaufverfolgungsdatei auf einen Windows-Computer verschieben, um sie in PerfView anzuzeigen.

Unter Linux kann die Ablaufverfolgung angezeigt werden, indem das Ausgabeformat von `dotnet-trace` in `speedscope` geändert wird. Das Format der Ausgabedatei kann mit der `-f|--format`-Option geändert werden – `-f speedscope` führt dazu, dass `dotnet-trace` eine `speedscope`-Datei generiert. Sie können zwischen `nettrace` (der Standardoption) und `speedscope` wählen. `Speedscope`-Dateien können unter <https://www.speedscope.app> geöffnet werden.

> [!NOTE]
> Die .net Core-Laufzeit generiert Ablauf Verfolgungen im `nettrace`-Format. Die Ablaufverfolgungen werden nach Abschluss der Ablaufverfolgung in speedscope (sofern angegeben) konvertiert. Da bei einigen Konvertierungen Datenverluste auftreten können, wird die ursprüngliche `nettrace`-Datei neben der konvertierten Datei beibehalten.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Verwenden von dotnet-trace zum Sammeln von Leistungsindikatorwerten über die Zeit

`dotnet-trace` kann:

* `EventCounter` für die grundlegende Systemüberwachung in leistungsabhängigen Umgebungen verwenden. Beispielsweise in der Produktion.
* Ablaufverfolgungen sammeln, damit diese nicht in Echtzeit angezeigt werden müssen.

Um z. B. Laufzeit-Leistungsindikatorwerte zu sammeln, verwenden Sie den folgenden Befehl:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Der obige Befehl sorgt dafür, dass die Laufzeit-Leistungsindikatoren einmal pro Sekunde gemeldet werden. Dies entspricht einer Systemüberwachung mit geringem Aufwand. Indem Sie `EventCounterIntervalSec=1` durch einen höheren Wert ersetzen (z. B. 60), können Sie eine kleinere Ablaufverfolgung mit geringerer Granularität in den Leistungsindikatordaten sammeln.

Der folgende Befehl reduziert den Mehraufwand und die Größe der Ablaufverfolgung stärker als der vorherige Befehl:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Der obige Befehl deaktiviert Laufzeitereignisse und den verwalteten Stapelprofiler.

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a>Vermeiden der Eingabe langer Befehle mithilfe der .rsp-Datei

Sie können `dotnet-trace` mit einer `.rsp`-Datei starten, die die zu übergebenden Argumente enthält. Dies kann hilfreich sein, wenn Sie Anbieter aktivieren, die lange Argumente erwarten, oder wenn Sie eine Shellumgebung verwenden, die Zeichen entfernt.

Es kann z. B. mühsam sein, den folgenden Anbieter bei jeder gewünschten Überwachung komplett tippen zu müssen:

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

Darüber hinaus enthält das Argument im vorherigen Beispiel `"`. Da Anführungszeichen nicht von jeder Shell gleich behandelt werden, können bei der Verwendung unterschiedlicher Shells verschiedene Probleme auftreten. Beispielsweise unterscheidet sich der Befehl, der in `zsh` eingegeben werden muss, von dem in `cmd`.

Statt den Befehl jedes Mal zu tippen, können Sie den folgenden Text in einer Datei mit dem Namen `myprofile.rsp` speichern.

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

Wenn Sie `myprofile.rsp` gespeichert haben, können Sie `dotnet-trace` mit dieser Konfiguration über den folgenden Befehl öffnen:

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a>Siehe auch

- [Bekannte Ereignisanbieter in .NET](well-known-event-providers.md)
