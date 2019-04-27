---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: e6215465acbf9bb94298d282d15f8735a0e20c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673081"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="56550-101">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="56550-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="56550-102">Eine sichere und interoperable Bindung, die abgeleitet [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) und verbundsicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56550-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <ws2007FederationHttpBinding>
```

## <a name="syntax"></a><span data-ttu-id="56550-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="56550-103">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="56550-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="56550-104">Attributes and Elements</span></span>

<span data-ttu-id="56550-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="56550-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="56550-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="56550-106">Attributes</span></span>

|<span data-ttu-id="56550-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="56550-107">Attribute</span></span>|<span data-ttu-id="56550-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56550-108">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="56550-109">Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="56550-109">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="56550-110">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="56550-110">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="56550-111">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56550-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="56550-112">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56550-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56550-113">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56550-113">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="56550-114">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="56550-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="56550-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56550-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="56550-116">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="56550-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="56550-117">Die maximale Pufferpoolgröße dieser Bindung.</span><span class="sxs-lookup"><span data-stu-id="56550-117">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="56550-118">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="56550-118">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="56550-119">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="56550-119">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="56550-120">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="56550-120">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="56550-121">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="56550-121">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="56550-122">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="56550-122">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="56550-123">Die maximale Nachrichtengröße in Byte einschließlich Header, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="56550-123">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="56550-124">Der Absender einer Nachricht, die diesen Grenzwert überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="56550-124">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="56550-125">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="56550-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="56550-126">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="56550-126">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="56550-127">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="56550-127">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="56550-128">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="56550-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="56550-129">-   Text: Verwenden Sie einen textnachrichtenencoder.</span><span class="sxs-lookup"><span data-stu-id="56550-129">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="56550-130">-Mtom: Verwenden Sie einen Encoder Message Transmission Organisation Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="56550-130">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="56550-131">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="56550-131">The default is Text.</span></span><br /><br /> <span data-ttu-id="56550-132">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="56550-132">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="56550-133">Der Konfigurationsname der Bindung.</span><span class="sxs-lookup"><span data-stu-id="56550-133">The configuration name of the binding.</span></span> <span data-ttu-id="56550-134">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56550-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="56550-135">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="56550-135">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="56550-136">Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="56550-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="56550-137">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56550-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="56550-138">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56550-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56550-139">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56550-139">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="56550-140">Ein URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="56550-140">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="56550-141">Die Version des aktuellen Datenschutzhinweises.</span><span class="sxs-lookup"><span data-stu-id="56550-141">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="56550-142">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="56550-142">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="56550-143">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="56550-143">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="56550-144">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="56550-144">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="56550-145">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56550-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="56550-146">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56550-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56550-147">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="56550-147">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="56550-148">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="56550-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="56550-149">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="56550-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="56550-150">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="56550-150">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="56550-151">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="56550-151">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="56550-152">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="56550-152">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="56550-153">-BigEndianUnicode: Unicode-bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="56550-153">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="56550-154">– Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="56550-154">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="56550-155">-   UTF8: 8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="56550-155">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="56550-156">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="56550-156">The default is UTF8.</span></span> <span data-ttu-id="56550-157">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="56550-157">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="56550-158">Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="56550-158">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="56550-159">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="56550-159">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="56550-160">Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="56550-160">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="56550-161">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="56550-161">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="56550-162">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="56550-162">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="56550-163">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56550-163">Child Elements</span></span>

|<span data-ttu-id="56550-164">Element</span><span class="sxs-lookup"><span data-stu-id="56550-164">Element</span></span>|<span data-ttu-id="56550-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56550-165">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56550-166">\<security></span><span class="sxs-lookup"><span data-stu-id="56550-166">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="56550-167">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="56550-167">Defines the security settings for the message.</span></span> <span data-ttu-id="56550-168">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="56550-168">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="56550-169">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="56550-169">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="56550-170">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="56550-170">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="56550-171">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="56550-171">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="56550-172">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="56550-172">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="56550-173">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="56550-173">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="56550-174">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="56550-174">Parent Elements</span></span>

|<span data-ttu-id="56550-175">Element</span><span class="sxs-lookup"><span data-stu-id="56550-175">Element</span></span>|<span data-ttu-id="56550-176">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56550-176">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56550-177">\<bindings></span><span class="sxs-lookup"><span data-stu-id="56550-177">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="56550-178">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="56550-178">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="56550-179">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56550-179">Remarks</span></span>

<span data-ttu-id="56550-180">Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten in mehreren Unternehmen oder vertrauenswürdigen Domänen für Authentifizierung und Autorisierung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="56550-180">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="56550-181">Er verwendet das WS-Trust-Protokoll, um die Identitätsdarstellung von einer vertrauenswürdigen Domäne zu einer anderen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="56550-181">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="56550-182">Eine verbundene HTTP-Bindung unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="56550-182">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="56550-183">Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="56550-183">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="56550-184">Weitere Informationen finden Sie unter [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="56550-184">For more information, see [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="56550-185">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56550-185">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="56550-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56550-186">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="56550-187">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="56550-187">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)
- [<span data-ttu-id="56550-188">Bindungen</span><span class="sxs-lookup"><span data-stu-id="56550-188">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="56550-189">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="56550-189">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="56550-190">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="56550-190">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="56550-191">\<binding></span><span class="sxs-lookup"><span data-stu-id="56550-191">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
