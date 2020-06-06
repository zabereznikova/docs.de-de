---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: 815ee3993a2f2b2819210b225c0cb0b3d3fd8b87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "84201013"
---
# \<netHttpBinding>
<span data-ttu-id="7f4ad-101">Stellt eine Bindung dar, die ein Windows Communication Foundation (WCF)-Dienst zum Konfigurieren und verfügbar machen von Endpunkten verwenden kann, die über HTTP kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-101">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="7f4ad-102">Bei Verwendung mit einem Duplexvertrag wird WebSockets verwendet; andernfalls wird HTTP verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-102">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="7f4ad-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f4ad-103">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
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
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="7f4ad-104">type</span><span class="sxs-lookup"><span data-stu-id="7f4ad-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f4ad-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f4ad-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7f4ad-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f4ad-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f4ad-107">Attributes</span></span>  
  
|<span data-ttu-id="7f4ad-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7f4ad-108">Attribute</span></span>|<span data-ttu-id="7f4ad-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f4ad-109">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="7f4ad-110">Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-110">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="7f4ad-111">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-111">The default is `false`.</span></span><br /><br /> <span data-ttu-id="7f4ad-112">Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-112">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="7f4ad-113">Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-113">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="7f4ad-114">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="7f4ad-115">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="7f4ad-116">Eine Internetressource gilt als lokal, wenn sie über eine lokale Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-116">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="7f4ad-117">Eine lokale Adresse befindet sich auf demselben Computer, LAN oder Intranet und wird durch das Fehlen eines Zeitraums (.) wie in den URIs und identifiziert, syntaktisch `http://webserver/` `http://localhost/` .</span><span class="sxs-lookup"><span data-stu-id="7f4ad-117">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs `http://webserver/` and `http://localhost/`.</span></span><br /><br /> <span data-ttu-id="7f4ad-118">Durch dieses Attribut wird festgelegt, ob mit BasicHttpBinding konfigurierte Endpunkte den Proxyserver zum Zugreifen auf lokale Ressourcen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-118">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="7f4ad-119">Wenn dieses Attribut `true` ist, wird bei Anforderungen lokaler Internetressourcen der Proxyserver nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-119">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="7f4ad-120">Ist dieses Attribut auf `true` festgelegt, sollten Sie den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-120">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="7f4ad-121">Wenn dieses Attribut `false` ist, werden alle Internetanforderungen über den Proxyserver ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-121">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="7f4ad-122">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7f4ad-123">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7f4ad-124">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-124">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="7f4ad-125">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-125">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="7f4ad-126">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-126">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="7f4ad-127">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-127">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="7f4ad-128">Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-128">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="7f4ad-129">Der Standardwert ist 524288 (0x80000) Bytes.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-129">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="7f4ad-130">Der Puffer-Manager reduziert den Pufferaufwand durch Verwendung eines Pufferpools.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-130">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="7f4ad-131">Puffer sind zur Verarbeitung von Nachrichten durch den Dienst erforderlich, wenn sie aus dem Kanal eintreffen.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-131">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="7f4ad-132">Wenn die Speicherkapazität des Pufferpools zur Verarbeitung der Nachrichten nicht ausreicht, muss der Puffer-Manager zusätzliche Speicherkapazität aus dem CLR-Heap zuweisen. Dadurch wird die Auslastung der Garbage Collection erhöht.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-132">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="7f4ad-133">Eine umfangreiche Zuweisung aus dem CLR-Heap der Garbage Collection weist darauf hin, dass die Größe des Pufferpools nicht ausreichend ist und dass die Leistung durch eine größere Zuweisung infolge einer Erhöhung der des maximalen Grenzwerts, der durch dieses Attribut angegeben wird, verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-133">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="7f4ad-134">Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-134">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="7f4ad-135">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-135">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="7f4ad-136">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-136">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="7f4ad-137">Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-137">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="7f4ad-138">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-138">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="7f4ad-139">Der Standardwert ist 65.536 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-139">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="7f4ad-140">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-140">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="7f4ad-141">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7f4ad-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7f4ad-142">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="7f4ad-143">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="7f4ad-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="7f4ad-144">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-144">The default is Text.</span></span> <span data-ttu-id="7f4ad-145">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="7f4ad-146">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-146">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7f4ad-147">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-147">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7f4ad-148">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-148">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7f4ad-149">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7f4ad-149">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7f4ad-150">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7f4ad-151">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7f4ad-152">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-152">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="7f4ad-153">Ein URI, der die Adresse des HTTP-Proxys enthält.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-153">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="7f4ad-154">Wenn `useSystemWebProxy` auf `true` festgelegt ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-154">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="7f4ad-155">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-155">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7f4ad-156">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7f4ad-157">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7f4ad-158">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-158">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7f4ad-159">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7f4ad-160">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7f4ad-161">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-161">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="7f4ad-162">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-162">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="7f4ad-163">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7f4ad-163">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7f4ad-164">-BigEndianUnicode: Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-164">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="7f4ad-165">-Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-165">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="7f4ad-166">-UTF8:8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="7f4ad-166">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="7f4ad-167">Der Standardwert ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-167">The default is UTF8.</span></span> <span data-ttu-id="7f4ad-168">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-168">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="7f4ad-169">Ein gültiger <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-169">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="7f4ad-170">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems bei Verfügbarkeit verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-170">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="7f4ad-171">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-171">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="7f4ad-172">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f4ad-172">Child Elements</span></span>  
  
|<span data-ttu-id="7f4ad-173">Element</span><span class="sxs-lookup"><span data-stu-id="7f4ad-173">Element</span></span>|<span data-ttu-id="7f4ad-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f4ad-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="7f4ad-175">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-175">Defines the security settings for the binding.</span></span> <span data-ttu-id="7f4ad-176">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-176">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="7f4ad-177">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-177">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="7f4ad-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-178">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f4ad-179">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f4ad-179">Parent Elements</span></span>  
  
|<span data-ttu-id="7f4ad-180">Element</span><span class="sxs-lookup"><span data-stu-id="7f4ad-180">Element</span></span>|<span data-ttu-id="7f4ad-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f4ad-181">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="7f4ad-182">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f4ad-183">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f4ad-183">Remarks</span></span>  
 <span data-ttu-id="7f4ad-184">NetHttpBinding verwendet HTTP als Transport für das Senden von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-184">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="7f4ad-185">Bei Verwendung mit einem Duplexvertrag wird WebSockets verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-185">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="7f4ad-186">Bei Verwendung mit einem Anforderungs-Antwort-Vertrag verhält sich NetHttpBinding wie BasicHttpBinding mit einem binären Encoder.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-186">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="7f4ad-187">Sicherheit ist standardmäßig deaktiviert, kann jedoch hinzugefügt werden, indem das Mode-Attribut des untergeordneten- [\<security>](security-of-basichttpbinding.md) Elements auf einen anderen Wert als festgelegt wird `None` .</span><span class="sxs-lookup"><span data-stu-id="7f4ad-187">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="7f4ad-188">Standardmäßig wird "Text"-Nachrichtencodierung und UTF-8-Textcodierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-188">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f4ad-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f4ad-189">Example</span></span>  
 <span data-ttu-id="7f4ad-190">Im folgenden Beispiel wird die Verwendung von <xref:System.ServiceModel.NetHttpBinding> veranschaulicht, bei der HTTP-Kommunikation und maximale Interoperabilität mit Webdiensten der ersten und zweiten Generation sichergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-190">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="7f4ad-191">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-191">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="7f4ad-192">Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-192">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="7f4ad-193">Wenn Sie die Standardbindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-193">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="7f4ad-194">Der Endpunkt muss auf die Bindungskonfiguration anhand des Namens und des `bindingConfiguration`-Attributs des `<endpoint>`-Elements verweisen, wie im folgenden Konfigurationscode für den Dienst gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-194">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="7f4ad-195">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f4ad-195">Example</span></span>  
 <span data-ttu-id="7f4ad-196">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-196">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7f4ad-197">Die Funktionalität aus dem vorherigen Beispiel kann erreicht werden, indem die bindingConfiguration aus der Endpunkt Adresse und der Name aus der Bindung entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="7f4ad-197">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="7f4ad-198">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="7f4ad-198">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4ad-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f4ad-199">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="7f4ad-200">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7f4ad-200">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7f4ad-201">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7f4ad-201">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7f4ad-202">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7f4ad-202">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
