---
title: Debuggen von Linux-Sicherungskopien
description: In diesem Artikel erfahren Sie, wie Sie Speicherabbilder aus Linux-Umgebungen erfassen und analysieren.
ms.date: 08/27/2020
ms.openlocfilehash: d62295e165f56e32ef73ab628ca9ebd77a4435d1
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598296"
---
# <a name="debug-linux-dumps"></a>Debuggen von Linux-Sicherungskopien

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

## <a name="collect-dumps-on-linux"></a>Erfassen von Speicherabbildern unter Linux

Die beiden empfohlenen Methoden für das Erfassen von Speicherabbildern unter Linux sind die Tools [`dotnet-dump`](dotnet-dump.md) und [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md).

### <a name="managed-dumps-with-dotnet-dump"></a>Verwaltete Speicherabbilder mit `dotnet-dump`

Das Tool [`dotnet-dump`](dotnet-dump.md) ist einfach zu verwenden und hängt nicht von nativen Debuggern ab. `dotnet-dump` funktioniert auf einer Vielzahl von Linux-Plattformen (z. B. Alpine oder ARM32/ARM64), für die möglicherweise keine herkömmlichen Debugtools verfügbar sind. `dotnet-dump` erfasst jedoch nur den verwalteten Zustand und kann daher nicht zum Debuggen von Problemen in nativem Code verwendet werden. Die von `dotnet-dump` erfassten Speicherabbilder werden in einer Umgebung analysiert, die über das Betriebssystem und die Architektur verfügt mit dem bzw. der auch das Speicherabbild erstellt wurde. Alternativ kann das Tool [`dotnet-gcdump`](dotnet-gcdump.md) verwendet werden, das nur GC-Heapinformationen erfasst, aber Speicherabbilder erzeugt, die unter Windows analysiert werden können.

### <a name="core-dumps-with-createdump"></a>Kernspeicherabbilder mit `createdump`

Eine Alternative zum Tool `dotnet-dump`, das nur verwaltete Speicherabbilder erstellt, ist das für die Erstellung von Kernspeicherabbildern unter Linux empfohlene Tool [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md), das sowohl native als auch verwaltete Informationen enthält. Andere Tools, z. B. gdb oder gcore, können ebenfalls zum Erstellen von Kernspeicherabbildern verwendet werden. Bei diesen fehlt allerdings möglicherweise der für das verwaltete Debuggen erforderliche Zustand, was bei der Analyse zu „UNKNOWN“ als Typen- oder Funktionsnamen führt.

Das Tool `createdump` wird mit der .NET Core-Runtime installiert und befindet sich bei libcoreclr.so (in der Regel unter „/usr/share/dotnet/shared/Microsoft.NETCore.App/[Version]“). Es verwendet als primäres Argument eine Prozess-ID, für die ein Speicherabbild erfasst wird, und kann auch optionale Parameter verwenden, die angeben, welche Art von Speicherabbild erfasst werden soll (die Standardeinstellung ist ein Minidump mit Heap). Beispiele für Optionen:

- **`<input-filename>`**

  Die zu konvertierende Eingabe-Ablaufverfolgungsdatei. Standard: *trace.nettrace*.

### <a name="options"></a>Optionen

- **`-f|--name <output-filename>`**

  Hiermit wird die Datei angegeben, in die das Speicherabbild geschrieben werden soll. Der Standardwert ist „/tmp/coredump.%p“, wobei „%p“ die Prozess-ID des Zielprozesses ist.

- **`-n|--normal`**

  Erstellen eines Minidumps

- **`-h|--withheap`**

  Erstellen eines Minidumps mit Heap (Standard)

- **`-t|--triage`**

  Erstellen eines Selektierungsminidumps

- **`-u|--full`**

  Erstellen eines vollständigen Kernspeicherabbilds

- **`-d|--diag`**

  Aktivieren von Diagnosemeldungen

Beachten Sie, dass für das Erfassen von Kernspeicherabbildern entweder die Funktion `SYS_PTRACE` erforderlich ist oder dass `createdump` mit sudo oder su ausgeführt wird.

## <a name="analyze-dumps-on-linux"></a>Analysieren von Speicherabbildern unter Linux

Sowohl verwaltete Speicherabbilder, die mit `dotnet-dump` erfasst wurden, als auch mit `createdump` erfasste Kernspeicherabbilder können mithilfe des Befehls `dotnet-dump analyze` mit dem Tool `dotnet-dump` analysiert werden. `dotnet dump` erfordert, dass die Umgebung, die das Speicherabbild analysiert, über das gleiche Betriebssystem und die gleiche Architektur verfügt wie die Umgebung, in der das Speicherabbild erfasst wurde.

Alternativ kann [LLDB](https://lldb.llvm.org/) zum Analysieren von Kernspeicherabbildern unter Linux verwendet werden, wobei sowohl verwaltete als auch native Frames analysiert werden können. LLDB verwendet die SOS-Erweiterung zum Debuggen von verwaltetem Code. Das CLI-Tool [`dotnet-sos`](dotnet-sos.md) kann verwendet werden, um die SOS-Erweiterung zu installieren, die [viele nützliche Befehle](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) zum Debuggen von verwaltetem Code enthält. Zum Analysieren von .NET Core-Speicherabbildern benötigen LLDB und SOS die folgenden .NET Core-Binärdateien aus der Umgebung, in der das Speicherabbild erstellt wurde:

1. libmscordaccore.so
2. libcoreclr.so
3. dotnet (der Host, der zum Starten der App verwendet wird)

In den meisten Fällen können diese Binärdateien mit dem Tool [`dotnet-symbol`](dotnet-symbol.md) heruntergeladen werden. Wenn die erforderlichen Binärdateien nicht mit `dotnet-symbol` heruntergeladen werden können (z. B. wenn eine vollständig selbst erstellte private Version von .NET Core verwendet wurde), müssen die oben aufgeführten Dateien möglicherweise aus der Umgebung kopiert werden, in der das Speicherabbild erstellt wurde. Wenn sich diese Dateien nicht am selben Ort wie die Speicherabbilddatei befinden, können Sie über den LLDB-/SOS-Befehl `setclrpath <path>` den Pfad festlegen, von dem sie geladen werden sollen, und über `setsymbolserver -directory <path>` den Pfad, unter dem nach Symboldateien gesucht werden soll.

Sobald die erforderlichen Dateien verfügbar sind, kann das Speicherabbild in LLDB geladen werden, indem der dotnet-Host als die zu debuggende ausführbare Datei angegeben wird:

```console
lldb --core <dump-file> <host-program>
```

In der obigen Befehlszeile ist `<dump-file>` der Pfad des Speicherabbilds, das analysiert werden soll, und `<host-program>` das native Programm, das die .NET Core-Anwendung gestartet hat. Dabei handelt es sich in der Regel um die Binärdatei `dotnet`, außer die App ist eigenständig. In diesem Fall wird der Name der Anwendung ohne die Erweiterung „.dll“ angegeben.

Nach dem Start von LLDB muss möglicherweise der Befehl `setsymbolserver` verwendet werden, um auf den richtigen Symbolspeicherort zu verweisen (`setsymbolserver -ms` für den Symbolserver von Microsoft oder `setsymbolserver -directory <path>` zum Angeben eines lokalen Pfads). Native Symbole können durch Ausführen von `loadsymbols` geladen werden. Nun können [SOS-Befehle](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) verwendet werden, um das Speicherabbild zu analysieren.

## <a name="see-also"></a>Weitere Informationen

- Unter [dotnet-sos](dotnet-sos.md) finden Sie weitere Details zur Installation der SOS-Erweiterung.
- Unter [dotnet-symbol](dotnet-symbol.md) finden Sie weitere Details zur Installation und Verwendung des Symboldownloadtools.
- Im [.NET Core-Diagnoserepository](https://github.com/dotnet/diagnostics/blob/master/documentation/) finden Sie weitere Details zum Debuggen, einschließlich hilfreicher häufig gestellter Fragen.
- Unter [Installieren von LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) finden Sie Anleitungen zur Installation von LLDB für Linux oder Mac.
