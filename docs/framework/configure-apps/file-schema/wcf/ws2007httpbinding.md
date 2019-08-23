---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 2fb9f7a16a360ddd61e6f8b935f928ddfdeb6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915252"
---
# <a name="ws2007httpbinding"></a><span data-ttu-id="0b456-101">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="0b456-101">\<ws2007HttpBinding></span></span>
<span data-ttu-id="0b456-102">Definiert eine interoperable Bindung, die Unterstützung für die entsprechenden Versionen der Bindungselemente <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> und <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0b456-102">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="0b456-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b456-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0b456-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b456-104">\<bindings></span></span>  
<span data-ttu-id="0b456-105">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="0b456-105">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b456-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b456-106">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b456-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b456-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0b456-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b456-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b456-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b456-109">Attributes</span></span>  
  
|<span data-ttu-id="0b456-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b456-110">Attribute</span></span>|<span data-ttu-id="0b456-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b456-111">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="0b456-112">Ein Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anfragen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="0b456-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="0b456-113">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0b456-113">The default is `false`.</span></span><br /><br /> <span data-ttu-id="0b456-114">Sie können diese Eigenschaft verwenden, wenn Sie mit ASP.NET-Webdiensten (ASMX) interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b456-114">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="0b456-115">Auf diese Weise wird sichergestellt, dass vom Server zurückgegebene Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b456-115">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="0b456-116">Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b456-116">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="0b456-117">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0b456-117">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="0b456-118">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="0b456-118">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="0b456-119">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="0b456-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b456-120">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0b456-120">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="0b456-121">Gibt den HTTP-Hostnamenvergleichsmodus an, der zum Analysieren von Uniform Resource Identifiers (URIs) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b456-121">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="0b456-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b456-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="0b456-123">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="0b456-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="0b456-124">Die maximale Pufferpoolgröße dieser Bindung.</span><span class="sxs-lookup"><span data-stu-id="0b456-124">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="0b456-125">Der Standardwert ist 524.288 Byte (512 × 1.024).</span><span class="sxs-lookup"><span data-stu-id="0b456-125">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="0b456-126">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="0b456-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="0b456-127">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="0b456-127">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="0b456-128">Bei Pufferpools können Sie dem Pool einen Puffer entnehmen, diesen verwenden und nach der Verwendung wieder in den Pool zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="0b456-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="0b456-129">Dadurch wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="0b456-129">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="0b456-130">Die maximale Nachrichtengröße in Byte einschließlich Header, die von einem mit dieser Bindung konfigurierten Kanal empfangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b456-130">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="0b456-131">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="0b456-131">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="0b456-132">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="0b456-132">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="0b456-133">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="0b456-133">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="0b456-134">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="0b456-134">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="0b456-135">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0b456-135">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0b456-136">-   `Text`: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="0b456-136">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="0b456-137">-   `Mtom`: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="0b456-137">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="0b456-138">Die Standardeinstellung ist `Text`.</span><span class="sxs-lookup"><span data-stu-id="0b456-138">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="0b456-139">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="0b456-139">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="0b456-140">Der Konfigurationsname der Bindung.</span><span class="sxs-lookup"><span data-stu-id="0b456-140">The configuration name of the binding.</span></span> <span data-ttu-id="0b456-141">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b456-141">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="0b456-142">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0b456-142">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0b456-143">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0b456-143">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="0b456-144">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="0b456-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="0b456-145">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="0b456-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b456-146">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0b456-146">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="0b456-147">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="0b456-147">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="0b456-148">Wenn `useSystemWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="0b456-148">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="0b456-149">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0b456-149">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0b456-150">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="0b456-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="0b456-151">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="0b456-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b456-152">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0b456-152">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="0b456-153">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="0b456-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0b456-154">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="0b456-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b456-155">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="0b456-155">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="0b456-156">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b456-156">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="0b456-157">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0b456-157">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0b456-158">-   `UnicodeFffeTextEncoding`: Unicode Big-codierte Codierung.</span><span class="sxs-lookup"><span data-stu-id="0b456-158">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="0b456-159">-   `Utf16TextEncoding`: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="0b456-159">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="0b456-160">-   `Utf8TextEncoding`: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="0b456-160">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="0b456-161">Die Standardeinstellung ist `Utf8TextEncoding`.</span><span class="sxs-lookup"><span data-stu-id="0b456-161">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="0b456-162">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="0b456-162">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="0b456-163">Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b456-163">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="0b456-164">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0b456-164">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="0b456-165">Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b456-165">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="0b456-166">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0b456-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b456-167">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b456-167">Child Elements</span></span>  
  
|<span data-ttu-id="0b456-168">Element</span><span class="sxs-lookup"><span data-stu-id="0b456-168">Element</span></span>|<span data-ttu-id="0b456-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b456-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b456-170">\<security></span><span class="sxs-lookup"><span data-stu-id="0b456-170">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="0b456-171">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="0b456-171">Defines the security settings for the binding.</span></span> <span data-ttu-id="0b456-172">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0b456-172">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="0b456-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0b456-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="0b456-174">Definiert die Beschränkungen bezüglich der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0b456-174">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="0b456-175">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="0b456-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="0b456-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0b456-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="0b456-177">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="0b456-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b456-178">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b456-178">Parent Elements</span></span>  
  
|<span data-ttu-id="0b456-179">Element</span><span class="sxs-lookup"><span data-stu-id="0b456-179">Element</span></span>|<span data-ttu-id="0b456-180">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b456-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b456-181">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b456-181">\<bindings></span></span>](bindings.md)|<span data-ttu-id="0b456-182">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="0b456-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b456-183">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b456-183">Remarks</span></span>  
 <span data-ttu-id="0b456-184">Die `WS2007HttpBinding` fügt ähnlich wie `WSHttpBinding` eine vom System bereitgestellte Bindung hinzu, verwendet aber die OASIS-Standardversionen (Organization for the Advancement of Structured Information Standards) des ReliableSession-, Security- und TransactionFlow-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="0b456-184">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="0b456-185">Beim Verwenden dieser Bindung sind keine Änderungen am Objektmodell oder Standardeinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0b456-185">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b456-186">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b456-186">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="0b456-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b456-187">See also</span></span>

- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="0b456-188">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b456-188">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0b456-189">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b456-189">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0b456-190">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0b456-190">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0b456-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b456-191">\<binding></span></span>](../../../misc/binding.md)
