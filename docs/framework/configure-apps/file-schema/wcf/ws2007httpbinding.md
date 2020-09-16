---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 102e220ad01410568a18ce4ea6fac06ca8c15230
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558731"
---
# \<ws2007HttpBinding>
<span data-ttu-id="77130-101">Definiert eine interoperable Bindung, die Unterstützung für die entsprechenden Versionen der Bindungselemente <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> und <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="77130-101">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007HttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="77130-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="77130-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77130-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="77130-103">Attributes and Elements</span></span>  
 <span data-ttu-id="77130-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="77130-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77130-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="77130-105">Attributes</span></span>  
  
|<span data-ttu-id="77130-106">attribute</span><span class="sxs-lookup"><span data-stu-id="77130-106">Attribute</span></span>|<span data-ttu-id="77130-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="77130-107">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="77130-108">Ein Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anfragen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="77130-108">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="77130-109">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="77130-109">The default is `false`.</span></span><br /><br /> <span data-ttu-id="77130-110">Sie können diese Eigenschaft verwenden, wenn Sie mit ASP.NET-Webdiensten (ASMX) interagieren, die Cookies verwenden.</span><span class="sxs-lookup"><span data-stu-id="77130-110">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="77130-111">Auf diese Weise wird sichergestellt, dass vom Server zurückgegebene Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="77130-111">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="77130-112">Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="77130-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="77130-113">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="77130-113">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="77130-114">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="77130-114">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="77130-115">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="77130-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="77130-116">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="77130-116">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="77130-117">Gibt den HTTP-Hostnamenvergleichsmodus an, der zum Analysieren von Uniform Resource Identifiers (URIs) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77130-117">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="77130-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77130-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="77130-119">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="77130-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="77130-120">Die maximale Pufferpoolgröße dieser Bindung.</span><span class="sxs-lookup"><span data-stu-id="77130-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="77130-121">Der Standardwert ist 524.288 Byte (512 × 1.024).</span><span class="sxs-lookup"><span data-stu-id="77130-121">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="77130-122">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="77130-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="77130-123">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="77130-123">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="77130-124">Bei Pufferpools können Sie dem Pool einen Puffer entnehmen, diesen verwenden und nach der Verwendung wieder in den Pool zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="77130-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="77130-125">Dadurch wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="77130-125">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="77130-126">Die maximale Nachrichtengröße in Byte einschließlich Header, die von einem mit dieser Bindung konfigurierten Kanal empfangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="77130-126">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="77130-127">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="77130-127">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="77130-128">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="77130-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="77130-129">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="77130-129">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="77130-130">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="77130-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="77130-131">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="77130-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="77130-132">-   `Text`: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="77130-132">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="77130-133">-   `Mtom`: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="77130-133">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="77130-134">Der Standardwert ist `Text`.</span><span class="sxs-lookup"><span data-stu-id="77130-134">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="77130-135">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="77130-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="77130-136">Der Konfigurationsname der Bindung.</span><span class="sxs-lookup"><span data-stu-id="77130-136">The configuration name of the binding.</span></span> <span data-ttu-id="77130-137">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77130-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="77130-138">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="77130-138">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="77130-139">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="77130-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="77130-140">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="77130-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="77130-141">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="77130-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="77130-142">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="77130-142">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="77130-143">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="77130-143">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="77130-144">Wenn `useSystemWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="77130-144">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="77130-145">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="77130-145">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="77130-146">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="77130-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="77130-147">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="77130-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="77130-148">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="77130-148">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="77130-149">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="77130-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="77130-150">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="77130-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="77130-151">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="77130-151">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="77130-152">Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="77130-152">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="77130-153">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="77130-153">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="77130-154">-   `UnicodeFffeTextEncoding`: Unicode Big-codierte Codierung.</span><span class="sxs-lookup"><span data-stu-id="77130-154">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="77130-155">-   `Utf16TextEncoding`: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="77130-155">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="77130-156">-   `Utf8TextEncoding`: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="77130-156">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="77130-157">Der Standardwert ist `Utf8TextEncoding`.</span><span class="sxs-lookup"><span data-stu-id="77130-157">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="77130-158">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="77130-158">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="77130-159">Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77130-159">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="77130-160">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="77130-160">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="77130-161">Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77130-161">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="77130-162">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="77130-162">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77130-163">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77130-163">Child Elements</span></span>  
  
|<span data-ttu-id="77130-164">Element</span><span class="sxs-lookup"><span data-stu-id="77130-164">Element</span></span>|<span data-ttu-id="77130-165">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="77130-165">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="77130-166">Definiert die Sicherheitseinstellungen für die Bindung.</span><span class="sxs-lookup"><span data-stu-id="77130-166">Defines the security settings for the binding.</span></span> <span data-ttu-id="77130-167">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="77130-167">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="77130-168">Definiert die Beschränkungen bezüglich der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="77130-168">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="77130-169">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="77130-169">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="77130-170">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="77130-170">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77130-171">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77130-171">Parent Elements</span></span>  
  
|<span data-ttu-id="77130-172">Element</span><span class="sxs-lookup"><span data-stu-id="77130-172">Element</span></span>|<span data-ttu-id="77130-173">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="77130-173">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="77130-174">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="77130-174">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77130-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77130-175">Remarks</span></span>  
 <span data-ttu-id="77130-176">Die `WS2007HttpBinding` fügt ähnlich wie `WSHttpBinding` eine vom System bereitgestellte Bindung hinzu, verwendet aber die OASIS-Standardversionen (Organization for the Advancement of Structured Information Standards) des ReliableSession-, Security- und TransactionFlow-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="77130-176">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="77130-177">Beim Verwenden dieser Bindung sind keine Änderungen am Objektmodell oder Standardeinstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77130-177">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77130-178">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77130-178">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77130-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77130-179">See also</span></span>

- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="77130-180">Bindungen</span><span class="sxs-lookup"><span data-stu-id="77130-180">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="77130-181">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="77130-181">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="77130-182">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="77130-182">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
