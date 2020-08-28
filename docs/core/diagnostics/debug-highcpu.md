---
title: Debuggen einer hohen CPU-Auslastung – .NET Core
description: In diesem Tutorial lernen Sie, wie Sie eine hohe CPU-Auslastung in .NET Core debuggen.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 93076bbce3baf3a219b25c927d2aba3d2d57456f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557801"
---
# <a name="debug-high-cpu-usage-in-net-core"></a>Debuggen einer hohen CPU-Auslastung in .NET Core

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher

In diesem Tutorial erfahren Sie, wie Sie eine exzessive CPU-Auslastung debuggen. Mithilfe des bereitgestellten Beispielquellcoderepositorys einer [ASP.NET Core-Web-App](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) können Sie absichtlich einen Deadlock auslösen. Infolge reagiert der Endpunkt nicht mehr, und es kommt zu einer Threadakkumulation. Des Weiteren werden Sie erfahren, wie Sie in einem solchen Szenario mithilfe von verschiedenen Diagnosedaten und Tools eine Diagnose erstellen.

In diesem Tutorial werden Sie Folgendes durchführen:

> [!div class="checklist"]
>
> - Untersuchen der hohen CPU-Auslastung
> - Feststellen der CPU-Auslastung mit [dotnet-counters](dotnet-counters.md)
> - Generieren von Ablaufverfolgungen mit [dotnet-trace](dotnet-trace.md)
> - Erstellen eines Leistungsprofils in PerfView
> - Diagnostizieren einer exzessiven CPU-Auslastung und Beheben derselben

## <a name="prerequisites"></a>Voraussetzungen

Im Tutorial wird Folgendes verwendet:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher
- [Beispieldebugziel](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) zum Auslösen des Szenarios
- [dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen und zum Generieren eines Profils
- [dotnet-counters](dotnet-counters.md) zur Überwachung der CPU-Auslastung

## <a name="cpu-counters"></a>CPU-Indikatoren

Bevor Sie versuchen, Diagnosedaten zu erfassen, muss eine hohe CPU-Auslastung gegeben sein. Führen Sie die [Beispielanwendung](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) mit dem folgenden Befehl im Stammverzeichnis des Projekts aus.

```dotnetcli
dotnet run
```

Suchen Sie mit dem folgenden Befehl nach der Prozess-ID:

```dotnetcli
dotnet-trace ps
```

Notieren Sie sich die in der Befehlsausgabe angezeigte Prozess-ID. Die Prozess-ID lautet in diesem Beispiel `22884`, Sie werden jedoch eine andere erhalten. Überprüfen Sie die aktuelle CPU-Auslastung mithilfe des Toolbefehls [dotnet-counters](dotnet-counters.md):

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

`refresh-interval` stellt die Anzahl von Sekunden dar, die verstreichen, wenn der Zähler CPU-Werte abruft. Die Ausgabe sollte ähnlich der Folgenden aussehen:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

Wenn die Web-App ausgeführt wird, werden unmittelbar nach dem Start keine CPU-Ressourcen verbraucht, und die Auslastung wird mit `0%` gemeldet. Navigieren Sie zur Route `api/diagscenario/highcpu`, und verwenden Sie `60000` als Routenparameter:

`https://localhost:5001/api/diagscenario/highcpu/60000`

Führen Sie nun noch einmal den Befehl [dotnet-counters](dotnet-counters.md) aus. Wenn Sie nur `cpu-usage` überwachen möchten, müssen Sie `System.Runtime[cpu-usage]` im Befehl angeben.

```dotnetcli
dotnet-counters monitor System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

Ihnen sollte ein Anstieg der CPU-Auslastung entsprechend der folgenden Darstellung angezeigt werden:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

Während der gesamten Dauer der Anforderung liegt die CPU-Auslastung ungefähr bei 25 %. Je nach Hostcomputer ist eine abweichende CPU-Auslastung zu erwarten.

> [!TIP]
> Wenn Sie die gemeldete CPU-Auslastung noch weiter steigern möchten, können Sie diesen Endpunkt in mehreren Browserregisterkarten gleichzeitig aufrufen.

Nun ist Ihre CPU mit Sicherheit höher ausgelastet als erwartet.

## <a name="trace-generation"></a>Generieren von Ablaufverfolgungen

Wenn Sie eine langsame Anforderung analysieren, benötigen Sie ein Diagnosetool, das Einblicke in den Code liefert. Die übliche Wahl ist ein Profiler, und es stehen verschiedene Profileroptionen zur Auswahl.

### <a name="linux"></a>[Linux](#tab/linux)

Mit dem Tool `perf` können Profile für .NET Core-Apps generiert werden. Beenden Sie die vorherige Instanz des [Beispieldebugziels](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios).

Legen Sie die Umgebungsvariable `COMPlus_PerfMapEnabled` so fest, dass die .NET Core-App eine `map`-Datei im Verzeichnis `/tmp` erstellt. Mit dieser `map`-Datei ordnet `perf` anhand des Namens CPU-Adressen zu JIT-generierten Funktionen zu. Weitere Informationen finden Sie unter [Schreiben einer Leistungszuordnung](../run-time-config/debugging-profiling.md#write-perf-map).

Führen Sie das [Beispieldebugziel](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) in der gleichen Terminalsitzung aus.

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

Rufen Sie noch einmal den API-Endpunkt (`https://localhost:5001/api/diagscenario/highcpu/60000`) auf, der die hohe CPU-Auslastung verursacht. Führen Sie den Befehl `perf` mit Ihrer Prozess-ID aus, während der Endpunkt innerhalb der 1-minütigen Anforderung aufgerufen wird:

```bash
sudo perf record -p 2266 -g
```

Der Befehl `perf` startet die Erfassung von Leistungsdaten. Lassen Sie den Vorgang ungefähr 20–30 Sekunden laufen, und drücken Sie dann <kbd>STRG+C</kbd>, um die Erfassung zu beenden. Mit demselben `perf`-Befehl können Sie auch die Ausgabe der Ablaufverfolgung anzeigen.

```bash
sudo perf report -f
```

Zudem können Sie mit den folgenden Befehlen ein _Flammendiagramm_ generieren:

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

Dieser Befehl generiert eine `flamegraph.svg`-Datei, die Sie im Browser anzeigen können, um das Leistungsproblem genauer zu untersuchen:

[![Bild des Flammendiagramms (.svg)](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)

### <a name="windows"></a>[Windows](#tab/windows)

Unter Windows können Sie das Tool [dotnet-trace](dotnet-trace.md) als Profiler verwenden. Rufen Sie unter Verwendung des vorherigen [Beispieldebugziels](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) noch einmal den Endpunkt (`https://localhost:5001/api/diagscenario/highcpu/60000`) auf, der eine hohe CPU-Auslastung verursacht. Verwenden Sie den Befehl `collect` wie folgt, während der Endpunkt innerhalb der 1-minütigen Anforderung aufgerufen wird:

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

Lassen Sie den [dotnet-trace](dotnet-trace.md)-Vorgang für ungefähr 20–30 Sekunden laufen, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um die Erfassung zu beenden. Als Ergebnis erhalten Sie eine `nettrace`-Datei, die sich im gleichen Ordner befindet. `nettrace`-Dateien können sehr gut in Kombination mit bestehenden Windows-Analysetools verwendet werden.

Öffnen Sie die `nettrace`-Datei wie folgt mit [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md).

[![PerfView-Bild](media/perfview.jpg)](media/perfview.jpg#lightbox)

---

## <a name="see-also"></a>Siehe auch

- [dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen
- [dotnet-counters](dotnet-counters.md) zum Überprüfen der Auslastung des verwalteten Speichers
- [dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei.
- [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Debuggen eines Deadlocks in .NET Core](debug-deadlock.md)
