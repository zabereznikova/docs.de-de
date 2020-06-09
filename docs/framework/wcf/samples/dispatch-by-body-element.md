---
title: Verteilen nach Textelement
ms.date: 03/30/2017
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
ms.openlocfilehash: 19913cdaa47d766f62a313e216a653ac69633a99
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594698"
---
# <a name="dispatch-by-body-element"></a><span data-ttu-id="e174b-102">Verteilen nach Textelement</span><span class="sxs-lookup"><span data-stu-id="e174b-102">Dispatch by Body Element</span></span>
<span data-ttu-id="e174b-103">Dieses Beispiel veranschaulicht, wie ein alternativer Algorithmus zum Zuweisen eingehender Nachrichten zu Vorgängen implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e174b-103">This sample demonstrates how to implement an alternate algorithm for assigning incoming messages to operations.</span></span>  
  
 <span data-ttu-id="e174b-104">Standardmäßig wählt der Dienstmodellverteiler die passende Verarbeitungsmethode für eine eingehende Nachricht auf der Grundlage des WS-Adressierungsaktionsheaders der Nachricht aus bzw. auf der Grundlage der entsprechenden Informationen in der HTTP SOAP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="e174b-104">By default, the service model dispatcher selects the appropriate handling method for an incoming message based on the message's WS-Addressing "Action" header or the equivalent information in the HTTP SOAP request.</span></span>  
  
 <span data-ttu-id="e174b-105">Einige SOAP 1.1-Webdienststapel, die nicht den WS-I Basic Profile 1.1-Richtlinien folgen, verteilen Nachrichten nicht auf der Grundlage des Aktions-URIs, sondern auf der Grundlage des qualifizierten XML-Namens des ersten Elements innerhalb des SOAP-Nachrichtentexts.</span><span class="sxs-lookup"><span data-stu-id="e174b-105">Some SOAP 1.1 Web services stacks that do not follow the WS-I Basic Profile 1.1 guidelines do not dispatch messages based on the Action URI, but rather based on the XML qualified name of the first element inside the SOAP body.</span></span> <span data-ttu-id="e174b-106">Gleichzeitig kann die Clientseite dieser Stapel Nachrichten mit einem leeren oder beliebigen HTTP SoapAction-Header senden, da dies mit den SOAP 1.1-Spezifikationen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e174b-106">Likewise, the client side of these stacks might send messages with an empty or arbitrary HTTP SoapAction header, which was permitted by the SOAP 1.1 specification.</span></span>  
  
 <span data-ttu-id="e174b-107">Um das Verfahren zu ändern, mit dem Nachrichten an Methoden verteilt werden, implementiert das Beispiel die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Erweiterbarkeitsschnittstelle auf dem `DispatchByBodyElementOperationSelector`.</span><span class="sxs-lookup"><span data-stu-id="e174b-107">To change the way messages are dispatched to methods, the sample implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> extensibility interface on the `DispatchByBodyElementOperationSelector`.</span></span> <span data-ttu-id="e174b-108">Diese Klasse wählt Operationen auf der Grundlage des ersten Elements des Nachrichtentexts aus.</span><span class="sxs-lookup"><span data-stu-id="e174b-108">This class selects operations based on the first element of the message body.</span></span>  
  
 <span data-ttu-id="e174b-109">Der Konstruktor erwartet ein mit Paaren von `XmlQualifiedName` und Zeichenketten gefülltes Wörterbuch, dabei geben die qualifizierten Namen den Namen des ersten untergeordneten Elements des SOAP-Nachrichtentexts an, und die Zeichenketten geben den entsprechenden Vorgangsnamen an.</span><span class="sxs-lookup"><span data-stu-id="e174b-109">The class constructor expects a dictionary populated with pairs of `XmlQualifiedName` and strings, whereby the qualified names indicate the name of the first child of the SOAP body and the strings indicate the matching operation name.</span></span> <span data-ttu-id="e174b-110">Der `defaultOperationName` ist der Name des Vorgangs, der alle Nachrichten empfängt, die nicht mit diesem Wörterbuch abgeglichen werden können.</span><span class="sxs-lookup"><span data-stu-id="e174b-110">The `defaultOperationName` is the name of the operation that receives all messages that cannot be matched against this dictionary:</span></span>  
  
```csharp
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
}
```  
  
 <span data-ttu-id="e174b-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Implementierungen sind sehr einfach zu erstellen, da die Schnittstelle nur eine Methode besitzt: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span><span class="sxs-lookup"><span data-stu-id="e174b-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementations are very straightforward to build as there is only one method on the interface: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span></span> <span data-ttu-id="e174b-112">Die Aufgabe dieser Methode ist, eingehende Nachrichten zu überprüfen und eine Zeichenkette zurückzugeben, die dem Namen einer Methode auf dem Dienstvertrag für den aktuellen Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="e174b-112">The job of this method is to inspect an incoming message and to return a string that equals the name of a method on the service contract for the current endpoint.</span></span>  
  
 <span data-ttu-id="e174b-113">In diesem Beispiel ruft die Vorgangsauswahl mithilfe von <xref:System.Xml.XmlDictionaryReader> einen <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> für den Text der eingehenden Nachricht ab.</span><span class="sxs-lookup"><span data-stu-id="e174b-113">In this sample, the operation selector acquires an <xref:System.Xml.XmlDictionaryReader> for the incoming message's body using <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span></span> <span data-ttu-id="e174b-114">Diese Methode setzt den Leser bereits auf das erste untergeordnete Element des Nachrichtentexts, sodass es ausreicht, den aktuellen Namen des Elements und den Namespace-URI abzurufen und diese zu einem `XmlQualifiedName` zu kombinieren, der dann für die Suche nach dem entsprechenden Vorgang aus dem Wörterbuch der Vorgangsauswahl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e174b-114">This method already positions the reader on the first child of the message's body so that it is sufficient to get the current element's name and namespace URI and combine them into an `XmlQualifiedName` that is then used for looking up the corresponding operation from the dictionary held by the operation selector.</span></span>  
  
```csharp
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 <span data-ttu-id="e174b-115">Wenn mit <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> oder einer der anderen Methoden, die Zugriff auf den Nachrichtentext haben, auf den Nachrichtentext zugegriffen wird, wird die Nachricht als "gelesen" markiert, was bedeutet, dass die Nachricht für weitere Verarbeitung nicht mehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e174b-115">Accessing the message body with <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> or any of the other methods that provide access to the message's body content causes the message to be marked as "read", which means that the message is invalid for any further processing.</span></span> <span data-ttu-id="e174b-116">Daher erstellt die Vorgangsauswahl mithilfe der im folgenden Code dargestellten Methode eine Kopie der eingehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e174b-116">Therefore, the operation selector creates a copy of the incoming message with the method shown in the following code.</span></span> <span data-ttu-id="e174b-117">Da die Position des Lesers während der Überprüfung nicht geändert wurde, kann auf diesen durch die neu erstellte Nachricht verwiesen werden, in die auch die Nachrichteneigenschaften und die Nachrichtenheader kopiert werden, sodass eine exakte Kopie der ursprünglichen Nachricht entsteht.</span><span class="sxs-lookup"><span data-stu-id="e174b-117">Because the reader's position has not been changed during the inspection, it can be referenced by the newly created message to which the message properties and the message headers are also copied, which results in an exact clone of the original message:</span></span>  
  
```csharp
private Message CreateMessageCopy(Message message,
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
```  
  
## <a name="adding-an-operation-selector-to-a-service"></a><span data-ttu-id="e174b-118">Hinzufügen einer Vorgangsauswahl zu einem Dienst</span><span class="sxs-lookup"><span data-stu-id="e174b-118">Adding an Operation Selector to a Service</span></span>  
 <span data-ttu-id="e174b-119">Diensdispatchselektoren sind Erweiterungen des Windows Communication Foundation (WCF)-Verteilers.</span><span class="sxs-lookup"><span data-stu-id="e174b-119">Service dispatch operation selectors are extensions to the Windows Communication Foundation (WCF) dispatcher.</span></span> <span data-ttu-id="e174b-120">Für die Auswahl von Methoden auf dem Rückrufkanal von Duplexverträgen stehen auch Clientvorgangsauswahlen zur Verfügung, die ähnlich funktionieren wie die hier erläuterten Verteilungsvorgangsauswahlen, die jedoch nicht explizit in diesem Beispiel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e174b-120">For selecting methods on the callback channel of duplex contracts, there are also client operation selectors, which work very much like the dispatch operation selectors described here, but which are not explicitly covered in this sample.</span></span>  
  
 <span data-ttu-id="e174b-121">Wie die meisten Dienstmodellerweiterungen werden auch Verteilungsvorgangsauwahlen dem Verteiler mithilfe von Verhaltensweisen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e174b-121">Like most service model extensions, dispatch operation selectors are added to the dispatcher using behaviors.</span></span> <span data-ttu-id="e174b-122">Ein *Verhalten* ist ein Konfigurationsobjekt, das entweder mindestens eine Erweiterung zur Dispatchlaufzeit (oder zur Client Laufzeit) hinzufügt oder andernfalls seine Einstellungen ändert.</span><span class="sxs-lookup"><span data-stu-id="e174b-122">A *behavior* is a configuration object, which either adds one or more extensions to the dispatch runtime (or to the client runtime) or otherwise changes its settings.</span></span>  
  
 <span data-ttu-id="e174b-123">Da Vorgangsauswahlen Vertragsbereiche besitzen, ist das entsprechende Verhalten, das hier implementiert wird, <xref:System.ServiceModel.Description.IContractBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e174b-123">Because operation selectors have contract scope, the appropriate behavior to implement here is the <xref:System.ServiceModel.Description.IContractBehavior>.</span></span> <span data-ttu-id="e174b-124">Da die Schnittstelle auf einer von <xref:System.Attribute> abgeleiteten Klasse implementiert wird, wie im folgenden Code dargestellt, kann das Verhalten deklarativ zu jedem Dienstvertrag hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e174b-124">Because the interface is implemented on a <xref:System.Attribute> derived class as shown in the following code, the behavior can be declaratively added to any service contract.</span></span> <span data-ttu-id="e174b-125">Immer wenn ein <xref:System.ServiceModel.ServiceHost> geöffnet und die Verteilungslaufzeit erstellt wird, werden alle Verhalten, die als Attribute auf Verträgen, Vorgängen und Dienstimplementierungen oder als Element in der Dienstkonfiguration gefunden werden, automatisch hinzugefügt und der Reihe nach auf Erweiterungen oder Änderungen der Standardkonfiguration abgefragt.</span><span class="sxs-lookup"><span data-stu-id="e174b-125">Whenever a <xref:System.ServiceModel.ServiceHost> is opened and the dispatch runtime is built, all behaviors found either as attributes on contracts, operations, and service implementations or as element in the service configuration are automatically added and subsequently asked to contribute extensions or modify the default configuration.</span></span>  
  
 <span data-ttu-id="e174b-126">Der Kürze wegen zeigt der folgende Codeauszug nur die Implementierung der Methode <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, die die Konfigurationsänderung für den Verteiler in diesem Beispiel bewirkt.</span><span class="sxs-lookup"><span data-stu-id="e174b-126">For brevity, the following code excerpt only shows the implementation of the method <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, which effects the configuration changes for the dispatcher in this sample.</span></span> <span data-ttu-id="e174b-127">Die anderen Methoden werden nicht dargestellt, da sie zum Aufrufer zurückkehren, ohne eine Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e174b-127">The other methods are not shown because they return to the caller without doing any work.</span></span>  
  
```csharp
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 <span data-ttu-id="e174b-128">Zuerst richtet die <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>-Implementierung das Suchwörterbuch für die Vorgangsauswahl ein, indem die <xref:System.ServiceModel.Description.OperationDescription>-Elemente in der <xref:System.ServiceModel.Description.ContractDescription> der Dienstendpunkte durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="e174b-128">First, the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> implementation sets up the lookup dictionary for the operation selector by iterating over the <xref:System.ServiceModel.Description.OperationDescription> elements in the service endpoint's <xref:System.ServiceModel.Description.ContractDescription>.</span></span> <span data-ttu-id="e174b-129">Anschließend wird jede Vorgangsauswahl auf das Vorhandensein des `DispatchBodyElementAttribute`-Verhaltens untersucht, einer Implementierung von<xref:System.ServiceModel.Description.IOperationBehavior>, das ebenfalls im Beispiel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e174b-129">Then, each operation description is inspected for the presence of the `DispatchBodyElementAttribute` behavior, an implementation of <xref:System.ServiceModel.Description.IOperationBehavior> that is also defined in this sample.</span></span> <span data-ttu-id="e174b-130">Diese Klasse ist zwar ebenfalls ein Verhalten, sie ist jedoch passiv und bewirkt keine aktiven Konfigurationsänderungen an der Verteilungslaufzeit.</span><span class="sxs-lookup"><span data-stu-id="e174b-130">While this class is also a behavior, it is passive and does not actively contribute any configuration changes to the dispatch runtime.</span></span> <span data-ttu-id="e174b-131">All ihre Methoden kehren zum Aufrufer zurück, ohne eine Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e174b-131">All of its methods return to the caller without taking any actions.</span></span> <span data-ttu-id="e174b-132">Das Vorgangsverhalten ist nur vorhanden, damit die für den neuen Verteilungsmechanismus erforderlichen Metadaten  d.h. der qualifizierte Name des Textelements, bei dessen Auftreten ein Vorgang ausgewählt wird  den entsprechenden Vorgängen zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="e174b-132">The operation behavior only exists so that the metadata required for the new dispatch mechanism, namely the qualified name of the body element on whose occurrence an operation is selected, can be associated with the respective operations.</span></span>  
  
 <span data-ttu-id="e174b-133">Wenn ein solches Verhalten gefunden wird, werden dem Wörterbuch ein aus dem qualifizierten XML-Namen gebildetes Wertepaar (`QName`-Eigenschaft) und der Vorgangsname (`Name`-Eigenschaft) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e174b-133">If such a behavior is found, a value pair created from the XML qualified name (`QName` property) and the operation name (`Name` property) is added to the dictionary.</span></span>  
  
 <span data-ttu-id="e174b-134">Nachdem das Wörterbuch gefüllt wurde, wird eine neue `DispatchByBodyElementOperationSelector` mit diesen Informationen erstellt und als Vorgangsauswahl der Verteilungslaufzeit festgelegt:</span><span class="sxs-lookup"><span data-stu-id="e174b-134">Once the dictionary is populated, a new `DispatchByBodyElementOperationSelector` is constructed with this information and set as the operation selector of the dispatch runtime:</span></span>  
  
```csharp
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## <a name="implementing-the-service"></a><span data-ttu-id="e174b-135">Implementieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="e174b-135">Implementing the Service</span></span>  
 <span data-ttu-id="e174b-136">Das in diesem Beispiel implementierte Verhalten wirkt sich unmittelbar darauf aus, wie übermittelte Nachrichten interpretiert und verteilt werden. Dies ist eine Funktion des Dienstvertrags.</span><span class="sxs-lookup"><span data-stu-id="e174b-136">The behavior implemented in this sample directly affects how messages from the wire are interpreted and dispatched, which is a function of the service contract.</span></span> <span data-ttu-id="e174b-137">Daher sollte das Verhalten auf Dienstvertragsebene in jeder Dienstimplementierung deklariert werden, die das Verhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="e174b-137">Consequently, the behavior should be declared on the service contract level in any service implementation that chooses to use it.</span></span>  
  
 <span data-ttu-id="e174b-138">Der Beispiel Projekt Dienst wendet das `DispatchByBodyElementBehaviorAttribute` Vertrags Verhalten auf den `IDispatchedByBody` Dienstvertrag an und beschriftet jeden der beiden Vorgänge `OperationForBodyA()` und `OperationForBodyB()` mit einem `DispatchBodyElementAttribute` Vorgangs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e174b-138">The sample project service applies the `DispatchByBodyElementBehaviorAttribute` contract behavior to the `IDispatchedByBody` service contract and labels each of the two operations `OperationForBodyA()` and `OperationForBodyB()` with a `DispatchBodyElementAttribute` operation behavior.</span></span> <span data-ttu-id="e174b-139">Wenn ein Diensthost für einen Dienst, der diesen Vertrag implementiert, geöffnet wird, werden diese Metadaten von dem Verteilungsersteller wie zuvor erläutert ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e174b-139">When a service host for a service that implements this contract is opened, this metadata is picked up by the dispatcher builder as previously described.</span></span>  
  
 <span data-ttu-id="e174b-140">Da die Vorgangsauswahl die Verteilung nur auf der Grundlage des Nachrichtentexts ausführt und die "Aktion" ignoriert, muss der Laufzeit mitgeteilt werden, nicht die Aktionsheader in den zurückgegebenen Antworten zu überprüfen. Weisen Sie dazu der `ReplyAction`-Eigenschaft von <xref:System.ServiceModel.OperationContractAttribute> den Platzhalter "\*" zu.</span><span class="sxs-lookup"><span data-stu-id="e174b-140">Because the operation selector dispatches solely based on the message body element and ignores the "Action", it is required to tell the runtime not to check the "Action" header on the returned replies by assigning the wildcard "\*" to the `ReplyAction` property of <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="e174b-141">Außerdem ist ein Standard Vorgang erforderlich, bei dem die Eigenschaft "action" auf den Platzhalter "" festgelegt ist \* .</span><span class="sxs-lookup"><span data-stu-id="e174b-141">Furthermore, it is required to have a default operation that has the "Action" property set to the wildcard "\*".</span></span> <span data-ttu-id="e174b-142">Der Standardvorgang empfängt alle Nachrichten, die nicht verteilt werden können und kein `DispatchBodyElementAttribute` besitzen:</span><span class="sxs-lookup"><span data-stu-id="e174b-142">The default operation receives all messages which cannot be dispatched and does not have a `DispatchBodyElementAttribute`:</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 <span data-ttu-id="e174b-143">Die Beispieldienstimplementierung ist einfach.</span><span class="sxs-lookup"><span data-stu-id="e174b-143">The sample service implementation is straightforward.</span></span> <span data-ttu-id="e174b-144">Jede Methode schließt die empfangene Nachricht in eine Antwortnachricht ein und sendet sie zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="e174b-144">Every method wraps the received message into a reply message and echoes it back to the client.</span></span>  
  
## <a name="running-and-building-the-sample"></a><span data-ttu-id="e174b-145">Erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="e174b-145">Running and Building the Sample</span></span>  
 <span data-ttu-id="e174b-146">Wenn Sie das Beispiel ausführen, wird der Textinhalt der Vorgangsantworten im Clientkonsolenfenster angezeigt, ähnlich der folgenden (formatierten) Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e174b-146">When you run the sample, the body content of the operation responses are displayed in the client console window similar to the following (formatted) output.</span></span>  
  
 <span data-ttu-id="e174b-147">Der Client sendet drei Nachrichten an den Dienst, dessen Textinhaltselemente entsprechend mit `bodyA`, `bodyB` und `bodyX` benannt werden.</span><span class="sxs-lookup"><span data-stu-id="e174b-147">The client sends three messages to the service whose body content element is named `bodyA`, `bodyB`, and `bodyX`, respectively.</span></span> <span data-ttu-id="e174b-148">Wie aus der vorstehenden Beschreibung und dem dargestellten Dienstvertrag hervorgeht, wird die eingehende Nachricht mit dem `bodyA`-Element an die `OperationForBodyA()`-Methode weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e174b-148">As can be deferred from the previous description and the service contract shown, the incoming message with the `bodyA` element is dispatched to the `OperationForBodyA()` method.</span></span> <span data-ttu-id="e174b-149">Da kein explizites Verteilungsziel für die Nachricht mit dem Textelement `bodyX` vorhanden ist, wird die Nachricht an den `DefaultOperation()` weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="e174b-149">Because there is no explicit dispatch target for the message with the `bodyX` body element, the message is dispatched to the `DefaultOperation()`.</span></span> <span data-ttu-id="e174b-150">Jeder der Dienstvorgänge schließt den empfangenen Nachrichtentext in ein Element ein, das spezifisch für die Methode ist, und sendet ihn zurück. Dies dient dazu, dass sich Eingangs- und Ausgangsnachricht in diesem Beispiel eindeutig entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e174b-150">Each of the service operations wraps the received message body into an element specific to the method and returns it, which is done to correlate input and output messages clearly for this sample:</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e174b-151">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e174b-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e174b-152">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e174b-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e174b-153">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e174b-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e174b-154">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e174b-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e174b-155">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e174b-155">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e174b-156">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e174b-156">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e174b-157">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e174b-157">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e174b-158">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e174b-158">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
