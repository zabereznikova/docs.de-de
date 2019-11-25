---
title: Problembehandlung bei der Korrelation
ms.date: 03/30/2017
ms.assetid: 98003875-233d-4512-a688-4b2a1b0b5371
ms.openlocfilehash: be48a55a87d199829de4038e7e2a7642c102acf2
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976019"
---
# <a name="troubleshooting-correlation"></a>Problembehandlung bei der Korrelation
Mit Korrelation werden Workflowdienstnachrichten miteinander und mit der richtigen Workflowinstanz verknüpft. Wenn die Konfiguration jedoch nicht richtig durchgeführt wurde, werden Meldungen nicht empfangen, und Anwendungen funktionieren nicht ordnungsgemäß. Dieses Thema bietet eine Übersicht über mehrere Methoden zum Beheben von Korrelationsproblemen. Des Weiteren werden einige häufig auftretende Probleme aufgeführt, die bei der Verwendung der Korrelation auftreten können.

## <a name="handle-the-unknownmessagereceived-event"></a>Behandeln des UnknownMessageReceived-Ereignisses
 Das <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>-Ereignis tritt auf, wenn von einem Dienst eine unbekannte Meldung empfangen wird. Dazu zählen auch Meldungen, die nicht mit einer vorhandenen Instanz korreliert werden können. Bei selbst gehosteten Diensten kann dieses Ereignis in der Hostanwendung behandelt werden.

```csharp
host.UnknownMessageReceived += delegate(object sender, UnknownMessageReceivedEventArgs e)
{
    Console.WriteLine("Unknown Message Received:");
    Console.WriteLine(e.Message);
};
```

 Bei im Internet gehosteten Diensten kann dieses Ereignis durch das Ableiten einer Klasse von <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> und Überschreiben der <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory.CreateWorkflowServiceHost%2A> behandelt werden.

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

 Diese benutzerdefinierte <xref:System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory> kann dann in der `svc`-Datei für den Dienst angegeben werden.

`<% @ServiceHost Language="C#" Service="OrderServiceWorkflow" Factory="CustomFactory" %>`

 Wenn dieser Handler aufgerufen wird, kann die Meldung mit der <xref:System.ServiceModel.UnknownMessageReceivedEventArgs.Message%2A>-Eigenschaft aus <xref:System.ServiceModel.UnknownMessageReceivedEventArgs> abgerufen werden. Die Meldung kann wie folgt aussehen.

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

 An den <xref:System.ServiceModel.ServiceHostBase.UnknownMessageReceived>-Handler weitergeleitete Meldungen enthalten möglicherweise Hinweise dazu, warum die Meldung nicht mit einer Instanz des Workflowdiensts korreliert.

## <a name="use-tracking-to-monitor-the-progress-of-the-workflow"></a>Überwachen des Workflowstatus mit der Nachverfolgung
 Eine Möglichkeit für das Überwachen des Status eines Workflows ist die Nachverfolgung. Standardmäßig werden Nachverfolgungsdatensätze für Ereignisse des Workflowlebenszyklus und Aktivitätslebenszyklus sowie zur Fehlerverteilung und Lesezeichenwiederaufnahme ausgegeben. Darüber hinaus können von benutzerdefinierten Aktivitäten benutzerdefinierte Nachverfolgungsdatensätze ausgegeben werden. Bei der Behandlung von Korrelationsproblemen erweisen sich die Datensätze zur Aktivitätsnachverfolgung, Lesezeichenwiederaufnahme und Fehlerverteilung als besonders nützlich. Mit den Datensätzen zur Aktivitätsnachverfolgung kann der aktuelle Status des Workflows festgestellt und bestimmt werden, welche Meldungsaktivität gerade auf Meldungen wartet. Datensätze zur Lesezeichenwiederaufnahme sind hilfreich, da sie angeben, dass eine Meldung vom Workflow empfangen wurde. Datensätze zur Fehlerverteilung enthalten einen Datensatz mit sämtlichen Fehlern im Workflow. Um die Nachverfolgung zu aktivieren, geben Sie den gewünschten <xref:System.Activities.Tracking.TrackingParticipant> in den <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> des <xref:System.ServiceModel.Activities.WorkflowServiceHost> an. Im folgenden Beispiel wird der `ConsoleTrackingParticipant` (aus dem Beispiel für die [benutzerdefinierte Nachverfolgung](../../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) ) mit dem Standard Überwachungs Profil konfiguriert.

```csharp
host.WorkflowExtensions.Add(new ConsoleTrackingParticipant());
```

 Ein Nachverfolgungsteilnehmer (z. B. der ConsoleTrackingParticipant) ist nützlich bei selbst gehosteten Workflowdiensten mit Konsolenfenster. Bei einem im Internet gehosteten Dienst sollte ein nach Verfolgungs Teilnehmer verwendet werden, der die Überwachungsinformationen in einem permanenten Speicher protokolliert, wie z. b. der integrierte <xref:System.Activities.Tracking.EtwTrackingParticipant>oder ein benutzerdefinierter nach Verfolgungs Teilnehmer, der die Informationen in einer Datei protokolliert.

 Weitere Informationen zum Nachverfolgen und Konfigurieren der Nachverfolgung für einen im Internet gehosteten Workflow Dienst finden Sie unter nach [Verfolgung und Ablauf](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)Verfolgung für Workflows, [Konfigurieren der Nachverfolgung für einen Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)und Beispiele für die nach [ &#91;Verfolgung von WF-Beispielen&#93; ](../../../../docs/framework/windows-workflow-foundation/samples/tracking.md)

## <a name="use-wcf-tracing"></a>Verwenden der WCF-Ablaufverfolgung
 Die WCF-Ablaufverfolgung stellt eine Ablaufverfolgung des Meldungsflusses zu und von einem Workflowdienst bereit. Diese Ablaufverfolgungsinformationen sind nützlich bei der Behebung von Korrelationsproblemen, besonders bei inhaltsbasierter Korrelation. Geben Sie zum Aktivieren der Ablaufverfolgung die gewünschten Ablaufverfolgungslistener im Abschnitt `system.diagnostics` der Datei `web.config` an, wenn es sich um einen im Internet gehosteten Workflowdienst handelt, bzw. in der Datei `app.config`, wenn es sich um einen selbst gehosteten Workflowdienst handelt. Geben Sie im `true`-Element im Abschnitt `logEntireMessage` des `messageLogging` für `diagnostics` den Wert `system.serviceModel` an, um den Inhalt der Meldungen in die Ablaufverfolgungsdatei aufzunehmen. Im folgenden Beispiel werden Ablaufverfolgungsinformationen einschließlich des Inhalts der Meldungen so konfiguriert, dass sie in eine Datei mit dem Namen `service.svclog` geschrieben werden.

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

 Zum Anzeigen der Ablauf Verfolgungs Informationen, die in `service.svclog`enthalten sind, wird das [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) verwendet. Dies ist besonders beim Beheben von inhaltsbasierten Korrelationsproblemen hilfreich, da Sie die Meldungsinhalte anzeigen und genau sehen können, welche Daten übergeben werden und ob diese mit der <xref:System.ServiceModel.CorrelationQuery> für die inhaltsbasierte Korrelation übereinstimmen. Weitere Informationen zur WCF-Ablauf Verfolgung finden Sie unter [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), Konfigurieren der Ablauf [Verfolgung](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)und [Verwenden der Ablauf Verfolgung zum Beheben von Problemen mit der Anwendung](../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="common-context-exchange-correlation-issues"></a>Allgemeine Probleme bei der Kontextaustauschkorrelation
 Bestimmte Korrelationstypen erfordern einen bestimmten Bindungstyp, damit die Korrelation einwandfrei funktioniert. Beispiele sind die Anforderung-Antwort-Korrelation, die eine bidirektionale Bindung (z. B. <xref:System.ServiceModel.BasicHttpBinding>) erfordert, und die Kontextaustauschkorrelation, die eine kontextbasierte Bindung (z. B. <xref:System.ServiceModel.BasicHttpContextBinding>) erfordert. Die meisten Bindungen unterstützen bidirektionale Vorgänge, sodass dies kein häufig auftretendes Problem bei der Anforderung-Antwort-Korrelation ist. Es gibt jedoch nur wenige kontextbasierte Bindungen, z. B. <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> und <xref:System.ServiceModel.NetTcpContextBinding>. Wenn eine dieser Bindungen nicht verwendet wird, kann der erste Aufruf eines Workflowdiensts erfolgreich ausgeführt werden. Die nachfolgenden Aufrufe geben jedoch die folgende <xref:System.ServiceModel.FaultException> als Fehler zurück.

```output
There is no context attached to the incoming message for the service
and the current operation is not marked with "CanCreateInstance = true".
In order to communicate with this service check whether the incoming binding
supports the context protocol and has a valid context initialized.
```

 Die für die Kontextkorrelation verwendeten Kontextinformationen können von der <xref:System.ServiceModel.Activities.SendReply> an die <xref:System.ServiceModel.Activities.Receive>-Aktivität zurückgegeben werden, die die Kontextkorrelation initialisiert, falls ein bidirektionaler Vorgang verwendet wird. Wenn es sich um einen unidirektionalen Vorgang handelt, kann der Aufrufer die Kontextinformationen angeben. Wird der Kontext nicht vom Aufrufer gesendet oder vom Workflowdienst zurückgegeben, wird die bereits zuvor beschriebene <xref:System.ServiceModel.FaultException> zurückgegeben, wenn ein nachfolgender Vorgang aufgerufen wird.

## <a name="common-request-reply-correlation-issues"></a>Allgemeine Probleme bei der Anforderung-Antwort-Korrelation
 Die Anforderung-Antwort-Korrelation wird mit einem <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply>-paar verwendet, um einen bidirektionalen Vorgang in einem Workflow Dienst zu implementieren, und mit einem <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> Paar, das einen bidirektionalen Vorgang in einem anderen Webdienst aufruft. Wenn Sie einen bidirektionalen Vorgang in einem WCF-Dienst aufrufen, kann der Dienst entweder ein herkömmlicher imperativer, imperativer Code basierter WCF-Dienst sein, oder es kann sich um einen Workflow Dienst handeln. Für die Anforderung-Antwort-Korrelation muss eine bidirektionale Bindung verwendet werden (z. B. <xref:System.ServiceModel.BasicHttpBinding>). Außerdem müssen die Vorgänge bidirektional ausgelegt sein.

 Wenn der Workflow Dienst gleichzeitige bidirektionale Vorgänge oder überlappende <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> oder <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> Paare hat, reicht die von <xref:System.ServiceModel.Activities.WorkflowServiceHost> bereitgestellte implizite Korrelations Handle-Verwaltung möglicherweise nicht aus, insbesondere in Szenarien mit hoher Belastung, und Nachrichten werden möglicherweise nicht ordnungsgemäß weitergeleitet. Zur Verhinderung dieses Problems empfiehlt es sich, bei der Verwendung der Anforderung-Antwort-Korrelation immer explizit einen <xref:System.ServiceModel.Activities.CorrelationHandle> anzugeben. Wenn Sie die **sendandreceivereply** -Vorlage und die **receiveandsendreply** -Vorlage im Abschnitt Messaging der **Toolbox** im Workflow-Designer verwenden, wird standardmäßig eine <xref:System.ServiceModel.Activities.CorrelationHandle> explizit konfiguriert. Bei der Erstellung eines Workflows mithilfe von Code wird der <xref:System.ServiceModel.Activities.CorrelationHandle> in den <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> der ersten Aktivität des Paars angegeben. Im folgenden Beispiel wird eine <xref:System.ServiceModel.Activities.Receive>-Aktivität mit einem expliziten <xref:System.ServiceModel.Activities.CorrelationInitializer.CorrelationHandle%2A>, der im <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> angegeben wurde, konfiguriert.

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

 Persistenz ist zwischen einem <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> Paar oder einem <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> paar nicht zulässig. Es wird eine Zone ohne Persistenz erstellt, die vorhanden ist, bis beide Aktivitäten abgeschlossen wurden. Wenn in der Zone ohne Persistenz eine Aktivität, z. B. eine Verzögerungsaktivität, vorhanden ist, die den Workflow in den Leerlauf versetzt, bleibt der Workflow nicht erhalten, auch wenn der Host zum Beibehalten von in den Leerlauf versetzten Workflows konfiguriert ist. Wenn eine Aktivität, z. B. eine Persist-Aktivität, den Workflow in der Zone ohne Persistenz explizit beizubehalten versucht, wird ein schwerwiegender Ausnahmefehler ausgelöst, der Workflow wird abgebrochen, und an den Aufrufer wird eine <xref:System.ServiceModel.FaultException> zurückgegeben. Die Meldung zum schwerwiegenden Ausnahmefehler lautet "System.InvalidOperationException: Persist-Aktivitäten können nicht in nicht persistenten Blöcken enthalten sein." Diese Ausnahme wird nicht an den Aufrufer zurückgegeben, sie kann jedoch angezeigt werden, wenn Nachverfolgung aktiviert ist. Die für die <xref:System.ServiceModel.FaultException> an den Aufrufer zurückgegebene Meldung lautet "Der Vorgang konnte nicht ausgeführt werden, da die Workflowinstanz '5836145b-7da2-49d0-a052-a49162adeab6' abgeschlossen wurde".

 Weitere Informationen zur Anforderung-Antwort-Korrelation finden Sie unter [Request-Reply](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md).

## <a name="common-content-correlation-issues"></a>Allgemeine Probleme bei der Inhaltskorrelation
 Die inhaltsbasierte Korrelation wird verwendet, wenn ein Workflowdienst mehrere Meldungen empfängt und ein Datenelement in den ausgetauschten Nachrichten die gewünschte Instanz angibt. Die inhaltsbasierte Korrelation verwendet diese Daten in der Nachricht, z. B. eine Kundennummer oder Bestell-ID, um Nachrichten an die richtige Workflowinstanz weiterzuleiten. In diesem Abschnitt werden mehrere häufig auftretende Probleme beschrieben, die bei der inhaltsbasierten Korrelation vorkommen können.

### <a name="ensure-the-identifying-data-is-unique"></a>Sicherstellen, dass die identifizierenden Daten eindeutig sind
 Die Daten zur Identifikation der Instanz werden per Hash in einen Korrelationsschlüssel umgewandelt. Dabei müssen Sie sicherstellen, dass die für die Korrelation verwendeten Daten eindeutig sind, da sonst Konflikte im Hashschlüssel auftreten und Nachrichten ggf. falsch weitergeleitet werden können. Wenn eine Korrelation z. B. ausschließlich auf einem Kundennamen basiert, kann es zu einem Konflikt kommen, da es möglicherweise mehrere Kunden mit dem gleichen Namen gibt. Der Doppelpunkt (:) darf nicht als Bestandteil der Daten verwendet werden, mit denen die Meldung korreliert wird, da hiermit bereits Schlüssel und Wert der Meldungsabfrage begrenzt werden, um die Zeichenfolge zu bilden, für die anschließend der Hashwert berechnet wird. Wenn Persistenz verwendet wird, stellen Sie sicher, dass die aktuellen identifizierenden Daten nicht von einer zuvor beibehaltenen Instanz verwendet wurden. Die vorübergehende Deaktivierung der Persistenz kann dabei helfen, das Problem zu identifizieren. Mit der WCF-Ablaufverfolgung kann der berechnete Korrelationsschlüssel angezeigt werden. Sie ist außerdem hilfreich beim Debuggen von Problemen dieser Art.

### <a name="race-conditions"></a>Racebedingungen
 Es gibt eine kleine zeitliche Lücke zwischen dem Zeitpunkt, zu dem der Dienst die Meldung empfängt, und der eigentlichen Initialisierung der Korrelation. In dieser Zeitspanne werden weitere Meldungen ignoriert. Wenn ein Workflowdienst die inhaltsbasierte Korrelation mit Daten initialisiert, die vom Client über einen unidirektionalen Vorgang gesendet werden, und der Client unmittelbar darauf weitere Meldungen sendet, werden diese Meldungen während des beschriebenen Intervalls ignoriert. Dies kann vermieden werden, indem die Korrelation mit einem bidirektionalen Vorgang initialisiert wird oder indem ein <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwendet wird.

### <a name="correlation-query-issues"></a>Probleme bei Korrelationsabfragen
 Mit Korrelationsabfragen wird angegeben, welche Daten in einer Meldung verwendet werden, um die Meldung zu korrelieren. Diese Daten werden mit einer XPath-Abfrage angegeben. Wenn Nachrichten nicht an einen Dienst weitergeleitet werden, obwohl keine Anzeichen eines Problems ersichtlich sind, können Sie einen Literalwert angeben, der mit dem Wert der Meldungsdaten und nicht mit einer XPath-Abfrage übereinstimmt. Verwenden Sie die `string`-Funktion, um einen Literalwert anzugeben. Im folgenden Beispiel wird ein <xref:System.ServiceModel.MessageQuerySet> konfiguriert, um den Literalwert `11445` für die `OrderId` zu verwenden, und die XPath-Abfrage wird auskommentiert.

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

 Wenn eine XPath-Abfrage falsch konfiguriert ist, sodass keine Korrelationsdaten abgerufen werden, wird ein Fehler mit der folgenden Meldung zurückgegeben: „Eine Korrelationsabfrage ergab ein leeres Resultset. Stellen Sie sicher, dass die Korrelationsabfragen für den Endpunkt ordnungsgemäß konfiguriert sind." Dieser Fehler lässt sich schnell beheben, indem die XPath-Abfrage wie im vorherigen Abschnitt beschrieben durch einen Literalwert ersetzt wird. Dieses Problem kann auftreten, wenn Sie den XPath-Abfrage-Generator in den Dialogfeldern **korrelationsinitialisierer hinzufügen** oder **CorrelatesOn-Definition** verwenden und der Workflow Dienst Nachrichten Verträge verwendet. Im folgenden Beispiel wird eine Nachrichtenvertragsklasse definiert.

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

 Dieser Nachrichtenvertrag wird von einer <xref:System.ServiceModel.Activities.Receive>-Aktivität in einem Workflow verwendet. Die `CartId` im Header der Nachricht wird zum Korrelieren der Nachricht mit der ordnungsgemäßen Instanz verwendet. Wenn die XPath-Abfrage zum Abrufen der `CartId` mit den Korrelationsdialogfeldern im Workflow-Designer erstellt wird, wird die folgende fehlerhafte XPath-Abfrage generiert.

```
sm:body()/xg0:AddItemMessage/xg0:CartId
```

 Diese XPath-Abfrage ist ordnungsgemäß, wenn die <xref:System.ServiceModel.Activities.Receive>-Aktivität Parameter für die Daten verwendet. Da sie jedoch einen Nachrichtenvertrag verwendet, ist die Abfrage fehlerhaft. Die folgende XPath-Abfrage ist die ordnungsgemäße Abfrage zum Abrufen der `CartId` aus dem Header.

```
sm:header()/tempuri:CartId
```

Dies kann anhand des Nachrichtentexts überprüft werden.

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

Im folgenden Beispiel wird eine für einen <xref:System.ServiceModel.Activities.Receive>-Vorgang konfigurierte `AddItem`-Aktivität gezeigt, die Daten mithilfe des vorherigen Nachrichtenvertrags empfängt. Die XPath-Abfrage ist ordnungsgemäß konfiguriert.

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
