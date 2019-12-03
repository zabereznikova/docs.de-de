---
title: Ablaufverfolgung und Nachrichtenprotokollierung
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: f6f2fd0bbbc191d466ac600bd9639c8955d5b7fe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715677"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="59433-102">Ablaufverfolgung und Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="59433-102">Tracing and Message Logging</span></span>
<span data-ttu-id="59433-103">In diesem Beispiel wird das Aktivieren der Ablaufverfolgung und Nachrichtenprotokollierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="59433-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="59433-104">Die resultierenden Ablauf Verfolgungen und Nachrichten Protokolle werden mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59433-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="59433-105">Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="59433-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59433-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="59433-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="59433-107">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="59433-107">Tracing</span></span>  
 <span data-ttu-id="59433-108">Windows Communication Foundation (WCF) verwendet den Ablauf Verfolgungs Mechanismus, der im <xref:System.Diagnostics>-Namespace definiert ist.</span><span class="sxs-lookup"><span data-stu-id="59433-108">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="59433-109">In diesem Ablaufverfolgungsmodell werden Ablaufverfolgungsdaten von Ablaufverfolgungsquellen erzeugt, die von Anwendungen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="59433-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="59433-110">Jede Quelle wird durch einen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="59433-110">Each source is identified by a name.</span></span> <span data-ttu-id="59433-111">Ablaufverfolgungsconsumer erstellen Ablaufverfolgungslistener für die Ablaufverfolgungsquellen, für die sie Informationen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="59433-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="59433-112">Sie müssen einen Listener für die Ablaufverfolgungsquelle erstellen, um Ablaufverfolgungsdaten zum empfangen.</span><span class="sxs-lookup"><span data-stu-id="59433-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="59433-113">In WCF kann dies erreicht werden, indem der folgende Code entweder in der Konfigurationsdatei des dienstanders oder des Clients hinzugefügt wird, indem die `switchValue`der Dienstmodell-Ablauf Verfolgungs Quelle festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="59433-113">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="59433-114">Weitere Informationen zu Ablauf Verfolgungs Quellen finden Sie im Abschnitt "Ablauf Verfolgungs Quelle" im Thema Konfigurieren der Ablauf [Verfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="59433-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="59433-115">Aktivitätsablaufverfolgung und Weitergabe</span><span class="sxs-lookup"><span data-stu-id="59433-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="59433-116">Wenn `ActivityTracing` aktiviert und `propagateActivity` auf `true` in den `system.ServiceModel`-Ablauf Verfolgungs Quellen für den Client und den Dienst festgelegt ist, stellen Sie die Korrelation von Ablauf Verfolgungen innerhalb logischer Verarbeitungseinheiten (Aktivitäten), über Aktivitäten innerhalb von Endpunkten (über Aktivitäts Übertragungen) und über Aktivitäten hinweg bereit, die mehrere Endpunkte umfassen (über die Aktivitäts-ID-Propagierung).</span><span class="sxs-lookup"><span data-stu-id="59433-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="59433-117">Mithilfe dieser drei Mechanismen (Aktivitäten, Übertragungen und Weitergabe) können Sie die Grundursache eines Fehlers schneller mit dem Tool Service Trace Viewer ermitteln.</span><span class="sxs-lookup"><span data-stu-id="59433-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="59433-118">Weitere Informationen finden Sie unter [Verwenden von Service Trace Viewer zum Anzeigen korrelierter Ablauf Verfolgungen und Problem](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)Behandlung.</span><span class="sxs-lookup"><span data-stu-id="59433-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="59433-119">Durch das Erstellen von benutzerdefinierten Aktivitätsablaufverfolgungen kann die von ServiceModel bereitgestellte Ablaufverfolgung erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="59433-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="59433-120">Durch die benutzerdefinierte Aktivitätsablaufverfolgung kann der Benutzer Ablaufverfolgungsaktivitäten für folgenden Aktionen erstellen:</span><span class="sxs-lookup"><span data-stu-id="59433-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="59433-121">Gruppieren von Ablaufverfolgungen in logische Arbeitseinheiten.</span><span class="sxs-lookup"><span data-stu-id="59433-121">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="59433-122">Korrelieren von Aktivitäten durch Übertragungen und Weitergabe.</span><span class="sxs-lookup"><span data-stu-id="59433-122">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="59433-123">Verringern der Leistungskosten der WCF-Ablauf Verfolgung (z. b. der Speicherplatz Kosten einer Protokolldatei).</span><span class="sxs-lookup"><span data-stu-id="59433-123">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="59433-124">Weitere Informationen zur benutzerdefinierten Aktivitäts Ablauf Verfolgung finden Sie im Beispiel zum [erweitern](../../../../docs/framework/wcf/samples/extending-tracing.md) der Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="59433-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="59433-125">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="59433-125">Message Logging</span></span>  
 <span data-ttu-id="59433-126">Die Nachrichten Protokollierung kann sowohl auf dem Client als auch auf dem Dienst einer beliebigen WCF-Anwendung aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="59433-126">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="59433-127">Zum Aktivieren der Nachrichtenprotokollierung müssen Sie dem Client oder dem Dienst den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="59433-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="59433-128">Wenn eine Nachricht aufgezeichnet wird, ist der Ablaufverfolgungstyp abhängig davon, ob die Ablaufverfolgung beim Client oder beim Server erfolgt.</span><span class="sxs-lookup"><span data-stu-id="59433-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="59433-129">Eine "Add"-Nachricht, die an einen Client gesendet wird, wird beispielsweise in der Kategorie "TransportWrite" beim Client verfolgt, während die gleiche Nachricht beim Dienst in der Kategorie "TransportRead" verfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="59433-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="59433-130">Konfigurieren Sie den Ablaufverfolgungslistener, indem Sie den folgenden Code im <xref:System.Diagnostics>-Abschnitt der Datei "App.config" für den Client oder der Datei "Web.config" für den Dienst hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="59433-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="59433-131">Nachrichten werden im XML-Format in dem in der Konfigurationsdatei angegebenen Zielverzeichnis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="59433-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59433-132">Ablaufverfolgungsdateien werden nur erstellt, wenn zuerst das Protokollverzeichnis erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="59433-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="59433-133">Stellen Sie sicher, dass das Verzeichnis C:\logs\ vorhanden ist, oder geben Sie ein anderes Protokollierungsverzeichnis in der Listenerkonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="59433-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="59433-134">Weitere Informationen finden Sie in den Anweisungen zum ersten Einrichten am Ende dieses Dokuments.</span><span class="sxs-lookup"><span data-stu-id="59433-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="59433-135">Weitere Informationen zur Nachrichten Protokollierung finden Sie im Thema [Konfigurieren der Nachrichten Protokollierung](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="59433-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="59433-136">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="59433-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="59433-137">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="59433-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="59433-138">Bevor Sie das Beispiel zur Ablaufverfolgung und Nachrichtenprotokollierung ausführen, erstellen Sie das Verzeichnis C:\logs\, in das der Dienst die SVCLOG-Dateien schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="59433-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="59433-139">Der Name dieses Verzeichnisses wird in der Konfigurationsdatei als Pfad für die zu protokollierenden Ablaufverfolgungen und Nachrichten definiert und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="59433-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="59433-140">Weisen Sie dem Benutzer Network Service Schreibzugriff für das Protokollverzeichnis zu.</span><span class="sxs-lookup"><span data-stu-id="59433-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="59433-141">Befolgen Sie zum C#erstellen C++der-,-oder-Visual Basic .NET-Edition der Projekt Mappe die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59433-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="59433-142">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="59433-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="59433-143">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="59433-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="59433-144">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="59433-144">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="59433-145">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="59433-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59433-146">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="59433-146">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="59433-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59433-147">See also</span></span>

- [<span data-ttu-id="59433-148">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="59433-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="59433-149">AppFabric-Überwachungs Beispiele</span><span class="sxs-lookup"><span data-stu-id="59433-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
