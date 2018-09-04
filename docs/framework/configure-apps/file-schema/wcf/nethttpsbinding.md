---
title: '&lt;netHttpsBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: 2dbcdbe7fff758bab0e932817feddab398ed9ed1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526503"
---
# <a name="ltnethttpsbindinggt"></a><span data-ttu-id="6db48-102">&lt;netHttpsBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="6db48-102">&lt;netHttpsBinding&gt;</span></span>
<span data-ttu-id="6db48-103">Stellt eine Bindung, die ein Windows Communication Foundation (WCF)-Dienst verwenden können, zum Konfigurieren und Verfügbarmachen von Endpunkten, die über HTTPS kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="6db48-103">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="6db48-104">Bei Verwendung mit einem Duplexvertrag werden WebSockets verwendet; andernfalls wird HTTPS verwendet.</span><span class="sxs-lookup"><span data-stu-id="6db48-104">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="6db48-105">Stammelement</span><span class="sxs-lookup"><span data-stu-id="6db48-105">Root Element</span></span>  
<span data-ttu-id="6db48-106">Nächste Element</span><span class="sxs-lookup"><span data-stu-id="6db48-106">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db48-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6db48-107">Syntax</span></span>  

```xml
<netHttpsBinding>  
  <binding allowCookies="Boolean"  
           bypassProxyOnLocal="Boolean"  
           closeTimeout="TimeSpan"   
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
           maxBufferPoolSize="Integer"  
           maxBufferSize="Integer"  
           maxReceivedMessageSize="Integer"  
           messageEncoding="Binary/Text/Mtom"  
           name="string"   
           openTimeout="TimeSpan"   
           proxyAddress="URI"  
           receiveTimeout="TimeSpan"  
           sendTimeout="TimeSpan"  
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                 realm="string" />  
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" 
               clientCredentialType="UserName/Certificate"/>  
    </security>  
    <readerQuotas maxArrayLength="Integer" 
                  maxBytesPerRead="Integer" 
                  maxDepth="Integer" 
                  maxNameTableCharCount="Integer" 
                  maxStringContentLength="Integer" />  
  </binding>  
</netHttpsBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="6db48-108">Typ</span><span class="sxs-lookup"><span data-stu-id="6db48-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6db48-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6db48-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6db48-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6db48-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6db48-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6db48-111">Attributes</span></span>  
  
|<span data-ttu-id="6db48-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6db48-112">Attribute</span></span>|<span data-ttu-id="6db48-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6db48-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="6db48-114">Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.</span><span class="sxs-lookup"><span data-stu-id="6db48-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="6db48-115">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="6db48-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="6db48-116">Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="6db48-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="6db48-117">Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="6db48-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="6db48-118">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6db48-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="6db48-119">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="6db48-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="6db48-120">Eine Internetressource gilt als lokal, wenn sie über eine lokale Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="6db48-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="6db48-121">Eine lokale Adresse befindet, befindet sich auf demselben Computer, der lokalen LAN oder Intranet und wird erkannt werden, anhand des fehlenden Punkts (.) wie in den URIs " http://webserver/ "und" http://localhost/ ".</span><span class="sxs-lookup"><span data-stu-id="6db48-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="6db48-122">Durch dieses Attribut wird festgelegt, ob mit BasicHttpBinding konfigurierte Endpunkte den Proxyserver zum Zugreifen auf lokale Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6db48-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="6db48-123">Wenn dieses Attribut `true` ist, wird bei Anforderungen lokaler Internetressourcen der Proxyserver nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6db48-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="6db48-124">Ist dieses Attribut auf `true` festgelegt, sollten Sie den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.</span><span class="sxs-lookup"><span data-stu-id="6db48-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="6db48-125">Wenn dieses Attribut `false` ist, werden alle Internetanforderungen über den Proxyserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6db48-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="6db48-126">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="6db48-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="6db48-127">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="6db48-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6db48-128">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6db48-128">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="6db48-129">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="6db48-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="6db48-130">Dieses Attribut ist vom Typ `HostnameComparisonMode` und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6db48-130">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="6db48-131">Der Standardwert lautet `StrongWildcard`, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="6db48-131">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="6db48-132">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="6db48-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="6db48-133">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="6db48-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="6db48-134">Der Puffer-Manager reduziert den Pufferaufwand durch Verwendung eines Pufferpools.</span><span class="sxs-lookup"><span data-stu-id="6db48-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="6db48-135">Puffer sind zur Verarbeitung von Nachrichten durch den Dienst erforderlich, wenn sie aus dem Kanal eintreffen.</span><span class="sxs-lookup"><span data-stu-id="6db48-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="6db48-136">Wenn die Speicherkapazität des Pufferpools zur Verarbeitung der Nachrichten nicht ausreicht, muss der Puffer-Manager zusätzliche Speicherkapazität aus dem CLR-Heap zuweisen. Dadurch wird die Auslastung der Garbage Collection erhöht.</span><span class="sxs-lookup"><span data-stu-id="6db48-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="6db48-137">Eine umfangreiche Zuweisung aus dem CLR-Heap der Garbage Collection weist darauf hin, dass die Größe des Pufferpools nicht ausreichend ist und dass die Leistung durch eine größere Zuweisung infolge einer Erhöhung der des maximalen Grenzwerts, der durch dieses Attribut angegeben wird, verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6db48-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="6db48-138">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6db48-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="6db48-139">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="6db48-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="6db48-140">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6db48-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="6db48-141">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="6db48-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="6db48-142">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="6db48-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="6db48-143">Der Standardwert beträgt 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="6db48-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="6db48-144">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="6db48-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="6db48-145">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6db48-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6db48-146">-Text: Verwenden Sie einen textnachrichtenencoder.</span><span class="sxs-lookup"><span data-stu-id="6db48-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="6db48-147">-Mtom: Verwenden eines Encoders Message Transmission Organisation Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="6db48-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="6db48-148">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="6db48-148">The default is Text.</span></span> <span data-ttu-id="6db48-149">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="6db48-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="6db48-150">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="6db48-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="6db48-151">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6db48-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="6db48-152">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6db48-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="6db48-153">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="6db48-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="6db48-154">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6db48-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="6db48-155">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="6db48-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="6db48-156">Gibt den XML-Namespace der Bindung an.</span><span class="sxs-lookup"><span data-stu-id="6db48-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="6db48-157">Der Standardwert ist „http://tempuri.org/Bindings“.</span><span class="sxs-lookup"><span data-stu-id="6db48-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="6db48-158">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6db48-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="6db48-159">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="6db48-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="6db48-160">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="6db48-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6db48-161">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6db48-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="6db48-162">Ein URI, der die Adresse des HTTP-Proxys enthält.</span><span class="sxs-lookup"><span data-stu-id="6db48-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="6db48-163">Wenn `useSystemWebProxy` auf `true` festgelegt ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="6db48-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="6db48-164">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="6db48-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="6db48-165">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="6db48-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="6db48-166">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="6db48-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6db48-167">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="6db48-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="6db48-168">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="6db48-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="6db48-169">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="6db48-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6db48-170">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="6db48-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="6db48-171">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6db48-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="6db48-172">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="6db48-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6db48-173">-BigEndianUnicode: Unicode BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="6db48-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="6db48-174">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="6db48-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="6db48-175">– UTF8: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="6db48-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="6db48-176">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="6db48-176">The default is UTF8.</span></span> <span data-ttu-id="6db48-177">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="6db48-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="6db48-178">Ein gültiger <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="6db48-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="6db48-179">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems bei Verfügbarkeit verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6db48-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="6db48-180">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="6db48-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="6db48-181">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6db48-181">Child Elements</span></span>  
  
|<span data-ttu-id="6db48-182">Element</span><span class="sxs-lookup"><span data-stu-id="6db48-182">Element</span></span>|<span data-ttu-id="6db48-183">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6db48-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6db48-184">\<security></span><span class="sxs-lookup"><span data-stu-id="6db48-184">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="6db48-185">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="6db48-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="6db48-186">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6db48-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="6db48-187">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="6db48-187">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="6db48-188">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="6db48-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="6db48-189">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="6db48-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6db48-190">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6db48-190">Parent Elements</span></span>  
  
|<span data-ttu-id="6db48-191">Element</span><span class="sxs-lookup"><span data-stu-id="6db48-191">Element</span></span>|<span data-ttu-id="6db48-192">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6db48-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6db48-193">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6db48-193">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="6db48-194">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="6db48-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6db48-195">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6db48-195">Remarks</span></span>  
 <span data-ttu-id="6db48-196">NetHttpsBinding verwendet HTTPS als Transport für das Senden von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="6db48-196">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="6db48-197">Bei Verwendung mit einem Duplexvertrag wird WebSockets verwendet.</span><span class="sxs-lookup"><span data-stu-id="6db48-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="6db48-198">Bei Verwendung mit einem Anforderungs-Antwort-Vertrag verhält sich NetHttpsBinding wie BasicHttpsBinding mit einem binären Encoder.</span><span class="sxs-lookup"><span data-stu-id="6db48-198">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="6db48-199">Sicherheit ist standardmäßig deaktiviert, jedoch können hinzugefügt werden, Festlegen des modusattributs des der [ \<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) untergeordnetes Element auf einen anderen Wert als `None`.</span><span class="sxs-lookup"><span data-stu-id="6db48-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="6db48-200">Standardmäßig wird "Text"-Nachrichtencodierung und UTF-8-Textcodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6db48-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db48-201">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6db48-201">Example</span></span>  
 <span data-ttu-id="6db48-202">Im folgenden Beispiel wird die Verwendung von <xref:System.ServiceModel.NetHttpBinding> veranschaulicht, bei der HTTPS-Kommunikation und maximale Interoperabilität mit Webdiensten der ersten und zweiten Generation sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6db48-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="6db48-203">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="6db48-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="6db48-204">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="6db48-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="6db48-205">Wenn Sie die Standardbindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="6db48-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="6db48-206">Der Endpunkt muss auf die Bindungskonfiguration anhand des Namens und des `bindingConfiguration`-Attributs des `<endpoint>`-Elements verweisen, wie im folgenden Konfigurationscode für den Dienst gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6db48-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpsBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpsBinding>  
      <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard" 
               receiveTimeout="00:10:00" 
               sendTimeout="00:10:00" 
               openTimeout="00:10:00" 
               closeTimeout="00:10:00" 
               maxReceivedMessageSize="65536" 
               maxBufferSize="65536" 
               maxBufferPoolSize="524288" 
               transferMode="Buffered" 
               messageEncoding="Binary" 
               textEncoding="utf-8" 
               bypassProxyOnLocal="false" 
               useDefaultWebProxy="true">  
        <security mode="None" />  
      </binding>  
    </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a><span data-ttu-id="6db48-207">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6db48-207">Example</span></span>  
 <span data-ttu-id="6db48-208">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6db48-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="6db48-209">Die Funktionalität aus dem vorherigen Beispiel kann erreicht werden, indem bindingConfiguration aus der Endpunktadresse und der Name aus der Bindung entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6db48-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name frm the binding.</span></span>  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="netHttpsBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <netHttpsBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Binary"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </netHttpsBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="6db48-210">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="6db48-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db48-211">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db48-211">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="6db48-212">Bindungen</span><span class="sxs-lookup"><span data-stu-id="6db48-212">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6db48-213">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6db48-213">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="6db48-214">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6db48-214">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="6db48-215">\<binding></span><span class="sxs-lookup"><span data-stu-id="6db48-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
