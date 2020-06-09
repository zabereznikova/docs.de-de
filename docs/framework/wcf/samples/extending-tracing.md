---
title: Erweitern der Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 59bdfeea41bac812840ffe166895050a6cd1ad2d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600515"
---
# <a name="extend-tracing"></a><span data-ttu-id="7e879-102">Ablauf Verfolgung erweitern</span><span class="sxs-lookup"><span data-stu-id="7e879-102">Extend tracing</span></span>

<span data-ttu-id="7e879-103">In diesem Beispiel wird veranschaulicht, wie die Windows Communication Foundation (WCF)-Ablauf Verfolgungs Funktion erweitert wird, indem benutzerdefinierte Aktivitäts Ablauf Verfolgungen in Client-und Dienst Code geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7e879-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="7e879-104">Das Schreiben von benutzerdefinierten Aktivitäts Ablauf Verfolgungen ermöglicht dem Benutzer das Erstellen von Ablauf Verfolgungs Aktivitäten und das Gruppieren von Ablauf Verfolgungen in logische Arbeitseinheiten.</span><span class="sxs-lookup"><span data-stu-id="7e879-104">Writing user-defined activity traces allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="7e879-105">Es ist auch möglich, Aktivitäten über Übertragungen (innerhalb desselben Endpunkts) und Weitergabe (über verschiedene Endpunkte) zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="7e879-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="7e879-106">In diesem Beispiel wird Ablaufverfolgung sowohl für den Client als auch den Dienst aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7e879-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="7e879-107">Weitere Informationen zum Aktivieren der Ablauf Verfolgung in Client-und Dienst Konfigurationsdateien finden Sie unter Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="7e879-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="7e879-108">Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="7e879-108">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e879-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="7e879-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e879-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7e879-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7e879-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7e879-111">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7e879-112">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e879-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e879-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7e879-113">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="7e879-114">Ablaufverfolgung und Aktivitätsweitergabe</span><span class="sxs-lookup"><span data-stu-id="7e879-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="7e879-115">Die benutzerdefinierte Aktivitäts Ablauf Verfolgung ermöglicht dem Benutzer, eigene Ablauf Verfolgungs Aktivitäten zu erstellen, um Ablauf Verfolgungen in logische Arbeitseinheiten zu gruppieren, Aktivitäten über Übertragungen und Weitergabe zu korrelieren und die Leistungskosten der WCF-Ablauf Verfolgung zu verringern (z. b. die Speicherplatz Kosten einer Protokolldatei).</span><span class="sxs-lookup"><span data-stu-id="7e879-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="add-custom-sources"></a><span data-ttu-id="7e879-116">Benutzerdefinierte Quellen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="7e879-116">Add custom sources</span></span>  
 <span data-ttu-id="7e879-117">Benutzerdefinierte Ablaufverfolgungen können sowohl zu Client- als auch Dienstcode hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7e879-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="7e879-118">Durch das Hinzufügen von Ablauf Verfolgungs Quellen zu den Client-oder Dienst Konfigurationsdateien können diese benutzerdefinierten Ablauf Verfolgungen aufgezeichnet und im [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7e879-118">Adding trace sources to the client or service configuration files allows for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="7e879-119">Der folgende Code zeigt, wie der Konfigurationsdatei eine benutzerdefinierte Ablaufverfolgungsquelle namens `ServerCalculatorTraceSource` hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7e879-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>
....
```  
  
### <a name="correlate-activities"></a><span data-ttu-id="7e879-120">Korrelieren von Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="7e879-120">Correlate activities</span></span>  
 <span data-ttu-id="7e879-121">Zum Korrelieren von Aktivitäten direkt zwischen Endpunkten muss für das `propagateActivity`-Attribut in der `true`-Ablaufverfolgungsquelle der Wert `System.ServiceModel` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7e879-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="7e879-122">Außerdem muss die Service Model-Aktivitäts Ablauf Verfolgung deaktiviert werden, damit Ablauf Verfolgungen ohne WCF-Aktivitäten weitergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7e879-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="7e879-123">Dies ist im folgenden Codebeispiel zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7e879-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e879-124">Das Deaktivieren von ServiceModel-Aktivitätsablaufverfolgung ist nicht dasselbe, wie die von der `switchValue`-Eigenschaft angegebene Ablaufverfolgungsebene zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e879-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessen-performance-cost"></a><span data-ttu-id="7e879-125">Leistungseinbußen mindern</span><span class="sxs-lookup"><span data-stu-id="7e879-125">Lessen performance cost</span></span>  
 <span data-ttu-id="7e879-126">Wenn `ActivityTracing` in der `System.ServiceModel`-Ablaufverfolgungsquelle ausgeschaltet wird, wird eine Ablaufverfolgungsdatei erstellt, die nur benutzerdefinierte Aktivitätsablaufverfolgungen, jedoch keine der ServiceModel-Aktivitätsablaufverfolgungen enthält.</span><span class="sxs-lookup"><span data-stu-id="7e879-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="7e879-127">Das Ausschließen von Service Model-Aktivitäts Ablauf Verfolgungen führt zu einer wesentlich geringeren Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="7e879-127">Excluding ServiceModel activity traces results in a much smaller log file.</span></span> <span data-ttu-id="7e879-128">Die Möglichkeit zum Korrelieren von WCF-Verarbeitungs Ablauf Verfolgungen geht jedoch verloren.</span><span class="sxs-lookup"><span data-stu-id="7e879-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="7e879-129">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="7e879-129">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7e879-130">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="7e879-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7e879-131">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7e879-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7e879-132">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e879-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e879-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e879-133">See also</span></span>

- <span data-ttu-id="7e879-134">[AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7e879-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
