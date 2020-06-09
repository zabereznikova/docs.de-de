---
title: Interoperabilität mit POX-Anwendungen
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: 64a6d850a32b14bc60cd43466e04b53a7a39be81
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579266"
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="d23cc-102">Interoperabilität mit POX-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d23cc-102">Interoperability with POX applications</span></span>

<span data-ttu-id="d23cc-103">"Plain Old XML" (POX)-Anwendungen kommunizieren durch Austauschen von unformatierten HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einem SOAP-Umschlag eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="d23cc-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> <span data-ttu-id="d23cc-104">Windows Communication Foundation (WCF) kann sowohl Dienste als auch Clients bereitstellen, die POX-Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="d23cc-104">Windows Communication Foundation (WCF) can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="d23cc-105">Auf dem-Dienst kann WCF verwendet werden, um Dienste zu implementieren, die Endpunkte für Clients verfügbar machen, z. b. Webbrowser und Skriptsprachen, die POX-Nachrichten senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="d23cc-105">On the service, WCF can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="d23cc-106">Auf dem Client kann das WCF-Programmiermodell verwendet werden, um Clients zu implementieren, die mit POX-basierten Diensten kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d23cc-106">On the client, the WCF programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d23cc-107">Dieses Dokument wurde ursprünglich für das .NET Framework 3,0 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d23cc-107">This document was originally written for the .NET Framework 3.0.</span></span>  <span data-ttu-id="d23cc-108">.NET Framework 3,5 verfügt über eine integrierte Unterstützung für die Arbeit mit POX-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d23cc-108">.NET Framework 3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="d23cc-109">Weitere Informationen finden Sie unter [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="d23cc-109">For more information about see [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md).</span></span>
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="d23cc-110">POX-Programmierung mit WCF</span><span class="sxs-lookup"><span data-stu-id="d23cc-110">POX programming with WCF</span></span>

<span data-ttu-id="d23cc-111">WCF-Dienste, die mithilfe von POX-Nachrichten über HTTP kommunizieren, verwenden [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d23cc-111">WCF services that communicate over HTTP using POX messages use a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

<span data-ttu-id="d23cc-112">Diese benutzerspezifische Bindung enthält zwei Elemente:</span><span class="sxs-lookup"><span data-stu-id="d23cc-112">This custom binding contains two elements:</span></span>

- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md)

<span data-ttu-id="d23cc-113">Der standardmäßige WCF-Text Nachrichten Encoder ist speziell für die Verwendung des- <xref:System.ServiceModel.Channels.MessageVersion.None%2A> Werts konfiguriert, mit dem XML-Nachrichten Nutzlasten verarbeitet werden können, die nicht in einem SOAP-Umschlag umschließt werden.</span><span class="sxs-lookup"><span data-stu-id="d23cc-113">The standard WCF Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>

<span data-ttu-id="d23cc-114">WCF-Clients, die mithilfe von POX-Nachrichten über HTTP kommunizieren, verwenden eine ähnliche Bindung (in folgendem imperativen Code gezeigt).</span><span class="sxs-lookup"><span data-stu-id="d23cc-114">WCF clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

<span data-ttu-id="d23cc-115">Da POX-Clients die URIs, an die Nachrichten gesendet werden, explizit angeben müssen, muss das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> in der Regel so konfiguriert werden, dass eine manuelle Adressierung möglich ist. Hierfür wird im Element die <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A>-Eigenschaft auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d23cc-115">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="d23cc-116">Auf diese Weise kann die Adresse für die Nachricht explizit über Anwendungscode angegeben werden, und es muss nicht jedes Mal, wenn eine Anwendung eine Nachricht an einen anderen HTTP-URI sendet, eine neue <xref:System.ServiceModel.ChannelFactory> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d23cc-116">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>

<span data-ttu-id="d23cc-117">Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren.</span><span class="sxs-lookup"><span data-stu-id="d23cc-117">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="d23cc-118">HTTP-spezifische Protokollinformationen, wie z. b. HTTP-Header und Statuscodes, werden im WCF-Programmiermodell über zwei Klassen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d23cc-118">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the WCF programming model through two classes:</span></span>

- <span data-ttu-id="d23cc-119"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.</span><span class="sxs-lookup"><span data-stu-id="d23cc-119"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>

- <span data-ttu-id="d23cc-120"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="d23cc-120"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>
  
<span data-ttu-id="d23cc-121">Im folgenden Codebeispiel wird gezeigt, wie eine HTTP GET-Anforderungs Nachricht erstellt wird, die an adressiert wird `http://localhost:8100/customers` .</span><span class="sxs-lookup"><span data-stu-id="d23cc-121">The following code example shows how to create an HTTP GET request message that is addressed to `http://localhost:8100/customers`.</span></span>

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

<span data-ttu-id="d23cc-122">Zuerst wird die leere Anforderung <xref:System.ServiceModel.Channels.Message> durch Aufruf von <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> erstellt.</span><span class="sxs-lookup"><span data-stu-id="d23cc-122">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="d23cc-123">Der <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Parameter zeigt an, dass kein SOAP-Envelope erforderlich ist. Der <xref:System.String.Empty>-Parameter wird als Aktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="d23cc-123">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="d23cc-124">Anschließend wird die Adresse für die Anforderungsnachricht angegeben, indem im <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Header der gewünschte URI festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d23cc-124">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="d23cc-125">Dann wird eine <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> erstellt. <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> wird auf die HTTP GET-Methode festgelegt, und für <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> wird der Wert `true` festgelegt, um anzuzeigen, dass keine Daten im Text der ausgehenden HTTP-Anforderungsnachricht gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d23cc-125">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="d23cc-126">Anschließend wird noch die Anforderungseigenschaft zur <xref:System.ServiceModel.Channels.Message.Properties%2A>-Auflistung der Anforderungsnachricht hinzugefügt, damit gesteuert werden kann, auf welche Weise der HTTP-Transport die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="d23cc-126">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="d23cc-127">Die Nachricht kann nun über eine geeignete Instanz von <xref:System.ServiceModel.Channels.IRequestChannel> gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d23cc-127">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>

<span data-ttu-id="d23cc-128">Auf ähnliche Weise kann beim Dienst die <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> aus der eingehenden Nachricht extrahiert und eine Antwort erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d23cc-128">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
