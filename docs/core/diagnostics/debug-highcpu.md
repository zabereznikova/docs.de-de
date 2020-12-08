---
title: Debuggen einer hohen CPU-Auslastung – .NET Core
description: In diesem Tutorial lernen Sie, wie Sie eine hohe CPU-Auslastung in .NET Core debuggen.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 91f31f77b54398d2f9816890338955bc9b0852e4
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437828"
---
# <a name="debug-high-cpu-usage-in-net-core"></a><span data-ttu-id="8b332-103">Debuggen einer hohen CPU-Auslastung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="8b332-103">Debug high CPU usage in .NET Core</span></span>

<span data-ttu-id="8b332-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="8b332-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="8b332-105">In diesem Tutorial erfahren Sie, wie Sie eine exzessive CPU-Auslastung debuggen.</span><span class="sxs-lookup"><span data-stu-id="8b332-105">In this tutorial, you'll learn how to debug an excessive CPU usage scenario.</span></span> <span data-ttu-id="8b332-106">Mithilfe des bereitgestellten Beispielquellcoderepositorys einer [ASP.NET Core-Web-App](/samples/dotnet/samples/diagnostic-scenarios) können Sie absichtlich einen Deadlock auslösen.</span><span class="sxs-lookup"><span data-stu-id="8b332-106">Using the provided example [ASP.NET Core web app](/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="8b332-107">Infolge reagiert der Endpunkt nicht mehr, und es kommt zu einer Threadakkumulation.</span><span class="sxs-lookup"><span data-stu-id="8b332-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="8b332-108">Des Weiteren werden Sie erfahren, wie Sie in einem solchen Szenario mithilfe von verschiedenen Diagnosedaten und Tools eine Diagnose erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b332-108">You'll learn how you can use various tools to diagnose this scenario with several key pieces of diagnostics data.</span></span>

<span data-ttu-id="8b332-109">In diesem Tutorial werden Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="8b332-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="8b332-110">Untersuchen der hohen CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="8b332-110">Investigate high CPU usage</span></span>
> - <span data-ttu-id="8b332-111">Feststellen der CPU-Auslastung mit [dotnet-counters](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="8b332-111">Determine CPU usage with [dotnet-counters](dotnet-counters.md)</span></span>
> - <span data-ttu-id="8b332-112">Generieren von Ablaufverfolgungen mit [dotnet-trace](dotnet-trace.md)</span><span class="sxs-lookup"><span data-stu-id="8b332-112">Use [dotnet-trace](dotnet-trace.md) for trace generation</span></span>
> - <span data-ttu-id="8b332-113">Erstellen eines Leistungsprofils in PerfView</span><span class="sxs-lookup"><span data-stu-id="8b332-113">Profile performance in PerfView</span></span>
> - <span data-ttu-id="8b332-114">Diagnostizieren einer exzessiven CPU-Auslastung und Beheben derselben</span><span class="sxs-lookup"><span data-stu-id="8b332-114">Diagnose and solve excessive CPU usage</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b332-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8b332-115">Prerequisites</span></span>

<span data-ttu-id="8b332-116">Im Tutorial wird Folgendes verwendet:</span><span class="sxs-lookup"><span data-stu-id="8b332-116">The tutorial uses:</span></span>

- <span data-ttu-id="8b332-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher</span><span class="sxs-lookup"><span data-stu-id="8b332-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="8b332-118">[Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios) zum Auslösen des Szenarios</span><span class="sxs-lookup"><span data-stu-id="8b332-118">[Sample debug target](/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario.</span></span>
- <span data-ttu-id="8b332-119">[dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen und zum Generieren eines Profils</span><span class="sxs-lookup"><span data-stu-id="8b332-119">[dotnet-trace](dotnet-trace.md) to list processes and generate a profile.</span></span>
- <span data-ttu-id="8b332-120">[dotnet-counters](dotnet-counters.md) zur Überwachung der CPU-Auslastung</span><span class="sxs-lookup"><span data-stu-id="8b332-120">[dotnet-counters](dotnet-counters.md) to monitor cpu usage.</span></span>

## <a name="cpu-counters"></a><span data-ttu-id="8b332-121">CPU-Indikatoren</span><span class="sxs-lookup"><span data-stu-id="8b332-121">CPU counters</span></span>

<span data-ttu-id="8b332-122">Bevor Sie versuchen, Diagnosedaten zu erfassen, muss eine hohe CPU-Auslastung gegeben sein.</span><span class="sxs-lookup"><span data-stu-id="8b332-122">Before attempting to collect diagnostics data, you need to observe a high CPU condition.</span></span> <span data-ttu-id="8b332-123">Führen Sie die [Beispielanwendung](/samples/dotnet/samples/diagnostic-scenarios) mit dem folgenden Befehl im Stammverzeichnis des Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="8b332-123">Run the [sample application](/samples/dotnet/samples/diagnostic-scenarios) using the following command from the project root directory.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="8b332-124">Suchen Sie mit dem folgenden Befehl nach der Prozess-ID:</span><span class="sxs-lookup"><span data-stu-id="8b332-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="8b332-125">Notieren Sie sich die in der Befehlsausgabe angezeigte Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="8b332-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="8b332-126">Die Prozess-ID lautet in diesem Beispiel `22884`, Sie werden jedoch eine andere erhalten.</span><span class="sxs-lookup"><span data-stu-id="8b332-126">Our process ID was `22884`, but yours will be different.</span></span> <span data-ttu-id="8b332-127">Überprüfen Sie die aktuelle CPU-Auslastung mithilfe des Toolbefehls [dotnet-counters](dotnet-counters.md):</span><span class="sxs-lookup"><span data-stu-id="8b332-127">To check the current CPU usage, use the [dotnet-counters](dotnet-counters.md) tool command:</span></span>

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

<span data-ttu-id="8b332-128">`refresh-interval` stellt die Anzahl von Sekunden dar, die verstreichen, wenn der Zähler CPU-Werte abruft.</span><span class="sxs-lookup"><span data-stu-id="8b332-128">The `refresh-interval` is the number of seconds between the counter polling CPU values.</span></span> <span data-ttu-id="8b332-129">Die Ausgabe sollte ähnlich der Folgenden aussehen:</span><span class="sxs-lookup"><span data-stu-id="8b332-129">The output should be similar to the following:</span></span>

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

<span data-ttu-id="8b332-130">Wenn die Web-App ausgeführt wird, werden unmittelbar nach dem Start keine CPU-Ressourcen verbraucht, und die Auslastung wird mit `0%` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="8b332-130">With the web app running, immediately after startup, the CPU isn't being consumed at all and is reported at `0%`.</span></span> <span data-ttu-id="8b332-131">Navigieren Sie zur Route `api/diagscenario/highcpu`, und verwenden Sie `60000` als Routenparameter:</span><span class="sxs-lookup"><span data-stu-id="8b332-131">Navigate to the `api/diagscenario/highcpu` route with `60000` as the route parameter:</span></span>

`https://localhost:5001/api/diagscenario/highcpu/60000`

<span data-ttu-id="8b332-132">Führen Sie nun noch einmal den Befehl [dotnet-counters](dotnet-counters.md) aus.</span><span class="sxs-lookup"><span data-stu-id="8b332-132">Now, rerun the [dotnet-counters](dotnet-counters.md) command.</span></span> <span data-ttu-id="8b332-133">Wenn Sie nur `cpu-usage` überwachen möchten, müssen Sie `System.Runtime[cpu-usage]` im Befehl angeben.</span><span class="sxs-lookup"><span data-stu-id="8b332-133">To monitor just the `cpu-usage`, specify `System.Runtime[cpu-usage]` as part of the command.</span></span>

```dotnetcli
dotnet-counters monitor --counters System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

<span data-ttu-id="8b332-134">Ihnen sollte ein Anstieg der CPU-Auslastung entsprechend der folgenden Darstellung angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="8b332-134">You should see an increase in CPU usage as shown below:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

<span data-ttu-id="8b332-135">Während der gesamten Dauer der Anforderung liegt die CPU-Auslastung ungefähr bei 25 %.</span><span class="sxs-lookup"><span data-stu-id="8b332-135">Throughout the duration of the request, the CPU usage will hover around 25% .</span></span> <span data-ttu-id="8b332-136">Je nach Hostcomputer ist eine abweichende CPU-Auslastung zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="8b332-136">Depending on the host machine, expect varying CPU usage.</span></span>

> [!TIP]
> <span data-ttu-id="8b332-137">Wenn Sie die gemeldete CPU-Auslastung noch weiter steigern möchten, können Sie diesen Endpunkt in mehreren Browserregisterkarten gleichzeitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8b332-137">To visualize an even higher CPU usage, you can exercise this endpoint in multiple browser tabs simultaneously.</span></span>

<span data-ttu-id="8b332-138">Nun ist Ihre CPU mit Sicherheit höher ausgelastet als erwartet.</span><span class="sxs-lookup"><span data-stu-id="8b332-138">At this point, you can safely say the CPU is running higher than you expect.</span></span>

## <a name="trace-generation"></a><span data-ttu-id="8b332-139">Generieren von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="8b332-139">Trace generation</span></span>

<span data-ttu-id="8b332-140">Wenn Sie eine langsame Anforderung analysieren, benötigen Sie ein Diagnosetool, das Einblicke in den Code liefert.</span><span class="sxs-lookup"><span data-stu-id="8b332-140">When analyzing a slow request, you need a diagnostics tool that can provide insights into what the code is doing.</span></span> <span data-ttu-id="8b332-141">Die übliche Wahl ist ein Profiler, und es stehen verschiedene Profileroptionen zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="8b332-141">The usual choice is a profiler, and there are different profiler options to choose from.</span></span>

### <a name="linux"></a>[<span data-ttu-id="8b332-142">Linux</span><span class="sxs-lookup"><span data-stu-id="8b332-142">Linux</span></span>](#tab/linux)

<span data-ttu-id="8b332-143">Mit dem Tool `perf` können Profile für .NET Core-Apps generiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b332-143">The `perf` tool can be used to generate .NET Core app profiles.</span></span> <span data-ttu-id="8b332-144">Beenden Sie die vorherige Instanz des [Beispieldebugziels](/samples/dotnet/samples/diagnostic-scenarios).</span><span class="sxs-lookup"><span data-stu-id="8b332-144">Exit the previous instance of the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios).</span></span>

<span data-ttu-id="8b332-145">Legen Sie die Umgebungsvariable `COMPlus_PerfMapEnabled` so fest, dass die .NET Core-App eine `map`-Datei im Verzeichnis `/tmp` erstellt.</span><span class="sxs-lookup"><span data-stu-id="8b332-145">Set the `COMPlus_PerfMapEnabled` environment variable to cause the .NET Core app to create a `map` file in the `/tmp` directory.</span></span> <span data-ttu-id="8b332-146">Mit dieser `map`-Datei ordnet `perf` anhand des Namens CPU-Adressen zu JIT-generierten Funktionen zu.</span><span class="sxs-lookup"><span data-stu-id="8b332-146">This `map` file is used by `perf` to map CPU address to JIT-generated functions by name.</span></span> <span data-ttu-id="8b332-147">Weitere Informationen finden Sie unter [Schreiben einer Leistungszuordnung](../run-time-config/debugging-profiling.md#write-perf-map).</span><span class="sxs-lookup"><span data-stu-id="8b332-147">For more information, see [Write perf map](../run-time-config/debugging-profiling.md#write-perf-map).</span></span>

<span data-ttu-id="8b332-148">Führen Sie das [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios) in der gleichen Terminalsitzung aus.</span><span class="sxs-lookup"><span data-stu-id="8b332-148">Run the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios) in the same terminal session.</span></span>

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

<span data-ttu-id="8b332-149">Rufen Sie noch einmal den API-Endpunkt (`https://localhost:5001/api/diagscenario/highcpu/60000`) auf, der die hohe CPU-Auslastung verursacht.</span><span class="sxs-lookup"><span data-stu-id="8b332-149">Exercise the high CPU API endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="8b332-150">Führen Sie den Befehl `perf` mit Ihrer Prozess-ID aus, während der Endpunkt innerhalb der 1-minütigen Anforderung aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="8b332-150">While it's running within the 1-minute request, run the `perf` command with your process ID:</span></span>

```bash
sudo perf record -p 2266 -g
```

<span data-ttu-id="8b332-151">Der Befehl `perf` startet die Erfassung von Leistungsdaten.</span><span class="sxs-lookup"><span data-stu-id="8b332-151">The `perf` command starts the performance collection process.</span></span> <span data-ttu-id="8b332-152">Lassen Sie den Vorgang ungefähr 20–30 Sekunden laufen, und drücken Sie dann <kbd>STRG+C</kbd>, um die Erfassung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8b332-152">Let it run for about 20-30 seconds, then press <kbd>Ctrl+C</kbd> to exit the collection process.</span></span> <span data-ttu-id="8b332-153">Mit demselben `perf`-Befehl können Sie auch die Ausgabe der Ablaufverfolgung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b332-153">You can use the same `perf` command to see the output of the trace.</span></span>

```bash
sudo perf report -f
```

<span data-ttu-id="8b332-154">Zudem können Sie mit den folgenden Befehlen ein _Flammendiagramm_ generieren:</span><span class="sxs-lookup"><span data-stu-id="8b332-154">You can also generate a _flame-graph_ by using the following commands:</span></span>

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

<span data-ttu-id="8b332-155">Dieser Befehl generiert eine `flamegraph.svg`-Datei, die Sie im Browser anzeigen können, um das Leistungsproblem genauer zu untersuchen:</span><span class="sxs-lookup"><span data-stu-id="8b332-155">This command generates a `flamegraph.svg` that you can view in the browser to investigate the performance problem:</span></span>

<span data-ttu-id="8b332-156">[![Bild des Flammendiagramms (.svg)](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8b332-156">[![Flame graph SVG image](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span></span>

### <a name="windows"></a>[<span data-ttu-id="8b332-157">Windows</span><span class="sxs-lookup"><span data-stu-id="8b332-157">Windows</span></span>](#tab/windows)

<span data-ttu-id="8b332-158">Unter Windows können Sie das Tool [dotnet-trace](dotnet-trace.md) als Profiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b332-158">On Windows, you can use the [dotnet-trace](dotnet-trace.md) tool as a profiler.</span></span> <span data-ttu-id="8b332-159">Rufen Sie unter Verwendung des vorherigen [Beispieldebugziels](/samples/dotnet/samples/diagnostic-scenarios) noch einmal den Endpunkt (`https://localhost:5001/api/diagscenario/highcpu/60000`) auf, der eine hohe CPU-Auslastung verursacht.</span><span class="sxs-lookup"><span data-stu-id="8b332-159">Using the previous [sample debug target](/samples/dotnet/samples/diagnostic-scenarios), exercise the high CPU endpoint (`https://localhost:5001/api/diagscenario/highcpu/60000`) again.</span></span> <span data-ttu-id="8b332-160">Verwenden Sie den Befehl `collect` wie folgt, während der Endpunkt innerhalb der 1-minütigen Anforderung aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="8b332-160">While it's running within the 1-minute request, use the `collect` command as follows:</span></span>

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

<span data-ttu-id="8b332-161">Lassen Sie den [dotnet-trace](dotnet-trace.md)-Vorgang für ungefähr 20–30 Sekunden laufen, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um die Erfassung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8b332-161">Let [dotnet-trace](dotnet-trace.md) run for about 20-30 seconds, and then press the <kbd>Enter</kbd> to exit the collection.</span></span> <span data-ttu-id="8b332-162">Als Ergebnis erhalten Sie eine `nettrace`-Datei, die sich im gleichen Ordner befindet.</span><span class="sxs-lookup"><span data-stu-id="8b332-162">The result is a `nettrace` file located in the same folder.</span></span> <span data-ttu-id="8b332-163">`nettrace`-Dateien können sehr gut in Kombination mit bestehenden Windows-Analysetools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b332-163">The `nettrace` files are a great way to use existing analysis tools on Windows.</span></span>

<span data-ttu-id="8b332-164">Öffnen Sie die `nettrace`-Datei wie folgt mit [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md).</span><span class="sxs-lookup"><span data-stu-id="8b332-164">Open the `nettrace` with [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) as shown below.</span></span>

<span data-ttu-id="8b332-165">[![PerfView-Bild](media/perfview.jpg)](media/perfview.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8b332-165">[![PerfView image](media/perfview.jpg)](media/perfview.jpg#lightbox)</span></span>

---

## <a name="see-also"></a><span data-ttu-id="8b332-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b332-166">See also</span></span>

- <span data-ttu-id="8b332-167">[dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen</span><span class="sxs-lookup"><span data-stu-id="8b332-167">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="8b332-168">[dotnet-counters](dotnet-counters.md) zum Überprüfen der Auslastung des verwalteten Speichers</span><span class="sxs-lookup"><span data-stu-id="8b332-168">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="8b332-169">[dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei.</span><span class="sxs-lookup"><span data-stu-id="8b332-169">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="8b332-170">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="8b332-170">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="8b332-171">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8b332-171">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8b332-172">Debuggen eines Deadlocks in .NET Core</span><span class="sxs-lookup"><span data-stu-id="8b332-172">Debug a deadlock in .NET Core</span></span>](debug-deadlock.md)
