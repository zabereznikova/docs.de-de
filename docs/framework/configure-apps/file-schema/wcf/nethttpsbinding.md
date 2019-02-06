---
title: <netHttpsBinding>
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: c79205332afaf97a6c94a9de2178492545ec932f
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759469"
---
# <a name="nethttpsbinding"></a><span data-ttu-id="b9aee-101">\<netHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="b9aee-101">\<netHttpsBinding></span></span>
<span data-ttu-id="b9aee-102">Stellt eine Bindung, die ein Windows Communication Foundation (WCF)-Dienst verwenden können, zum Konfigurieren und Verfügbarmachen von Endpunkten, die über HTTPS kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="b9aee-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="b9aee-103">Bei Verwendung mit einem Duplexvertrag werden WebSockets verwendet; andernfalls wird HTTPS verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9aee-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="b9aee-104">Stammelement</span><span class="sxs-lookup"><span data-stu-id="b9aee-104">Root Element</span></span>  
<span data-ttu-id="b9aee-105">Nächste Element</span><span class="sxs-lookup"><span data-stu-id="b9aee-105">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9aee-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9aee-106">Syntax</span></span>  
  
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
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpsBinding>
```  
  
## <a name="type"></a><span data-ttu-id="b9aee-107">Typ</span><span class="sxs-lookup"><span data-stu-id="b9aee-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9aee-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9aee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b9aee-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9aee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9aee-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9aee-110">Attributes</span></span>  
  
|<span data-ttu-id="b9aee-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b9aee-111">Attribute</span></span>|<span data-ttu-id="b9aee-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9aee-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="b9aee-113">Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.</span><span class="sxs-lookup"><span data-stu-id="b9aee-113">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="b9aee-114">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b9aee-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b9aee-115">Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-115">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="b9aee-116">Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-116">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="b9aee-117">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9aee-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="b9aee-118">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="b9aee-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b9aee-119">Eine Internetressource gilt als lokal, wenn sie über eine lokale Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-119">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="b9aee-120">Eine lokale Adresse befindet, befindet sich auf demselben Computer, der lokalen LAN oder Intranet und wird erkannt werden, anhand des fehlenden Punkts (.) wie in den URIs " http://webserver/ "und" http://localhost/ ".</span><span class="sxs-lookup"><span data-stu-id="b9aee-120">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="b9aee-121">Durch dieses Attribut wird festgelegt, ob mit BasicHttpBinding konfigurierte Endpunkte den Proxyserver zum Zugreifen auf lokale Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-121">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="b9aee-122">Wenn dieses Attribut `true` ist, wird bei Anforderungen lokaler Internetressourcen der Proxyserver nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9aee-122">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="b9aee-123">Ist dieses Attribut auf `true` festgelegt, sollten Sie den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-123">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="b9aee-124">Wenn dieses Attribut `false` ist, werden alle Internetanforderungen über den Proxyserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-124">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="b9aee-125">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b9aee-126">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="b9aee-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b9aee-127">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b9aee-127">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="b9aee-128">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="b9aee-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="b9aee-129">Dieses Attribut ist vom Typ `HostnameComparisonMode` und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9aee-129">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="b9aee-130">Der Standardwert lautet `StrongWildcard`, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="b9aee-130">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="b9aee-131">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-131">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="b9aee-132">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9aee-132">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="b9aee-133">Der Puffer-Manager reduziert den Pufferaufwand durch Verwendung eines Pufferpools.</span><span class="sxs-lookup"><span data-stu-id="b9aee-133">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="b9aee-134">Puffer sind zur Verarbeitung von Nachrichten durch den Dienst erforderlich, wenn sie aus dem Kanal eintreffen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-134">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="b9aee-135">Wenn die Speicherkapazität des Pufferpools zur Verarbeitung der Nachrichten nicht ausreicht, muss der Puffer-Manager zusätzliche Speicherkapazität aus dem CLR-Heap zuweisen. Dadurch wird die Auslastung der Garbage Collection erhöht.</span><span class="sxs-lookup"><span data-stu-id="b9aee-135">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="b9aee-136">Eine umfangreiche Zuweisung aus dem CLR-Heap der Garbage Collection weist darauf hin, dass die Größe des Pufferpools nicht ausreichend ist und dass die Leistung durch eine größere Zuweisung infolge einer Erhöhung der des maximalen Grenzwerts, der durch dieses Attribut angegeben wird, verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9aee-136">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="b9aee-137">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-137">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="b9aee-138">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9aee-138">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="b9aee-139">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b9aee-139">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="b9aee-140">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="b9aee-140">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="b9aee-141">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="b9aee-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b9aee-142">Der Standardwert beträgt 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="b9aee-142">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="b9aee-143">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="b9aee-143">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="b9aee-144">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b9aee-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b9aee-145">-   Text: Verwenden Sie einen textnachrichtenencoder.</span><span class="sxs-lookup"><span data-stu-id="b9aee-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="b9aee-146">-Mtom: Verwenden Sie einen Encoder Message Transmission Organisation Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="b9aee-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="b9aee-147">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="b9aee-147">The default is Text.</span></span> <span data-ttu-id="b9aee-148">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="b9aee-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="b9aee-149">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="b9aee-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b9aee-150">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9aee-150">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b9aee-151">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b9aee-151">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b9aee-152">Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.</span><span class="sxs-lookup"><span data-stu-id="b9aee-152">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b9aee-153">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b9aee-154">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b9aee-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="b9aee-155">Gibt den XML-Namespace der Bindung an.</span><span class="sxs-lookup"><span data-stu-id="b9aee-155">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="b9aee-156">Der Standardwert ist „http://tempuri.org/Bindings“.</span><span class="sxs-lookup"><span data-stu-id="b9aee-156">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="b9aee-157">Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b9aee-157">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="b9aee-158">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-158">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b9aee-159">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="b9aee-159">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b9aee-160">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b9aee-160">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="b9aee-161">Ein URI, der die Adresse des HTTP-Proxys enthält.</span><span class="sxs-lookup"><span data-stu-id="b9aee-161">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="b9aee-162">Wenn `useSystemWebProxy` auf `true` festgelegt ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="b9aee-162">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="b9aee-163">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="b9aee-163">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b9aee-164">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b9aee-165">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="b9aee-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b9aee-166">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="b9aee-166">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b9aee-167">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b9aee-168">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="b9aee-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b9aee-169">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="b9aee-169">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="b9aee-170">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9aee-170">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b9aee-171">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b9aee-171">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b9aee-172">-BigEndianUnicode: Unicode-BigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="b9aee-172">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="b9aee-173">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="b9aee-173">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="b9aee-174">-   UTF8: 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="b9aee-174">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b9aee-175">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="b9aee-175">The default is UTF8.</span></span> <span data-ttu-id="b9aee-176">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="b9aee-176">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="b9aee-177">Ein gültiger <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-177">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="b9aee-178">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems bei Verfügbarkeit verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9aee-178">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="b9aee-179">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="b9aee-179">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="b9aee-180">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9aee-180">Child Elements</span></span>  
  
|<span data-ttu-id="b9aee-181">Element</span><span class="sxs-lookup"><span data-stu-id="b9aee-181">Element</span></span>|<span data-ttu-id="b9aee-182">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9aee-182">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9aee-183">\<security></span><span class="sxs-lookup"><span data-stu-id="b9aee-183">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="b9aee-184">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="b9aee-184">Defines the security settings for the binding.</span></span> <span data-ttu-id="b9aee-185">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b9aee-185">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|<span data-ttu-id="b9aee-186">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b9aee-186">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b9aee-187">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b9aee-187">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b9aee-188">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b9aee-188">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9aee-189">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9aee-189">Parent Elements</span></span>  
  
|<span data-ttu-id="b9aee-190">Element</span><span class="sxs-lookup"><span data-stu-id="b9aee-190">Element</span></span>|<span data-ttu-id="b9aee-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9aee-191">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9aee-192">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b9aee-192">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="b9aee-193">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-193">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9aee-194">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9aee-194">Remarks</span></span>  
 <span data-ttu-id="b9aee-195">NetHttpsBinding verwendet HTTPS als Transport für das Senden von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b9aee-195">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="b9aee-196">Bei Verwendung mit einem Duplexvertrag wird WebSockets verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9aee-196">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="b9aee-197">Bei Verwendung mit einem Anforderungs-Antwort-Vertrag verhält sich NetHttpsBinding wie BasicHttpsBinding mit einem binären Encoder.</span><span class="sxs-lookup"><span data-stu-id="b9aee-197">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="b9aee-198">Sicherheit ist standardmäßig deaktiviert, jedoch können hinzugefügt werden, Festlegen des modusattributs des der [ \<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) untergeordnetes Element auf einen anderen Wert als `None`.</span><span class="sxs-lookup"><span data-stu-id="b9aee-198">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="b9aee-199">Standardmäßig wird "Text"-Nachrichtencodierung und UTF-8-Textcodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9aee-199">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9aee-200">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9aee-200">Example</span></span>  
 <span data-ttu-id="b9aee-201">Im folgenden Beispiel wird die Verwendung von <xref:System.ServiceModel.NetHttpBinding> veranschaulicht, bei der HTTPS-Kommunikation und maximale Interoperabilität mit Webdiensten der ersten und zweiten Generation sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b9aee-201">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="b9aee-202">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9aee-202">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="b9aee-203">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9aee-203">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="b9aee-204">Wenn Sie die Standardbindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="b9aee-204">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="b9aee-205">Der Endpunkt muss auf die Bindungskonfiguration anhand des Namens und des `bindingConfiguration`-Attributs des `<endpoint>`-Elements verweisen, wie im folgenden Konfigurationscode für den Dienst gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9aee-205">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="b9aee-206">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9aee-206">Example</span></span>  
 <span data-ttu-id="b9aee-207">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-207">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b9aee-208">Die Funktionalität aus dem vorherigen Beispiel kann erfolgen, indem BindingConfiguration aus die Endpunktadresse und den Namen der Bindung entfernen.</span><span class="sxs-lookup"><span data-stu-id="b9aee-208">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding hostNameComparisonMode="StrongWildcard"
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
  
 <span data-ttu-id="b9aee-209">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="b9aee-209">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9aee-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9aee-210">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="b9aee-211">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b9aee-211">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b9aee-212">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b9aee-212">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b9aee-213">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b9aee-213">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b9aee-214">\<binding></span><span class="sxs-lookup"><span data-stu-id="b9aee-214">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
