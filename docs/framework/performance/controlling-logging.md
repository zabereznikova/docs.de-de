---
title: Steuern der Protokollierung in .NET Framework
description: Verwenden Sie die Ereignis Ablauf Verfolgung für Windows (Event Tracing for Windows, etw), um die .net-Protokollierung zu steuern und Ereignisse aufzuzeichnen Common Language Runtime Verwenden Sie Tools wie logman, tracerpt und XPerf.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: 45d9244eb11b914fd203f24057e1b65c6bef18c2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309585"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="bb232-104">Steuern der Protokollierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bb232-104">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="bb232-105">Sie können mithilfe der Ereignisablaufverfolgung für Windows (ETW) Common Language Runtime (CLR)-Ereignisse aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bb232-105">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="bb232-106">Sie können Ablaufverfolgungen mit den folgenden Tools erstellen und anzeigen:</span><span class="sxs-lookup"><span data-stu-id="bb232-106">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="bb232-107">Die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) sind im Windows-Betriebssystem enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb232-107">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="bb232-108">Die [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference)-Tools im [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="bb232-108">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="bb232-109">Weitere Informationen zu Xperf finden Sie im [Windows Performance-Blog](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span><span class="sxs-lookup"><span data-stu-id="bb232-109">For more information about Xperf, see the [Windows Performance blog](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span></span>

<span data-ttu-id="bb232-110">Wenn Sie CLR-Ereignisinformationen erfassen möchten, muss der CLR-Anbieter auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb232-110">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="bb232-111">Geben Sie an der Eingabeaufforderung `logman query providers` ein, um festzustellen, ob der Anbieter installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bb232-111">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="bb232-112">Eine Anbieterliste wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb232-112">A list of providers is displayed.</span></span> <span data-ttu-id="bb232-113">Diese Liste sollte wie folgt einen Eintrag für den CLR-Anbieter enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb232-113">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="bb232-114">Wenn der CLR-Anbieter nicht aufgeführt ist, können Sie ihn unter Windows Vista und späteren Betriebssystemen mithilfe des Windows-Befehlszeilentools [Wevtutil](/windows-server/administration/windows-commands/wevtutil) installieren.</span><span class="sxs-lookup"><span data-stu-id="bb232-114">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="bb232-115">Öffnen Sie das Eingabeaufforderungsfenster als Administrator.</span><span class="sxs-lookup"><span data-stu-id="bb232-115">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="bb232-116">Ändern Sie das Eingabe Aufforderungs Verzeichnis in den Ordner .NET Framework 4 (%windir%\Microsoft.NET\Framework [64] \v4. \<.NET version> ). \ ).</span><span class="sxs-lookup"><span data-stu-id="bb232-116">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="bb232-117">Dieser Ordner enthält die Datei "CLR-ETW.man".</span><span class="sxs-lookup"><span data-stu-id="bb232-117">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="bb232-118">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, um den CLR-Anbieter zu installieren:</span><span class="sxs-lookup"><span data-stu-id="bb232-118">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="bb232-119">Erfassen von CLR-ETW-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="bb232-119">Capturing CLR ETW Events</span></span>

<span data-ttu-id="bb232-120">Sie können die Befehlszeilentools [Logman](/windows-server/administration/windows-commands/logman) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) verwenden, um ETW-Ereignisse zu erfassen. Mit den Tools [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) und [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) können Sie die Ablaufverfolgungsereignisse dekodieren.</span><span class="sxs-lookup"><span data-stu-id="bb232-120">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="bb232-121">Zum Aktivieren der Protokollierung müssen Benutzer drei Informationen angeben:</span><span class="sxs-lookup"><span data-stu-id="bb232-121">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="bb232-122">Anbieter, mit dem kommuniziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb232-122">The provider to communicate to.</span></span>

- <span data-ttu-id="bb232-123">Eine 64-Bit-Zahl, die einen Satz von Schlüsselwörtern darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb232-123">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="bb232-124">Jedes Schlüsselwort stellt einen Satz von Ereignissen dar, den der Anbieter aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="bb232-124">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="bb232-125">Die Zahl stellt einen kombinierten Satz von Schlüsselwörtern dar, die aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb232-125">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="bb232-126">Eine kleine Zahl, die die Ebene (den Ausführlichkeitsgrad) der Protokollierung darstellt.</span><span class="sxs-lookup"><span data-stu-id="bb232-126">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="bb232-127">Ebene 1 ist die am wenigsten ausführliche, Ebene 5 die ausführlichste.</span><span class="sxs-lookup"><span data-stu-id="bb232-127">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="bb232-128">Ebene 0 ist ein Standard mit anbieterspezifischer Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="bb232-128">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="bb232-129">So erfassen Sie CLR-ETW-Ereignisse mit Logman</span><span class="sxs-lookup"><span data-stu-id="bb232-129">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="bb232-130">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bb232-130">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="bb232-131">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="bb232-131">where:</span></span>

    - <span data-ttu-id="bb232-132">Durch den `-p`-Parameter wird die Anbieter-GUID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bb232-132">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="bb232-133">`0x1CCBD` gibt die Kategorien der Ereignisse an, die ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="bb232-133">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="bb232-134">`0x5` legt die Ebene der Protokollierung fest (in diesem Fall "Ausführlich" (5)).</span><span class="sxs-lookup"><span data-stu-id="bb232-134">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="bb232-135">Mit dem `-ets`-Parameter wird Logman angewiesen, Befehle an Ereignisablaufverfolgungs-Sitzungen zu senden.</span><span class="sxs-lookup"><span data-stu-id="bb232-135">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="bb232-136">Der `-ct perf`-Parameter gibt an, dass mit der `QueryPerformanceCounter`-Funktion der Zeitstempel für jedes Ereignis protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="bb232-136">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="bb232-137">Geben Sie Folgendes ein, um die Protokollierung der Ereignisse zu beenden:</span><span class="sxs-lookup"><span data-stu-id="bb232-137">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="bb232-138">Mit diesem Befehl wird eine binäre Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb232-138">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="bb232-139">So erfassen Sie CLR-ETW-Ereignisse mit XPerf</span><span class="sxs-lookup"><span data-stu-id="bb232-139">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="bb232-140">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bb232-140">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="bb232-141">Dabei ist die GUID die GUID des CLR-ETW-Anbieters, und `0x1CCBD:5` verfolgt sämtliche Vorgänge auf und unterhalb von Ebene 5 (Ausführlich).</span><span class="sxs-lookup"><span data-stu-id="bb232-141">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="bb232-142">Geben Sie Folgendes ein, um die Ablaufverfolgung zu beenden:</span><span class="sxs-lookup"><span data-stu-id="bb232-142">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="bb232-143">Mit diesem Befehl wird eine Ablaufverfolgungsdatei mit dem Namen "clrevents.etl" erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb232-143">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="bb232-144">Anzeigen von CLR-ETW-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="bb232-144">Viewing CLR ETW Events</span></span>

<span data-ttu-id="bb232-145">Verwenden Sie die unten aufgeführten Befehle, um die CLR-ETW-Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb232-145">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="bb232-146">Eine Beschreibung der Ereignisse finden Sie unter [CLR-ETW-Ereignisse](clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="bb232-146">For a description of the events, see [CLR ETW Events](clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="bb232-147">So zeigen Sie CLR-ETW-Ereignisse mit Tracerpt an</span><span class="sxs-lookup"><span data-stu-id="bb232-147">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="bb232-148">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bb232-148">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="bb232-149">Mit diesem Befehl werden zwei Dateien erstellt: "dumpfile.xml" und "summary.txt".</span><span class="sxs-lookup"><span data-stu-id="bb232-149">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="bb232-150">In der Datei "dumpfile.xml" werden alle Ereignisse aufgeführt, wohingegen "summary.txt" eine Zusammenfassung der Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="bb232-150">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="bb232-151">So zeigen Sie CLR-ETW-Ereignisse mit Xperf an</span><span class="sxs-lookup"><span data-stu-id="bb232-151">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="bb232-152">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bb232-152">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="bb232-153">Mit diesem Befehl wird der ETL-Datei-Viewer von Xperf geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bb232-153">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="bb232-154">In diesem Viewer werden die CLR-Ereignisse in der Ansicht **Generische Ereignisse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb232-154">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="bb232-155">Zum Anzeigen eines nach Typen kategorisierten Datenrasters von Ereignissen wählen Sie in der Ansicht einen Zeitraum aus, klicken Sie dann mit der rechten Maustaste, und wählen Sie **Zusammenfassung** aus.</span><span class="sxs-lookup"><span data-stu-id="bb232-155">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="bb232-156">So konvertieren Sie die ETL-Datei in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="bb232-156">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="bb232-157">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="bb232-157">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="bb232-158">Dieser Befehl bewirkt, dass XPerf die Ereignisse als CSV-Datei (CSV) sichert, die Sie anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bb232-158">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="bb232-159">Da für unterschiedliche Ereignisse auch unterschiedliche Felder verfügbar sind, enthält diese CSV-Datei vor den Daten mehrere Headerzeilen.</span><span class="sxs-lookup"><span data-stu-id="bb232-159">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="bb232-160">Das erste Feld jeder Zeile ist für den Ereignistyp vorgesehen, der den Header angibt, der zum Ermitteln der weiteren Felder verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb232-160">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb232-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb232-161">See also</span></span>

- [<span data-ttu-id="bb232-162">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="bb232-162">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="bb232-163">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bb232-163">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
