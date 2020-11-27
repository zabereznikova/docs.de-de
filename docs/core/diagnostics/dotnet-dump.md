---
title: Diagnosetool „dotnet-dump“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-dump“ installieren und zum Erfassen und Analysieren von Windows- und Linux-Speicherabbildern ohne nativen Debugger verwenden.
ms.date: 11/17/2020
ms.openlocfilehash: ea9a70c4dc47b5006339e9a197712092eb66b241
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822203"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>Hilfsprogramm zum Sammeln und Analysieren von Speicherabbildern (dotnet-dump)

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

> [!NOTE]
> `dotnet-dump` für macOS wird nur mit .NET 5.0 und höheren Versionen unterstützt.

## <a name="install"></a>Installieren

Es gibt zwei Möglichkeiten, `dotnet-dump` herunterzuladen und zu installieren:

- **Globales dotnet-Tool:**

  Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-dump) `dotnet-dump` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- **Direkter Download:**

  Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:

  | OS  | Plattform |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-dump/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64) |

## <a name="synopsis"></a>Übersicht

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>Beschreibung

Mit dem globalen Tool `dotnet-dump` können Sie Windows- und Linux-Speicherabbilder ohne nativen Debugger wie `lldb` unter Linux sammeln und analysieren. Dieses Tool ist auf Plattformen wie z. B. Alpine Linux wichtig, bei denen kein voll funktionsfähiges Tool `lldb` verfügbar ist. Mit dem Tool `dotnet-dump` können Sie SOS-Befehle zum Analysieren von Abstürzen und dem Garbage Collector (GC) ausführen, es handelt sich jedoch nicht um einen nativen Debugger, sodass Elemente wie das Anzeigen von nativen Stapelrahmen nicht unterstützt werden.

## <a name="options"></a>Optionen

- **`--version`**

  Mit dieser Option wird die Version des Hilfsprogramms „dotnet-dump“ angezeigt.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="commands"></a>Befehle

| Befehl                                     |
| ------------------------------------------- |
| [dotnet-dump collect](#dotnet-dump-collect) |
| [dotnet-dump analyze](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>dotnet-dump collect

Erfasst ein Speicherabbild von einem Prozess.

### <a name="synopsis"></a>Übersicht

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>Optionen

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

- **`-p|--process-id <PID>`**

  Hiermit wird die ID-Nummer des Prozesses angegeben, von dem ein Speicherabbild gesammelt werden soll.

- **`-n|--name <name>`**

  Hiermit wird der Name des Prozesses angegeben, von dem ein Speicherabbild gesammelt werden soll.

- **`--type <Full|Heap|Mini>`**

  Gibt den Speicherabbildtyp an, der festlegt, welche Arten von Informationen vom Prozess gesammelt werden. Es gibt drei Typen:

  - `Full`: Das größte Speicherabbild, das den gesamten Arbeitsspeicher einschließlich der Modulimages enthält
  - `Heap`: eine große und relativ umfassende Sicherung, die Modullisten, Threadlisten, alle Stapel, Ausnahmeinformationen, Handleinformationen und den gesamten Arbeitsspeicher mit Ausnahme von zugeordneten Images enthält.
  - `Mini`: eine kleine Sicherung, die Modullisten, Threadlisten, Ausnahmeinformationen und alle Stapel enthält.

  Wenn nichts anderes angegeben wird, wird als Standard `Full` verwendet.

- **`-o|--output <output_dump_path>`**

  Der vollständige Pfad und der Dateiname, in den das gesammelte Speicherabbild geschrieben werden soll.

  Wenn nichts angegeben wird, gilt:

  - Unter Windows ist der Standard *.\dump_JJJJMMTT_HHMMSS.dmp*.
  - Unter Linux ist der Standard *./core_JJJJMMTT_HHMMSS*.

  JJJJMMTT entspricht Jahr/Monat/Tag, und HHMMSS entspricht Stunde/Minute/Sekunde.

- **`--diag`**

  Aktiviert die Diagnoseprotokollierung für die Speicherabbildsammlung.

## <a name="dotnet-dump-analyze"></a>dotnet-dump analyze

Startet eine interaktive Shell zum Durchsuchen eines Speicherabbilds. Die Shell akzeptiert verschiedene [SOS-Befehle](#analyze-sos-commands).

### <a name="synopsis"></a>Übersicht

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>Argumente

- **`<dump_path>`**

  Gibt den Pfad zu der Speicherabbilddatei an, die analysiert werden soll.

### <a name="options"></a>Optionen

- **`-c|--command <debug_command>`**

  Gibt den [Befehl](#analyze-sos-commands) an, der beim Starten in der Shell ausgeführt werden soll.

### <a name="analyze-sos-commands"></a>SOS-Befehle zum Analysieren

| Befehl                             | Funktion                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | Zeigt alle verfügbaren Befehle an.                                                               |
| `soshelp|help <command>`            | Zeigt den angegebenen Befehl an.                                                               |
| `exit|quit`                         | Beendet den interaktiven Modus.                                                                       |
| `clrstack <arguments>`              | Stellt eine Stapelüberwachung ausschließlich für verwalteten Code bereit.                                                  |
| `clrthreads <arguments>`            | Listet die ausgeführten verwalteten Threads auf.                                                            |
| `dumpasync <arguments>`             | Zeigt Informationen zu Computern im asynchronen Zustand im Heap der Garbage Collection an.                |
| `dumpassembly <arguments>`          | Zeigt Details zu einer Assembly an.                                                           |
| `dumpclass <arguments>`             | Zeigt Informationen zu einer EE-Klassenstruktur an der angegebenen Adresse an.                     |
| `dumpdelegate <arguments>`          | Zeigt Informationen zu einem Delegaten an.                                                        |
| `dumpdomain <arguments>`            | Zeigt Informationen zu allen AppDomains und allen Assemblys in den Domänen an.                |
| `dumpheap <arguments>`              | Zeigt Informationen zum Garbage Collector-Heap und Sammlungsstatistiken zu Objekten an.       |
| `dumpil <arguments>`                | Zeigt die Microsoft Intermediate Language (MSIL) an, die einer verwalteten Methode zugeordnet ist. |
| `dumplog <arguments>`               | Schreibt den Inhalt eines Belastungsprotokolls im Speicher in die angegebene Datei.                         |
| `dumpmd <arguments>`                | Zeigt Informationen zu einer MethodDesc-Struktur an der angegebenen Adresse an.                   |
| `dumpmodule <arguments>`            | Zeigt Informationen zu einer EE-Modulstruktur an der angegebenen Adresse an.                    |
| `dumpmt <arguments>`                | Zeigt Informationen zu einer Methodentabelle bei der angegebenen Adresse an.                           |
| `dumpobj <arguments>`               | Zeigt Informationen zu einem Objekt an der angegebenen Adresse an.                                       |
| `dso|dumpstackobjects <arguments>`  | Zeigt alle innerhalb der Grenzen des aktuellen Stapels gefundenen verwalteten Objekte an.                    |
| `eeheap <arguments>`                | Zeigt Informationen zu dem von internen Laufzeit-Datenstrukturen verwendeten Prozessspeicher an.              |
| `finalizequeue <arguments>`         | Zeigt alle für den Abschluss registrierten Objekte an.                                             |
| `gcroot <arguments>`                | Zeigt Informationen zu Verweisen auf ein Objekt (oder Stämmen eines Objekts) an der angegebenen Adresse an.              |
| `gcwhere <arguments>`               | Zeigt den Speicherort im GC-Heap des übergebenen Arguments an.                               |
| `ip2md <arguments>`                 | Zeigt die MethodDesc-Struktur an der angegebenen Adresse in JIT-Code an.                       |
| `histclear <arguments>`             | Gibt alle von der Familie der `hist*`-Befehle verwendeten Ressourcen frei.                                |
| `histinit <arguments>`              | Initialisiert die SOS-Strukturen aus dem Belastungsprotokoll, die in der zu debuggenden Komponente gespeichert sind.                     |
| `histobj <arguments>`               | Zeigt die Umsetzungen im Garbage Collection-Belastungsprotokoll im Zusammenhang mit `<arguments>` an.              |
| `histobjfind <arguments>`           | Zeigt alle Protokolleinträge an, die auf ein Objekt bei der angegebenen Adresse verweisen.               |
| `histroot <arguments>`              | Zeigt Informationen zu sowohl Heraufstufungen als auch Umsetzungen des angegebenen Stamms an.        |
| `lm|modules`                        | Zeigt die nativen Module im Prozess an.                                                   |
| `name2ee <arguments>`               | Zeigt die MethodTable-Struktur und die EEClass-Struktur für `<argument>` an.                |
| `pe|printexception <arguments>`     | Zeigt ein Objekt an, das von der Ausnahmeklasse an der Adresse `<argument>` abgeleitet wurde.             |
| `setsymbolserver <arguments>`       | Aktiviert die Symbolserverunterstützung.                                                             |
| `syncblk <arguments>`               | Zeigt die Informationen zum SyncBlock-Container an.                                                           |
| `threads|setthread <threadid>`      | Legt die ID des aktuellen Threads für die SOS-Befehle fest oder zeigt diese an.                                  |

## <a name="using-dotnet-dump"></a>Verwenden von `dotnet-dump`

Der erste Schritt besteht im Sammeln eines Speicherabbilds. Dieser Schritt kann übersprungen werden, wenn bereits ein Kernspeicherabbild generiert wurde. Das Betriebssystem und die integrierte [Speicherabbild-Generierungsfunktion](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) der .NET Core-Runtime können Kernspeicherabbilder erstellen.

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

Analysieren Sie nun das Kernspeicherabbild mit dem Befehl `analyze`:

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

Durch diese Aktion wird eine interaktive Sitzung aufgerufen, die Befehle wie die folgenden akzeptiert:

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

So zeigen Sie einen Ausnahmefehler an, der Ihre App beendet hat

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a>Spezielle Anweisungen für Docker

Wenn Sie den Prozess unter Docker ausführen, sind für die Speicherabbildsammlung `SYS_PTRACE`-Funktionen (`--cap-add=SYS_PTRACE` oder `--privileged`) erforderlich.

In Linux-Docker-Images des Microsoft .NET Core SDK können einige `dotnet-dump`-Befehle folgende Ausnahme auslösen:

> Ausnahmefehler: System.DllNotFoundException: Ausnahme, da die freigegebene Bibliothek „libdl.so“ oder eine ihrer Abhängigkeiten nicht geladen werden kann.

Um dieses Problem zu umgehen, installieren Sie das Paket „libc6-dev“.

## <a name="see-also"></a>Weitere Informationen

- [Blog zum Sammeln und Analysieren von Speicherabbildern](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [Heapanalysetool (dotnet-gcdump)](dotnet-gcdump.md)
