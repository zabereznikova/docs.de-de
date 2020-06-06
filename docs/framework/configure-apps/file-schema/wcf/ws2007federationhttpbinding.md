---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139314"
---
# \<ws2007FederationHttpBinding>

<span data-ttu-id="9f924-101">Eine sichere und interoperable Bindung, die von abgeleitet ist [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) und Verbund Sicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f924-101">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="9f924-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f924-102">Syntax</span></span>

```xml
<ws2007FederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007FederationHttpBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f924-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f924-103">Attributes and Elements</span></span>

<span data-ttu-id="9f924-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f924-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f924-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f924-105">Attributes</span></span>

|<span data-ttu-id="9f924-106">attribute</span><span class="sxs-lookup"><span data-stu-id="9f924-106">Attribute</span></span>|<span data-ttu-id="9f924-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f924-107">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="9f924-108">Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f924-108">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="9f924-109">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="9f924-109">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="9f924-110">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="9f924-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9f924-111">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="9f924-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f924-112">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9f924-112">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="9f924-113">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="9f924-113">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="9f924-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f924-114">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="9f924-115">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="9f924-115">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="9f924-116">Die maximale Pufferpoolgröße dieser Bindung.</span><span class="sxs-lookup"><span data-stu-id="9f924-116">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9f924-117">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="9f924-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="9f924-118">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="9f924-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="9f924-119">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="9f924-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="9f924-120">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="9f924-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="9f924-121">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="9f924-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="9f924-122">Die maximale Nachrichtengröße in Byte einschließlich Header, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="9f924-122">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="9f924-123">Der Absender einer Nachricht, die diesen Grenzwert überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="9f924-123">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="9f924-124">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="9f924-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9f924-125">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="9f924-125">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="9f924-126">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="9f924-126">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="9f924-127">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9f924-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f924-128">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="9f924-128">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="9f924-129">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="9f924-129">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="9f924-130">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="9f924-130">The default is Text.</span></span><br /><br /> <span data-ttu-id="9f924-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="9f924-131">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="9f924-132">Der Konfigurationsname der Bindung.</span><span class="sxs-lookup"><span data-stu-id="9f924-132">The configuration name of the binding.</span></span> <span data-ttu-id="9f924-133">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f924-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9f924-134">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="9f924-134">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9f924-135">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9f924-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="9f924-136">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="9f924-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9f924-137">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="9f924-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f924-138">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9f924-138">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="9f924-139">Ein URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="9f924-139">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="9f924-140">Die Version des aktuellen Datenschutzhinweises.</span><span class="sxs-lookup"><span data-stu-id="9f924-140">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="9f924-141">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="9f924-141">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="9f924-142">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="9f924-142">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="9f924-143">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="9f924-143">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="9f924-144">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="9f924-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9f924-145">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="9f924-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f924-146">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="9f924-146">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="9f924-147">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="9f924-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9f924-148">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="9f924-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f924-149">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9f924-149">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="9f924-150">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f924-150">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9f924-151">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9f924-151">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f924-152">-BigEndianUnicode: Unicode Big Endian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="9f924-152">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="9f924-153">-Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="9f924-153">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="9f924-154">-UTF8:8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="9f924-154">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="9f924-155">Der Standardwert ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="9f924-155">The default is UTF8.</span></span> <span data-ttu-id="9f924-156">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="9f924-156">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="9f924-157">Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f924-157">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="9f924-158">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="9f924-158">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="9f924-159">Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f924-159">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="9f924-160">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="9f924-160">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="9f924-161">Der Standardwert lautet `true`.</span><span class="sxs-lookup"><span data-stu-id="9f924-161">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9f924-162">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f924-162">Child Elements</span></span>

|<span data-ttu-id="9f924-163">Element</span><span class="sxs-lookup"><span data-stu-id="9f924-163">Element</span></span>|<span data-ttu-id="9f924-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f924-164">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="9f924-165">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9f924-165">Defines the security settings for the message.</span></span> <span data-ttu-id="9f924-166">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9f924-166">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="9f924-167">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="9f924-167">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9f924-168">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="9f924-168">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="9f924-169">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="9f924-169">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9f924-170">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f924-170">Parent Elements</span></span>

|<span data-ttu-id="9f924-171">Element</span><span class="sxs-lookup"><span data-stu-id="9f924-171">Element</span></span>|<span data-ttu-id="9f924-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f924-172">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="9f924-173">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="9f924-173">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9f924-174">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9f924-174">Remarks</span></span>

<span data-ttu-id="9f924-175">Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten in mehreren Unternehmen oder vertrauenswürdigen Domänen für Authentifizierung und Autorisierung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="9f924-175">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="9f924-176">Er verwendet das WS-Trust-Protokoll, um die Identitätsdarstellung von einer vertrauenswürdigen Domäne zu einer anderen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="9f924-176">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="9f924-177">Eine verbundene HTTP-Bindung unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="9f924-177">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="9f924-178">Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f924-178">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="9f924-179">Weitere Informationen finden Sie unter [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9f924-179">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="9f924-180">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f924-180">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007FederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </ws2007FederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9f924-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f924-181">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [<span data-ttu-id="9f924-182">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f924-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9f924-183">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f924-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9f924-184">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9f924-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
