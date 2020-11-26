---
title: Nachrichteninspektoren
description: Erfahren Sie, wie Sie WCF-Client-und Dienst Nachrichten Inspektoren implementieren und konfigurieren, die einen Nachrichten Validierungs Mechanismus bereitstellen.
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 4b2f7b97d0895e3cb7550217f64a2b0b14545abf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240705"
---
# <a name="message-inspectors"></a><span data-ttu-id="43d38-103">Nachrichteninspektoren</span><span class="sxs-lookup"><span data-stu-id="43d38-103">Message Inspectors</span></span>

<span data-ttu-id="43d38-104">In diesem Beispiel wird veranschaulicht, wie Client- und Dienstnachrichteninspektoren implementiert und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-104">This sample demonstrates how to implement and configure client and service message inspectors.</span></span>  
  
 <span data-ttu-id="43d38-105">Ein Nachrichteninspektor ist ein erweiterbares Objekt, das programmgesteuert in der Clientlaufzeit und Dispatchlaufzeit des Dienstmodels oder durch Konfiguration verwendet werden kann. Außerdem kann es Nachrichten nach dem Empfang oder vor dem Versand überprüfen und ändern.</span><span class="sxs-lookup"><span data-stu-id="43d38-105">A message inspector is an extensibility object that can be used in the service model's client runtime and dispatch runtime programmatically or through configuration and that can inspect and alter messages after they are received or before they are sent.</span></span>  
  
 <span data-ttu-id="43d38-106">In diesem Beispiel wird ein Überprüfungsmechanismus für grundlegende Client- und Dienstnachrichten implementiert, der eingehende Nachrichten anhand eines Satzes von konfigurierbaren XML-Schemadokumenten überprüft.</span><span class="sxs-lookup"><span data-stu-id="43d38-106">This sample implements a basic client and service message validation mechanism that validates incoming messages against a set of configurable XML Schema documents.</span></span> <span data-ttu-id="43d38-107">Beachten Sie, dass in diesem Beispiel keine Nachrichten für jeden Vorgang überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-107">Note that this sample does not validate messages for each operation.</span></span> <span data-ttu-id="43d38-108">Diese Vereinfachung ist beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="43d38-108">This is an intentional simplification.</span></span>  
  
## <a name="message-inspector"></a><span data-ttu-id="43d38-109">Nachrichteninspektor</span><span class="sxs-lookup"><span data-stu-id="43d38-109">Message Inspector</span></span>  

 <span data-ttu-id="43d38-110">Clientnachrichteninspektoren implementieren die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>-Schnittstelle, und Dienstnachrichteninspektoren implementieren die <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="43d38-110">Client message inspectors implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> interface and service message inspectors implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> interface.</span></span> <span data-ttu-id="43d38-111">Die Implementierungen können in einer Klasse zusammengefasst werden, um einen Nachrichteninspektor zu bilden, der für beide Seiten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="43d38-111">The implementations can be combined into a single class to form a message inspector that works for both sides.</span></span> <span data-ttu-id="43d38-112">In diesem Beispiel wird so ein kombinierter Nachrichteninspektor implementiert.</span><span class="sxs-lookup"><span data-stu-id="43d38-112">This sample implements such a combined message inspector.</span></span> <span data-ttu-id="43d38-113">Der Inspektor wird erstellt und übergibt einen Schemasatz, anhand dessen eingehende und ausgehende Nachrichten überprüft werden. Außerdem kann der Entwickler festlegen, ob eingehende oder ausgehende Nachrichten überprüft werden und ob der Inspektor sich im Dispatch- oder Clientmodus befindet. Diese letzte Einstellung beeinflusst die Fehlerbehandlung, die später in diesem Thema erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="43d38-113">The inspector is constructed passing in a set of schemas against which incoming and outgoing messages are validated and allows the developer to specify whether incoming or outgoing messages are validated and whether the inspector is in dispatch or client mode, which affects the error handling as discussed later in this topic.</span></span>  
  
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
  
 <span data-ttu-id="43d38-114">Jeder Dienstnachrichteninspektor (Dienstverteilernachrichteninspektor) muss die beiden <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>-Methoden <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> und <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> implementieren.</span><span class="sxs-lookup"><span data-stu-id="43d38-114">Any service (dispatcher) message inspector must implement the two <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> methods <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span></span>  
  
 <span data-ttu-id="43d38-115"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> wird vom Verteiler aufgerufen, wenn eine Nachricht empfangen, durch den Kanalstapel verarbeitet und einem Dienst zugeordnet wurde, jedoch bevor sie deserialisiert und an einen Vorgang verteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="43d38-115"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> is invoked by the dispatcher when a message has been received, processed by the channel stack and assigned to a service, but before it is deserialized and dispatched to an operation.</span></span> <span data-ttu-id="43d38-116">Wenn die eingehende Nachricht verschlüsselt war, ist die Nachricht bereits entschlüsselt, wenn sie den Nachrichteninspektor erreicht.</span><span class="sxs-lookup"><span data-stu-id="43d38-116">If the incoming message was encrypted, the message is already decrypted when it reaches the message inspector.</span></span> <span data-ttu-id="43d38-117">Die Methode ruft die `request`-Nachricht ab, die als Verweisparameter übergeben wurde. Dadurch kann die Nachricht nach Bedarf überprüft, bearbeitet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-117">The method gets the `request` message passed as a reference parameter, which allows the message to be inspected, manipulated or replaced as required.</span></span> <span data-ttu-id="43d38-118">Der Rückgabewert kann jedes Objekt sein und wird als Korrelationsstatusobjekt verwendet, dass an <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> übergeben wird, wenn der Dienst eine Antwort auf eine aktuelle Nachricht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="43d38-118">The return value can be any object and is used as a correlation state object that is passed to <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> when the service returns a reply to the current message.</span></span> <span data-ttu-id="43d38-119">In diesem Beispiel delegiert <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> die Inspektion (Validierung) der Nachricht an eine private, lokale Methode `ValidateMessageBody` und gibt kein Korrelationsstatusobjekt zurück.</span><span class="sxs-lookup"><span data-stu-id="43d38-119">In this sample, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delegates the inspection (validation) of the message to the private, local method `ValidateMessageBody` and returns no correlation state object.</span></span> <span data-ttu-id="43d38-120">Diese Methode stellt sicher, dass keine ungültigen Nachrichten an den Dienst übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-120">This method ensures that no invalid messages pass into the service.</span></span>  
  
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
  
 <span data-ttu-id="43d38-121"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> wird immer dann aufgerufen, wenn eine Antwort zum Versenden zurück an einen Client bereit ist, oder bei unidirektionalen Nachrichten, wenn die eingehende Nachricht verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="43d38-121"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> is invoked whenever a reply is ready to be sent back to a client, or in the case of one-way messages, when the incoming message has been processed.</span></span> <span data-ttu-id="43d38-122">Dadurch können sich Erweiterungen darauf verlassen, unabhängig von MEP symmetrisch aufgerufen zu werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-122">This allows extensions to count on being called symmetrically, regardless of MEP.</span></span> <span data-ttu-id="43d38-123">Wie bei <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> wird die Nachricht als Verweisparameter übergeben und kann überprüft, bearbeitet oder ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-123">As with <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, the message is passed as a reference parameter and can be inspected, modified or replaced.</span></span> <span data-ttu-id="43d38-124">Die in diesem Beispiel durchgeführte Überprüfung der Nachricht wird ebenfalls an die `ValidMessageBody`-Methode delegiert, die Behandlung der Validierungsfehler erfolgt in diesem Fall jedoch etwas anders.</span><span class="sxs-lookup"><span data-stu-id="43d38-124">The validation of the message that is performed in this sample is again delegated to the `ValidMessageBody` method, but the handling of validation errors is slightly different in this case.</span></span>  
  
 <span data-ttu-id="43d38-125">Wenn ein Validierungsfehler beim Dienst auftritt, löst die `ValidateMessageBody`-Methode von <xref:System.ServiceModel.FaultException> abgeleitete Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="43d38-125">If a validation error occurs on the service, the `ValidateMessageBody` method throws <xref:System.ServiceModel.FaultException>-derived exceptions.</span></span> <span data-ttu-id="43d38-126">In der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>-Methode können diese Ausnahmen in der Infrastruktur des Dienstmodells abgelegt werden, wo sie automatisch in SOAP-Fehler transformiert und an den Client weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, these exceptions can be put into the service model infrastructure where they are automatically transformed into SOAP faults and relayed to the client.</span></span> <span data-ttu-id="43d38-127">In der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>-Methode dürfen <xref:System.ServiceModel.FaultException>-Ausnahmen nicht in der Infrastruktur abgelegt werden, da die Transformation der vom Dienst ausgelösten Fehlerausnahmen vor dem Aufrufen des Nachrichteninspektors erfolgt.</span><span class="sxs-lookup"><span data-stu-id="43d38-127">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, <xref:System.ServiceModel.FaultException> exceptions must not be put into the infrastructure, because the transformation of fault exceptions thrown by the service occurs before the message inspector is called.</span></span> <span data-ttu-id="43d38-128">Die folgende Implementierung erfasst deshalb die bekannte `ReplyValidationFault`-Ausnahme und ersetzt die Antwortnachricht durch eine explizite Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="43d38-128">Therefore the following implementation catches the known `ReplyValidationFault` exception and replaces the reply message with an explicit fault message.</span></span> <span data-ttu-id="43d38-129">Diese Methode stellt sicher, dass keine ungültigen Nachrichten von der Dienstimplementierung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-129">This method ensures that no invalid messages are returned by the service implementation.</span></span>  
  
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
  
 <span data-ttu-id="43d38-130">Der Clientnachrichteninspektor ist sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="43d38-130">The client message inspector is very similar.</span></span> <span data-ttu-id="43d38-131">Die beiden Methoden, die von <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> implementiert werden müssen, lauten <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> und <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span><span class="sxs-lookup"><span data-stu-id="43d38-131">The two methods that must be implemented from <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> are <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> and <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span></span>  
  
 <span data-ttu-id="43d38-132"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> wird aufgerufen, wenn die Nachricht entweder von der Clientanwendung oder vom Vorgangsformatierer erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="43d38-132"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> is invoked when the message has been composed either by the client application or by the operation formatter.</span></span> <span data-ttu-id="43d38-133">Wie bei Verteilernachrichteninspektoren kann die Nachricht entweder nur überprüft oder vollständig ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-133">As with the dispatcher message inspectors, the message can just be inspected or entirely replaced.</span></span> <span data-ttu-id="43d38-134">In diesem Beispiel delegiert der Inspektor dieselbe lokale `ValidateMessageBody`-Hilfsmethode, die auch für Verteilernachrichteninspektoren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43d38-134">In this sample, the inspector delegates to the same local `ValidateMessageBody` helper method that is also used for the dispatch message inspectors.</span></span>  
  
 <span data-ttu-id="43d38-135">Die Verhaltensunterschiede zwischen Client- und die Dienstvalidierung (wie im Konstruktor festgelegt) bestehen darin, dass die Clientvalidierung lokale Ausnahmen, die im Benutzercode abgelegt sind, auslöst, weil sie lokal auftreten und nicht aufgrund eines Dienstausfalls.</span><span class="sxs-lookup"><span data-stu-id="43d38-135">The behavioral difference between the client and service validation (as specified in the constructor) is that the client validation throws local exceptions that are put into the user code because they occur locally and not because of a service failure.</span></span> <span data-ttu-id="43d38-136">Im Allgemeinen gilt, dass Dienstverteilerinspektoren Fehler auslösen und Clientinspektoren Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="43d38-136">Generally, the rule is that service dispatcher inspectors throw faults and that client inspectors throw exceptions.</span></span>  
  
 <span data-ttu-id="43d38-137">Diese <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>-Implementierung stellt sicher, dass keine ungültigen Nachrichten an den Dienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-137">This <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> implementation ensures that no invalid messages are sent to the service.</span></span>  
  
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
  
 <span data-ttu-id="43d38-138">Die `AfterReceiveReply`-Implementierung stellt sicher, dass keine ungültigen, vom Dienst empfangenen Nachrichten an den Client-Benutzercode weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-138">The `AfterReceiveReply` implementation ensures that no invalid messages received from the service are relayed to the client user code.</span></span>  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 <span data-ttu-id="43d38-139">Das Kernstück dieses bestimmten Nachrichteninspektors ist die `ValidateMessageBody`-Methode.</span><span class="sxs-lookup"><span data-stu-id="43d38-139">The heart of this particular message inspector is the `ValidateMessageBody` method.</span></span> <span data-ttu-id="43d38-140">Um seine Funktion auszuführen, umschließt er die Teilstruktur des Textinhalts der weitergeleiteten Nachricht mit einem Validierungs-<xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="43d38-140">To perform its work, it wraps a validating <xref:System.Xml.XmlReader> around the body content sub-tree of the passed message.</span></span> <span data-ttu-id="43d38-141">Der Reader wird mit dem Schemasatz aufgefüllt, den der Nachrichteninspektor enthält und der Validierungsrückruf wird auf einen Delegaten festgelegt, der auf `InspectionValidationHandler` verweist, der wiederum gemeinsam mit dieser Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="43d38-141">The reader is populated with the set of schemas that the message inspector holds and the validation callback is set to a delegate referring to the `InspectionValidationHandler` that is defined alongside this method.</span></span> <span data-ttu-id="43d38-142">Um die Validierung auszuführen, wird die Nachricht dann gelesen und in einen Speicherstream-gesicherten <xref:System.Xml.XmlDictionaryWriter> übertragen.</span><span class="sxs-lookup"><span data-stu-id="43d38-142">To perform the validation, the message is then read and spooled into a memory stream-backed <xref:System.Xml.XmlDictionaryWriter>.</span></span> <span data-ttu-id="43d38-143">Wenn ein Validierungsfehler oder eine Warnung im Prozess auftritt, wird die Rückrufmethode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="43d38-143">If a validation error or warning occurs in the process, the callback method is invoked.</span></span>  
  
 <span data-ttu-id="43d38-144">Wenn kein Fehler auftritt, wird eine neue Nachricht erstellt, die die Eigenschaften und Header der ursprünglichen Nachricht kopiert und das jetzt validierte Infoset im Speicherstream verwendet, der von einem <xref:System.Xml.XmlDictionaryReader> umschlossen und zur Ersatznachricht hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="43d38-144">If no error occurs, a new message is constructed that copies the properties and headers from the original message and uses the now-validated infoset in the memory stream, which is wrapped by an <xref:System.Xml.XmlDictionaryReader> and added to the replacement message.</span></span>  
  
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
  
 <span data-ttu-id="43d38-145">Die `InspectionValidationHandler`-Methode wird immer dann vom validierenden <xref:System.Xml.XmlReader> aufgerufen, wenn ein Schemavalidierungsfehler oder eine Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="43d38-145">The `InspectionValidationHandler` method is called by the validating <xref:System.Xml.XmlReader> whenever a schema validation error or warning occurs.</span></span> <span data-ttu-id="43d38-146">Die folgende Implementierung funktioniert nur mit Fehlern und ignoriert alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="43d38-146">The following implementation only works with errors and ignores all warnings.</span></span>  
  
 <span data-ttu-id="43d38-147">Auf den ersten Blick scheint es möglich, einen validierenden <xref:System.Xml.XmlReader> in die Nachricht mit dem Nachrichteninspektor einzufügen und die Validierung bei der Verarbeitung der Nachricht durchzuführen, ohne die Nachricht zu sichern.</span><span class="sxs-lookup"><span data-stu-id="43d38-147">On first consideration, it might seem possible to inject a validating <xref:System.Xml.XmlReader> into the message with the message inspector and let the validation happen as the message is processed and without buffering the message.</span></span> <span data-ttu-id="43d38-148">Dies würde jedoch bedeuten, dass dieser Rückruf die Validierungsausnahmen an einem beliebigen Punkt der Dienstmodellinfrastruktur oder des Benutzercodes auslöst, wenn ungültige XML-Knoten erkannt werden. Das kann zu unvorhersehbarem Verhalten führen.</span><span class="sxs-lookup"><span data-stu-id="43d38-148">That, however, means that this callback throws the validation exceptions somewhere into the service model infrastructure or the user code as invalid XML nodes are detected, resulting in unpredictable behavior.</span></span> <span data-ttu-id="43d38-149">Der Pufferungsansatz schützt den Benutzercode vollständig vor ungültigen Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="43d38-149">The buffering approach shields the user code from invalid messages, entirely.</span></span>  
  
 <span data-ttu-id="43d38-150">Wie bereits erläutert unterscheiden sich die vom Handler ausgelösten Ausnahmen zwischen dem Client und dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="43d38-150">As previously discussed, the exceptions thrown by the handler differ between the client and the service.</span></span> <span data-ttu-id="43d38-151">Beim Dienst werden die Ausnahmen von <xref:System.ServiceModel.FaultException> abgeleitet, beim Client sind die Ausnahmen reguläre benutzerdefinierte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="43d38-151">On the service, the exceptions are derived from <xref:System.ServiceModel.FaultException>, on the client the exceptions are regular custom exceptions.</span></span>  
  
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
  
## <a name="behavior"></a><span data-ttu-id="43d38-152">Verhalten</span><span class="sxs-lookup"><span data-stu-id="43d38-152">Behavior</span></span>  

 <span data-ttu-id="43d38-153">Nachrichteninspektoren sind Erweiterungen zur Clientlaufzeit oder der Dispatchlaufzeit.</span><span class="sxs-lookup"><span data-stu-id="43d38-153">Message inspectors are extensions to the client runtime or the dispatch runtime.</span></span> <span data-ttu-id="43d38-154">Solche Erweiterungen werden mithilfe von *Verhaltensweisen* konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="43d38-154">Such extensions are configured using *behaviors*.</span></span> <span data-ttu-id="43d38-155">Eine Verhaltensweise ist eine Klasse, die das Verhalten der Dienstmodelllaufzeit ändert, indem sie die Standardkonfiguration ändert oder Erweiterungen (wie Nachrichteninspektoren) hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="43d38-155">A behavior is a class that changes the behavior of the service model runtime by changing the default configuration or adding extensions (such as message inspectors) to it.</span></span>  
  
 <span data-ttu-id="43d38-156">Bei der folgenden `SchemaValidationBehavior`-Klasse handelt es sich um die Verhaltensweise, mit der der Nachrichteninspektor dieses Beispiels zur Client- oder Dispatchlaufzeit hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="43d38-156">The following `SchemaValidationBehavior` class is the behavior used to add this sample's message inspector to the client or dispatch runtime.</span></span> <span data-ttu-id="43d38-157">Die Implementierung ist in beiden Fällen ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="43d38-157">The implementation is rather basic in both cases.</span></span> <span data-ttu-id="43d38-158">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> und <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A> wird der Nachrichteninspektor erstellt und zur <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A>-Auflistung der entsprechenden Laufzeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43d38-158">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> and <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, the message inspector is created and added to the <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> collection of the respective runtime.</span></span>  
  
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
> <span data-ttu-id="43d38-159">Diese bestimmte Verhaltensweise tritt nicht als Attribut auf und kann deshalb nicht deklarativ zu einem Vertragstyp eines Diensttyps hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-159">This particular behavior does not double as an attribute and therefore cannot be added declaratively onto a contract type of a service type.</span></span> <span data-ttu-id="43d38-160">Diese Entscheidung wurde absichtlich getroffen, da die Schemaauflistung nicht in einer Attributdeklaration geladen werden kann und für den Verweis auf einen gesonderten Konfigurationsspeicherort (z. B. auf die Anwendungseinstellungen) in diesem Attribut müsste ein Konfigurationselement erstellt werden, dass nicht mit der restlichen Dienstmodellkonfiguration konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="43d38-160">This is a by-design decision made because the schema collection cannot be loaded in an attribute declaration and referring to an extra configuration location (for instance to the application settings) in this attribute means creating a configuration element that is not consistent with the rest of the service model configuration.</span></span> <span data-ttu-id="43d38-161">Deshalb kann diese Verhaltensweise nur zwingend über Code und eine Erweiterung der Dienstmodellkonfiguration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-161">Therefore, this behavior can only be added imperatively through code and through a service model configuration extension.</span></span>  
  
## <a name="adding-the-message-inspector-through-configuration"></a><span data-ttu-id="43d38-162">Hinzufügen des Nachrichteninspektors durch Konfiguration</span><span class="sxs-lookup"><span data-stu-id="43d38-162">Adding the Message Inspector through Configuration</span></span>  

 <span data-ttu-id="43d38-163">Zum Konfigurieren eines benutzerdefinierten Verhaltens für einen Endpunkt in der Anwendungs Konfigurationsdatei benötigt das Dienstmodell Implementierer, um ein Konfigurations *Erweiterungs Element* zu erstellen, das von einer von abgeleiteten Klasse repräsentiert wird <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> .</span><span class="sxs-lookup"><span data-stu-id="43d38-163">For configuring a custom behavior on an endpoint in the application configuration file, the service model requires implementers to create a configuration *extension element* represented by a class derived from <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span></span> <span data-ttu-id="43d38-164">Diese Erweiterung muss dann zum Konfigurationsabschnitt für Erweiterungen des Dienstmodells hinzugefügt werden, wie für die folgende in diesem Abschnitt erläuterte Erweiterung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d38-164">This extension must then be added to the service model's configuration section for extensions as shown for the following extension discussed in this section.</span></span>  
  
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
  
 <span data-ttu-id="43d38-165">Erweiterungen können entweder in der Anwendungs- oder der ASP.NET-Konfigurationsdatei (häufigste Auswahl) oder in der Konfigurationsdatei für den Computer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-165">Extensions can be added in the application or ASP.NET configuration file, which is the most common choice, or in the machine configuration file.</span></span>  
  
 <span data-ttu-id="43d38-166">Wenn die Erweiterung zu einem Konfigurationsbereich hinzugefügt wird, kann die Verhaltensweise zu einer Verhaltenskonfiguration hinzugefügt werden, wie in folgendem Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d38-166">When the extension is added to a configuration scope, the behavior can be added to a behavior configuration as it is shown in the following code.</span></span> <span data-ttu-id="43d38-167">Verhaltenskonfigurationen sind wiederverwendbare Elemente, die nach Bedarf auf mehrere Endpunkte angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="43d38-167">Behavior configurations are reusable elements that can be applied to multiple endpoints as required.</span></span> <span data-ttu-id="43d38-168">Da die bestimmte Verhaltensweise, die hier konfiguriert werden soll, <xref:System.ServiceModel.Description.IEndpointBehavior> implementiert, ist sie nur im entsprechenden Konfigurationsbereich in der Konfigurationsdatei gültig.</span><span class="sxs-lookup"><span data-stu-id="43d38-168">Because the particular behavior to be configured here implements <xref:System.ServiceModel.Description.IEndpointBehavior>, it is only valid in the respective configuration section in the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="43d38-169">Das `<schemaValidator>`-Element, das den Nachrichteninspektor konfiguriert, wird von der `SchemaValidationBehaviorExtensionElement`-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43d38-169">The `<schemaValidator>` element that configures the message inspector is backed by the `SchemaValidationBehaviorExtensionElement` class.</span></span> <span data-ttu-id="43d38-170">Die Klasse macht zwei öffentliche boolesche Eigenschaften namens `ValidateRequest` und `ValidateReply` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d38-170">The class exposes two Boolean public properties named `ValidateRequest` and `ValidateReply`.</span></span> <span data-ttu-id="43d38-171">Beide Eigenschaften sind mit einem <xref:System.Configuration.ConfigurationPropertyAttribute> gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="43d38-171">Both of these are marked with a <xref:System.Configuration.ConfigurationPropertyAttribute>.</span></span> <span data-ttu-id="43d38-172">Dieses Attribut bildet die Verknüpfung zwischen den Codeeigenschaften und den XML-Attributen, die im vorangehenden XML-Konfigurationselement sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="43d38-172">This attribute constitutes the link between the code properties and the XML attributes that can be seen on the preceding XML configuration element.</span></span> <span data-ttu-id="43d38-173">Die Klasse verfügt auch über eine Eigenschaft `Schemas`, die zusätzlich mit dem <xref:System.Configuration.ConfigurationCollectionAttribute> gekennzeichnet und vom Typ `SchemaCollection` ist. Diese Eigenschaft ist ebenfalls Teil des Beispiels, ist aber zur besseren Übersichtlichkeit nicht in diesem Dokument enthalten.</span><span class="sxs-lookup"><span data-stu-id="43d38-173">The class also has a property `Schemas` that is additionally marked with the <xref:System.Configuration.ConfigurationCollectionAttribute> and is of the type `SchemaCollection`, which is also part of this sample but omitted from this document for brevity.</span></span> <span data-ttu-id="43d38-174">Diese Eigenschaft unterstützt zusammen mit der Auflistung und der Auflistelementklasse `SchemaConfigElement` das `<schemas>`-Element im vorangehenden Konfigurationsausschnitt und ermöglicht das Hinzufügen einer Schemaauflistung zum Validierungssatz.</span><span class="sxs-lookup"><span data-stu-id="43d38-174">This property along with the collection and the collection element class `SchemaConfigElement` backs the `<schemas>` element in the preceding configuration snippet and allows adding a collection of schemas to the validation set.</span></span>  
  
 <span data-ttu-id="43d38-175">Die überschriebene `CreateBehavior`-Methode wandelt die Konfigurationsdaten in ein Verhaltensobjekt um, wenn die Laufzeit die Konfigurationsdaten beim Erstellen eines Clients oder Endpunkts bewertet.</span><span class="sxs-lookup"><span data-stu-id="43d38-175">The overridden `CreateBehavior` method turns the configuration data into a behavior object when the runtime evaluates the configuration data as it builds a client or an endpoint.</span></span>  
  
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
  
## <a name="adding-message-inspectors-imperatively"></a><span data-ttu-id="43d38-176">Imperatives Hinzufügen von Nachrichteninspektoren</span><span class="sxs-lookup"><span data-stu-id="43d38-176">Adding Message Inspectors Imperatively</span></span>  

 <span data-ttu-id="43d38-177">Außer über Attribute (was aus dem oben genannten Grund in diesem Beispiel nicht unterstützt wird) und die Konfiguration können Verhaltensweisen relativ einfach mithilfe von imperativem Code zu einem Client oder einer Dienstlaufzeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-177">Except through attributes (which is not supported in this sample for the reason cited previously) and configuration, behaviors can quite easily be added to a client and service runtime using imperative code.</span></span> <span data-ttu-id="43d38-178">In diesem Beispiel wird dies in der Clientanwendung durchgeführt, um den Clientnachrichteninspektor zu testen.</span><span class="sxs-lookup"><span data-stu-id="43d38-178">In this sample, this is done in the client application to test the client message inspector.</span></span> <span data-ttu-id="43d38-179">Die `GenericClient`-Klasse wird von <xref:System.ServiceModel.ClientBase%601> abgeleitet, der dem Benutzercode die Endpunktkonfiguration verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="43d38-179">The `GenericClient` class is derived from <xref:System.ServiceModel.ClientBase%601>, which exposes the endpoint configuration to the user code.</span></span> <span data-ttu-id="43d38-180">Bevor der Client implizit geöffnet wird, kann die Endpunktkonfiguration geändert werden, z. B. durch Hinzufügen von Verhaltensweisen, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="43d38-180">Before the client is implicitly opened the endpoint configuration can be changed, for instance by adding behaviors as shown in the following code.</span></span> <span data-ttu-id="43d38-181">Das Hinzufügen von Verhaltensweisen zum Dienst ist in großen Teilen mit der hier dargestellten Clienttechnik vergleichbar und muss vor dem Öffnen des Diensthosts durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43d38-181">Adding the behavior on the service is largely equivalent to the client technique shown here and must be performed before the service host is opened.</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="43d38-182">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="43d38-182">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="43d38-183">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="43d38-183">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="43d38-184">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43d38-184">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="43d38-185">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="43d38-185">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="43d38-186">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="43d38-186">The samples may already be installed on your machine.</span></span> <span data-ttu-id="43d38-187">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="43d38-187">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="43d38-188">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d38-188">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="43d38-189">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43d38-189">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
