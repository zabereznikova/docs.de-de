---
title: <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
ms.openlocfilehash: 20ba643fddbac8a488e5457f0195cc253d4d23f7
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139314"
---
# <a name="ws2007federationhttpbinding"></a><span data-ttu-id="ab97b-101">\<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ab97b-101">\<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="ab97b-102">Eine sichere und interoperable Bindung, die von [\<WSFederationHttpBinding->](wsfederationhttpbinding.md) abgeleitet ist und Verbund Sicherheit unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-102">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) and supports federated security.</span></span>

<span data-ttu-id="ab97b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ab97b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ab97b-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ab97b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ab97b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ab97b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ab97b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WS2007FederationHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="ab97b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab97b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab97b-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ab97b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab97b-108">Attributes and Elements</span></span>

<span data-ttu-id="ab97b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab97b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab97b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab97b-110">Attributes</span></span>

|<span data-ttu-id="ab97b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ab97b-111">Attribute</span></span>|<span data-ttu-id="ab97b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab97b-112">Description</span></span>|
|---------------|-----------------|
|`bypassProxyOnLocal`|<span data-ttu-id="ab97b-113">Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab97b-113">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="ab97b-114">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ab97b-114">The default is `false`.</span></span>|
|`closeTimeout`|<span data-ttu-id="ab97b-115">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="ab97b-116">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ab97b-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab97b-117">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab97b-117">The default is 00:01:00.</span></span>|
|`hostNameComparisonMode`|<span data-ttu-id="ab97b-118">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="ab97b-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="ab97b-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab97b-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="ab97b-120">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="ab97b-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|`maxBufferPoolSize`|<span data-ttu-id="ab97b-121">Die maximale Pufferpoolgröße dieser Bindung.</span><span class="sxs-lookup"><span data-stu-id="ab97b-121">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="ab97b-122">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="ab97b-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="ab97b-123">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="ab97b-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="ab97b-124">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="ab97b-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="ab97b-125">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="ab97b-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="ab97b-126">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="ab97b-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|`maxReceivedMessageSize`|<span data-ttu-id="ab97b-127">Die maximale Nachrichtengröße in Byte einschließlich Header, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="ab97b-127">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="ab97b-128">Der Absender einer Nachricht, die diesen Grenzwert überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="ab97b-128">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="ab97b-129">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ab97b-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ab97b-130">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="ab97b-130">The default is 65536.</span></span>|
|`messageEncoding`|<span data-ttu-id="ab97b-131">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="ab97b-131">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="ab97b-132">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ab97b-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ab97b-133">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="ab97b-133">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="ab97b-134">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="ab97b-134">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="ab97b-135">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="ab97b-135">The default is Text.</span></span><br /><br /> <span data-ttu-id="ab97b-136">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="ab97b-136">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|`name`|<span data-ttu-id="ab97b-137">Der Konfigurationsname der Bindung.</span><span class="sxs-lookup"><span data-stu-id="ab97b-137">The configuration name of the binding.</span></span> <span data-ttu-id="ab97b-138">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab97b-138">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ab97b-139">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="ab97b-139">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ab97b-140">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab97b-140">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|`openTimeout`|<span data-ttu-id="ab97b-141">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ab97b-142">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ab97b-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab97b-143">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab97b-143">The default is 00:01:00.</span></span>|
|`privacyNoticeAt`|<span data-ttu-id="ab97b-144">Ein URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="ab97b-144">A URI at which the privacy notice is located.</span></span>|
|`privacyNoticeVersion`|<span data-ttu-id="ab97b-145">Die Version des aktuellen Datenschutzhinweises.</span><span class="sxs-lookup"><span data-stu-id="ab97b-145">The version of the current privacy notice.</span></span>|
|`proxyAddress`|<span data-ttu-id="ab97b-146">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-146">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="ab97b-147">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="ab97b-147">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="ab97b-148">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ab97b-148">The default is `null`.</span></span>|
|`receiveTimeout`|<span data-ttu-id="ab97b-149">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ab97b-150">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ab97b-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab97b-151">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="ab97b-151">The default is 00:10:00.</span></span>|
|`sendTimeout`|<span data-ttu-id="ab97b-152">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ab97b-153">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="ab97b-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ab97b-154">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="ab97b-154">The default is 00:01:00.</span></span>|
|`textEncoding`|<span data-ttu-id="ab97b-155">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab97b-155">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="ab97b-156">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ab97b-156">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ab97b-157">-BigEndianUnicode: Unicode Big Endian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ab97b-157">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="ab97b-158">-Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ab97b-158">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="ab97b-159">-UTF8:8-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="ab97b-159">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="ab97b-160">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="ab97b-160">The default is UTF8.</span></span> <span data-ttu-id="ab97b-161">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="ab97b-161">This attribute is of type <xref:System.Text.Encoding>.</span></span>|
|`transactionFlow`|<span data-ttu-id="ab97b-162">Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ab97b-162">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="ab97b-163">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ab97b-163">The default is `false`.</span></span>|
|`useDefaultWebProxy`|<span data-ttu-id="ab97b-164">Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab97b-164">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="ab97b-165">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="ab97b-165">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="ab97b-166">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="ab97b-166">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ab97b-167">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab97b-167">Child Elements</span></span>

|<span data-ttu-id="ab97b-168">Element</span><span class="sxs-lookup"><span data-stu-id="ab97b-168">Element</span></span>|<span data-ttu-id="ab97b-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab97b-169">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab97b-170">\<Sicherheits ></span><span class="sxs-lookup"><span data-stu-id="ab97b-170">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="ab97b-171">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ab97b-171">Defines the security settings for the message.</span></span> <span data-ttu-id="ab97b-172">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ab97b-172">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="ab97b-173">[\<von Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ab97b-173">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="ab97b-174">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="ab97b-174">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="ab97b-175">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="ab97b-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="ab97b-176">[\<ReliableSession->](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ab97b-176">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="ab97b-177">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="ab97b-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ab97b-178">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab97b-178">Parent Elements</span></span>

|<span data-ttu-id="ab97b-179">Element</span><span class="sxs-lookup"><span data-stu-id="ab97b-179">Element</span></span>|<span data-ttu-id="ab97b-180">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab97b-180">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab97b-181">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="ab97b-181">\<bindings></span></span>](bindings.md)|<span data-ttu-id="ab97b-182">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="ab97b-182">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab97b-183">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab97b-183">Remarks</span></span>

<span data-ttu-id="ab97b-184">Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten in mehreren Unternehmen oder vertrauenswürdigen Domänen für Authentifizierung und Autorisierung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ab97b-184">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="ab97b-185">Er verwendet das WS-Trust-Protokoll, um die Identitätsdarstellung von einer vertrauenswürdigen Domäne zu einer anderen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ab97b-185">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="ab97b-186">Eine verbundene HTTP-Bindung unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="ab97b-186">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="ab97b-187">Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab97b-187">Services configured with this binding must use the HTTP transport.</span></span> <span data-ttu-id="ab97b-188">Weitere Informationen finden Sie unter [\<WSFederationHttpBinding >](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ab97b-188">For more information, see [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="ab97b-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab97b-189">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ab97b-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab97b-190">See also</span></span>

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [<span data-ttu-id="ab97b-191">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ab97b-191">\<wsFederationHttpBinding></span></span>](wsfederationhttpbinding.md)
- [<span data-ttu-id="ab97b-192">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ab97b-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ab97b-193">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ab97b-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ab97b-194">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ab97b-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ab97b-195">\<Bindungs ></span><span class="sxs-lookup"><span data-stu-id="ab97b-195">\<binding></span></span>](bindings.md)
