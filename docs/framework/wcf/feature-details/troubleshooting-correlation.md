---
title: Problembehandlung bei der Korrelation
ms.date: 03/30/2017
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
ms.openlocfilehash: a5942c13bb4026cfeb8f664c60fb658373ffcca5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596707"
---
# <a name="troubleshooting-correlation"></a><span data-ttu-id="05ddb-102">Problembehandlung bei der Korrelation</span><span class="sxs-lookup"><span data-stu-id="05ddb-102">Troubleshooting Correlation</span></span>
<span data-ttu-id="05ddb-103">Mit Korrelation werden Workflowdienstnachrichten miteinander und mit der richtigen Workflowinstanz verknüpft. Wenn die Konfiguration jedoch nicht richtig durchgeführt wurde, werden Meldungen nicht empfangen, und Anwendungen funktionieren nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="05ddb-103">Correlation is used to relate workflow service messages to each other and to the correct workflow instance, but if it is not configured correctly, messages will not be received and applications will not work correctly.</span></span> <span data-ttu-id="05ddb-104">Dieses Thema bietet eine Übersicht über mehrere Methoden zum Beheben von Korrelationsproblemen. Des Weiteren werden einige häufig auftretende Probleme aufgeführt, die bei der Verwendung der Korrelation auftreten können.</span><span class="sxs-lookup"><span data-stu-id="05ddb-104">This topic provides an overview of several methods for troubleshooting correlation issues, and also lists some common issues that can occur when you use correlation.</span></span>

## <a name="handle-the-unknownmessagereceived-event"></a><span data-ttu-id="05ddb-105">Behandeln des UnknownMessageReceived-Ereignisses</span><span class="sxs-lookup"><span data-stu-id="05ddb-105">Handle the UnknownMessageReceived Event</span></span>
 <span data-ttu-id="05ddb-106">Das <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>-Ereignis tritt auf, wenn von einem Dienst eine unbekannte Meldung empfangen wird. Dazu zählen auch Meldungen, die nicht mit einer vorhandenen Instanz korreliert werden können.</span><span class="sxs-lookup"><span data-stu-id="05ddb-106">The <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> event occurs when an unknown message is received by a service, including messages that cannot be correlated to an existing instance.</span></span> <span data-ttu-id="05ddb-107">Bei selbst gehosteten Diensten kann dieses Ereignis in der Hostanwendung behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-107">For self-hosted services, this event can be handled in the host application.</span></span>

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 <span data-ttu-id="05ddb-108">Bei im Internet gehosteten Diensten kann dieses Ereignis durch das Ableiten einer Klasse von <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> und Überschreiben der <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A> behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-108">For Web-hosted services, this event can be handled by deriving a class from <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> and overriding <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A>.</span></span>

```csharp
class CustomFactory : WorkflowServiceHostFactory
{
    protected override WorkflowServiceHost CreateWorkflowServiceHost(Activity activity, Uri[] baseAddresses)
    {
        // Create the WorkflowServiceHost.
        WorkflowServiceHost host = new WorkflowServiceHost(activity, baseAddresses);

        // Handle the UnknownMessageReceived event.
        host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
        {
            Console.WriteLine("Unknown Message Received:");
            Console.WriteLine(e.Message);
        };

        return host;
    }
}
```

 <span data-ttu-id="05ddb-109">Diese benutzerdefinierte <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> kann dann in der `svc`-Datei für den Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-109">This custom <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> can then be specified in the `svc` file for the service.</span></span>

`<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>`

 <span data-ttu-id="05ddb-110">Wenn dieser Handler aufgerufen wird, kann die Meldung mit der <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A>-Eigenschaft aus <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> abgerufen werden. Die Meldung kann wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="05ddb-110">When this handler is invoked, the message can be retrieved by using the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A> property of the <xref:System.ServiceModel.UnknownMessageReceivedEventArgs>, and will resemble the following message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <To s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://localhost:8080/OrderService</To>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
  </s:Header>
  <s:Body>
    <AddItem xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItem>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="05ddb-111">An den <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>-Handler weitergeleitete Meldungen enthalten möglicherweise Hinweise dazu, warum die Meldung nicht mit einer Instanz des Workflowdiensts korreliert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-111">Inspecting messages dispatched to the <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived> handler may provide clues about why the message did not correlate to an instance of the workflow service.</span></span>

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a><span data-ttu-id="05ddb-112">Überwachen des Workflowstatus mit der Nachverfolgung</span><span class="sxs-lookup"><span data-stu-id="05ddb-112">Use Tracking to Monitor the Progress of the Workflow</span></span>
 <span data-ttu-id="05ddb-113">Eine Möglichkeit für das Überwachen des Status eines Workflows ist die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="05ddb-113">Tracking provides a way to monitor the progress of a workflow.</span></span> <span data-ttu-id="05ddb-114">Standardmäßig werden Nachverfolgungsdatensätze für Ereignisse des Workflowlebenszyklus und Aktivitätslebenszyklus sowie zur Fehlerverteilung und Lesezeichenwiederaufnahme ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-114">By default, tracking records are emitted for workflow life-cycle events, activity life-cycle events, fault propagation, and bookmark resumption.</span></span> <span data-ttu-id="05ddb-115">Darüber hinaus können von benutzerdefinierten Aktivitäten benutzerdefinierte Nachverfolgungsdatensätze ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-115">Additionally, custom tracking records can be emitted by custom activities.</span></span> <span data-ttu-id="05ddb-116">Bei der Behandlung von Korrelationsproblemen erweisen sich die Datensätze zur Aktivitätsnachverfolgung, Lesezeichenwiederaufnahme und Fehlerverteilung als besonders nützlich.</span><span class="sxs-lookup"><span data-stu-id="05ddb-116">When troubleshooting correlation, the activity tracking records, the bookmark resumption records, and the fault propagation records are the most useful.</span></span> <span data-ttu-id="05ddb-117">Mit den Datensätzen zur Aktivitätsnachverfolgung kann der aktuelle Status des Workflows festgestellt und bestimmt werden, welche Meldungsaktivität gerade auf Meldungen wartet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-117">The activity tracking records can be used to determine the current progress of the workflow and can help identify which messaging activity is currently waiting for messages.</span></span> <span data-ttu-id="05ddb-118">Datensätze zur Lesezeichenwiederaufnahme sind hilfreich, da sie angeben, dass eine Meldung vom Workflow empfangen wurde. Datensätze zur Fehlerverteilung enthalten einen Datensatz mit sämtlichen Fehlern im Workflow.</span><span class="sxs-lookup"><span data-stu-id="05ddb-118">Bookmark resumption records are useful because they indicate that a message was received by the workflow, and fault propagation records provide a record of any faults in the workflow.</span></span> <span data-ttu-id="05ddb-119">Um die Nachverfolgung zu aktivieren, geben Sie den gewünschten <xref:System.Activities.Tracking.TrackingParticipant> in den <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> des <xref:System.ServiceModel.Activities.WorkflowServiceHost> an.</span><span class="sxs-lookup"><span data-stu-id="05ddb-119">To enable tracking, specify the desired <xref:System.Activities.Tracking.TrackingParticipant> in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> of the <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="05ddb-120">Im folgenden Beispiel `ConsoleTrackingParticipant` wird der (aus dem Beispiel für die [benutzerdefinierte Nachverfolgung](../../windows-workflow-foundation/samples/custom-tracking.md) ) mit dem Standard Überwachungs Profil konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-120">In the following example, the `ConsoleTrackingParticipant` (from the [Custom Tracking](../../windows-workflow-foundation/samples/custom-tracking.md) sample) is configured by using the default tracking profile.</span></span>

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 <span data-ttu-id="05ddb-121">Ein Nachverfolgungsteilnehmer (z. B. der ConsoleTrackingParticipant) ist nützlich bei selbst gehosteten Workflowdiensten mit Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="05ddb-121">A tracking participant such as the ConsoleTrackingParticipant is useful for self-hosted workflow services that have a console window.</span></span> <span data-ttu-id="05ddb-122">Bei einem im Internet gehosteten Dienst sollte ein nach Verfolgungs Teilnehmer verwendet werden, der die Überwachungsinformationen in einem permanenten Speicher protokolliert, wie z. b. der integrierte <xref:System.Activities.Tracking.EtwTrackingParticipant> , oder ein benutzerdefinierter nach Verfolgungs Teilnehmer, der die Informationen in einer Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-122">For a Web-hosted service, a tracking participant that logs the tracking information to a durable store should be used, such as the built-in <xref:System.Activities.Tracking.EtwTrackingParticipant>, or a custom tracking participant that logs the information to a file.</span></span>

 <span data-ttu-id="05ddb-123">Weitere Informationen zum Nachverfolgen und Konfigurieren der Nachverfolgung für einen im Internet gehosteten Workflow Dienst finden Sie unter nach [Verfolgung und Ablauf](../../windows-workflow-foundation/workflow-tracking-and-tracing.md)Verfolgung für Workflows, [Konfigurieren der Nachverfolgung für einen Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)und [&#91;WF-Beispiele&#93;](../../windows-workflow-foundation/samples/tracking.md) Beispiele für die Nachverfolgung.</span><span class="sxs-lookup"><span data-stu-id="05ddb-123">For more information about tracking and configuring tracking for a Web-hosted workflow service, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md), [Configuring Tracking for a Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md), and the [Tracking &#91;WF Samples&#93;](../../windows-workflow-foundation/samples/tracking.md) samples.</span></span>

## <a name="use-wcf-tracing"></a><span data-ttu-id="05ddb-124">Verwenden der WCF-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="05ddb-124">Use WCF Tracing</span></span>
 <span data-ttu-id="05ddb-125">Die WCF-Ablaufverfolgung stellt eine Ablaufverfolgung des Meldungsflusses zu und von einem Workflowdienst bereit.</span><span class="sxs-lookup"><span data-stu-id="05ddb-125">WCF tracing provides tracing of the flow of messages to and from a workflow service.</span></span> <span data-ttu-id="05ddb-126">Diese Ablaufverfolgungsinformationen sind nützlich bei der Behebung von Korrelationsproblemen, besonders bei inhaltsbasierter Korrelation.</span><span class="sxs-lookup"><span data-stu-id="05ddb-126">This tracing information is useful when troubleshooting correlation issues, especially for content-based correlation.</span></span> <span data-ttu-id="05ddb-127">Geben Sie zum Aktivieren der Ablaufverfolgung die gewünschten Ablaufverfolgungslistener im Abschnitt `system.diagnostics` der Datei `web.config` an, wenn es sich um einen im Internet gehosteten Workflowdienst handelt, bzw. in der Datei `app.config`, wenn es sich um einen selbst gehosteten Workflowdienst handelt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-127">To enable tracing, specify the desired trace listeners in the `system.diagnostics` section of the `web.config` file if the workflow service is Web-hosted, or the `app.config` file if the workflow service is self-hosted.</span></span> <span data-ttu-id="05ddb-128">Geben Sie im `true`-Element im Abschnitt `logEntireMessage` des `messageLogging` für `diagnostics` den Wert `system.serviceModel` an, um den Inhalt der Meldungen in die Ablaufverfolgungsdatei aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="05ddb-128">To include the contents of the messages in the trace file, specify `true` for `logEntireMessage` in the `messageLogging` element in the `diagnostics` section of `system.serviceModel`.</span></span> <span data-ttu-id="05ddb-129">Im folgenden Beispiel werden Ablaufverfolgungsinformationen einschließlich des Inhalts der Meldungen so konfiguriert, dass sie in eine Datei mit dem Namen `service.svclog` geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-129">In the following example, tracing information, including the content of the messages, is configured to be written to a file that is named `service.svclog`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.ServiceModel" switchValue="Information" propagateActivity="true">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
      <source name="System.ServiceModel.MessageLogging">
        <listeners>
          <add name="corr"/>
        </listeners>
      </source>
    </sources>

    <sharedListeners>
      <add name="corr" type="System.Diagnostics.XmlWriterTraceListener" initializeData="c:\logs\service.svclog">
      </add>
    </sharedListeners>
  </system.diagnostics>

  <system.serviceModel>
    <diagnostics>
      <messageLogging logEntireMessage="true" logMalformedMessages="false"
         logMessagesAtServiceLevel="false" logMessagesAtTransportLevel="true" maxSizeOfMessageToLog="2147483647">
      </messageLogging>
    </diagnostics>
  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="05ddb-130">Zum Anzeigen der Ablauf Verfolgungs Informationen, die in enthalten sind `service.svclog` , wird das [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-130">To view the trace information that is contained in `service.svclog`, the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) is used.</span></span> <span data-ttu-id="05ddb-131">Dies ist besonders beim Beheben von inhaltsbasierten Korrelationsproblemen hilfreich, da Sie die Meldungsinhalte anzeigen und genau sehen können, welche Daten übergeben werden und ob diese mit der <xref:System.ServiceModel.CorrelationQuery> für die inhaltsbasierte Korrelation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="05ddb-131">This is especially useful when troubleshooting content-based correlation issues because you can view the message contents and see exactly what is being passed, and whether it matches the <xref:System.ServiceModel.CorrelationQuery> for the content-based correlation.</span></span> <span data-ttu-id="05ddb-132">Weitere Informationen zur WCF-Ablauf Verfolgung finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md), Konfigurieren der Ablauf [Verfolgung](../diagnostics/tracing/configuring-tracing.md)und [Verwenden der Ablauf Verfolgung zum Beheben von Problemen mit der Anwendung](../diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="05ddb-132">For more information about WCF tracing, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md), [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md), and [Using Tracing to Troubleshoot Your Application](../diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="common-context-exchange-correlation-issues"></a><span data-ttu-id="05ddb-133">Allgemeine Probleme bei der Kontextaustauschkorrelation</span><span class="sxs-lookup"><span data-stu-id="05ddb-133">Common Context Exchange Correlation Issues</span></span>
 <span data-ttu-id="05ddb-134">Bestimmte Korrelationstypen erfordern einen bestimmten Bindungstyp, damit die Korrelation einwandfrei funktioniert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-134">Certain types of correlation require that a specific type of binding is used for the correlation to work correctly.</span></span> <span data-ttu-id="05ddb-135">Beispiele sind die Anforderung-Antwort-Korrelation, die eine bidirektionale Bindung (z. B. <xref:System.ServiceModel.BasicHttpBinding>) erfordert, und die Kontextaustauschkorrelation, die eine kontextbasierte Bindung (z. B. <xref:System.ServiceModel.BasicHttpContextBinding>) erfordert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-135">Examples include request-reply correlation, which requires a two-way binding such as <xref:System.ServiceModel.BasicHttpBinding>, and context exchange correlation, which requires a context-based binding such as <xref:System.ServiceModel.BasicHttpContextBinding>.</span></span> <span data-ttu-id="05ddb-136">Die meisten Bindungen unterstützen bidirektionale Vorgänge, sodass dies kein häufig auftretendes Problem bei der Anforderung-Antwort-Korrelation ist. Es gibt jedoch nur wenige kontextbasierte Bindungen, z. B. <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> und <xref:System.ServiceModel.NetTcpContextBinding>.</span><span class="sxs-lookup"><span data-stu-id="05ddb-136">Most bindings support two-way operations so this is not a common issue for request-reply correlation, but there are only a handful of context-based bindings including <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding>, and <xref:System.ServiceModel.NetTcpContextBinding>.</span></span> <span data-ttu-id="05ddb-137">Wenn eine dieser Bindungen nicht verwendet wird, kann der erste Aufruf eines Workflowdiensts erfolgreich ausgeführt werden. Die nachfolgenden Aufrufe geben jedoch die folgende <xref:System.ServiceModel.FaultException> als Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="05ddb-137">If one of these bindings is not used, the initial call to a workflow service will succeed, but subsequent calls will fail with the following <xref:System.ServiceModel.FaultException>.</span></span>

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 <span data-ttu-id="05ddb-138">Die für die Kontextkorrelation verwendeten Kontextinformationen können von der <xref:System.ServiceModel.Activities.SendReply> an die <xref:System.ServiceModel.Activities.Receive>-Aktivität zurückgegeben werden, die die Kontextkorrelation initialisiert, falls ein bidirektionaler Vorgang verwendet wird. Wenn es sich um einen unidirektionalen Vorgang handelt, kann der Aufrufer die Kontextinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-138">The context information that is used for context correlation can be returned by the <xref:System.ServiceModel.Activities.SendReply> to the <xref:System.ServiceModel.Activities.Receive> activity that initializes the context correlation when using a two-way operation, or it can be specified by the caller if the operation is one-way.</span></span> <span data-ttu-id="05ddb-139">Wird der Kontext nicht vom Aufrufer gesendet oder vom Workflowdienst zurückgegeben, wird die bereits zuvor beschriebene <xref:System.ServiceModel.FaultException> zurückgegeben, wenn ein nachfolgender Vorgang aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="05ddb-139">If the context is not sent by the caller or returned by the workflow service, then the same <xref:System.ServiceModel.FaultException> described previously will be returned when a subsequent operation is invoked.</span></span>

## <a name="common-request-reply-correlation-issues"></a><span data-ttu-id="05ddb-140">Allgemeine Probleme bei der Anforderung-Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="05ddb-140">Common Request-Reply Correlation Issues</span></span>
 <span data-ttu-id="05ddb-141">Die Anforderung-Antwort-Korrelation wird mit einem Paar verwendet, um einen bidirektionalen <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Vorgang in einem Workflow Dienst zu implementieren, und mit einem <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> Paar, das einen bidirektionalen Vorgang in einem anderen Webdienst aufruft.</span><span class="sxs-lookup"><span data-stu-id="05ddb-141">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="05ddb-142">Wenn Sie einen bidirektionalen Vorgang in einem WCF-Dienst aufrufen, kann der Dienst entweder ein herkömmlicher imperativer, imperativer Code basierter WCF-Dienst sein, oder es kann sich um einen Workflow Dienst handeln.</span><span class="sxs-lookup"><span data-stu-id="05ddb-142">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based WCF service or it can be a workflow service.</span></span> <span data-ttu-id="05ddb-143">Für die Anforderung-Antwort-Korrelation muss eine bidirektionale Bindung verwendet werden (z. B. <xref:System.ServiceModel.BasicHttpBinding>). Außerdem müssen die Vorgänge bidirektional ausgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="05ddb-143">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>, and the operations must be two-way.</span></span>

 <span data-ttu-id="05ddb-144">Wenn der Workflow Dienst gleichzeitige bidirektionale Vorgänge oder überlappende- <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> oder- <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> Paare hat, reicht die von bereitgestellte implizite Korrelations Handle <xref:System.ServiceModel.Activities.WorkflowServiceHost> -Verwaltung möglicherweise nicht aus, insbesondere in Szenarien mit hoher Belastung, und Nachrichten werden möglicherweise nicht ordnungsgemäß weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-144">If the workflow service has two-way operations in parallel, or overlapping <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> or <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pairs, then the implicit correlation handle management provided by <xref:System.ServiceModel.Activities.WorkflowServiceHost> may not be sufficient, especially in high-stress scenarios, and messages may not be correctly routed.</span></span> <span data-ttu-id="05ddb-145">Zur Verhinderung dieses Problems empfiehlt es sich, bei der Verwendung der Anforderung-Antwort-Korrelation immer explizit einen <xref:System.ServiceModel.Activities.CorrelationHandle> anzugeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-145">To prevent this issue from occurring, we recommend that you always explicitly specify a <xref:System.ServiceModel.Activities.CorrelationHandle> when using request-reply correlation.</span></span> <span data-ttu-id="05ddb-146">Wenn Sie die **sendandreceivereply** -Vorlage und die **receiveandsendreply** -Vorlage im Abschnitt Messaging der **Toolbox** im Workflow-Designer verwenden, <xref:System.ServiceModel.Activities.CorrelationHandle> wird standardmäßig ein explizit konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-146">When using the **SendAndReceiveReply** and **ReceiveAndSendReply** templates from the Messaging section of the **Toolbox** in the workflow designer, a <xref:System.ServiceModel.Activities.CorrelationHandle> is explicitly configured by default.</span></span> <span data-ttu-id="05ddb-147">Bei der Erstellung eines Workflows mithilfe von Code wird der <xref:System.ServiceModel.Activities.CorrelationHandle> in den <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> der ersten Aktivität des Paars angegeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-147">When building a workflow by using code, the <xref:System.ServiceModel.Activities.CorrelationHandle> is specified in the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> of the first activity in the pair.</span></span> <span data-ttu-id="05ddb-148">Im folgenden Beispiel wird eine <xref:System.ServiceModel.Activities.Receive>-Aktivität mit einem expliziten <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A>, der im <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> angegeben wurde, konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-148">In the following example, a <xref:System.ServiceModel.Activities.Receive> activity is configured with an explicit <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A> specified in the <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.</span></span>

```csharp
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();

Receive StartOrder = new Receive
{
    CanCreateInstance = true,
    ServiceContractName = OrderContractName,
    OperationName = "StartOrder",
    CorrelationInitializers =
    {
        new RequestReplyCorrelationInitializer
        {
            CorrelationHandle = RRHandle
        }
    }
};

SendReply ReplyToStartOrder = new SendReply
{
    Request = StartOrder,
    Content = ... // Contains the return value, if any.
};

// Construct a workflow using StartOrder and ReplyToStartOrder.
```

 <span data-ttu-id="05ddb-149">Persistenz ist zwischen einem <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> Paar oder einem Paar nicht zulässig <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> .</span><span class="sxs-lookup"><span data-stu-id="05ddb-149">Persistence is not permitted between a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair or a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair.</span></span> <span data-ttu-id="05ddb-150">Es wird eine Zone ohne Persistenz erstellt, die vorhanden ist, bis beide Aktivitäten abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-150">A no-persist zone is created that lasts until both activities have completed.</span></span> <span data-ttu-id="05ddb-151">Wenn in der Zone ohne Persistenz eine Aktivität, z. B. eine Verzögerungsaktivität, vorhanden ist, die den Workflow in den Leerlauf versetzt, bleibt der Workflow nicht erhalten, auch wenn der Host zum Beibehalten von in den Leerlauf versetzten Workflows konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="05ddb-151">If an activity, such as a delay activity, is in this no-persist zone and causes the workflow to become idle, the workflow will not persist even if it the host is configured to persist workflows when they become idle.</span></span> <span data-ttu-id="05ddb-152">Wenn eine Aktivität, z. B. eine Persist-Aktivität, den Workflow in der Zone ohne Persistenz explizit beizubehalten versucht, wird ein schwerwiegender Ausnahmefehler ausgelöst, der Workflow wird abgebrochen, und an den Aufrufer wird eine <xref:System.ServiceModel.FaultException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-152">If an activity, such as a persist activity, attempts to explicitly persist in the no-persist zone, a fatal exception is thrown, the workflow aborts, and a <xref:System.ServiceModel.FaultException> is returned to the caller.</span></span> <span data-ttu-id="05ddb-153">Die Meldung zum schwerwiegenden Ausnahmefehler lautet "System.InvalidOperationException: Persist-Aktivitäten können nicht in nicht persistenten Blöcken enthalten sein."</span><span class="sxs-lookup"><span data-stu-id="05ddb-153">The fatal exception message is "System.InvalidOperationException: Persist activities cannot be contained within no persistence blocks.".</span></span> <span data-ttu-id="05ddb-154">Diese Ausnahme wird nicht an den Aufrufer zurückgegeben, sie kann jedoch angezeigt werden, wenn Nachverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="05ddb-154">This exception is not returned to the caller but can be observed if tracking is enabled.</span></span> <span data-ttu-id="05ddb-155">Die für die <xref:System.ServiceModel.FaultException> an den Aufrufer zurückgegebene Meldung lautet "Der Vorgang konnte nicht ausgeführt werden, da die Workflowinstanz '5836145b-7da2-49d0-a052-a49162adeab6' abgeschlossen wurde".</span><span class="sxs-lookup"><span data-stu-id="05ddb-155">The message for the <xref:System.ServiceModel.FaultException> returned to the caller is "The operation could not be performed because WorkflowInstance '5836145b-7da2-49d0-a052-a49162adeab6' has completed".</span></span>

 <span data-ttu-id="05ddb-156">Weitere Informationen zur Anforderung-Antwort-Korrelation finden Sie unter [Request-Reply](request-reply-correlation.md).</span><span class="sxs-lookup"><span data-stu-id="05ddb-156">For more information about request-reply correlation, see [Request-Reply](request-reply-correlation.md).</span></span>

## <a name="common-content-correlation-issues"></a><span data-ttu-id="05ddb-157">Allgemeine Probleme bei der Inhaltskorrelation</span><span class="sxs-lookup"><span data-stu-id="05ddb-157">Common Content Correlation Issues</span></span>
 <span data-ttu-id="05ddb-158">Die inhaltsbasierte Korrelation wird verwendet, wenn ein Workflowdienst mehrere Meldungen empfängt und ein Datenelement in den ausgetauschten Nachrichten die gewünschte Instanz angibt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-158">Content-based correlation is used when a workflow service receives multiple messages and a piece of data in the exchanged messages identifies the desired instance.</span></span> <span data-ttu-id="05ddb-159">Die inhaltsbasierte Korrelation verwendet diese Daten in der Nachricht, z. B. eine Kundennummer oder Bestell-ID, um Nachrichten an die richtige Workflowinstanz weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="05ddb-159">Content-based correlation uses this data in the message, such as a customer number or order ID, to route messages to the correct workflow instance.</span></span> <span data-ttu-id="05ddb-160">In diesem Abschnitt werden mehrere häufig auftretende Probleme beschrieben, die bei der inhaltsbasierten Korrelation vorkommen können.</span><span class="sxs-lookup"><span data-stu-id="05ddb-160">This section describes several common issues that may occur when using content-based correlation.</span></span>

### <a name="ensure-the-identifying-data-is-unique"></a><span data-ttu-id="05ddb-161">Sicherstellen, dass die identifizierenden Daten eindeutig sind</span><span class="sxs-lookup"><span data-stu-id="05ddb-161">Ensure the Identifying Data Is Unique</span></span>
 <span data-ttu-id="05ddb-162">Die Daten zur Identifikation der Instanz werden per Hash in einen Korrelationsschlüssel umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-162">The data that is used to identify the instance is hashed into a correlation key.</span></span> <span data-ttu-id="05ddb-163">Dabei müssen Sie sicherstellen, dass die für die Korrelation verwendeten Daten eindeutig sind, da sonst Konflikte im Hashschlüssel auftreten und Nachrichten ggf. falsch weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="05ddb-163">Care must be taken to guarantee that the data that is used for correlation is unique or else collisions in the hashed key might occur and cause messages to be misrouted.</span></span> <span data-ttu-id="05ddb-164">Wenn eine Korrelation z. B. ausschließlich auf einem Kundennamen basiert, kann es zu einem Konflikt kommen, da es möglicherweise mehrere Kunden mit dem gleichen Namen gibt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-164">For example, a correlation based only on a customer name may cause a collision because there may be multiple customers who have the same name.</span></span> <span data-ttu-id="05ddb-165">Der Doppelpunkt (:) darf nicht als Bestandteil der Daten verwendet werden, mit denen die Meldung korreliert wird, da hiermit bereits Schlüssel und Wert der Meldungsabfrage begrenzt werden, um die Zeichenfolge zu bilden, für die anschließend der Hashwert berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="05ddb-165">The colon (:) should not be used as part of the data that is used to correlate the message because it is already used to delimit the message query’s key and value to form the string that is subsequently hashed.</span></span> <span data-ttu-id="05ddb-166">Wenn Persistenz verwendet wird, stellen Sie sicher, dass die aktuellen identifizierenden Daten nicht von einer zuvor beibehaltenen Instanz verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-166">If persistence is being used, make sure that the current identifying data has not been used by a previously persisted instance.</span></span> <span data-ttu-id="05ddb-167">Die vorübergehende Deaktivierung der Persistenz kann dabei helfen, das Problem zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05ddb-167">Temporarily disabling persistence can help identify this issue.</span></span> <span data-ttu-id="05ddb-168">Mit der WCF-Ablaufverfolgung kann der berechnete Korrelationsschlüssel angezeigt werden. Sie ist außerdem hilfreich beim Debuggen von Problemen dieser Art.</span><span class="sxs-lookup"><span data-stu-id="05ddb-168">WCF tracing can be used to view the calculated correlation key and is useful for debugging this kind of issue.</span></span>

### <a name="race-conditions"></a><span data-ttu-id="05ddb-169">Racebedingungen</span><span class="sxs-lookup"><span data-stu-id="05ddb-169">Race Conditions</span></span>
 <span data-ttu-id="05ddb-170">Es gibt eine kleine zeitliche Lücke zwischen dem Zeitpunkt, zu dem der Dienst die Meldung empfängt, und der eigentlichen Initialisierung der Korrelation. In dieser Zeitspanne werden weitere Meldungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-170">There is a small gap in time between the service receiving a message and the correlation actually being initialized, during which follow-up messages will be ignored.</span></span> <span data-ttu-id="05ddb-171">Wenn ein Workflowdienst die inhaltsbasierte Korrelation mit Daten initialisiert, die vom Client über einen unidirektionalen Vorgang gesendet werden, und der Client unmittelbar darauf weitere Meldungen sendet, werden diese Meldungen während des beschriebenen Intervalls ignoriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-171">If a workflow service initializes the content-based correlation by using data passed from the client over a one-way operation, and the caller sends immediate follow-up messages, these messages will be ignored during this interval.</span></span> <span data-ttu-id="05ddb-172">Dies kann vermieden werden, indem die Korrelation mit einem bidirektionalen Vorgang initialisiert wird oder indem ein <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05ddb-172">This can be avoided by using a two-way operation to initialize the correlation, or by using a <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span>

### <a name="correlation-query-issues"></a><span data-ttu-id="05ddb-173">Probleme bei Korrelationsabfragen</span><span class="sxs-lookup"><span data-stu-id="05ddb-173">Correlation Query Issues</span></span>
 <span data-ttu-id="05ddb-174">Mit Korrelationsabfragen wird angegeben, welche Daten in einer Meldung verwendet werden, um die Meldung zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="05ddb-174">Correlation queries are used to specify what data in a message is used to correlate the message.</span></span> <span data-ttu-id="05ddb-175">Diese Daten werden mit einer XPath-Abfrage angegeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-175">This data is specified by using an XPath query.</span></span> <span data-ttu-id="05ddb-176">Wenn Nachrichten nicht an einen Dienst weitergeleitet werden, obwohl keine Anzeichen eines Problems ersichtlich sind, können Sie einen Literalwert angeben, der mit dem Wert der Meldungsdaten und nicht mit einer XPath-Abfrage übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-176">If messages to a service are not being dispatched even though everything appears to be correct, one strategy for troubleshooting is to specify a literal value that matches the value of the message data instead of an XPath query.</span></span> <span data-ttu-id="05ddb-177">Verwenden Sie die `string`-Funktion, um einen Literalwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="05ddb-177">To specify a literal value, use the `string` function.</span></span> <span data-ttu-id="05ddb-178">Im folgenden Beispiel wird ein <xref:System.ServiceModel.MessageQuerySet> konfiguriert, um den Literalwert `11445` für die `OrderId` zu verwenden, und die XPath-Abfrage wird auskommentiert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-178">In the following example, a <xref:System.ServiceModel.MessageQuerySet> is configured to use a literal value of `11445` for the `OrderId` and the XPath query is commented out.</span></span>

```csharp
MessageQuerySet = new MessageQuerySet
{
    {
        "OrderId",
        //new XPathMessageQuery("sm:body()/tempuri:StartOrderResponse/tempuri:OrderId")
        new XPathMessageQuery("string('11445')")
    }
}
```

 <span data-ttu-id="05ddb-179">Wenn eine XPath-Abfrage falsch konfiguriert ist, sodass keine Korrelationsdaten abgerufen werden, wird ein Fehler mit der folgenden Meldung zurückgegeben: „Eine Korrelationsabfrage ergab ein leeres Resultset.</span><span class="sxs-lookup"><span data-stu-id="05ddb-179">If an XPath query is configured incorrectly such that no correlation data is retrieved, a fault is returned with the following message: "A correlation query yielded an empty result set.</span></span> <span data-ttu-id="05ddb-180">Stellen Sie sicher, dass die Korrelationsabfragen für den Endpunkt ordnungsgemäß konfiguriert sind."</span><span class="sxs-lookup"><span data-stu-id="05ddb-180">Please ensure correlation queries for the endpoint are correctly configured."</span></span> <span data-ttu-id="05ddb-181">Dieser Fehler lässt sich schnell beheben, indem die XPath-Abfrage wie im vorherigen Abschnitt beschrieben durch einen Literalwert ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="05ddb-181">One quick way to troubleshoot this is to replace the XPath query with a literal value as described in the previous section.</span></span> <span data-ttu-id="05ddb-182">Dieses Problem kann auftreten, wenn Sie den XPath-Abfrage-Generator in den Dialogfeldern **korrelationsinitialisierer hinzufügen** oder **CorrelatesOn-Definition** verwenden und der Workflow Dienst Nachrichten Verträge verwendet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-182">This issue can occur if you use the XPath query builder in the **Add Correlation Initializers** or **CorrelatesOn Definition** dialog boxes and your workflow service uses message contracts.</span></span> <span data-ttu-id="05ddb-183">Im folgenden Beispiel wird eine Nachrichtenvertragsklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-183">In the following example, a message contract class is defined.</span></span>

```csharp
[MessageContract]
public class AddItemMessage
{
    [MessageHeader]
    public string CartId;

    [MessageBodyMember]
    public string Item;
}
```

 <span data-ttu-id="05ddb-184">Dieser Nachrichtenvertrag wird von einer <xref:System.ServiceModel.Activities.Receive>-Aktivität in einem Workflow verwendet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-184">This message contract is used by a <xref:System.ServiceModel.Activities.Receive> activity in a workflow.</span></span> <span data-ttu-id="05ddb-185">Die `CartId` im Header der Nachricht wird zum Korrelieren der Nachricht mit der ordnungsgemäßen Instanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="05ddb-185">The `CartId` in the header of the message is used to correlate the message to the correct instance.</span></span> <span data-ttu-id="05ddb-186">Wenn die XPath-Abfrage zum Abrufen der `CartId` mit den Korrelationsdialogfeldern im Workflow-Designer erstellt wird, wird die folgende fehlerhafte XPath-Abfrage generiert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-186">If the XPath query that retrieves the `CartId` is created using the correlation dialogs in the workflow designer, the following incorrect XPath query is generated.</span></span>

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 <span data-ttu-id="05ddb-187">Diese XPath-Abfrage ist ordnungsgemäß, wenn die <xref:System.ServiceModel.Activities.Receive>-Aktivität Parameter für die Daten verwendet. Da sie jedoch einen Nachrichtenvertrag verwendet, ist die Abfrage fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="05ddb-187">This XPath query would be correct if the <xref:System.ServiceModel.Activities.Receive> activity used parameters for the data, but since it is using a message contract it is incorrect.</span></span> <span data-ttu-id="05ddb-188">Die folgende XPath-Abfrage ist die ordnungsgemäße Abfrage zum Abrufen der `CartId` aus dem Header.</span><span class="sxs-lookup"><span data-stu-id="05ddb-188">The following XPath query is the correct XPath query to retrieve the `CartId` from the header.</span></span>

```
sm:header()/tempuri:CartId
```

<span data-ttu-id="05ddb-189">Dies kann anhand des Nachrichtentexts überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="05ddb-189">This can be confirmed by examining the body of the message.</span></span>

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header>
    <Action s:mustUnderstand="1" xmlns="http://schemas.microsoft.com/ws/2005/05/addressing/none">http://tempuri.org/IService/AddItem</Action>
    <h:CartId xmlns:h="http://tempuri.org/">80c95b41-c98d-4660-a6c1-99412206e54c</h:CartId>
  </s:Header>
  <s:Body>
    <AddItemMessage xmlns="http://tempuri.org/">
      <Item>Books</Item>
    </AddItemMessage>
  </s:Body>
</s:Envelope>
```

<span data-ttu-id="05ddb-190">Im folgenden Beispiel wird eine für einen <xref:System.ServiceModel.Activities.Receive>-Vorgang konfigurierte `AddItem`-Aktivität gezeigt, die Daten mithilfe des vorherigen Nachrichtenvertrags empfängt.</span><span class="sxs-lookup"><span data-stu-id="05ddb-190">The following example shows a <xref:System.ServiceModel.Activities.Receive> activity configured for an `AddItem` operation that uses the previous message contract to receive data.</span></span> <span data-ttu-id="05ddb-191">Die XPath-Abfrage ist ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="05ddb-191">The XPath query is correctly configured.</span></span>

```xaml
<Receive CorrelatesWith="[CCHandle] OperationName="AddItem" ServiceContractName="p:IService">
  <Receive.CorrelatesOn>
    <XPathMessageQuery x:Key="key1">
      <XPathMessageQuery.Namespaces>
        <ssx:XPathMessageContextMarkup>
          <x:String x:Key="xg0">http://schemas.datacontract.org/2004/07/MessageContractWFService</x:String>
        </ssx:XPathMessageContextMarkup>
      </XPathMessageQuery.Namespaces>sm:header()/tempuri:CartId</XPathMessageQuery>
  </Receive.CorrelatesOn>
  <ReceiveMessageContent DeclaredMessageType="m:AddItemMessage">
    <p1:OutArgument x:TypeArguments="m:AddItemMessage">[AddItemMessage]</p1:OutArgument>
  </ReceiveMessageContent>
</Receive>
```
