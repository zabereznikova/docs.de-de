---
title: Ablaufverfolgung und Nachrichtenprotokollierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cae7d806ce68f6804f97195c9bf2571328af6dff
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="e4905-102">Ablaufverfolgung und Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e4905-102">Tracing and Message Logging</span></span>
<span data-ttu-id="e4905-103">In diesem Beispiel wird das Aktivieren der Ablaufverfolgung und Nachrichtenprotokollierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e4905-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="e4905-104">Die resultierende ablaufverfolgungen und Nachrichtenprotokollen mit angezeigt werden die [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="e4905-105">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4905-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e4905-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="e4905-107">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e4905-107">Tracing</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="e4905-108"> verwendet den im <xref:System.Diagnostics>-Namespace definierten Ablaufverfolgungsmechanismus.</span><span class="sxs-lookup"><span data-stu-id="e4905-108"> uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="e4905-109">In diesem Ablaufverfolgungsmodell werden Ablaufverfolgungsdaten von Ablaufverfolgungsquellen erzeugt, die von Anwendungen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4905-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="e4905-110">Jede Quelle wird durch einen Namen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e4905-110">Each source is identified by a name.</span></span> <span data-ttu-id="e4905-111">Ablaufverfolgungsconsumer erstellen Ablaufverfolgungslistener für die Ablaufverfolgungsquellen, für die sie Informationen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="e4905-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="e4905-112">Sie müssen einen Listener für die Ablaufverfolgungsquelle erstellen, um Ablaufverfolgungsdaten zum empfangen.</span><span class="sxs-lookup"><span data-stu-id="e4905-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="e4905-113">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann hierzu der folgende Code in der Konfigurationsdatei des Diensts oder Clients hinzugefügt werden, indem die Dienstmodell-Ablaufverfolgungsquelle `switchValue` festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="e4905-113">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
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
  
 <span data-ttu-id="e4905-114">Weitere Informationen zu Ablaufverfolgungsquellen, finden Sie im Abschnitt Ablaufverfolgungsquelle in der [Konfigurieren der Ablaufverfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="e4905-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="e4905-115">Aktivitätsablaufverfolgung und Weitergabe</span><span class="sxs-lookup"><span data-stu-id="e4905-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="e4905-116">Mit `ActivityTracing` aktiviert und `propagateActivity` festgelegt `true` in die `system.ServiceModel` Ablaufverfolgungsquellen für Client und Dienst Korrelation von ablaufverfolgungen in logischen Verarbeitungseinheiten (Aktivitäten), geben Sie über Aktivitäten innerhalb von Endpunkten ( durch aktivitätsübertragungen) und über Aktivitäten über mehrere Endpunkte (über die ID-Aktivitätsweitergabe).</span><span class="sxs-lookup"><span data-stu-id="e4905-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="e4905-117">Mithilfe dieser drei Mechanismen (Aktivitäten, Übertragungen und Weitergabe) können Sie die Grundursache eines Fehlers schneller mit dem Tool Service Trace Viewer ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e4905-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="e4905-118">Weitere Informationen finden Sie unter [mithilfe von Service Trace Viewer für korrelierte Ablaufverfolgungen anzeigen und Problembehandlung](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="e4905-119">Durch das Erstellen von benutzerdefinierten Aktivitätsablaufverfolgungen kann die von ServiceModel bereitgestellte Ablaufverfolgung erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="e4905-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="e4905-120">Durch die benutzerdefinierte Aktivitätsablaufverfolgung kann der Benutzer Ablaufverfolgungsaktivitäten für folgenden Aktionen erstellen:</span><span class="sxs-lookup"><span data-stu-id="e4905-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
-   <span data-ttu-id="e4905-121">Gruppieren von Ablaufverfolgungen in logische Arbeitseinheiten.</span><span class="sxs-lookup"><span data-stu-id="e4905-121">Group traces into logical units of work.</span></span>  
  
-   <span data-ttu-id="e4905-122">Korrelieren von Aktivitäten durch Übertragungen und Weitergabe.</span><span class="sxs-lookup"><span data-stu-id="e4905-122">Correlate activities through transfers and propagation.</span></span>  
  
-   <span data-ttu-id="e4905-123">Verringern der Leistungskosten für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Ablaufverfolgung (beispielsweise der benötigte Speicherplatz für eine Protokolldatei).</span><span class="sxs-lookup"><span data-stu-id="e4905-123">Lessen the performance cost of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="e4905-124">Weitere Informationen über eine benutzerdefinierte Aktivität Ablaufverfolgung finden Sie unter der [erweitern Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e4905-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="e4905-125">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e4905-125">Message Logging</span></span>  
 <span data-ttu-id="e4905-126">Die Nachrichtenprotokollierung kann auf dem Client und dem Dienst aller [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e4905-126">Message logging can be enabled both on the client and service of any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="e4905-127">Zum Aktivieren der Nachrichtenprotokollierung müssen Sie dem Client oder dem Dienst den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e4905-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
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
  
 <span data-ttu-id="e4905-128">Wenn eine Nachricht aufgezeichnet wird, ist der Ablaufverfolgungstyp abhängig davon, ob die Ablaufverfolgung beim Client oder beim Server erfolgt.</span><span class="sxs-lookup"><span data-stu-id="e4905-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="e4905-129">Eine "Add"-Nachricht, die an einen Client gesendet wird, wird beispielsweise in der Kategorie "TransportWrite" beim Client verfolgt, während die gleiche Nachricht beim Dienst in der Kategorie "TransportRead" verfolgt wird.</span><span class="sxs-lookup"><span data-stu-id="e4905-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="e4905-130">Konfigurieren Sie den Ablaufverfolgungslistener, indem Sie den folgenden Code im <xref:System.Diagnostics>-Abschnitt der Datei "App.config" für den Client oder der Datei "Web.config" für den Dienst hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e4905-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
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
  
 <span data-ttu-id="e4905-131">Nachrichten werden im XML-Format in dem in der Konfigurationsdatei angegebenen Zielverzeichnis protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e4905-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4905-132">Ablaufverfolgungsdateien werden nur erstellt, wenn zuerst das Protokollverzeichnis erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e4905-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="e4905-133">Stellen Sie sicher, dass das Verzeichnis C:\logs\ vorhanden ist, oder geben Sie ein anderes Protokollierungsverzeichnis in der Listenerkonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="e4905-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="e4905-134">Weitere Informationen finden Sie in den Anweisungen zum ersten Einrichten am Ende dieses Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e4905-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="e4905-135">Weitere Informationen zur nachrichtenprotokollierung finden Sie unter der [Konfigurieren der Nachrichtenprotokollierung](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="e4905-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e4905-136">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e4905-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e4905-137">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e4905-138">Bevor Sie das Beispiel zur Ablaufverfolgung und Nachrichtenprotokollierung ausführen, erstellen Sie das Verzeichnis C:\logs\, in das der Dienst die SVCLOG-Dateien schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="e4905-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="e4905-139">Der Name dieses Verzeichnisses wird in der Konfigurationsdatei als Pfad für die zu protokollierenden Ablaufverfolgungen und Nachrichten definiert und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e4905-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="e4905-140">Weisen Sie dem Benutzer Network Service Schreibzugriff für das Protokollverzeichnis zu.</span><span class="sxs-lookup"><span data-stu-id="e4905-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3.  <span data-ttu-id="e4905-141">Führen Sie zum Erstellen der C#-, C++ oder Visual Basic .NET Edition der Lösung die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="e4905-142">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e4905-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4905-143">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e4905-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e4905-144">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e4905-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e4905-145">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="e4905-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e4905-146">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e4905-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="e4905-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4905-147">See Also</span></span>  
 [<span data-ttu-id="e4905-148">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e4905-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e4905-149">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="e4905-149">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
