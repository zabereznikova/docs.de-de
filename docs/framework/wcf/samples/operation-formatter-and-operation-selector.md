---
title: Vorgangsformatierer und Vorgangsauswahl
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: 9d1bc0afa54f89e064eab3f3e45da60c8d10de38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144278"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="18653-102">Vorgangsformatierer und Vorgangsauswahl</span><span class="sxs-lookup"><span data-stu-id="18653-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="18653-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF)-Erweiterbarkeitspunkte verwendet werden können, um Nachrichtendaten in einem anderen Format als von WCF erwartet zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="18653-103">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="18653-104">Standardmäßig erwarten WCF-Formatters, dass Methodenparameter `soap:body` unter das Element aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="18653-104">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="18653-105">Das Beispiel zeigt, wie ein benutzerdefinierter Vorgangsformatierer implementiert wird, der Parameterdaten aus einer HTTP-GET-Abfragezeichenfolge stattdessen analysiert und mit diesen Daten dann Methoden aufruft.</span><span class="sxs-lookup"><span data-stu-id="18653-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="18653-106">Das Beispiel basiert auf dem [Ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritte `ICalculator` , das den Servicevertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="18653-106">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="18653-107">Es zeigt, wie Add-, Subtract-, Multiply- und Divide-Nachrichten so geändert werden können, dass für Client-an-Server-Anforderungen HTTP GET und für Server-zu-Client-Antworten HTTP POST mit POX-Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18653-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="18653-108">Zu diesem Zweck enthält das Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="18653-108">To do so, the sample provides the following:</span></span>  
  
- <span data-ttu-id="18653-109">`QueryStringFormatter`, der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> und <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> für den Client bzw. den Server implementiert und die Daten in der Abfragezeichenfolge verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="18653-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
- <span data-ttu-id="18653-110">`UriOperationSelector`, die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> auf dem Server implementiert, um die Vorgangsverteilung anhand des Vorgangsnamens in der GET-Anforderung zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="18653-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
- <span data-ttu-id="18653-111">`EnableHttpGetRequestsBehavior`-Endpunktverhalten (und entsprechende Konfiguration), das die erforderliche Vorgangsauswahl der Laufzeit hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="18653-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
- <span data-ttu-id="18653-112">Zeigt, wie ein neuer Vorgangsformatierer in die Laufzeit eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="18653-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
- <span data-ttu-id="18653-113">In diesem Beispiel sind sowohl der Client als auch der Dienst Konsolenanwendungen (.exe).</span><span class="sxs-lookup"><span data-stu-id="18653-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18653-114">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="18653-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="18653-115">Wichtige Konzepte</span><span class="sxs-lookup"><span data-stu-id="18653-115">Key Concepts</span></span>  
 <span data-ttu-id="18653-116">`QueryStringFormatter`- Der Vorgangsforr ist die Komponente in WCF, die für die Konvertierung einer Nachricht in ein Array von Parameterobjekten und ein Array von Parameterobjekten in eine Nachricht verantwortlich ist.</span><span class="sxs-lookup"><span data-stu-id="18653-116">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="18653-117">Auf dem Client erfolgt dies mithilfe der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Schnittstelle, und auf dem Server mit der <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="18653-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="18653-118">Mit diesen Schnittstellen können Benutzer die Anforderungs- und Antwortnachrichten aus der `Serialize`-Methode und der `Deserialize`-Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="18653-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="18653-119">In diesem Beispiel implementiert `QueryStringFormatter` beide Schnittstellen und wird sowohl auf dem Client als auch auf dem Server implementiert.</span><span class="sxs-lookup"><span data-stu-id="18653-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="18653-120">Anforderung:</span><span class="sxs-lookup"><span data-stu-id="18653-120">Request:</span></span>  
  
- <span data-ttu-id="18653-121">Das Beispiel verwendet die <xref:System.ComponentModel.TypeConverter>-Klasse, um Parameterdaten in der Anforderungsnachricht in und aus Zeichenfolgen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="18653-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="18653-122">Wenn ein <xref:System.ComponentModel.TypeConverter> für einen bestimmten Typ nicht verfügbar ist, löst der Beispielformatierer eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="18653-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
- <span data-ttu-id="18653-123">In der `IClientMessageFormatter.SerializeRequest`-Methode auf dem Client erstellt der Formatierer einen URI mit der entsprechenden Empfängeradresse und fügt den Vorgangsnamen als Suffix an.</span><span class="sxs-lookup"><span data-stu-id="18653-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="18653-124">Dieser Name dient dann zum Verteilen zum entsprechenden Vorgang auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="18653-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="18653-125">Dann nimmt er das Array mit Parameterobjekten und serialisiert die Parameterdaten mithilfe von Parameternamen und den von der <xref:System.ComponentModel.TypeConverter>-Klasse konvertierten Werten in die URI-Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="18653-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="18653-126">Die <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Eigenschaft und die <xref:System.ServiceModel.Channels.MessageProperties.Via%2A>-Eigenschaft werden dann auf diesen URI festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18653-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="18653-127">Auf <xref:System.ServiceModel.Channels.MessageProperties> wird über die <xref:System.ServiceModel.Channels.Message.Properties%2A>-Eigenschaft zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="18653-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
- <span data-ttu-id="18653-128">In der `IDispatchMessageFormatter.DeserializeRequest`-Methode auf dem Server ruft der Formatierer den `Via`-URI in den Eigenschaften der eingehenden Anforderungsnachricht ab.</span><span class="sxs-lookup"><span data-stu-id="18653-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="18653-129">Er analysiert die Name-Wert-Paare in der URI-Abfragezeichenfolge in Parameternamen und Werte und füllt mit diesen Parameternamen und Werten das an die Methode übergebene Parameterarray auf.</span><span class="sxs-lookup"><span data-stu-id="18653-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="18653-130">Beachten Sie, dass die Vorgangsverteilung bereits stattgefunden hat; daher wird das Namenssuffix in dieser Methode ignoriert.</span><span class="sxs-lookup"><span data-stu-id="18653-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="18653-131">Antwort:</span><span class="sxs-lookup"><span data-stu-id="18653-131">Response:</span></span>  
  
- <span data-ttu-id="18653-132">In diesem Beispiel wird HTTP GET nur für die Anforderung verwendet.</span><span class="sxs-lookup"><span data-stu-id="18653-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="18653-133">Der Formatierer delegiert das Senden der Antwort an den ursprünglichen Formatierer, von dem XML-Nachrichten generiert worden wären.</span><span class="sxs-lookup"><span data-stu-id="18653-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="18653-134">Eines der Ziele dieses Beispiels besteht darin, zu zeigen, wie solch ein delegierender Formatierer implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="18653-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="18653-135">UriPathSuffixOperationSelector-Klasse</span><span class="sxs-lookup"><span data-stu-id="18653-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="18653-136">Mit der <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Schnittstelle können Benutzer ihre eigene Logik für die Entscheidung implementieren, für welchen Vorgang eine bestimmte Nachricht weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="18653-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="18653-137">In diesem Beispiel muss `UriPathSuffixOperationSelector` zum Auswählen des entsprechenden Vorgangs auf dem Server implementiert werden, da anstelle eines Aktionsheaders in der Nachricht der Vorgangsname in dem HTTP-GET-URI eingetragen wird.</span><span class="sxs-lookup"><span data-stu-id="18653-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="18653-138">Das Beispiel ist so eingerichtet, dass bei Vorgangsnamen die Groß- und Kleinschreibung nicht beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="18653-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="18653-139">Die `SelectOperation`-Methode nimmt die eingehende Nachricht entgegen und schlägt den `Via`-URI in deren Nachrichteneigenschaften nach.</span><span class="sxs-lookup"><span data-stu-id="18653-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="18653-140">Sie extrahiert das Vorgangsnamenssuffix aus dem URI, schlägt in einer internen Tabelle den Namen des Vorgangs nach, an den die Nachricht weitergeleitet werden soll, und gibt diesen Vorgangsnamen dann zurück.</span><span class="sxs-lookup"><span data-stu-id="18653-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="18653-141">EnableHttpGetRequestsBehavior-Klasse</span><span class="sxs-lookup"><span data-stu-id="18653-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="18653-142">Die `UriPathSuffixOperationSelector`-Komponente kann programmgesteuert oder über ein Endpunktverhalten eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="18653-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="18653-143">Das Beispiel implementiert das `EnableHttpGetRequestsBehavior`-Verhalten, das in der Anwendungskonfigurationsdatei des Diensts angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="18653-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="18653-144">Auf dem Server:</span><span class="sxs-lookup"><span data-stu-id="18653-144">On the server:</span></span>  
  
 <span data-ttu-id="18653-145">Der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> wird auf die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Implementierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18653-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="18653-146">Standardmäßig verwendet WCF einen genau übereinstimmenden Adressfilter.</span><span class="sxs-lookup"><span data-stu-id="18653-146">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="18653-147">Der URI in der eingehenden Nachricht enthält ein Vorgangsnamenssuffix, gefolgt von einer Abfragezeichenfolge, die Parameterdaten enthält. Daher ändert das Endpunktverhalten auch den Adressfilter in einen Präfixübereinstimmungsfilter.</span><span class="sxs-lookup"><span data-stu-id="18653-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="18653-148">Für diesen Zweck<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> wird der WCF verwendet.</span><span class="sxs-lookup"><span data-stu-id="18653-148">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="18653-149">Installieren von Vorgangsformatierern</span><span class="sxs-lookup"><span data-stu-id="18653-149">Installing operation formatters</span></span>  
 <span data-ttu-id="18653-150">Vorgangsverhaltensweisen, die Formatierer angeben, sind eindeutig.</span><span class="sxs-lookup"><span data-stu-id="18653-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="18653-151">Standardmäßig wird ein solches Verhalten für jeden Vorgang stets zum Erstellen des erforderlichen Vorgangsformatierers implementiert.</span><span class="sxs-lookup"><span data-stu-id="18653-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="18653-152">Auch wenn diese Verhaltensweisen wie noch ein weiteres Vorgangsverhalten aussehen mögen, sind sie nicht durch andere Attribute zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="18653-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="18653-153">Um ein Ersetzungsverhalten zu installieren, muss die Implementierung nach bestimmten Formatiererverhalten suchen, die standardmäßig vom WCF-Typlader installiert werden, und entweder ersetzen oder ein kompatibles Verhalten hinzufügen, das nach dem Standardverhalten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18653-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="18653-154">Diese Vorgangsformatiererverhalten können programmgesteuert vor dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> eingerichtet werden, oder indem man ein Vorgangsverhalten angibt, das nach dem Standardverhalten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18653-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="18653-155">Es kann jedoch nicht einfach wie ein Endpunktverhalten (und damit per Konfiguration) eingerichtet werden, da das Verhaltensmodell das Ersetzen eines Verhaltens durch ein anderes oder sonstiges Ändern der Beschreibungsstruktur nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="18653-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="18653-156">Auf dem Client:</span><span class="sxs-lookup"><span data-stu-id="18653-156">On the client:</span></span>  
  
 <span data-ttu-id="18653-157">Die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Implementierung muss implementiert werden, damit sie die Anforderungen in HTTP-GET-Anforderungen konvertieren und für Antworten an den ursprünglichen Formatierer delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="18653-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="18653-158">Dies erfolgt durch Aufrufen der `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`-Hilfsmethode.</span><span class="sxs-lookup"><span data-stu-id="18653-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="18653-159">Es muss vor dem Aufruf von `CreateChannel` durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18653-159">This must be done before calling `CreateChannel`.</span></span>  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="18653-160">Auf dem Server:</span><span class="sxs-lookup"><span data-stu-id="18653-160">On the server:</span></span>  
  
- <span data-ttu-id="18653-161">Die <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle muss implementiert werden, damit sie HTTP-GET-Anforderungen lesen und zum Schreiben von Antworten an den ursprünglichen Formatierer delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="18653-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="18653-162">Dies erfolgt durch Aufrufen derselben `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`-Hilfsmethode wie beim Client (siehe vorheriges Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="18653-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
- <span data-ttu-id="18653-163">Das muss erfolgen, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="18653-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="18653-164">In diesem Beispiel wird gezeigt, wie der Formatierer manuell geändert wird, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="18653-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="18653-165">Dasselbe lässt sich auch erreichen, indem man eine Klasse von <xref:System.ServiceModel.ServiceHost> ableitet, die vor dem Öffnen `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` aufruft (Beispiel dazu finden Sie in der Hostingdokumentation).</span><span class="sxs-lookup"><span data-stu-id="18653-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="18653-166">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="18653-166">User experience</span></span>  
 <span data-ttu-id="18653-167">Auf dem Server:</span><span class="sxs-lookup"><span data-stu-id="18653-167">On the server:</span></span>  
  
- <span data-ttu-id="18653-168">Die `ICalculator`-Serverimplementierung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="18653-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
- <span data-ttu-id="18653-169">Die „App.config“-Datei für den Dienst muss eine benutzerdefinierte POX-Bindung verwenden, die für das `messageVersion`-Attribut des `textMessageEncoding`-Elements `None` festlegt.</span><span class="sxs-lookup"><span data-stu-id="18653-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="18653-170">Außerdem muss die App.config-Datei für den Dienst das benutzerdefinierte `EnableHttpGetRequestsBehavior` angeben, indem sie es dem Abschnitt mit den Verhaltenserweiterungen hinzufügt und verwendet.</span><span class="sxs-lookup"><span data-stu-id="18653-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- <span data-ttu-id="18653-171">Fügen Sie Vorgangsformatierer vor dem Aufrufen von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> hinzu.</span><span class="sxs-lookup"><span data-stu-id="18653-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="18653-172">Auf dem Client:</span><span class="sxs-lookup"><span data-stu-id="18653-172">On the client:</span></span>  
  
- <span data-ttu-id="18653-173">Die Clientimplementierung muss nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="18653-173">The client implementation does not need to change.</span></span>  
  
- <span data-ttu-id="18653-174">Die Datei „App.config“ für den Client muss eine benutzerdefinierte POX-Bindung verwenden, die für das `messageVersion`-Attribut des `textMessageEncoding`-Elements `None` festlegt.</span><span class="sxs-lookup"><span data-stu-id="18653-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="18653-175">Ein Unterschied zum Dienst besteht darin, dass der Client die manuelle Adressierung aktivieren muss, damit die Empfängeradresse der ausgehenden Nachricht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="18653-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="18653-176">Die App.config für den Client muss dasselbe benutzerdefinierte `EnableHttpGetRequestsBehavior` wie der Server angeben.</span><span class="sxs-lookup"><span data-stu-id="18653-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
- <span data-ttu-id="18653-177">Fügen Sie Vorgangsformatierer vor dem Aufrufen von <xref:System.ServiceModel.ChannelFactory%601.CreateChannel> hinzu.</span><span class="sxs-lookup"><span data-stu-id="18653-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="18653-178">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="18653-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="18653-179">Alle vier Vorgänge (Add, Subtract, Multiply und Divide) müssen erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="18653-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="18653-180">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="18653-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="18653-181">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="18653-181">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="18653-182">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="18653-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="18653-183">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="18653-183">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="18653-184">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="18653-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="18653-185">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="18653-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="18653-186">Um die Lösung zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="18653-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="18653-187">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="18653-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
