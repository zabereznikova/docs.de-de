---
title: Nachrichteninspektoren
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 705401a182d5d816bc2682f5f21ff09ca95f21c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144447"
---
# <a name="message-inspectors"></a>Nachrichteninspektoren
In diesem Beispiel wird veranschaulicht, wie Client- und Dienstnachrichteninspektoren implementiert und konfiguriert werden.  
  
 Ein Nachrichteninspektor ist ein erweiterbares Objekt, das programmgesteuert in der Clientlaufzeit und Dispatchlaufzeit des Dienstmodels oder durch Konfiguration verwendet werden kann. Außerdem kann es Nachrichten nach dem Empfang oder vor dem Versand überprüfen und ändern.  
  
 In diesem Beispiel wird ein Überprüfungsmechanismus für grundlegende Client- und Dienstnachrichten implementiert, der eingehende Nachrichten anhand eines Satzes von konfigurierbaren XML-Schemadokumenten überprüft. Beachten Sie, dass in diesem Beispiel keine Nachrichten für jeden Vorgang überprüft werden. Diese Vereinfachung ist beabsichtigt.  
  
## <a name="message-inspector"></a>Nachrichteninspektor  
 Clientnachrichteninspektoren implementieren die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>-Schnittstelle, und Dienstnachrichteninspektoren implementieren die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>-Schnittstelle. Die Implementierungen können in einer Klasse zusammengefasst werden, um einen Nachrichteninspektor zu bilden, der für beide Seiten funktioniert. In diesem Beispiel wird so ein kombinierter Nachrichteninspektor implementiert. Der Inspektor wird erstellt und übergibt einen Schemasatz, anhand dessen eingehende und ausgehende Nachrichten überprüft werden. Außerdem kann der Entwickler festlegen, ob eingehende oder ausgehende Nachrichten überprüft werden und ob der Inspektor sich im Dispatch- oder Clientmodus befindet. Diese letzte Einstellung beeinflusst die Fehlerbehandlung, die später in diesem Thema erläutert wird.  
  
```csharp
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 Jeder Dienstnachrichteninspektor (Dienstverteilernachrichteninspektor) muss die beiden <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>-Methoden <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> und <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> implementieren.  
  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> wird vom Verteiler aufgerufen, wenn eine Nachricht empfangen, durch den Kanalstapel verarbeitet und einem Dienst zugeordnet wurde, jedoch bevor sie deserialisiert und an einen Vorgang verteilt wurde. Wenn die eingehende Nachricht verschlüsselt war, ist die Nachricht bereits entschlüsselt, wenn sie den Nachrichteninspektor erreicht. Die Methode ruft die `request`-Nachricht ab, die als Verweisparameter übergeben wurde. Dadurch kann die Nachricht nach Bedarf überprüft, bearbeitet oder ersetzt werden. Der Rückgabewert kann jedes Objekt sein und wird als Korrelationsstatusobjekt verwendet, dass an <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> übergeben wird, wenn der Dienst eine Antwort auf eine aktuelle Nachricht zurückgibt. In diesem Beispiel delegiert <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> die Inspektion (Validierung) der Nachricht an eine private, lokale Methode `ValidateMessageBody` und gibt kein Korrelationsstatusobjekt zurück. Diese Methode stellt sicher, dass keine ungültigen Nachrichten an den Dienst übergeben werden.  
  
```csharp  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> wird immer dann aufgerufen, wenn eine Antwort zum Versenden zurück an einen Client bereit ist, oder bei unidirektionalen Nachrichten, wenn die eingehende Nachricht verarbeitet wurde. Dadurch können sich Erweiterungen darauf verlassen, unabhängig von MEP symmetrisch aufgerufen zu werden. Wie bei <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> wird die Nachricht als Verweisparameter übergeben und kann überprüft, bearbeitet oder ersetzt werden. Die in diesem Beispiel durchgeführte Überprüfung der Nachricht wird ebenfalls an die `ValidMessageBody`-Methode delegiert, die Behandlung der Validierungsfehler erfolgt in diesem Fall jedoch etwas anders.  
  
 Wenn ein Validierungsfehler beim Dienst auftritt, löst die `ValidateMessageBody`-Methode von <xref:System.ServiceModel.FaultException> abgeleitete Ausnahmen aus. In der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>-Methode können diese Ausnahmen in der Infrastruktur des Dienstmodells abgelegt werden, wo sie automatisch in SOAP-Fehler transformiert und an den Client weitergeleitet werden. In der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>-Methode dürfen <xref:System.ServiceModel.FaultException>-Ausnahmen nicht in der Infrastruktur abgelegt werden, da die Transformation der vom Dienst ausgelösten Fehlerausnahmen vor dem Aufrufen des Nachrichteninspektors erfolgt. Die folgende Implementierung erfasst deshalb die bekannte `ReplyValidationFault`-Ausnahme und ersetzt die Antwortnachricht durch eine explizite Fehlermeldung. Diese Methode stellt sicher, dass keine ungültigen Nachrichten von der Dienstimplementierung zurückgegeben werden.  
  
```csharp  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 Der Clientnachrichteninspektor ist sehr ähnlich. Die beiden Methoden, die von <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> implementiert werden müssen, lauten <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> und <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.  
  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> wird aufgerufen, wenn die Nachricht entweder von der Clientanwendung oder vom Vorgangsformatierer erstellt wurde. Wie bei Verteilernachrichteninspektoren kann die Nachricht entweder nur überprüft oder vollständig ersetzt werden. In diesem Beispiel delegiert der Inspektor dieselbe lokale `ValidateMessageBody`-Hilfsmethode, die auch für Verteilernachrichteninspektoren verwendet wird.  
  
 Die Verhaltensunterschiede zwischen Client- und die Dienstvalidierung (wie im Konstruktor festgelegt) bestehen darin, dass die Clientvalidierung lokale Ausnahmen, die im Benutzercode abgelegt sind, auslöst, weil sie lokal auftreten und nicht aufgrund eines Dienstausfalls. Im Allgemeinen gilt, dass Dienstverteilerinspektoren Fehler auslösen und Clientinspektoren Ausnahmen auslösen.  
  
 Diese <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>-Implementierung stellt sicher, dass keine ungültigen Nachrichten an den Dienst gesendet werden.  
  
```csharp  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 Die `AfterReceiveReply`-Implementierung stellt sicher, dass keine ungültigen, vom Dienst empfangenen Nachrichten an den Client-Benutzercode weitergeleitet werden.  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 Das Kernstück dieses bestimmten Nachrichteninspektors ist die `ValidateMessageBody`-Methode. Um seine Funktion auszuführen, umschließt er die Teilstruktur des Textinhalts der weitergeleiteten Nachricht mit einem Validierungs-<xref:System.Xml.XmlReader>. Der Reader wird mit dem Schemasatz aufgefüllt, den der Nachrichteninspektor enthält und der Validierungsrückruf wird auf einen Delegaten festgelegt, der auf `InspectionValidationHandler` verweist, der wiederum gemeinsam mit dieser Methode definiert ist. Um die Validierung auszuführen, wird die Nachricht dann gelesen und in einen Speicherstream-gesicherten <xref:System.Xml.XmlDictionaryWriter> übertragen. Wenn ein Validierungsfehler oder eine Warnung im Prozess auftritt, wird die Rückrufmethode aufgerufen.  
  
 Wenn kein Fehler auftritt, wird eine neue Nachricht erstellt, die die Eigenschaften und Header der ursprünglichen Nachricht kopiert und das jetzt validierte Infoset im Speicherstream verwendet, der von einem <xref:System.Xml.XmlDictionaryReader> umschlossen und zur Ersatznachricht hinzugefügt wurde.  
  
```csharp  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 Die `InspectionValidationHandler`-Methode wird immer dann vom validierenden <xref:System.Xml.XmlReader> aufgerufen, wenn ein Schemavalidierungsfehler oder eine Warnung auftritt. Die folgende Implementierung funktioniert nur mit Fehlern und ignoriert alle Warnungen.  
  
 Auf den ersten Blick scheint es möglich, einen validierenden <xref:System.Xml.XmlReader> in die Nachricht mit dem Nachrichteninspektor einzufügen und die Validierung bei der Verarbeitung der Nachricht durchzuführen, ohne die Nachricht zu sichern. Dies würde jedoch bedeuten, dass dieser Rückruf die Validierungsausnahmen an einem beliebigen Punkt der Dienstmodellinfrastruktur oder des Benutzercodes auslöst, wenn ungültige XML-Knoten erkannt werden. Das kann zu unvorhersehbarem Verhalten führen. Der Pufferungsansatz schützt den Benutzercode vollständig vor ungültigen Nachrichten.  
  
 Wie bereits erläutert unterscheiden sich die vom Handler ausgelösten Ausnahmen zwischen dem Client und dem Dienst. Beim Dienst werden die Ausnahmen von <xref:System.ServiceModel.FaultException> abgeleitet, beim Client sind die Ausnahmen reguläre benutzerdefinierte Ausnahmen.  
  
```csharp  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a>Verhalten  
 Nachrichteninspektoren sind Erweiterungen zur Clientlaufzeit oder der Dispatchlaufzeit. Solche Erweiterungen werden mit *Verhalten*konfiguriert. Eine Verhaltensweise ist eine Klasse, die das Verhalten der Dienstmodelllaufzeit ändert, indem sie die Standardkonfiguration ändert oder Erweiterungen (wie Nachrichteninspektoren) hinzufügt.  
  
 Bei der folgenden `SchemaValidationBehavior`-Klasse handelt es sich um die Verhaltensweise, mit der der Nachrichteninspektor dieses Beispiels zur Client- oder Dispatchlaufzeit hinzugefügt wird. Die Implementierung ist in beiden Fällen ganz einfach. In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> und <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A> wird der Nachrichteninspektor erstellt und zur <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A>-Auflistung der entsprechenden Laufzeit hinzugefügt.  
  
```csharp
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;
    bool validateRequest;
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,
       System.ServiceModel.Channels.BindingParameterCollection
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,
         System.ServiceModel.Dispatcher.EndpointDispatcher
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =
           new SchemaValidationMessageInspector(schemaSet,
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
> Diese bestimmte Verhaltensweise tritt nicht als Attribut auf und kann deshalb nicht deklarativ zu einem Vertragstyp eines Diensttyps hinzugefügt werden. Diese Entscheidung wurde absichtlich getroffen, da die Schemaauflistung nicht in einer Attributdeklaration geladen werden kann und für den Verweis auf einen gesonderten Konfigurationsspeicherort (z. B. auf die Anwendungseinstellungen) in diesem Attribut müsste ein Konfigurationselement erstellt werden, dass nicht mit der restlichen Dienstmodellkonfiguration konsistent ist. Deshalb kann diese Verhaltensweise nur zwingend über Code und eine Erweiterung der Dienstmodellkonfiguration hinzugefügt werden.  
  
## <a name="adding-the-message-inspector-through-configuration"></a>Hinzufügen des Nachrichteninspektors durch Konfiguration  
 Zum Konfigurieren eines benutzerdefinierten Verhaltens auf einem Endpunkt in der Anwendungskonfigurationsdatei erfordert das Dienstmodell Implementierer, um ein *Konfigurationserweiterungselement* zu erstellen, das durch eine von <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>abgeleitete Klasse dargestellt wird. Diese Erweiterung muss dann zum Konfigurationsabschnitt für Erweiterungen des Dienstmodells hinzugefügt werden, wie für die folgende in diesem Abschnitt erläuterte Erweiterung gezeigt.  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 Erweiterungen können entweder in der Anwendungs- oder der ASP.NET-Konfigurationsdatei (häufigste Auswahl) oder in der Konfigurationsdatei für den Computer hinzugefügt werden.  
  
 Wenn die Erweiterung zu einem Konfigurationsbereich hinzugefügt wird, kann die Verhaltensweise zu einer Verhaltenskonfiguration hinzugefügt werden, wie in folgendem Code gezeigt. Verhaltenskonfigurationen sind wiederverwendbare Elemente, die nach Bedarf auf mehrere Endpunkte angewendet werden können. Da die bestimmte Verhaltensweise, die hier konfiguriert werden soll, <xref:System.ServiceModel.Description.IEndpointBehavior> implementiert, ist sie nur im entsprechenden Konfigurationsbereich in der Konfigurationsdatei gültig.  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 Das `<schemaValidator>`-Element, das den Nachrichteninspektor konfiguriert, wird von der `SchemaValidationBehaviorExtensionElement`-Klasse unterstützt. Die Klasse macht zwei öffentliche boolesche Eigenschaften namens `ValidateRequest` und `ValidateReply` verfügbar. Beide Eigenschaften sind mit einem <xref:System.Configuration.ConfigurationPropertyAttribute> gekennzeichnet. Dieses Attribut bildet die Verknüpfung zwischen den Codeeigenschaften und den XML-Attributen, die im vorangehenden XML-Konfigurationselement sichtbar sind. Die Klasse verfügt auch über eine Eigenschaft `Schemas`, die zusätzlich mit dem <xref:System.Configuration.ConfigurationCollectionAttribute> gekennzeichnet und vom Typ `SchemaCollection` ist. Diese Eigenschaft ist ebenfalls Teil des Beispiels, ist aber zur besseren Übersichtlichkeit nicht in diesem Dokument enthalten. Diese Eigenschaft unterstützt zusammen mit der Auflistung und der Auflistelementklasse `SchemaConfigElement` das `<schemas>`-Element im vorangehenden Konfigurationsausschnitt und ermöglicht das Hinzufügen einer Schemaauflistung zum Validierungssatz.  
  
 Die überschriebene `CreateBehavior`-Methode wandelt die Konfigurationsdaten in ein Verhaltensobjekt um, wenn die Laufzeit die Konfigurationsdaten beim Erstellen eines Clients oder Endpunkts bewertet.  
  
```csharp
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType
    {
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs
     //.NET Framework to build a nested section of
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a>Imperatives Hinzufügen von Nachrichteninspektoren  
 Außer über Attribute (was aus dem oben genannten Grund in diesem Beispiel nicht unterstützt wird) und die Konfiguration können Verhaltensweisen relativ einfach mithilfe von imperativem Code zu einem Client oder einer Dienstlaufzeit hinzugefügt werden. In diesem Beispiel wird dies in der Clientanwendung durchgeführt, um den Clientnachrichteninspektor zu testen. Die `GenericClient`-Klasse wird von <xref:System.ServiceModel.ClientBase%601> abgeleitet, der dem Benutzercode die Endpunktkonfiguration verfügbar macht. Bevor der Client implizit geöffnet wird, kann die Endpunktkonfiguration geändert werden, z. B. durch Hinzufügen von Verhaltensweisen, wie im folgenden Code dargestellt. Das Hinzufügen von Verhaltensweisen zum Dienst ist in großen Teilen mit der hier dargestellten Clienttechnik vergleichbar und muss vor dem Öffnen des Diensthosts durchgeführt werden.  
  
```csharp  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die Lösung zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
