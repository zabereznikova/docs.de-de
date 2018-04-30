---
title: Interoperabilität mit POX-Anwendungen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 42f6bbb1a5605bd0a604f5cfe31ce5ea48d9bb10
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="interoperability-with-pox-applications"></a><span data-ttu-id="82785-102">Interoperabilität mit POX-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="82785-102">Interoperability with POX Applications</span></span>
<span data-ttu-id="82785-103">"Plain Old XML" (POX)-Anwendungen kommunizieren, indem Sie den Austausch von unformatierte HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einen SOAP-Umschlag eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="82785-103">"Plain Old XML" (POX) applications communicate by exchanging raw HTTP messages that contain only XML application data that is not enclosed within a SOAP envelope.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="82785-104"> kann Dienste und Clients bereitstellen, die POX-Nachrichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="82785-104"> can provide both services and clients that use POX messages.</span></span> <span data-ttu-id="82785-105">Beim Dienst kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für die Implementierung von Diensten verwendet werden, die Endpunkte wie Webbrowser und Skriptsprachen, mit denen POX-Nachrichten gesendet und empfangen werden können, für Clients verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="82785-105">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can be used to implement services that expose endpoints to clients such as Web browsers and scripting languages that send and receive POX messages.</span></span> <span data-ttu-id="82785-106">Auf dem Client kann das Programmiermodell von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Implementierung von Clients, die mit POX-basierten Diensten kommunizieren, herangezogen werden.</span><span class="sxs-lookup"><span data-stu-id="82785-106">On the client, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model can be used to implement clients that communicate with POX-based services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82785-107">Dieses Dokument wurde ursprünglich für [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&#160;3.0 geschrieben.</span><span class="sxs-lookup"><span data-stu-id="82785-107">This document was originally written for the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.</span></span>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]<span data-ttu-id="82785-108">&amp;#160;3.5 verfügt über intergrierte Unterstützung für die Arbeit mit POX-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="82785-108"> 3.5 has built-in support for working with POX applications.</span></span> <span data-ttu-id="82785-109">Weitere Informationen finden Sie unter [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span><span class="sxs-lookup"><span data-stu-id="82785-109">For more information about see [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)</span></span>  
  
## <a name="pox-programming-with-wcf"></a><span data-ttu-id="82785-110">POX-Programmierung mit WCF</span><span class="sxs-lookup"><span data-stu-id="82785-110">POX Programming with WCF</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="82785-111"> Dienste, die für die Kommunikation über HTTP unter Verwendung von POX-Nachrichten mithilfe einer [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="82785-111"> services that communicate over HTTP using POX messages use a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
```xml  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="82785-112">Diese benutzerspezifische Bindung enthält zwei Elemente:</span><span class="sxs-lookup"><span data-stu-id="82785-112">This custom binding contains two elements:</span></span>  
  
-   <span data-ttu-id="82785-113">Die [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) und</span><span class="sxs-lookup"><span data-stu-id="82785-113">The [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) and</span></span>  
  
-   <span data-ttu-id="82785-114">Die [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="82785-114">The [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
 <span data-ttu-id="82785-115">Der standardmäßige Textnachrichtenencoder von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist spezifisch für die Verwendung des <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Werts konfiguriert, wodurch XML-Nachrichten ohne SOAP-Envelope verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="82785-115">The standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Text Message Encoder is specially configured to use the <xref:System.ServiceModel.Channels.MessageVersion.None%2A> value, which allows it to process XML message payloads that do not arrive wrapped in a SOAP envelope.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="82785-116">-Clients, die über HTTP unter Verwendung von POX-Nachrichten kommunizieren, verwenden eine ähnliche Bindung (wie im folgenden imperativen Code zu sehen ist):</span><span class="sxs-lookup"><span data-stu-id="82785-116"> clients that communicate over HTTP using POX messages use a similar binding (shown in the following imperative code).</span></span>  
  
```  
private static Binding CreatePoxBinding()  
{  
    TextMessageEncodingBindingElement encoder =   
    new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );  
    HttpTransportBindingElement transport = new HttpTransportBindingElement();  
    transport.ManualAddressing = true;  
    return new CustomBinding( new BindingElement[] { encoder, transport } );  
}   
```  
  
 <span data-ttu-id="82785-117">Da POX-Clients die URIs, an die Nachrichten gesendet werden, explizit angeben müssen, muss das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> in der Regel so konfiguriert werden, dass eine manuelle Adressierung möglich ist. Hierfür wird im Element die <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A>-Eigenschaft auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82785-117">Because POX clients must explicitly specify the URIs to which they send messages, they usually must configure the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> to a manual addressing mode by setting the <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> property to `true` on the element.</span></span> <span data-ttu-id="82785-118">Auf diese Weise kann die Adresse für die Nachricht explizit über Anwendungscode angegeben werden, und es muss nicht jedes Mal, wenn eine Anwendung eine Nachricht an einen anderen HTTP-URI sendet, eine neue <xref:System.ServiceModel.ChannelFactory> erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="82785-118">This allows messages to be addressed explicitly by application code and it is not necessary to create a new <xref:System.ServiceModel.ChannelFactory> every time an application sends a message to a different HTTP URI.</span></span>  
  
 <span data-ttu-id="82785-119">Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren.</span><span class="sxs-lookup"><span data-stu-id="82785-119">Because POX messages do not use SOAP headers to convey important protocol information, POX clients and services often must manipulate pieces of the underlying HTTP request used to send or receive a message.</span></span> <span data-ttu-id="82785-120">HTTP-spezifische Protokollinformationen wie HTTP-Header und Statuscodes werden im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Programmiermodell durch zwei Klassen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="82785-120">HTTP-specific protocol information such as the HTTP headers and status codes are surfaced in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model through two classes:</span></span>  
  
-   <span data-ttu-id="82785-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.</span><span class="sxs-lookup"><span data-stu-id="82785-121"><xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, which contains information about the HTTP request, such as the HTTP method and request headers.</span></span>  
  
-   <span data-ttu-id="82785-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.</span><span class="sxs-lookup"><span data-stu-id="82785-122"><xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, which contains information about the HTTP response, such as the HTTP status code and status description, as well as any HTTP response headers.</span></span>  
  
 <span data-ttu-id="82785-123">Im folgenden Codebeispiel wird veranschaulicht, wie eine HTTP GET-Anforderungsnachricht zu erstellen, die an adressiert wird http://localhost:8100/customers.</span><span class="sxs-lookup"><span data-stu-id="82785-123">The following code example shows how to create an HTTP GET request message that is addressed to http://localhost:8100/customers.</span></span>  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = "http://localhost:8100/customers";  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = "GET";  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 <span data-ttu-id="82785-124">Zuerst wird die leere Anforderung <xref:System.ServiceModel.Channels.Message> durch Aufruf von <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> erstellt.</span><span class="sxs-lookup"><span data-stu-id="82785-124">First, an empty request <xref:System.ServiceModel.Channels.Message> is created by calling <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>.</span></span> <span data-ttu-id="82785-125">Der <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Parameter zeigt an, dass kein SOAP-Envelope erforderlich ist. Der <xref:System.String.Empty>-Parameter wird als Aktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="82785-125">The <xref:System.ServiceModel.Channels.MessageVersion.None%2A> parameter is used to indicate that a SOAP envelope is not required and <xref:System.String.Empty> parameter is passed as the Action.</span></span> <span data-ttu-id="82785-126">Anschließend wird die Adresse für die Anforderungsnachricht angegeben, indem im <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Header der gewünschte URI festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="82785-126">The request message is then addressed by setting <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> header to the desired URI.</span></span> <span data-ttu-id="82785-127">Dann wird eine <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> erstellt. <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> wird auf die HTTP GET-Methode festgelegt, und für <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> wird der Wert `true` festgelegt, um anzuzeigen, dass keine Daten im Text der ausgehenden HTTP-Anforderungsnachricht gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82785-127">Next, an <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> is created and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> is set to the HTTP verb GET method and the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> is set to `true` to indicate that no data should be sent in the body of the outgoing HTTP request message.</span></span> <span data-ttu-id="82785-128">Anschließend wird noch die Anforderungseigenschaft zur <xref:System.ServiceModel.Channels.Message.Properties%2A>-Auflistung der Anforderungsnachricht hinzugefügt, damit gesteuert werden kann, auf welche Weise der HTTP-Transport die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="82785-128">Finally, the request property is added to the <xref:System.ServiceModel.Channels.Message.Properties%2A> collection of the request message so it can influence how the HTTP Transport sends the request.</span></span> <span data-ttu-id="82785-129">Die Nachricht kann nun über eine geeignete Instanz von <xref:System.ServiceModel.Channels.IRequestChannel> gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="82785-129">The message is then ready to be sent over an appropriate instance of the <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span>  
  
 <span data-ttu-id="82785-130">Auf ähnliche Weise kann beim Dienst die <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> aus der eingehenden Nachricht extrahiert und eine Antwort erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="82785-130">Similar techniques can be used on the service to extract the <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> from an incoming message and construct a response.</span></span>
