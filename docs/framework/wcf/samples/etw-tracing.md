---
title: ETW-Ablaufverfolgung
description: In diesem Beispiel wird veranschaulicht, wie End-to-End (E2E)-Ablauf Verfolgung mithilfe der Ereignis Ablauf Verfolgung für Windows (ETW) und ETWTraceListener implementiert wird.
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 6777b2d14786f7a79b3605bec93b4da62ff24616
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258477"
---
# <a name="etw-tracing"></a><span data-ttu-id="d03d5-103">ETW-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d03d5-103">ETW Tracing</span></span>

<span data-ttu-id="d03d5-104">In diesem Beispiel wird das Implementieren der End-to-End (E2E)-Ablaufverfolgung mit Event Tracing for Windows (ETW) und dem in diesem Beispiel bereitgestellten `ETWTraceListener` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d03d5-104">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="d03d5-105">Das Beispiel basiert auf den ersten [Schritten und umfasst](getting-started-sample.md) die ETW-Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="d03d5-105">The sample is based on the [Getting Started](getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d03d5-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="d03d5-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d03d5-107">In diesem Beispiel wird davon ausgegangen, dass Sie mit Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md)vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="d03d5-107">This sample assumes that you are familiar with [Tracing and Message Logging](tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="d03d5-108">Alle Ablaufverfolgungsquellen im <xref:System.Diagnostics>-Ablaufverfolgungsmodell können über mehrere Ablaufverfolgungslistener verfügen, die bestimmen, wann und wie die Daten verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="d03d5-108">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="d03d5-109">Der Typ des Listeners definiert das Format, in dem Ablaufverfolgungsdaten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="d03d5-109">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="d03d5-110">Im folgenden Codebeispiel wird das Hinzufügen eines Listeners zur Konfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d03d5-110">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="d03d5-111">Damit dieser Listener verwendet werden kann, muss eine ETW-Ablaufverfolgungssitzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="d03d5-111">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="d03d5-112">Diese Sitzung kann mithilfe von Logman.exe oder Tracelog.exe gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="d03d5-112">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="d03d5-113">Dieses Beispiel umfasst die Datei "SetupETW.bat", sodass Sie die ETW-Ablaufverfolgungssitzung einrichten können. Außerdem wird die Datei "CleanupETW.bat" zum Schließen der Sitzung und Abschließen der Protokolldatei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d03d5-113">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d03d5-114">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="d03d5-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="d03d5-115">Weitere Informationen zu diesen Tools finden Sie unter. <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="d03d5-115">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="d03d5-116">Bei der Verwendung von ETWTraceListener werden Ablaufverfolgungen in binären ETL-Dateien protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d03d5-116">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="d03d5-117">Wenn die ServiceModel-Ablaufverfolgung aktiviert ist, werden alle generierten Ablaufverfolgungen in der gleichen Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d03d5-117">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="d03d5-118">Verwenden Sie das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen von ETL-und SVCLOG-Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="d03d5-118">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="d03d5-119">Der Viewer erstellt eine End-to-End-Ansicht des Systems, mit der eine Nachricht von der Quelle zum Ziel und zur Verwendung verfolgt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d03d5-119">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="d03d5-120">Der ETW-Ablaufverfolgungslistener unterstützt zirkuläre Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="d03d5-120">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="d03d5-121">Um dieses Feature zu aktivieren, wechseln Sie zu **Start**, **Ausführen** , und geben `cmd` Sie ein, um eine Befehlskonsole zu starten.</span><span class="sxs-lookup"><span data-stu-id="d03d5-121">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="d03d5-122">Ersetzen Sie im folgenden Befehl den `<logfilename>`-Parameter durch den Namen der Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="d03d5-122">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="d03d5-123">Der `-f`-Schalter und der `-max`-Schalter sind optional.</span><span class="sxs-lookup"><span data-stu-id="d03d5-123">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="d03d5-124">Sie geben das binäre zirkuläre Format bzw. die maximale Protokollgröße von 1000 MB an.</span><span class="sxs-lookup"><span data-stu-id="d03d5-124">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="d03d5-125">Mit dem `-p`-Schalter wird der Ablaufverfolgungsanbieter angegeben.</span><span class="sxs-lookup"><span data-stu-id="d03d5-125">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="d03d5-126">In diesem Beispiel ist `"{411a0819-c24b-428c-83e2-26b41091702e}"` die GUID für "XML ETW Sample Provider".</span><span class="sxs-lookup"><span data-stu-id="d03d5-126">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="d03d5-127">Geben Sie den folgenden Befehl ein, um die Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="d03d5-127">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="d03d5-128">Nach Abschluss der Protokollierung können Sie die Sitzung mit dem folgenden Befehl beenden.</span><span class="sxs-lookup"><span data-stu-id="d03d5-128">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="d03d5-129">Bei diesem Prozess werden binäre zirkuläre Protokolle generiert, die Sie mit dem Tool Ihrer Wahl verarbeiten können, einschließlich des [Service Trace Viewer-Tools (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) oder der tracerpt.</span><span class="sxs-lookup"><span data-stu-id="d03d5-129">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="d03d5-130">Weitere Informationen zu einem alternativen Listener zum Durchführen der zirkulären Protokollierung finden Sie auch im Beispiel für eine [zirkuläre Ablauf Verfolgung](circular-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="d03d5-130">You can also review the [Circular Tracing](circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d03d5-131">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d03d5-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d03d5-132">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d03d5-132">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d03d5-133">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d03d5-133">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d03d5-134">Zur Verwendung der Befehle RegisterProvider.bat, SetupETW.bat und CleanupETW.bat muss die Ausführung unter einem lokalen Administratorkonto erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d03d5-134">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="d03d5-135">Wenn Sie Windows Vista oder höher verwenden, müssen Sie auch die Eingabeaufforderung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="d03d5-135">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="d03d5-136">Klicken Sie hierzu mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d03d5-136">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="d03d5-137">Führen Sie vor dem Ausführen des Beispiels RegisterProvider.bat auf dem Client und dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="d03d5-137">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="d03d5-138">Dadurch wird die resultierende Datei ETWTracingSampleLog.etl zum Generieren von Ablaufverfolgungen eingerichtet, die von Service Trace Viewer angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="d03d5-138">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="d03d5-139">Diese Datei befindet sich im Ordner C:\logs.</span><span class="sxs-lookup"><span data-stu-id="d03d5-139">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="d03d5-140">Wenn dieser Ordner nicht vorhanden ist, muss er erstellt werden. Andernfalls werden keine Ablaufverfolgungen generiert.</span><span class="sxs-lookup"><span data-stu-id="d03d5-140">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="d03d5-141">Führen Sie dann SetupETW.bat auf dem Client- und dem Servercomputer aus, um die ETW-Ablaufverfolgungssitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="d03d5-141">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="d03d5-142">Die Datei SetupETW.bat befindet sich unter dem Ordner CS\Client.</span><span class="sxs-lookup"><span data-stu-id="d03d5-142">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="d03d5-143">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d03d5-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="d03d5-144">Führen Sie nach dem Abschließen des Beispiels CleanupETW.bat aus, um das Erstellen der Datei ETWTracingSampleLog.etl abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d03d5-144">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="d03d5-145">Öffnen Sie die Datei "ETWTracingSampleLog.etl" in Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="d03d5-145">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="d03d5-146">Sie werden aufgefordert, die binär formatierte Datei als SVCLOG-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d03d5-146">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="d03d5-147">Öffnen Sie die neu erstellte SVCLOG-Datei im Viewer für Dienstabläufe, um die ETW- und ServiceModel-Ablaufverfolgungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d03d5-147">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d03d5-148">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d03d5-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d03d5-149">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d03d5-149">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d03d5-150">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d03d5-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d03d5-151">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d03d5-151">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="d03d5-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d03d5-152">See also</span></span>

- <span data-ttu-id="d03d5-153">[AppFabric-Überwachungsbeispiele](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d03d5-153">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
