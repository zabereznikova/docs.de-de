---
title: 'Tutorial: Debuggen eines Arbeitsspeicherverlusts'
description: Erfahren Sie, wie Sie einen Arbeitsspeicherverlust in .NET Core debuggen.
ms.topic: tutorial
ms.date: 04/20/2020
ms.openlocfilehash: 7fa87a411606e81ffe91348c3cbce5f258a6e4e2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538591"
---
# <a name="debug-a-memory-leak-in-net-core"></a>Debuggen eines Arbeitsspeicherverlusts in .NET Core

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher

In diesem Tutorial werden die Tools zum Analysieren eines .NET Core-Arbeitsspeicherverlusts vorgestellt.

In diesem Tutorial wird eine Beispiel-App verwendet, die absichtlich zu einem Arbeitsspeicherverlust führt. Das Beispiel wird als Übung bereitgestellt. Sie können auch eine App analysieren, die unbeabsichtigt einen Arbeitsspeicherverlust verursacht.

In diesem Tutorial werden Sie Folgendes durchführen:

> [!div class="checklist"]
>
> - Untersuchen der verwalteten Speicherauslastung mit [dotnet-counters](dotnet-counters.md).
> - Generieren einer Dumpdatei.
> - Analysieren der Speicherauslastung mithilfe der Dumpdatei.

## <a name="prerequisites"></a>Voraussetzungen

Im Tutorial wird Folgendes verwendet:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher
- [dotnet-trace](dotnet-trace.md) zu Auflisten von Prozessen.
- [dotnet-counters](dotnet-counters.md) zum Untersuchen der verwalteten Speicherauslastung.
- [dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Dumpdatei.
- Eine [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/)-App für die Diagnose.

In diesem Tutorial wird davon ausgegangen, dass das Beispiel und die Tools installiert und einsatzbereit sind.

## <a name="examine-managed-memory-usage"></a>Untersuchen der verwalteten Speicherauslastung

Bevor Sie mit dem Erfassen von Diagnosedaten beginnen, um die Grundursache für dieses Szenario zu ermitteln, müssen Sie sicherstellen, dass tatsächlich ein Arbeitsspeicherverlust stattfindet (Vergrößerung des Arbeitsspeichers). Sie können das Tool [dotnet-counters](dotnet-counters.md) verwenden, um dies zu bestätigen.

Öffnen Sie ein Konsolenfenster, und navigieren Sie zu dem Verzeichnis, das Sie zum Herunterladen und Entzippen des [Beispieldebugziels](/samples/dotnet/samples/diagnostic-scenarios/) verwendet haben. Führen Sie das Ziel aus:

```dotnetcli
dotnet run
```

Suchen Sie in einer separaten Konsole mithilfe des Tools [dotnet-trace](dotnet-trace.md) nach der Prozess-ID:

```console
dotnet-trace ps
```

Die Ausgabe sollte in etwa wie folgt aussehen:

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

Überprüfen Sie nun die verwaltete Speicherauslastung mit dem Tool [dotnet-counters](dotnet-counters.md). Das `--refresh-interval` gibt die Anzahl der Sekunden zwischen Aktualisierungen an:

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

Die Liveausgabe sollte in etwa wie folgt aussehen:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

Konzentrieren Sie sich auf diese Zeile:

```console
    GC Heap Size (MB)                                  4
```

Sie können sehen, dass der verwaltete Heapspeicher nach dem Start 4 MB groß ist.

Verwenden Sie nun die URL `https://localhost:5001/api/diagscenario/memleak/20000`.

Beachten Sie, dass die Speicherauslastung auf 30 MB angewachsen ist.

```console
    GC Heap Size (MB)                                 30
```

Wenn Sie die Speicherauslastung überwachen, können Sie sicher sagen, dass der Arbeitsspeicher zunimmt oder Verluste aufweist. Der nächste Schritt besteht darin, die richtigen Daten für die Arbeitsspeicheranalyse zu erfassen.

### <a name="generate-memory-dump"></a>Generieren eines Speicherabbilds

Wenn Sie mögliche Arbeitsspeicherverluste analysieren, benötigen Sie Zugriff auf den Arbeitsspeicherheap der App. Anschließend können Sie den Arbeitsspeicherinhalt analysieren. Wenn Sie Beziehungen zwischen Objekten betrachten, erstellen Sie Theorien dazu, warum der Arbeitsspeicher nicht freigegeben wird. Eine gängige Quelle für Diagnosedaten ist ein Speicherabbild unter Windows oder der entsprechende Core Dump unter Linux. Zum Generieren eines Speicherabbilds einer .NET Core-Anwendung können Sie das Tool [dotnet-dump)](dotnet-dump.md) verwenden.

Führen Sie den folgenden Befehl aus, um einen Linux-Core Dump zu generieren, indem Sie das zuvor erstellte [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/) verwenden.

```dotnetcli
dotnet-dump collect -p 4807
```

Das Ergebnis ist ein Core Dump, der sich im gleichen Ordner befindet.

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a>Neustarten des fehlgeschlagenen Prozesses

Nachdem das Speicherabbild erfasst wurde, sollten Sie über genügend Informationen verfügen, um den fehlgeschlagenen Prozess zu diagnostizieren. Wenn der fehlgeschlagene Prozess auf einem Produktionsserver ausgeführt wird, ist dies jetzt der ideale Zeitpunkt für die kurzfristige Wartung, indem der Prozess neu gestartet wird.

In diesem Tutorial benötigen Sie das [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/) nicht mehr, und Sie können es schließen. Navigieren Sie zu dem Terminal, über das der Server gestartet wurde, und drücken Sie <kbd>STRG+C</kbd>.

### <a name="analyze-the-core-dump"></a>Analysieren des Speicherabbilds

Nachdem Sie nun ein Speicherabbild generiert haben, verwenden Sie das Tool [dotnet-dump](dotnet-dump.md), um das Speicherabbild zu analysieren:

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

Dabei ist `core_20190430_185145` der Name des Speicherabbilds, das Sie analysieren möchten.

> [!NOTE]
> Wenn eine Fehlermeldung angezeigt wird, die besagt, dass *libdl.so* nicht gefunden wurde, müssen Sie ggf. das Paket *libc6-dev* installieren. Weitere Informationen finden Sie unter [Voraussetzungen für .NET Core unter Linux](../install/linux.md).

Es wird eine Eingabeaufforderung angezeigt, in der Sie SOS-Befehle eingeben können. Im Allgemeinen gilt die erste Untersuchung dem Gesamtstatus des verwalteten Heaps:

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

Hier können Sie sehen, dass die meisten Objekte entweder `String`- oder `Customer`-Objekte sind.

Sie können den Befehl `dumpheap` erneut mit der-Methodentabelle (MT) verwenden, um eine Liste aller `String`-Instanzen zu erhalten:

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

Sie können jetzt den Befehl `gcroot` in einer `System.String`-Instanz verwenden, um zu sehen, wie und warum das Objekt über Rootzugriff verfügt. Seien Sie geduldig, da die Ausführung dieses Befehls mehrere Minuten bei einem Heap von 30 MB benötigt:

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

Sie können sehen, dass `String` direkt vom `Customer`-Objekt verwendet und indirekt von einem `CustomerCache`-Objekt verwendet wird.

Sie können weitere Speicherabbilder für Objekte erstellen, um zu erkennen, dass die meisten `String`-Objekte einem ähnlichen Muster folgen. An diesem Punkt hat die Untersuchung genügend Informationen bereitgestellt, um die Grundursache im Code zu ermitteln.

Mit diesem allgemeinen Verfahren können Sie die Quelle von größeren Arbeitsspeicherverlusten identifizieren.

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

In diesem Tutorial haben Sie einen Beispielwebserver gestartet. Dieser Server sollte heruntergefahren worden sein, wie im Abschnitt [Neustarten des fehlgeschlagenen Vorgangs](#restart-the-failed-process) beschrieben.

Sie können auch die erstellte Speicherabbilddatei löschen.

## <a name="see-also"></a>Siehe auch

- [dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen
- [dotnet-counters](dotnet-counters.md) zum Überprüfen der Auslastung des verwalteten Speichers
- [dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei.
- [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Debuggen von hoher CPU-Auslastung in .NET Core](debug-highcpu.md)
