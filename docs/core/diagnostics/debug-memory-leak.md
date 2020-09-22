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
# <a name="debug-a-memory-leak-in-net-core"></a><span data-ttu-id="5829d-103">Debuggen eines Arbeitsspeicherverlusts in .NET Core</span><span class="sxs-lookup"><span data-stu-id="5829d-103">Debug a memory leak in .NET Core</span></span>

<span data-ttu-id="5829d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 3.1 SDK und höher</span><span class="sxs-lookup"><span data-stu-id="5829d-104">**This article applies to:** ✔️ .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="5829d-105">In diesem Tutorial werden die Tools zum Analysieren eines .NET Core-Arbeitsspeicherverlusts vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="5829d-105">This tutorial demonstrates the tools to analyze a .NET Core memory leak.</span></span>

<span data-ttu-id="5829d-106">In diesem Tutorial wird eine Beispiel-App verwendet, die absichtlich zu einem Arbeitsspeicherverlust führt.</span><span class="sxs-lookup"><span data-stu-id="5829d-106">This tutorial uses a sample app, which is designed to intentionally leak memory.</span></span> <span data-ttu-id="5829d-107">Das Beispiel wird als Übung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5829d-107">The sample is provided as an exercise.</span></span> <span data-ttu-id="5829d-108">Sie können auch eine App analysieren, die unbeabsichtigt einen Arbeitsspeicherverlust verursacht.</span><span class="sxs-lookup"><span data-stu-id="5829d-108">You can analyze an app that is unintentionally leaking memory too.</span></span>

<span data-ttu-id="5829d-109">In diesem Tutorial werden Sie Folgendes durchführen:</span><span class="sxs-lookup"><span data-stu-id="5829d-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="5829d-110">Untersuchen der verwalteten Speicherauslastung mit [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="5829d-110">Examine managed memory usage with [dotnet-counters](dotnet-counters.md).</span></span>
> - <span data-ttu-id="5829d-111">Generieren einer Dumpdatei.</span><span class="sxs-lookup"><span data-stu-id="5829d-111">Generate a dump file.</span></span>
> - <span data-ttu-id="5829d-112">Analysieren der Speicherauslastung mithilfe der Dumpdatei.</span><span class="sxs-lookup"><span data-stu-id="5829d-112">Analyze the memory usage using the dump file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5829d-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5829d-113">Prerequisites</span></span>

<span data-ttu-id="5829d-114">Im Tutorial wird Folgendes verwendet:</span><span class="sxs-lookup"><span data-stu-id="5829d-114">The tutorial uses:</span></span>

- <span data-ttu-id="5829d-115">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder höher</span><span class="sxs-lookup"><span data-stu-id="5829d-115">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="5829d-116">[dotnet-trace](dotnet-trace.md) zu Auflisten von Prozessen.</span><span class="sxs-lookup"><span data-stu-id="5829d-116">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
- <span data-ttu-id="5829d-117">[dotnet-counters](dotnet-counters.md) zum Untersuchen der verwalteten Speicherauslastung.</span><span class="sxs-lookup"><span data-stu-id="5829d-117">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
- <span data-ttu-id="5829d-118">[dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Dumpdatei.</span><span class="sxs-lookup"><span data-stu-id="5829d-118">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
- <span data-ttu-id="5829d-119">Eine [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/)-App für die Diagnose.</span><span class="sxs-lookup"><span data-stu-id="5829d-119">A [sample debug target](/samples/dotnet/samples/diagnostic-scenarios/) app to diagnose.</span></span>

<span data-ttu-id="5829d-120">In diesem Tutorial wird davon ausgegangen, dass das Beispiel und die Tools installiert und einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="5829d-120">The tutorial assumes the sample and tools are installed and ready to use.</span></span>

## <a name="examine-managed-memory-usage"></a><span data-ttu-id="5829d-121">Untersuchen der verwalteten Speicherauslastung</span><span class="sxs-lookup"><span data-stu-id="5829d-121">Examine managed memory usage</span></span>

<span data-ttu-id="5829d-122">Bevor Sie mit dem Erfassen von Diagnosedaten beginnen, um die Grundursache für dieses Szenario zu ermitteln, müssen Sie sicherstellen, dass tatsächlich ein Arbeitsspeicherverlust stattfindet (Vergrößerung des Arbeitsspeichers).</span><span class="sxs-lookup"><span data-stu-id="5829d-122">Before you start collecting diagnostics data to help us root cause this scenario, you need to make sure you're actually seeing a memory leak (memory growth).</span></span> <span data-ttu-id="5829d-123">Sie können das Tool [dotnet-counters](dotnet-counters.md) verwenden, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5829d-123">You can use the [dotnet-counters](dotnet-counters.md) tool to confirm that.</span></span>

<span data-ttu-id="5829d-124">Öffnen Sie ein Konsolenfenster, und navigieren Sie zu dem Verzeichnis, das Sie zum Herunterladen und Entzippen des [Beispieldebugziels](/samples/dotnet/samples/diagnostic-scenarios/) verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="5829d-124">Open a console window and navigate to the directory where you downloaded and unzipped the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios/).</span></span> <span data-ttu-id="5829d-125">Führen Sie das Ziel aus:</span><span class="sxs-lookup"><span data-stu-id="5829d-125">Run the target:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="5829d-126">Suchen Sie in einer separaten Konsole mithilfe des Tools [dotnet-trace](dotnet-trace.md) nach der Prozess-ID:</span><span class="sxs-lookup"><span data-stu-id="5829d-126">From a separate console, find the process ID using the [dotnet-trace](dotnet-trace.md) tool:</span></span>

```console
dotnet-trace ps
```

<span data-ttu-id="5829d-127">Die Ausgabe sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5829d-127">The output should be similar to:</span></span>

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

<span data-ttu-id="5829d-128">Überprüfen Sie nun die verwaltete Speicherauslastung mit dem Tool [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="5829d-128">Now, check managed memory usage with the [dotnet-counters](dotnet-counters.md) tool.</span></span> <span data-ttu-id="5829d-129">Das `--refresh-interval` gibt die Anzahl der Sekunden zwischen Aktualisierungen an:</span><span class="sxs-lookup"><span data-stu-id="5829d-129">The `--refresh-interval` specifies the number of seconds between refreshes:</span></span>

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

<span data-ttu-id="5829d-130">Die Liveausgabe sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5829d-130">The live output should be similar to:</span></span>

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

<span data-ttu-id="5829d-131">Konzentrieren Sie sich auf diese Zeile:</span><span class="sxs-lookup"><span data-stu-id="5829d-131">Focusing on this line:</span></span>

```console
    GC Heap Size (MB)                                  4
```

<span data-ttu-id="5829d-132">Sie können sehen, dass der verwaltete Heapspeicher nach dem Start 4 MB groß ist.</span><span class="sxs-lookup"><span data-stu-id="5829d-132">You can see that the managed heap memory is 4 MB right after startup.</span></span>

<span data-ttu-id="5829d-133">Verwenden Sie nun die URL `https://localhost:5001/api/diagscenario/memleak/20000`.</span><span class="sxs-lookup"><span data-stu-id="5829d-133">Now, hit the URL `https://localhost:5001/api/diagscenario/memleak/20000`.</span></span>

<span data-ttu-id="5829d-134">Beachten Sie, dass die Speicherauslastung auf 30 MB angewachsen ist.</span><span class="sxs-lookup"><span data-stu-id="5829d-134">Observe that the memory usage has grown to 30 MB.</span></span>

```console
    GC Heap Size (MB)                                 30
```

<span data-ttu-id="5829d-135">Wenn Sie die Speicherauslastung überwachen, können Sie sicher sagen, dass der Arbeitsspeicher zunimmt oder Verluste aufweist.</span><span class="sxs-lookup"><span data-stu-id="5829d-135">By watching the memory usage, you can safely say that memory is growing or leaking.</span></span> <span data-ttu-id="5829d-136">Der nächste Schritt besteht darin, die richtigen Daten für die Arbeitsspeicheranalyse zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="5829d-136">The next step is to collect the right data for memory analysis.</span></span>

### <a name="generate-memory-dump"></a><span data-ttu-id="5829d-137">Generieren eines Speicherabbilds</span><span class="sxs-lookup"><span data-stu-id="5829d-137">Generate memory dump</span></span>

<span data-ttu-id="5829d-138">Wenn Sie mögliche Arbeitsspeicherverluste analysieren, benötigen Sie Zugriff auf den Arbeitsspeicherheap der App.</span><span class="sxs-lookup"><span data-stu-id="5829d-138">When analyzing possible memory leaks, you need access to the app's memory heap.</span></span> <span data-ttu-id="5829d-139">Anschließend können Sie den Arbeitsspeicherinhalt analysieren.</span><span class="sxs-lookup"><span data-stu-id="5829d-139">Then you can analyze the memory contents.</span></span> <span data-ttu-id="5829d-140">Wenn Sie Beziehungen zwischen Objekten betrachten, erstellen Sie Theorien dazu, warum der Arbeitsspeicher nicht freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5829d-140">Looking at relationships between objects, you create theories on why memory isn't being freed.</span></span> <span data-ttu-id="5829d-141">Eine gängige Quelle für Diagnosedaten ist ein Speicherabbild unter Windows oder der entsprechende Core Dump unter Linux.</span><span class="sxs-lookup"><span data-stu-id="5829d-141">A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux.</span></span> <span data-ttu-id="5829d-142">Zum Generieren eines Speicherabbilds einer .NET Core-Anwendung können Sie das Tool [dotnet-dump)](dotnet-dump.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5829d-142">To generate a dump of a .NET Core application, you can use the [dotnet-dump)](dotnet-dump.md) tool.</span></span>

<span data-ttu-id="5829d-143">Führen Sie den folgenden Befehl aus, um einen Linux-Core Dump zu generieren, indem Sie das zuvor erstellte [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5829d-143">Using the [sample debug target](/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:</span></span>

```dotnetcli
dotnet-dump collect -p 4807
```

<span data-ttu-id="5829d-144">Das Ergebnis ist ein Core Dump, der sich im gleichen Ordner befindet.</span><span class="sxs-lookup"><span data-stu-id="5829d-144">The result is a core dump located in the same folder.</span></span>

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a><span data-ttu-id="5829d-145">Neustarten des fehlgeschlagenen Prozesses</span><span class="sxs-lookup"><span data-stu-id="5829d-145">Restart the failed process</span></span>

<span data-ttu-id="5829d-146">Nachdem das Speicherabbild erfasst wurde, sollten Sie über genügend Informationen verfügen, um den fehlgeschlagenen Prozess zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="5829d-146">Once the dump is collected, you should have sufficient information to diagnose the failed process.</span></span> <span data-ttu-id="5829d-147">Wenn der fehlgeschlagene Prozess auf einem Produktionsserver ausgeführt wird, ist dies jetzt der ideale Zeitpunkt für die kurzfristige Wartung, indem der Prozess neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5829d-147">If the failed process is running on a production server, now it's the ideal time for short-term remediation by restarting the process.</span></span>

<span data-ttu-id="5829d-148">In diesem Tutorial benötigen Sie das [Beispieldebugziel](/samples/dotnet/samples/diagnostic-scenarios/) nicht mehr, und Sie können es schließen.</span><span class="sxs-lookup"><span data-stu-id="5829d-148">In this tutorial, you're now done with the [Sample debug target](/samples/dotnet/samples/diagnostic-scenarios/) and you can close it.</span></span> <span data-ttu-id="5829d-149">Navigieren Sie zu dem Terminal, über das der Server gestartet wurde, und drücken Sie <kbd>STRG+C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="5829d-149">Navigate to the terminal that started the server, and press <kbd>Ctrl+C</kbd>.</span></span>

### <a name="analyze-the-core-dump"></a><span data-ttu-id="5829d-150">Analysieren des Speicherabbilds</span><span class="sxs-lookup"><span data-stu-id="5829d-150">Analyze the core dump</span></span>

<span data-ttu-id="5829d-151">Nachdem Sie nun ein Speicherabbild generiert haben, verwenden Sie das Tool [dotnet-dump](dotnet-dump.md), um das Speicherabbild zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="5829d-151">Now that you have a core dump generated, use the [dotnet-dump](dotnet-dump.md) tool to analyze the dump:</span></span>

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

<span data-ttu-id="5829d-152">Dabei ist `core_20190430_185145` der Name des Speicherabbilds, das Sie analysieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5829d-152">Where `core_20190430_185145` is the name of the core dump you want to analyze.</span></span>

> [!NOTE]
> <span data-ttu-id="5829d-153">Wenn eine Fehlermeldung angezeigt wird, die besagt, dass *libdl.so* nicht gefunden wurde, müssen Sie ggf. das Paket *libc6-dev* installieren.</span><span class="sxs-lookup"><span data-stu-id="5829d-153">If you see an error complaining that *libdl.so* cannot be found, you may have to install the *libc6-dev* package.</span></span> <span data-ttu-id="5829d-154">Weitere Informationen finden Sie unter [Voraussetzungen für .NET Core unter Linux](../install/linux.md).</span><span class="sxs-lookup"><span data-stu-id="5829d-154">For more information, see [Prerequisites for .NET Core on Linux](../install/linux.md).</span></span>

<span data-ttu-id="5829d-155">Es wird eine Eingabeaufforderung angezeigt, in der Sie SOS-Befehle eingeben können.</span><span class="sxs-lookup"><span data-stu-id="5829d-155">You'll be presented with a prompt where you can enter SOS commands.</span></span> <span data-ttu-id="5829d-156">Im Allgemeinen gilt die erste Untersuchung dem Gesamtstatus des verwalteten Heaps:</span><span class="sxs-lookup"><span data-stu-id="5829d-156">Commonly, the first thing you want to look at is the overall state of the managed heap:</span></span>

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

<span data-ttu-id="5829d-157">Hier können Sie sehen, dass die meisten Objekte entweder `String`- oder `Customer`-Objekte sind.</span><span class="sxs-lookup"><span data-stu-id="5829d-157">Here you can see that most objects are either `String` or `Customer` objects.</span></span>

<span data-ttu-id="5829d-158">Sie können den Befehl `dumpheap` erneut mit der-Methodentabelle (MT) verwenden, um eine Liste aller `String`-Instanzen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="5829d-158">You can use the `dumpheap` command again with the method table (MT) to get a list of all the `String` instances:</span></span>

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

<span data-ttu-id="5829d-159">Sie können jetzt den Befehl `gcroot` in einer `System.String`-Instanz verwenden, um zu sehen, wie und warum das Objekt über Rootzugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="5829d-159">You can now use the `gcroot` command on a `System.String` instance to see how and why the object is rooted.</span></span> <span data-ttu-id="5829d-160">Seien Sie geduldig, da die Ausführung dieses Befehls mehrere Minuten bei einem Heap von 30 MB benötigt:</span><span class="sxs-lookup"><span data-stu-id="5829d-160">Be patient because this command takes several minutes with a 30-MB heap:</span></span>

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

<span data-ttu-id="5829d-161">Sie können sehen, dass `String` direkt vom `Customer`-Objekt verwendet und indirekt von einem `CustomerCache`-Objekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5829d-161">You can see that the `String` is directly held by the `Customer` object and indirectly held by a `CustomerCache` object.</span></span>

<span data-ttu-id="5829d-162">Sie können weitere Speicherabbilder für Objekte erstellen, um zu erkennen, dass die meisten `String`-Objekte einem ähnlichen Muster folgen.</span><span class="sxs-lookup"><span data-stu-id="5829d-162">You can continue dumping out objects to see that most `String` objects follow a similar pattern.</span></span> <span data-ttu-id="5829d-163">An diesem Punkt hat die Untersuchung genügend Informationen bereitgestellt, um die Grundursache im Code zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5829d-163">At this point, the investigation provided sufficient information to identify the root cause in your code.</span></span>

<span data-ttu-id="5829d-164">Mit diesem allgemeinen Verfahren können Sie die Quelle von größeren Arbeitsspeicherverlusten identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5829d-164">This general procedure allows you to identify the source of major memory leaks.</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="5829d-165">Bereinigen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5829d-165">Clean up resources</span></span>

<span data-ttu-id="5829d-166">In diesem Tutorial haben Sie einen Beispielwebserver gestartet.</span><span class="sxs-lookup"><span data-stu-id="5829d-166">In this tutorial, you started a sample web server.</span></span> <span data-ttu-id="5829d-167">Dieser Server sollte heruntergefahren worden sein, wie im Abschnitt [Neustarten des fehlgeschlagenen Vorgangs](#restart-the-failed-process) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5829d-167">This server should have been shut down as explained in the [Restart the failed process](#restart-the-failed-process) section.</span></span>

<span data-ttu-id="5829d-168">Sie können auch die erstellte Speicherabbilddatei löschen.</span><span class="sxs-lookup"><span data-stu-id="5829d-168">You can also delete the dump file that was created.</span></span>

## <a name="see-also"></a><span data-ttu-id="5829d-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5829d-169">See also</span></span>

- <span data-ttu-id="5829d-170">[dotnet-trace](dotnet-trace.md) zum Auflisten von Prozessen</span><span class="sxs-lookup"><span data-stu-id="5829d-170">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="5829d-171">[dotnet-counters](dotnet-counters.md) zum Überprüfen der Auslastung des verwalteten Speichers</span><span class="sxs-lookup"><span data-stu-id="5829d-171">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="5829d-172">[dotnet-dump](dotnet-dump.md) zum Erfassen und Analysieren einer Speicherabbilddatei.</span><span class="sxs-lookup"><span data-stu-id="5829d-172">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="5829d-173">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="5829d-173">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="5829d-174">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5829d-174">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5829d-175">Debuggen von hoher CPU-Auslastung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="5829d-175">Debug high CPU in .NET Core</span></span>](debug-highcpu.md)
