---
title: Zirkuläre Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 1f6c5287e6a53ed26ee5c9ed477e08dafc512e3f
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45569475"
---
# <a name="circular-tracing"></a><span data-ttu-id="e29bc-102">Zirkuläre Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e29bc-102">Circular Tracing</span></span>
<span data-ttu-id="e29bc-103">Dieses Beispiel veranschaulicht die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners.</span><span class="sxs-lookup"><span data-stu-id="e29bc-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="e29bc-104">Ein gängiges Szenario bei Produktionsdiensten besteht darin, dass Dienste vorhanden sind, die für längere Zeiträume verfügbar sind, und dass die Ablaufverfolgung auf einer unteren Ebene aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e29bc-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="e29bc-105">Diese Dienste belegen viel Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="e29bc-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="e29bc-106">Bei der Problembehandlung sind zum Lösen eines Problems bei einem Dienst die aktuellsten Daten aus dem Ablaufverfolgungsprotokoll relevant.</span><span class="sxs-lookup"><span data-stu-id="e29bc-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="e29bc-107">Dieses Beispiel zeigt die Implementierung eines zirkulären Puffer-Ablaufverfolgungslisteners, bei der nur die neuesten Ablaufverfolgungen bis zu einer zu konfigurierenden Datenmenge auf der Festplatte aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="e29bc-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="e29bc-108">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und einen benutzerdefinierten Ablaufverfolgungslistener enthält.</span><span class="sxs-lookup"><span data-stu-id="e29bc-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes a custom tracing listener.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e29bc-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e29bc-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e29bc-110">In diesem Beispiel wird davon ausgegangen, dass Sie kennen die [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel und Leseberechtigungen für die Dokumentation für die [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e29bc-110">This sample assumes that you are familiar with the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="e29bc-111">Zirkulärer Puffer-Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="e29bc-111">Circular Buffer Trace Listener</span></span>  
 <span data-ttu-id="e29bc-112">Die Implementierung des zirkulären Puffer-Ablaufverfolgungslisteners beruht auf dem Konzept, dass zwei Dateien vorhanden sind, von denen jede bis zur Hälfte der gewünschten Ablaufverfolgungsprotokolldaten speichern kann.</span><span class="sxs-lookup"><span data-stu-id="e29bc-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="e29bc-113">Der Listener erstellt eine Datei und schreibt in diese, bis sie den Grenzwert der halben Datengröße erreicht. Dann wechselt der Listener zu einer zweiten Datei.</span><span class="sxs-lookup"><span data-stu-id="e29bc-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="e29bc-114">Wenn der Listener den Grenzwert bei der zweiten Datei erreicht, überschreibt er die erste Datei mit neuen Ablaufverfolgungen.</span><span class="sxs-lookup"><span data-stu-id="e29bc-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>  
  
 <span data-ttu-id="e29bc-115">Dieser Listener leitet sich von der `XmlWriteTraceListener` und ermöglicht es die Protokolle angezeigt werden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e29bc-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="e29bc-116">Beim Anzeigen der Protokolle können die beiden Protokolldateien leicht rekombiniert werden, indem man beide Protokolldateien gleichzeitig im Service Trace Viewer öffnet.</span><span class="sxs-lookup"><span data-stu-id="e29bc-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="e29bc-117">Der Service Trace Viewer erledigt automatisch das Sortieren der Ablaufverfolgungen, so dass diese in der korrekten Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e29bc-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e29bc-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e29bc-118">Configuration</span></span>  
 <span data-ttu-id="e29bc-119">Durch Hinzufügen des folgenden Codes für einen Listener und Quellelemente kann ein Dienst zum Verwenden des zirkulären Puffer-Ablaufverfolgungslisteners konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e29bc-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="e29bc-120">Die maximale Dateigröße wird durch Angeben des `maxFileSizeKB`-Attributs in der Konfiguration des zirkulären Ablaufverfolgungslisteners festlegt.</span><span class="sxs-lookup"><span data-stu-id="e29bc-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="e29bc-121">Dies wird im folgenden Code demonstriert.</span><span class="sxs-lookup"><span data-stu-id="e29bc-121">This is demonstrated in the following code.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">  
      <listeners>  
        <add name="CircularTraceListener" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"   
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e29bc-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e29bc-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e29bc-123">Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e29bc-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e29bc-124">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e29bc-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e29bc-125">Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e29bc-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e29bc-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e29bc-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e29bc-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e29bc-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e29bc-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e29bc-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e29bc-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e29bc-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a><span data-ttu-id="e29bc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e29bc-130">See Also</span></span>  
 [<span data-ttu-id="e29bc-131">AppFabric-Überwachungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="e29bc-131">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
