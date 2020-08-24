---
title: '.NET Core: Debuggen von Deadlocks'
description: In diesem Tutorial lernen Sie, wie Sie ein Sperrproblem in .NET Core debuggen.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 6f060e1ae801eb4eacbbd1fb67110f827c37f597
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557879"
---
# <a name="debug-a-deadlock-in-net-core"></a>Debuggen eines Deadlocks in .NET Core

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher

In diesem Tutorial erfahren Sie, wie Sie ein Deadlockszenario debuggen. Mithilfe des bereitgestellten Beispielquellcoderepositorys einer [ASP.NET Core-Web-App](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) können Sie absichtlich einen Deadlock auslösen. Infolge reagiert der Endpunkt nicht mehr, und es kommt zu einer Threadakkumulation. Sie erfahren, wie Sie verschiedene Tools zum Analysieren des Problems verwenden können, z. B. Kernspeicherabbilder, Analysen von Kernspeicherabbildern und die Prozessnachverfolgung.

In diesem Tutorial werden Sie Folgendes durchführen:

> [!div class="checklist"]
>
> - Untersuchen einer nicht reagierenden App
> - Generieren einer Kern-Speicherabbilddatei
> - Analysieren von Prozessthreads in der Abbilddatei
> - Analysieren von Aufrufstapeln und Synchronisierungsblöcken
> - Diagnostizieren und Beheben eines Deadlocks

## <a name="prerequisites"></a>Voraussetzungen

Im Tutorial wird Folgendes verwendet:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine höhere Version
- [Beispieldebugziel-Web-App](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) zum Auslösen des Szenarios
- [dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen
- [dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei

## <a name="core-dump-generation"></a>Generieren des Kernspeicherabbilds

Ein Kernspeicherabbild oder Arbeitsspeicherabbild ermöglicht Ihnen das Untersuchen des Zustands der Threads einer Anwendung und möglichen Sperren, die Konflikte aufweisen, um eine nicht reagierende Anwendung zu untersuchen. Führen Sie die [Beispieldebuganwendung](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) mit dem folgenden Befehl aus dem Beispielstammverzeichnis aus:

```dotnetcli
dotnet run
```

Suchen Sie mit dem folgenden Befehl nach der Prozess-ID:

```dotnetcli
dotnet-trace ps
```

Notieren Sie sich die in der Befehlsausgabe angezeigte Prozess-ID. Die Prozess-ID lautet in diesem Beispiel `4807`, Sie werden jedoch eine andere erhalten. Rufen Sie die folgende URL auf, bei dieser handelt es sich um einen API-Endpunkt auf der Beispielwebsite:

`https://localhost:5001/api/diagscenario/deadlock`

Die API-Anforderung an die Website wird nicht mehr reagieren. Lassen Sie die Anforderung etwa 10-15 Sekunden laufen. Erstellen Sie dann das Kernspeicherabbild mithilfe des folgenden Befehls:

### <a name="linux"></a>[Linux](#tab/linux)

```bash
sudo dotnet-dump collect -p 4807
```

### <a name="windows"></a>[Windows](#tab/windows)

```console
dotnet-dump collect -p 4807
```

---

## <a name="analyze-the-core-dump"></a>Analysieren des Speicherabbilds

Öffnen Sie das Kernspeicherabbild mithilfe des folgenden `dotnet-dump analyze`-Befehls, um mit der Analyse des Kernspeicherabbilds zu beginnen. Das Argument entspricht dem Pfad zur Kern-Speicherabbilddatei, die zuvor erfasst wurde.

```dotnetcli
dotnet-dump analyze  ~/.dotnet/tools/core_20190513_143916
```

Da Sie einen potenziellen Absturz untersuchen, sollten Sie sich einen allgemeinen Überblick über die Threadaktivität im Prozess verschaffen. Wie unten gezeigt können Sie den `threads`-Befehl verwenden:

```console
> threads
*0 0x1DBFF (121855)
 1 0x1DC01 (121857)
 2 0x1DC02 (121858)
 3 0x1DC03 (121859)
 4 0x1DC04 (121860)
 5 0x1DC05 (121861)
 6 0x1DC06 (121862)
 7 0x1DC07 (121863)
 8 0x1DC08 (121864)
 9 0x1DC09 (121865)
 10 0x1DC0A (121866)
 11 0x1DC0D (121869)
 12 0x1DC0E (121870)
 13 0x1DC10 (121872)
 14 0x1DC11 (121873)
 15 0x1DC12 (121874)
 16 0x1DC13 (121875)
 17 0x1DC14 (121876)
 18 0x1DC15 (121877)
 19 0x1DC1C (121884)
 20 0x1DC1D (121885)
 21 0x1DC1E (121886)
 22 0x1DC21 (121889)
 23 0x1DC22 (121890)
 24 0x1DC23 (121891)
 25 0x1DC24 (121892)
 26 0x1DC25 (121893)
...
...
 317 0x1DD48 (122184)
 318 0x1DD49 (122185)
 319 0x1DD4A (122186)
 320 0x1DD4B (122187)
 321 0x1DD4C (122188)
 ```

Die Ausgabe zeigt alle derzeit im Prozess ausgeführten Threads mit ihrer zugehörigen Debuggerthread-ID und der Betriebssystemthread-ID an. Basierend auf der Ausgabe liegen mehr als 300 Threads vor.

Der nächste Schritt besteht darin, sich ein besseres Verständnis darüber zu verschaffen, wofür die Threads derzeit zuständig sind, indem Sie die Aufrufstapel der einzelnen Threads abrufen. Zum Ausgeben der Aufrufstapel können Sie den `clrstack`-Befehl verwenden. Dieser kann entweder einen einzelnen oder alle Aufrufstapel ausgeben. Verwenden Sie den folgenden Befehl, um alle Aufrufstapel für alle Threads im Prozess auszugeben:

```console
clrstack -all
```

Ein repräsentativer Abschnitt der Ausgabe sieht wie folgt aus:

```console
  ...
  ...
  ...
        Child SP               IP Call Site
00007F2AE37B5680 00007f305abc6360 [GCFrame: 00007f2ae37b5680]
00007F2AE37B5770 00007f305abc6360 [GCFrame: 00007f2ae37b5770]
00007F2AE37B57D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae37b57d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE37B5920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE37B5950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE37B5CA0 00007f30593044af [GCFrame: 00007f2ae37b5ca0]
00007F2AE37B5D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae37b5d70]
OS Thread Id: 0x1dc82
        Child SP               IP Call Site
00007F2AE2FB4680 00007f305abc6360 [GCFrame: 00007f2ae2fb4680]
00007F2AE2FB4770 00007f305abc6360 [GCFrame: 00007f2ae2fb4770]
00007F2AE2FB47D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae2fb47d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE2FB4920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE2FB4950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE2FB4CA0 00007f30593044af [GCFrame: 00007f2ae2fb4ca0]
00007F2AE2FB4D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae2fb4d70]
OS Thread Id: 0x1dc83
        Child SP               IP Call Site
00007F2AE27B3680 00007f305abc6360 [GCFrame: 00007f2ae27b3680]
00007F2AE27B3770 00007f305abc6360 [GCFrame: 00007f2ae27b3770]
00007F2AE27B37D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae27b37d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE27B3920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE27B3950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE27B3CA0 00007f30593044af [GCFrame: 00007f2ae27b3ca0]
00007F2AE27B3D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae27b3d70]
OS Thread Id: 0x1dc84
        Child SP               IP Call Site
00007F2AE1FB2680 00007f305abc6360 [GCFrame: 00007f2ae1fb2680]
00007F2AE1FB2770 00007f305abc6360 [GCFrame: 00007f2ae1fb2770]
00007F2AE1FB27D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae1fb27d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE1FB2920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE1FB2950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE1FB2CA0 00007f30593044af [GCFrame: 00007f2ae1fb2ca0]
00007F2AE1FB2D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae1fb2d70]
OS Thread Id: 0x1dc85
        Child SP               IP Call Site
00007F2AE17B1680 00007f305abc6360 [GCFrame: 00007f2ae17b1680]
00007F2AE17B1770 00007f305abc6360 [GCFrame: 00007f2ae17b1770]
00007F2AE17B17D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae17b17d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE17B1920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE17B1950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE17B1CA0 00007f30593044af [GCFrame: 00007f2ae17b1ca0]
00007F2AE17B1D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae17b1d70]
OS Thread Id: 0x1dc86
        Child SP               IP Call Site
00007F2AE0FB0680 00007f305abc6360 [GCFrame: 00007f2ae0fb0680]
00007F2AE0FB0770 00007f305abc6360 [GCFrame: 00007f2ae0fb0770]
00007F2AE0FB07D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae0fb07d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE0FB0920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE0FB0950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE0FB0CA0 00007f30593044af [GCFrame: 00007f2ae0fb0ca0]
00007F2AE0FB0D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae0fb0d70]
OS Thread Id: 0x1dc87
        Child SP               IP Call Site
00007F2AE07AF680 00007f305abc6360 [GCFrame: 00007f2ae07af680]
00007F2AE07AF770 00007f305abc6360 [GCFrame: 00007f2ae07af770]
00007F2AE07AF7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae07af7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE07AF920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE07AF950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE07AFCA0 00007f30593044af [GCFrame: 00007f2ae07afca0]
00007F2AE07AFD70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae07afd70]
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
...
...
```

Durch Beobachtung der mehr als 300 Threads wird ein Muster aufgezeigt, dass ein Großteil der Threads einen Aufrufstapel gemein haben:

```console
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
```

Der Aufrufstapel zeigt auf, dass die Anforderung bei der Deadlockmethode eingegangen ist, die wiederum `Monitor.ReliableEnter` aufruft. Diese Methode gibt an, dass die Threads versuchen, eine Bildschirmsperre zu aktivieren. Sie warten auf die Verfügbarkeit der Sperre. Diese wird wahrscheinlich durch einen anderen Thread gesperrt.

Der nächste Schritt besteht darin, herauszufinden, welcher Thread tatsächlich die Bildschirmsperre enthält. Da Bildschirme Sperrinformationen üblicherweise in der Synchronisierungsblocktabelle speichern, können Sie den `syncblk`-Befehl verwenden, um weitere Informationen abzurufen:

```console
> syncblk
Index         SyncBlock MonitorHeld Recursion Owning Thread Info          SyncBlock Owner
   43 00000246E51268B8          603         1 0000024B713F4E30 5634  28   00000249654b14c0 System.Object
   44 00000246E5126908            3         1 0000024B713F47E0 51d4  29   00000249654b14d8 System.Object
-----------------------------
Total           344
CCW             1
RCW             2
ComClassFactory 0
Free            0
```

Hier sind die zwei Spalten **MonitorHeld** und **Owning Thread Info** von Interesse. Die Spalte **MonitorHeld** zeigt die Anzahl der wartenden Threads an und, ob eine Bildschirmsperre von einem Thread abgerufen wird. Die Spalte **Owning Thread Info** zeigt an, welcher Thread die Bildschirmsperre derzeit enthält. Die Threadinformationen umfassen drei verschiedene untergeordnete Spalten. Die zweite untergeordnete Spalte enthält die Betriebssystemthread-ID.

Nun wissen Sie, dass zwei verschiedene Threads (0x5634 und 0x51d4) eine Bildschirmsperre enthalten. Als Nächstes sehen Sie sich an, was diese Threads tun. Sie müssen überprüfen, ob diese die Sperre auf unbegrenzte Zeit halten. Verwenden Sie die Befehle `setthread` und `clrstack`, um zwischen den Threads zu wechseln und die Aufrufstapel anzuzeigen.

Sehen Sie sich den ersten Thread an, indem Sie den Befehl `setthread` ausführen und den Index des 0x5634-Threads suchen (der Index im Beispiel lautet 28). Die Deadlockfunktion wartet darauf, dass sie eine Sperre empfängt, jedoch besitzt sie die Sperre bereits. Es liegt ein Deadlock vor, der auf die Sperre wartet, die er bereits besitzt.

```console
> setthread 28
> clrstack
OS Thread Id: 0x5634 (28)
        Child SP               IP Call Site
0000004E46AFEAA8 00007fff43a5cbc4 [GCFrame: 0000004e46afeaa8]
0000004E46AFEC18 00007fff43a5cbc4 [GCFrame: 0000004e46afec18]
0000004E46AFEC68 00007fff43a5cbc4 [HelperMethodFrame_1OBJ: 0000004e46afec68] System.Threading.Monitor.Enter(System.Object)
0000004E46AFEDC0 00007FFE5EAF9C80 testwebapi.Controllers.DiagScenarioController.DeadlockFunc() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 58]
0000004E46AFEE30 00007FFE5EAF9B8C testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_0() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 26]
0000004E46AFEE80 00007FFEBB251A5B System.Threading.ThreadHelper.ThreadStart_Context(System.Object) [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 44]
0000004E46AFEEB0 00007FFE5EAEEEEC System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/_/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
0000004E46AFEF20 00007FFEBB234EAB System.Threading.ThreadHelper.ThreadStart() [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 93]
0000004E46AFF138 00007ffebdcc6b63 [GCFrame: 0000004e46aff138]
0000004E46AFF3A0 00007ffebdcc6b63 [DebuggerU2MCatchHandlerFrame: 0000004e46aff3a0]
```

Der zweite Thread ist ähnlich. Er versucht ebenfalls eine Sperre abzurufen, die er bereits besitzt. Die verbleibenden über 300 Threads warten wahrscheinlich ebenfalls auf eine der Sperren, die zum Deadlock geführt haben.

## <a name="see-also"></a>Siehe auch

- [dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen
- [dotnet-counters](dotnet-counters.md) zum Überprüfen der Auslastung des verwalteten Speichers
- [dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei.
- [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Welche Diagnosetools sind in .NET Core verfügbar?](index.md)
