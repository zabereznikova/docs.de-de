---
title: Ablaufverfolgung von .NET-Anwendungen mit perfcollect
description: In diesem Tutorial werden Sie Schritt für Schritt durch das Erfassen einer Ablaufverfolgung mit perfcollect in .NET geleitet.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 53e4584953d2af4e766daadfa757cca752ae7329
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593219"
---
# <a name="trace-net-applications-with-perfcollect"></a><span data-ttu-id="2d770-103">Ablaufverfolgung von .NET-Anwendungen mit perfcollect</span><span class="sxs-lookup"><span data-stu-id="2d770-103">Trace .NET applications with PerfCollect</span></span>

<span data-ttu-id="2d770-104">**Dieser Artikel gilt für: ✔️** .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="2d770-104">**This article applies to: ✔️** .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="2d770-105">Wenn unter Linux Leistungsprobleme auftreten, können Sie mit `perfcollect` eine Ablaufverfolgung erfassen, um detaillierte Informationen zu den Vorgängen auf dem Computer zum Zeitpunkt des Leistungsproblems zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="2d770-105">When performance problems are encountered on Linux, collecting a trace with `perfcollect` can be used to gather detailed information about what was happening on the machine at the time of the performance problem.</span></span>

<span data-ttu-id="2d770-106">Bei `perfcollect` handelt es sich um ein Bash-Skript, das das [Linux Trace Toolkit Next Generation (LTTng)](https://lttng.org) verwendet, um Ereignisse zu erfassen, die von der Runtime oder einer beliebigen [EventSource](xref:System.Diagnostics.Tracing.EventListener)-Klasse geschrieben wurden. Zudem verwendet es [perf](https://perf.wiki.kernel.org/), um CPU-Beispiele des Zielprozesses zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="2d770-106">`perfcollect` is a bash script that leverages [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org) to collect events written from the runtime or any [EventSource](xref:System.Diagnostics.Tracing.EventListener), as well as [perf](https://perf.wiki.kernel.org/) to collect CPU samples of the target process.</span></span>

## <a name="prepare-your-machine"></a><span data-ttu-id="2d770-107">Vorbereiten Ihres Computers</span><span class="sxs-lookup"><span data-stu-id="2d770-107">Prepare your machine</span></span>

<span data-ttu-id="2d770-108">Führen Sie die folgenden Schritte durch, um Ihren Computer für das Erfassen einer Leistungsablaufverfolgung mit `perfcollect` vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="2d770-108">Follow these steps to prepare your machine to collect a performance trace with `perfcollect`.</span></span>

> [!NOTE]
> <span data-ttu-id="2d770-109">Wenn Sie sich in einer Containerumgebung befinden, muss Ihr Container über `SYS_ADMIN`-Funktionen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2d770-109">If you are in a container environment, your container needs to have `SYS_ADMIN` capability.</span></span> <span data-ttu-id="2d770-110">Weitere Informationen zur Ablaufverfolgung von Anwendungen innerhalb von Containern mithilfe von perfcollect finden Sie unter [Sammeln von Diagnosen in Containern](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="2d770-110">For more information on tracing applications inside containers using PerfCollect, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

1. <span data-ttu-id="2d770-111">Laden Sie `perfcollect` herunter.</span><span class="sxs-lookup"><span data-stu-id="2d770-111">Download `perfcollect`.</span></span>

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. <span data-ttu-id="2d770-112">Sorgen Sie dafür, dass das Skript ausführbar ist.</span><span class="sxs-lookup"><span data-stu-id="2d770-112">Make the script executable.</span></span>

    > ```bash
    > chmod +x perfcollect
    > ```

3. <span data-ttu-id="2d770-113">Installieren Sie die für die Ablaufverfolgung erforderlichen Komponenten. Dabei handelt es sich um die eigentlichen Ablaufverfolgungsbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="2d770-113">Install tracing prerequisites - these are the actual tracing libraries.</span></span>

    > ```bash
    > sudo ./perfcollect install
    > ```

    <span data-ttu-id="2d770-114">Auf diese Weise werden die folgenden erforderlichen Komponenten auf Ihrem Computer installiert:</span><span class="sxs-lookup"><span data-stu-id="2d770-114">This will install the following prerequisites on your machine:</span></span>

    1. <span data-ttu-id="2d770-115">`perf`: Dies ist das Linux-Subsystem zu Leistungsereignissen und die begleitende Anwendung zur Benutzermodusanzeige/-sammlung.</span><span class="sxs-lookup"><span data-stu-id="2d770-115">`perf`: the Linux Performance Events subsystem and companion user-mode collection/viewer application.</span></span> <span data-ttu-id="2d770-116">`perf` ist Teil der Linux-Kernelquelle, wird bei der Standardeinstellung normalerweise jedoch nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="2d770-116">`perf` is part of the Linux kernel source, but is not usually installed by default.</span></span>

    2. <span data-ttu-id="2d770-117">`LTTng`: Dies wird zum Erfassen von Ereignisdaten verwendet, die zur Laufzeit von CoreCLR ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2d770-117">`LTTng`: Used to capture event data emitted at runtime by CoreCLR.</span></span> <span data-ttu-id="2d770-118">Diese Daten werden dann verwendet, um das Verhalten verschiedener Runtimekomponenten wie GC, JIT und Threadpool zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="2d770-118">This data is then used to analyze the behavior of various runtime components such as the GC, JIT, and thread pool.</span></span>

<span data-ttu-id="2d770-119">Die neuesten Versionen von .NET Core und das Linux-Leistungstool unterstützen die automatische Auflösung von Methodennamen für Frameworkcode.</span><span class="sxs-lookup"><span data-stu-id="2d770-119">Recent versions of .NET Core and the Linux perf tool support automatic resolution of method names for framework code.</span></span> <span data-ttu-id="2d770-120">Wenn Sie mit Version 3.1 oder einer früheren Version von .NET Core arbeiten, ist ein zusätzlicher Schritt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2d770-120">If you are working with .NET Core version 3.1 or less, an extra step is necessary.</span></span> <span data-ttu-id="2d770-121">Weitere Informationen finden Sie unter [Auflösen von Frameworksymbolen](#resolve-framework-symbols).</span><span class="sxs-lookup"><span data-stu-id="2d770-121">See [Resolving Framework Symbols](#resolve-framework-symbols) for details.</span></span>

<span data-ttu-id="2d770-122">Zum Auflösen von Methodennamen nativer Runtime-DLLs (z. B. libcoreclr.so) löst `perfcollect` beim Konvertieren von Daten Symbole für diese auf. Allerdings trifft dies nur zu, wenn die Symbole für diese Binärdateien vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2d770-122">For resolving method names of native runtime DLLs (such as libcoreclr.so), `perfcollect` will resolve symbols for them when it converts the data, but only if the symbols for these binaries are present.</span></span> <span data-ttu-id="2d770-123">Weitere Informationen finden Sie im Abschnitt [Abrufen von Symbolen für die native Runtime](#get-symbols-for-the-native-runtime).</span><span class="sxs-lookup"><span data-stu-id="2d770-123">See [Getting Symbols for the Native Runtime](#get-symbols-for-the-native-runtime) section for details.</span></span>

## <a name="collect-a-trace"></a><span data-ttu-id="2d770-124">Erfassen einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2d770-124">Collect a trace</span></span>

1. <span data-ttu-id="2d770-125">Sie benötigen zwei Shells: eine zum Steuern der Ablaufverfolgung, als **[Trace]** bezeichnet, und eine zum Ausführen der Anwendung, als **[App]** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2d770-125">Have two shells available - one for controlling tracing, referred to as **[Trace]**, and one for running the application, referred to as **[App]**.</span></span>

2. <span data-ttu-id="2d770-126">**[Trace]** Starten Sie die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="2d770-126">**[Trace]** Start collection.</span></span>

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    <span data-ttu-id="2d770-127">Erwartete Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2d770-127">Expected Output:</span></span>

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. <span data-ttu-id="2d770-128">**[App]** Richten Sie die Anwendungsshell mit den folgenden Umgebungsvariablen ein. Dies ermöglicht die CoreCLR-Konfiguration für die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="2d770-128">**[App]** Set up the application shell with the following environment variables - this enables tracing configuration of CoreCLR.</span></span>

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. <span data-ttu-id="2d770-129">**[App]** Führen Sie die App aus, und zwar so lange wie nötig, um das Leistungsproblem zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="2d770-129">**[App]** Run the app - let it run as long as you need to in order to capture the performance problem.</span></span> <span data-ttu-id="2d770-130">Die genaue Ausführungsdauer kann auch nur sehr kurz sein, solange das Zeitfenster, in dem das zu untersuchende Leistungsproblem auftritt, ausreichend erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="2d770-130">The exact length can be as short as you need as long as it sufficiently captures the window of time where the performance problem you want to investigate occurs.</span></span>

    > ```bash
    > dotnet run
    > ```

5. <span data-ttu-id="2d770-131">**[Trace]** Halten Sie die Ablaufverfolgung an. Drücken Sie dazu STRG+C.</span><span class="sxs-lookup"><span data-stu-id="2d770-131">**[Trace]** Stop collection - hit CTRL+C.</span></span>

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    <span data-ttu-id="2d770-132">Die komprimierte Ablaufverfolgungsdatei ist jetzt im aktuellen Arbeitsverzeichnis gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d770-132">The compressed trace file is now stored in the current working directory.</span></span>

## <a name="view-a-trace"></a><span data-ttu-id="2d770-133">Anzeigen einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="2d770-133">View a trace</span></span>

<span data-ttu-id="2d770-134">Es gibt mehrere Möglichkeiten, die erfasste Ablaufverfolgung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d770-134">There are a number of options for viewing the trace that was collected.</span></span> <span data-ttu-id="2d770-135">Ablaufverfolgungen werden am besten mithilfe von [PerfView](https://aka.ms/perfview) unter Windows angezeigt. Sie können aber auch direkt unter Linux mithilfe von `PerfCollect` selbst oder mit `TraceCompass` angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2d770-135">Traces are best viewed using [PerfView](https://aka.ms/perfview) on Windows, but they can be viewed directly on Linux using `PerfCollect` itself or `TraceCompass`.</span></span>

### <a name="use-perfcollect-to-view-the-trace-file"></a><span data-ttu-id="2d770-136">Verwenden von perfcollect zum Anzeigen der Ablaufverfolgungsdatei</span><span class="sxs-lookup"><span data-stu-id="2d770-136">Use PerfCollect to view the trace file</span></span>

<span data-ttu-id="2d770-137">Sie können perfcollect selbst verwenden, um die erfasste Ablaufverfolgung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d770-137">You can use perfcollect itself to view the trace that you collected.</span></span> <span data-ttu-id="2d770-138">Führen Sie zu diesem Zweck den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2d770-138">To do this, use the following command:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip
```

<span data-ttu-id="2d770-139">Dadurch wird standardmäßig die CPU-Überwachung der Anwendung mithilfe von `perf` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2d770-139">By default, this will show the CPU trace of the application using `perf`.</span></span>

<span data-ttu-id="2d770-140">Zum Anzeigen der über `LTTng` erfassten Ereignisse können Sie das Flag `-viewer lttng` übergeben, um die einzelnen Ereignisse anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="2d770-140">To look at the events that were collected via `LTTng`, you can pass in the flag `-viewer lttng` to see the individual events:</span></span>

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

<span data-ttu-id="2d770-141">Dadurch wird der `babeltrace`-Viewer zum Drucken der Nutzdaten der Ereignisse verwendet:</span><span class="sxs-lookup"><span data-stu-id="2d770-141">This will use `babeltrace` viewer to print the events payload:</span></span>

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a><span data-ttu-id="2d770-142">Verwenden von PerfView zum Öffnen der Ablaufverfolgungsdatei</span><span class="sxs-lookup"><span data-stu-id="2d770-142">Use PerfView to open the trace file</span></span>

<span data-ttu-id="2d770-143">Zum Anzeigen einer Aggregatansicht sowohl des CPU-Beispiels als auch der Ereignisse können Sie `PerfView` auf einem Windows-Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d770-143">To see an aggregate view of both the CPU sample and the events, you can use `PerfView` on a Windows machine.</span></span>

1. <span data-ttu-id="2d770-144">Kopieren Sie die trace.zip-Datei von Linux auf einen Windows-Computer.</span><span class="sxs-lookup"><span data-stu-id="2d770-144">Copy the trace.zip file from Linux to a Windows machine.</span></span>

2. <span data-ttu-id="2d770-145">Laden Sie PerfView über den folgenden Link herunter: <https://aka.ms/perfview>.</span><span class="sxs-lookup"><span data-stu-id="2d770-145">Download PerfView from <https://aka.ms/perfview>.</span></span>

3. <span data-ttu-id="2d770-146">Führen Sie PerfView.exe aus.</span><span class="sxs-lookup"><span data-stu-id="2d770-146">Run PerfView.exe</span></span>

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

<span data-ttu-id="2d770-147">PerfView zeigt die Liste der Ansichten an, die auf der Grundlage der in der Ablaufverfolgungsdatei enthaltenen Daten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2d770-147">PerfView will display the list of views that are supported based on the data contained in the trace file.</span></span>

- <span data-ttu-id="2d770-148">Wählen Sie für CPU-Untersuchungen **CPU-Stapel** aus.</span><span class="sxs-lookup"><span data-stu-id="2d770-148">For CPU investigations, choose **CPU stacks**.</span></span>

- <span data-ttu-id="2d770-149">Wählen Sie für detaillierte Informationen **GCStats** aus.</span><span class="sxs-lookup"><span data-stu-id="2d770-149">For detailed GC information, choose **GCStats**.</span></span>

- <span data-ttu-id="2d770-150">Wählen Sie für JIT-Informationen pro Prozess/Modul/Methode **JITStats** aus.</span><span class="sxs-lookup"><span data-stu-id="2d770-150">For per-process/module/method JIT information, choose **JITStats**.</span></span>

- <span data-ttu-id="2d770-151">Wenn für die von Ihnen benötigten Informationen keine Ansicht vorhanden ist, können Sie versuchen, die Ereignisse in der Rohdatenansicht für Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d770-151">If there is not a view for the information you need, you can try looking for the events in the raw events view.</span></span>  <span data-ttu-id="2d770-152">Wählen Sie **Ereignisse** aus.</span><span class="sxs-lookup"><span data-stu-id="2d770-152">Choose **Events**.</span></span>

<span data-ttu-id="2d770-153">Weitere Informationen zum Interpretieren von Ansichten in PerfView finden Sie unter den Hilfeverknüpfungen in der Ansicht selbst oder im Hauptfenster von PerfView unter **Help > Users Guide** (Hilfe > Benutzerleitfaden).</span><span class="sxs-lookup"><span data-stu-id="2d770-153">For more information on how to interpret views in PerfView, see help links in the view itself, or from the main window in PerfView, choose **Help->Users Guide**.</span></span>

### <a name="use-tracecompass-to-open-the-trace-file"></a><span data-ttu-id="2d770-154">Verwenden von TraceCompass zum Öffnen der Ablaufverfolgungsdatei</span><span class="sxs-lookup"><span data-stu-id="2d770-154">Use TraceCompass to open the trace file</span></span>

<span data-ttu-id="2d770-155">[Eclipse Trace Compass](https://www.eclipse.org/tracecompass/) ist eine weitere Option zum Anzeigen der Ablaufverfolgungen.</span><span class="sxs-lookup"><span data-stu-id="2d770-155">[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) is another option you can use to view the traces.</span></span> <span data-ttu-id="2d770-156">`TraceCompass` funktioniert auch auf Linux-Computern, sodass Sie die Ablaufverfolgung nicht auf einen Windows-Computer verschieben müssen.</span><span class="sxs-lookup"><span data-stu-id="2d770-156">`TraceCompass` works on Linux machines as well, so you don't need to move your trace over to a Windows machine.</span></span> <span data-ttu-id="2d770-157">Wenn Sie `TraceCompass` zum Öffnen Ihrer Ablaufverfolgungsdatei verwenden möchten, müssen Sie die Datei entzippen.</span><span class="sxs-lookup"><span data-stu-id="2d770-157">To use `TraceCompass` to open your trace file, you will need to unzip the file.</span></span>

```bash
unzip myTrace.trace.zip
```

<span data-ttu-id="2d770-158">`perfcollect` speichert die erfasste LTTng-Ablaufverfolgung in einem CTF-Dateiformat in einem Unterverzeichnis von `lttngTrace`.</span><span class="sxs-lookup"><span data-stu-id="2d770-158">`perfcollect` will save the LTTng trace it collected into a CTF file format in a subdirectory in the `lttngTrace`.</span></span> <span data-ttu-id="2d770-159">Die CTF-Datei wird in einem Verzeichnis ähnlich dem folgenden gespeichert: `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span><span class="sxs-lookup"><span data-stu-id="2d770-159">Specifically, the CTF file will be located in a directory that looks like `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.</span></span>

<span data-ttu-id="2d770-160">Sie können die CTF-Ablaufverfolgungsdatei in `TraceCompass` öffnen, indem Sie auf `File -> Open Trace` und dann auf die `metadata`-Datei klicken.</span><span class="sxs-lookup"><span data-stu-id="2d770-160">You can open the CTF trace file in `TraceCompass` by selecting `File -> Open Trace` and select the `metadata` file.</span></span>

<span data-ttu-id="2d770-161">Weitere Informationen finden Sie in der [`TraceCompass`-Dokumentation](https://www.eclipse.org/tracecompass/).</span><span class="sxs-lookup"><span data-stu-id="2d770-161">For more details, please refer to [`TraceCompass` documentation](https://www.eclipse.org/tracecompass/).</span></span>

## <a name="resolve-framework-symbols"></a><span data-ttu-id="2d770-162">Auflösen von Frameworksymbolen</span><span class="sxs-lookup"><span data-stu-id="2d770-162">Resolve framework symbols</span></span>

<span data-ttu-id="2d770-163">Frameworksymbole müssen manuell generiert werden, wenn die Ablaufverfolgung erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="2d770-163">Framework symbols need to be manually generated at the time the trace is collected.</span></span> <span data-ttu-id="2d770-164">Sie unterscheiden sich von Symbolen auf App-Ebene, da das Framework vorkompiliert ist, während der App-Code JIT-kompiliert ist.</span><span class="sxs-lookup"><span data-stu-id="2d770-164">They are different than app-level symbols because the framework is pre-compiled while app code is just-in-time-compiled.</span></span> <span data-ttu-id="2d770-165">Bei Frameworkcode, der in nativen Code vorkompiliert wurde, müssen Sie für die Generierung der Zuordnung vom nativen Code zum Namen der Methoden `crossgen` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2d770-165">For framework code that was precompiled to native code, you need to call `crossgen` that knows how to generate the mapping from the native code to the name of the methods.</span></span>

<span data-ttu-id="2d770-166">`perfcollect` kann die meisten Details verarbeiten, `crossgen` muss jedoch verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="2d770-166">`perfcollect` can handle most of the details for you, but it needs to have `crossgen` available.</span></span> <span data-ttu-id="2d770-167">Es wird in der Standardeinstellung nicht mit der .NET-Verteilung installiert.</span><span class="sxs-lookup"><span data-stu-id="2d770-167">By default it is not installed with .NET distribution.</span></span> <span data-ttu-id="2d770-168">Wenn `crossgen` nicht vorhanden ist, werden Sie von `perfcollect` gewarnt und auf diese Anweisungen verwiesen.</span><span class="sxs-lookup"><span data-stu-id="2d770-168">If `crossgen` is not there, `perfcollect` warns you and refers you to these instructions.</span></span> <span data-ttu-id="2d770-169">Sie müssen exakt die richtige Version von crossgen für die verwendete Runtime abrufen, um Fehler zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2d770-169">To fix things you need to fetch exactly the right version of crossgen for the runtime you are using.</span></span> <span data-ttu-id="2d770-170">Wenn Sie das crossgen-Tool im gleichen Verzeichnis wie die .NET-Runtime-DLLs (z. B. libcoreclr.so) ablegen, kann `perfcollect` es finden und für Sie die Frameworksymbole der Ablaufverfolgungsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2d770-170">If you place the crossgen tool in the same directory as the .NET Runtime DLLs (for example, libcoreclr.so), then `perfcollect` can find it and add the framework symbols to the trace file for you.</span></span>

<span data-ttu-id="2d770-171">Normalerweise wird beim Erstellen einer .NET-Anwendung nur die DLL für den von Ihnen geschriebenen Code generiert. Dabei wird eine Shared Runtime für den Rest verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d770-171">Normally when you create a .NET application, it just generates the DLL for the code you wrote, using a shared copy of the runtime for the rest.</span></span>   <span data-ttu-id="2d770-172">Sie können jedoch auch eine sogenannte „eigenständige“ Version einer Anwendung generieren, die alle Runtime-DLLs enthält.</span><span class="sxs-lookup"><span data-stu-id="2d770-172">However you can also generate what is called a 'self-contained' version of an application and this contains all runtime DLLs.</span></span> <span data-ttu-id="2d770-173">`crossgen` ist Teil des NuGet-Pakets, das zum Erstellen eigenständiger Apps verwendet wird. Eine Möglichkeit zum Abrufen der richtigen `crossgen`-Version ist daher, ein eigenständiges Paket Ihrer Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d770-173">`crossgen` is part of the NuGet package that is used to create self-contained apps, so one way of getting the right version of `crossgen` is to create a self-contained package of your application.</span></span>

<span data-ttu-id="2d770-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2d770-174">For example:</span></span>

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

<span data-ttu-id="2d770-175">Dadurch wird eine neue Hallo Welt-Anwendung als eigenständige App erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d770-175">This creates a new Hello World application and builds it as a self-contained app.</span></span>

<span data-ttu-id="2d770-176">Als Nebeneffekt der Erstellung einer eigenständigen Anwendung lädt das .NET-Tool ein NuGet-Paket mit dem Namen „runtime.linux-x64.microsoft.netcore.app“ herunter und legt es im Verzeichnis „~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION“ ab, wobei VERSION für die Versionsnummer Ihrer .NET Core-Runtime (z. B. 2.1.0) steht.</span><span class="sxs-lookup"><span data-stu-id="2d770-176">As a side effect of creating the self-contained application the dotnet tool will download a NuGet package called runtime.linux-x64.microsoft.netcore.app and place it in the directory ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION, where VERSION is the version number of your .NET Core runtime (for example, 2.1.0).</span></span> <span data-ttu-id="2d770-177">Darunter befindet sich ein Toolverzeichnis, innerhalb dessen sich das von Ihnen benötigte crossgen-Tool befindet.</span><span class="sxs-lookup"><span data-stu-id="2d770-177">Under that is a tools directory and inside there is the crossgen tool you need.</span></span> <span data-ttu-id="2d770-178">Ab .NET Core 3.0 ist das Paketverzeichnis „~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION“.</span><span class="sxs-lookup"><span data-stu-id="2d770-178">Starting with .NET Core 3.0, the package location is ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION.</span></span>

<span data-ttu-id="2d770-179">Das `crossgen`-Tool muss neben der Runtime abgelegt werden, die tatsächlich von Ihrer Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d770-179">The `crossgen` tool needs to be put next to the runtime that is actually used by your application.</span></span> <span data-ttu-id="2d770-180">In der Regel verwendet Ihre App die unter „/usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION“ installierte freigegebene Version von .NET Core, wobei VERSION für die Versionsnummer der .NET-Runtime steht.</span><span class="sxs-lookup"><span data-stu-id="2d770-180">Typically your app uses the shared version of .NET Core that is installed at /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION where VERSION is the version number of the .NET Runtime.</span></span> <span data-ttu-id="2d770-181">Da es sich um einen freigegebenen Speicherort handelt, müssen Sie Administrator sein, um diesen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2d770-181">This is a shared location, so you need to be super-user to modify it.</span></span> <span data-ttu-id="2d770-182">Wenn die VERSION 2.1.0 ist, lauten die Befehle zum Aktualisieren von `crossgen` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d770-182">If the VERSION is 2.1.0 the commands to update `crossgen` would be:</span></span>

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

<span data-ttu-id="2d770-183">Sobald Sie diesen Schritt abgeschlossen haben, verwendet `perfcollect` crossgen zum Einschließen von Frameworksymbolen.</span><span class="sxs-lookup"><span data-stu-id="2d770-183">Once you have done this, `perfcollect` will use crossgen to include framework symbols.</span></span> <span data-ttu-id="2d770-184">Die von `perfcollect` üblicherweise ausgegebene Warnung sollte nicht mehr angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2d770-184">The warning that `perfcollect` used to issue should go away.</span></span> <span data-ttu-id="2d770-185">Dies muss nur einmal pro Computer erfolgen (bis Sie die Runtime aktualisieren).</span><span class="sxs-lookup"><span data-stu-id="2d770-185">This only has to be one once per machine (until you update your runtime).</span></span>

### <a name="alternative-turn-off-use-of-precompiled-code"></a><span data-ttu-id="2d770-186">Alternative: Deaktivieren der Verwendung von vorkompiliertem Code</span><span class="sxs-lookup"><span data-stu-id="2d770-186">Alternative: Turn off use of precompiled code</span></span>

<span data-ttu-id="2d770-187">Wenn Sie die .NET-Runtime nicht aktualisieren (`crossgen` nicht hinzufügen) können oder die oben beschriebene Prozedur aus irgendeinem Grund nicht funktioniert, können Sie einen anderen Ansatz zum Abrufen von Frameworksymbolen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d770-187">If you don't have the ability to update the .NET Runtime (to add `crossgen`), or if the above procedure did not work for some reason, there is another approach to getting framework symbols.</span></span> <span data-ttu-id="2d770-188">Sie können die Runtime anweisen, den vorkompilierten Frameworkcode einfach nicht zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d770-188">You can tell the runtime to simply not use the precompiled framework code.</span></span> <span data-ttu-id="2d770-189">Der Code wird JIT-kompiliert, und `crossgen` wird nicht benötigt.</span><span class="sxs-lookup"><span data-stu-id="2d770-189">The code will be Just-In-Time compiled and `crossgen` is not needed.</span></span>

> [!NOTE]
> <span data-ttu-id="2d770-190">Wenn Sie sich für diesen Ansatz entscheiden, könnte sich die Startzeit Ihrer Anwendung verlängern.</span><span class="sxs-lookup"><span data-stu-id="2d770-190">Choosing this approach may increase the startup time for your application.</span></span>

<span data-ttu-id="2d770-191">Hierfür können Sie die folgende Umgebungsvariable hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2d770-191">To do this, you can add the following environment variable:</span></span>

```bash
export COMPlus_ZapDisable=1
```

<span data-ttu-id="2d770-192">Mit dieser Änderung müssten die Symbole für den gesamten .NET-Code abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2d770-192">With this change, you should get the symbols for all .NET code.</span></span>

## <a name="get-symbols-for-the-native-runtime"></a><span data-ttu-id="2d770-193">Abrufen von Symbolen für die native Runtime</span><span class="sxs-lookup"><span data-stu-id="2d770-193">Get symbols for the native runtime</span></span>

<span data-ttu-id="2d770-194">In den meisten Fällen sind Sie an Ihrem eigenen Code interessiert, den `perfcollect` standardmäßig auflöst.</span><span class="sxs-lookup"><span data-stu-id="2d770-194">Most of the time you are interested in your own code, which `perfcollect` resolves by default.</span></span> <span data-ttu-id="2d770-195">Manchmal ist es hilfreich zu wissen, was innerhalb der .NET-DLLs vor sich geht (wovon der letzte Abschnitt handelte). Manchmal ist es aber auch interessant, was in den nativen Runtime-DLLs (in der Regel libcoreclr.so) geschieht.</span><span class="sxs-lookup"><span data-stu-id="2d770-195">Sometimes it is useful to see what is going on inside the .NET DLLs (which is what the last section was about), but sometimes what is going on in the native runtime dlls (typically libcoreclr.so), is interesting.</span></span>  <span data-ttu-id="2d770-196">`perfcollect` löst die Symbole für diese auf, wenn deren Daten konvertiert werden. Dies ist jedoch nur der Fall, wenn die Symbole für diese nativen DLLs vorhanden sind (und sich neben der Bibliothek befinden, der sie dienen).</span><span class="sxs-lookup"><span data-stu-id="2d770-196">`perfcollect` will resolve the symbols for these when it converts its data, but only if the symbols for these native DLLs are present (and are beside the library they are for).</span></span>

<span data-ttu-id="2d770-197">Sie können hierfür den globalen Befehl [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d770-197">There is a global command called [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) that does this.</span></span> <span data-ttu-id="2d770-198">So verwenden Sie „dotnet-symbol“ zum Abrufen von Symbolen der nativen Runtime:</span><span class="sxs-lookup"><span data-stu-id="2d770-198">To use dotnet-symbol to get native runtime symbols:</span></span>

1. <span data-ttu-id="2d770-199">Installieren Sie `dotnet-symbol`:</span><span class="sxs-lookup"><span data-stu-id="2d770-199">Install `dotnet-symbol`:</span></span>

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. <span data-ttu-id="2d770-200">Laden Sie die Symbole herunter.</span><span class="sxs-lookup"><span data-stu-id="2d770-200">Download the symbols.</span></span> <span data-ttu-id="2d770-201">Wenn Sie die Version 2.1.0 der .NET Core-Runtime installiert haben, lautet der Befehl hierfür folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="2d770-201">If your installed version of the .NET Core runtime is 2.1.0, the command to do this is:</span></span>

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. <span data-ttu-id="2d770-202">Kopieren Sie die Symbole in das richtige Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2d770-202">Copy the symbols to the correct place.</span></span>

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    <span data-ttu-id="2d770-203">Wenn dies nicht möglich ist, weil Sie keinen Schreibzugriff auf das entsprechende Verzeichnis haben, können Sie die Symbole mithilfe von `perf buildid-cache` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2d770-203">If this cannot be done because you do not have write access to the appropriate directory, you can use `perf buildid-cache` to add the symbols.</span></span>

<span data-ttu-id="2d770-204">Danach sollten symbolische Namen für die nativen DLLs zurückgegeben werden, wenn Sie `perfcollect` ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d770-204">After this, you should get symbolic names for the native dlls when you run `perfcollect`.</span></span>

## <a name="collect-in-a-docker-container"></a><span data-ttu-id="2d770-205">Sammeln in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="2d770-205">Collect in a Docker container</span></span>

<span data-ttu-id="2d770-206">Weitere Informationen zur Verwendung von `perfcollect` in Containerumgebungen finden Sie unter [Sammeln von Diagnosen in Containern](./diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="2d770-206">For more information on how to use `perfcollect` in container environments, see [Collect diagnostics in containers](./diagnostics-in-containers.md).</span></span>

## <a name="learn-more-about-collection-options"></a><span data-ttu-id="2d770-207">Weitere Informationen zu Sammlungsoptionen</span><span class="sxs-lookup"><span data-stu-id="2d770-207">Learn more about collection options</span></span>

<span data-ttu-id="2d770-208">Mit `perfcollect` können Sie die folgenden optionalen Flags gemäß Ihren Diagnoseanforderungen angeben.</span><span class="sxs-lookup"><span data-stu-id="2d770-208">You can specify the following optional flags with `perfcollect` to better suit your diagnostic needs.</span></span>

### <a name="collect-for-a-specific-duration"></a><span data-ttu-id="2d770-209">Sammeln für eine bestimmte Dauer</span><span class="sxs-lookup"><span data-stu-id="2d770-209">Collect for a specific duration</span></span>

<span data-ttu-id="2d770-210">Zum Sammeln einer Ablaufverfolgung für eine bestimmte Dauer ist die Option `-collectsec` geeignet, gefolgt von der Gesamtanzahl der Sekunden für die Sammlung.</span><span class="sxs-lookup"><span data-stu-id="2d770-210">When you want to collect a trace for a specific duration, you can use `-collectsec` option followed by a number specifying the total seconds to collect a trace for.</span></span>

### <a name="collect-threadtime-traces"></a><span data-ttu-id="2d770-211">Sammeln von Ablaufverfolgungen der Threadzeit</span><span class="sxs-lookup"><span data-stu-id="2d770-211">Collect threadtime traces</span></span>

<span data-ttu-id="2d770-212">Wenn Sie threadspezifische Daten zur CPU-Auslastung sammeln möchten, geben Sie `-threadtime` mit `perfcollect` an.</span><span class="sxs-lookup"><span data-stu-id="2d770-212">Specifying `-threadtime` with `perfcollect` lets you collect per-thread CPU usage data.</span></span> <span data-ttu-id="2d770-213">Auf diese Weise können Sie die CPU-Zeit pro Thread analysieren.</span><span class="sxs-lookup"><span data-stu-id="2d770-213">This lets you analyze where every thread was spending its CPU time.</span></span>

### <a name="collect-traces-for-managed-memory-and-garbage-collector-performance"></a><span data-ttu-id="2d770-214">Sammeln von Ablaufverfolgungen für die Leistung des Garbage Collectors und des verwalteten Speichers</span><span class="sxs-lookup"><span data-stu-id="2d770-214">Collect traces for managed memory and garbage collector performance</span></span>

<span data-ttu-id="2d770-215">Mit den folgenden Optionen können Sie die GC-Ereignisse direkt von der Laufzeit erfassen.</span><span class="sxs-lookup"><span data-stu-id="2d770-215">The following options let you specifically collect the GC events from the runtime.</span></span>

* `perfcollect collect -gccollectonly`

<span data-ttu-id="2d770-216">Es wird nur eine minimale Anzahl von GC-Ereignissen gesammelt.</span><span class="sxs-lookup"><span data-stu-id="2d770-216">Collect only a minimal set of GC Collection events.</span></span> <span data-ttu-id="2d770-217">Hierbei handelt es sich um das am wenigsten ausführliche Sammlungsprofil von GC-Ereignissen mit den geringsten Auswirkungen auf die Leistung der Ziel-App.</span><span class="sxs-lookup"><span data-stu-id="2d770-217">This is the least verbose GC eventing collection profile with the lowest impact on the target app's performance.</span></span> <span data-ttu-id="2d770-218">Dieser Befehl entspricht dem Befehl `PerfView.exe /GCCollectOnly collect` in PerfView.</span><span class="sxs-lookup"><span data-stu-id="2d770-218">This command is analogous to `PerfView.exe /GCCollectOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gconly`

<span data-ttu-id="2d770-219">Mit JIT-, Ladeprogramm- und Ausnahmeereignissen werden ausführlichere GC-Ereignisse gesammelt.</span><span class="sxs-lookup"><span data-stu-id="2d770-219">Collect more verbose GC collection events with JIT, Loader, and Exception events.</span></span> <span data-ttu-id="2d770-220">Dies erfordert ausführlichere Ereignisse (z. B. Zuordnungs- und GC-Joininformationen) und wirkt sich stärker auf die Leistung der Ziel-App aus als Option `-gccollectonly`.</span><span class="sxs-lookup"><span data-stu-id="2d770-220">This requests more verbose events (such as the allocation information and GC join information) and will have more impact to the target app's performance than `-gccollectonly` option.</span></span> <span data-ttu-id="2d770-221">Dieser Befehl entspricht dem Befehl `PerfView.exe /GCOnly collect` in PerfView.</span><span class="sxs-lookup"><span data-stu-id="2d770-221">This command is analogous to `PerfView.exe /GCOnly collect` command in PerfView.</span></span>

* `perfcollect collect -gcwithheap`

<span data-ttu-id="2d770-222">Hierbei werden die ausführlichsten GC-Ereignisse gesammelt, die auch die beibehaltenen Objekte und Bewegungen des Heaps nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="2d770-222">Collect the most verbose GC collection events which tracks the heap survival and movements as well.</span></span> <span data-ttu-id="2d770-223">Dies ermöglicht eine detaillierte Analyse des GC-Verhaltens, führt jedoch zu hohen Leistungseinbußen, da jede GC mehr als doppelt so lange dauern kann.</span><span class="sxs-lookup"><span data-stu-id="2d770-223">This gives in-depth analysis of the GC behavior but will incur high performance cost as each GC can take more than two times longer.</span></span> <span data-ttu-id="2d770-224">Wenn Sie Ablaufverfolgungen in Produktionsumgebungen verwenden möchten, sollten Sie über die Auswirkungen dieser Option auf die Leistung Bescheid wissen.</span><span class="sxs-lookup"><span data-stu-id="2d770-224">It is recommended you understand the performance implication of using this trace option when tracing in production environments.</span></span>
