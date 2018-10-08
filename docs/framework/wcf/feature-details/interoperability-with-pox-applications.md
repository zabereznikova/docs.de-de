---
title: Interoperabilität mit POX-Anwendungen
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850080"
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="dd3c2-102">Interoperabilität mit POX-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="dd3c2-102">Interoperability with POX applications</span></span>

<span data-ttu-id="dd3c2-103">"Plain Old XML" (POX)-Anwendungen kommunizieren, indem Sie den Austausch von unformatierte HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einem SOAP-Umschlag eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> <span data-ttu-id="dd3c2-104">Windows Communication Foundation (WCF) bieten, die Dienste und Clients, die POX-Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-104">Windows Communication Foundation (WCF) can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="dd3c2-105">Für den Dienst kann WCF verwendet werden, Implementieren von Diensten, die Endpunkte für Clients, z. B. Webbrowser verfügbar zu machen und Skriptsprachen, mit die POX-Nachrichten senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-105">On the service, WCF can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="dd3c2-106">Auf dem Client kann die WCF-Programmiermodell verwendet werden, zur Implementierung von Clients, die mit POX-basierten Diensten kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-106">On the client, the WCF programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd3c2-107">Dieses Dokument wurde ursprünglich für [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&#160;3.0 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]<span data-ttu-id="dd3c2-108">&amp;#160;3.5 verfügt über intergrierte Unterstützung für die Arbeit mit POX-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-108"> 3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="dd3c2-109">Weitere Informationen finden Sie unter [WCF-HTTP-Webprogrammierungsmodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="dd3c2-109">For more information about see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="dd3c2-110">POX-Programmierung mit WCF</span><span class="sxs-lookup"><span data-stu-id="dd3c2-110">POX programming with WCF</span></span>

<span data-ttu-id="dd3c2-111">WCF-Dienste, die Kommunikation über HTTP unter Verwendung von POX-Nachrichten verwenden eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="dd3c2-111">WCF services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

<span data-ttu-id="dd3c2-112">Diese benutzerspezifische Bindung enthält zwei Elemente:</span><span class="sxs-lookup"><span data-stu-id="dd3c2-112">This custom binding contains two elements:</span></span>

- [<span data-ttu-id="dd3c2-113">\<HttpTransport ></span><span class="sxs-lookup"><span data-stu-id="dd3c2-113">\<httpTransport></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [<span data-ttu-id="dd3c2-114">\<TextMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="dd3c2-114">\<textMessageEncoding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

<span data-ttu-id="dd3c2-115">Der Standard, speziell für die Verwendung konfiguriert Textnachrichtenencoder WCF, die <xref:System.ServiceModel.Channels.MessageVersion.None%2A> -Wert, der kann zum Verarbeiten von XML-Nutzlasten für Nachrichten, die nicht eingetroffen in einen SOAP-Umschlag eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-115">The standard WCF Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>

<span data-ttu-id="dd3c2-116">WCF-Clients, die über HTTP unter Verwendung von POX-Nachrichten kommunizieren, verwenden eine ähnliche Bindung (siehe folgenden imperativen Code).</span><span class="sxs-lookup"><span data-stu-id="dd3c2-116">WCF clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>

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

<span data-ttu-id="dd3c2-117">Da POX-Clients die URIs, an die Nachrichten gesendet werden, explizit angeben müssen, muss das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> in der Regel so konfiguriert werden, dass eine manuelle Adressierung möglich ist. Hierfür wird im Element die <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A>-Eigenschaft auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="dd3c2-118">Auf diese Weise kann die Adresse für die Nachricht explizit über Anwendungscode angegeben werden, und es muss nicht jedes Mal, wenn eine Anwendung eine Nachricht an einen anderen HTTP-URI sendet, eine neue <xref:System.ServiceModel.ChannelFactory> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>

<span data-ttu-id="dd3c2-119">Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="dd3c2-120">HTTP-spezifische Protokollinformationen wie HTTP-Header und Statuscodes werden in der WCF-Programmiermodell über zwei Klassen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="dd3c2-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the WCF programming model through two classes:</span></span>

- <span data-ttu-id="dd3c2-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>

- <span data-ttu-id="dd3c2-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>
  
<span data-ttu-id="dd3c2-123">Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine HTTP GET-Request-Nachricht zu erstellen, die an adressiert wird `http://localhost:8100/customers`.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-123">The following code example shows how to create an HTTP GET request message that is addressed to `http://localhost:8100/customers`.</span></span>

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

<span data-ttu-id="dd3c2-124">Zuerst wird die leere Anforderung <xref:System.ServiceModel.Channels.Message> durch Aufruf von <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> erstellt.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="dd3c2-125">Der <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Parameter zeigt an, dass kein SOAP-Envelope erforderlich ist. Der <xref:System.String.Empty>-Parameter wird als Aktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="dd3c2-126">Anschließend wird die Adresse für die Anforderungsnachricht angegeben, indem im <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Header der gewünschte URI festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="dd3c2-127">Dann wird eine <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> erstellt. <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> wird auf die HTTP GET-Methode festgelegt, und für <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> wird der Wert `true` festgelegt, um anzuzeigen, dass keine Daten im Text der ausgehenden HTTP-Anforderungsnachricht gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="dd3c2-128">Anschließend wird noch die Anforderungseigenschaft zur <xref:System.ServiceModel.Channels.Message.Properties%2A>-Auflistung der Anforderungsnachricht hinzugefügt, damit gesteuert werden kann, auf welche Weise der HTTP-Transport die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="dd3c2-129">Die Nachricht kann nun über eine geeignete Instanz von <xref:System.ServiceModel.Channels.IRequestChannel> gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>

<span data-ttu-id="dd3c2-130">Auf ähnliche Weise kann beim Dienst die <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> aus der eingehenden Nachricht extrahiert und eine Antwort erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dd3c2-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
