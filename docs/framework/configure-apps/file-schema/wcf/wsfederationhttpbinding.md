---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 3c4edc17fd669fbe23ec38ff26a61e867c04c561
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915070"
---
# <a name="wsfederationhttpbinding"></a><span data-ttu-id="654b6-101">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="654b6-101">\<wsFederationHttpBinding></span></span>

<span data-ttu-id="654b6-102">Definiert eine Bindung, die WS-Federation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="654b6-102">Defines a binding that supports WS-Federation.</span></span>

<span data-ttu-id="654b6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="654b6-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="654b6-104">\<Bindungen > </span><span class="sxs-lookup"><span data-stu-id="654b6-104">\<bindings></span></span>\
<span data-ttu-id="654b6-105">wsFederationBinding-Element</span><span class="sxs-lookup"><span data-stu-id="654b6-105">wsFederationBinding element</span></span>

## <a name="syntax"></a><span data-ttu-id="654b6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="654b6-106">Syntax</span></span>

```xml
<wsFederationHttpBinding>
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
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
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
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="654b6-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="654b6-107">Attributes and Elements</span></span>

<span data-ttu-id="654b6-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="654b6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="654b6-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="654b6-109">Attributes</span></span>

|<span data-ttu-id="654b6-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="654b6-110">Attribute</span></span>|<span data-ttu-id="654b6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654b6-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="654b6-112">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="654b6-112">bypassProxyOnLocal</span></span>|<span data-ttu-id="654b6-113">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="654b6-113">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="654b6-114">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="654b6-114">The default is `false`.</span></span>|
|<span data-ttu-id="654b6-115">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="654b6-115">closeTimeout</span></span>|<span data-ttu-id="654b6-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-116">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="654b6-117">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="654b6-117">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="654b6-118">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="654b6-118">The default is 00:01:00.</span></span>|
|<span data-ttu-id="654b6-119">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="654b6-119">hostnameComparisonMode</span></span>|<span data-ttu-id="654b6-120">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="654b6-120">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="654b6-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="654b6-121">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="654b6-122">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="654b6-122">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="654b6-123">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="654b6-123">maxBufferPoolSize</span></span>|<span data-ttu-id="654b6-124">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-124">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="654b6-125">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="654b6-125">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="654b6-126">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="654b6-126">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="654b6-127">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="654b6-127">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="654b6-128">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="654b6-128">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="654b6-129">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="654b6-129">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="654b6-130">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="654b6-130">maxReceivedMessageSize</span></span>|<span data-ttu-id="654b6-131">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="654b6-131">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="654b6-132">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="654b6-132">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="654b6-133">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="654b6-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="654b6-134">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="654b6-134">The default is 65536.</span></span>|
|<span data-ttu-id="654b6-135">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="654b6-135">messageEncoding</span></span>|<span data-ttu-id="654b6-136">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="654b6-136">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="654b6-137">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="654b6-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="654b6-138">Text Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="654b6-138">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="654b6-139">MTOM Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="654b6-139">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="654b6-140">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="654b6-140">The default is Text.</span></span><br /><br /> <span data-ttu-id="654b6-141">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="654b6-141">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="654b6-142">Name</span><span class="sxs-lookup"><span data-stu-id="654b6-142">name</span></span>|<span data-ttu-id="654b6-143">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="654b6-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="654b6-144">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="654b6-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="654b6-145">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="654b6-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="654b6-146">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="654b6-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="654b6-147">openTimeout</span><span class="sxs-lookup"><span data-stu-id="654b6-147">openTimeout</span></span>|<span data-ttu-id="654b6-148">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-148">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="654b6-149">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="654b6-149">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="654b6-150">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="654b6-150">The default is 00:01:00.</span></span>|
|<span data-ttu-id="654b6-151">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="654b6-151">privacyNoticeAt</span></span>|<span data-ttu-id="654b6-152">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="654b6-152">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="654b6-153">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="654b6-153">privacyNoticeVersion</span></span>|<span data-ttu-id="654b6-154">Eine ganze Zahl, die die Version des aktuellen Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-154">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="654b6-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="654b6-155">proxyAddress</span></span>|<span data-ttu-id="654b6-156">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="654b6-157">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="654b6-157">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="654b6-158">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="654b6-158">The default is `null`.</span></span>|
|<span data-ttu-id="654b6-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="654b6-159">receiveTimeout</span></span>|<span data-ttu-id="654b6-160">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="654b6-161">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="654b6-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="654b6-162">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="654b6-162">The default is 00:10:00.</span></span>|
|<span data-ttu-id="654b6-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="654b6-163">sendTimeout</span></span>|<span data-ttu-id="654b6-164">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="654b6-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="654b6-165">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="654b6-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="654b6-166">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="654b6-166">The default is 00:01:00.</span></span>|
|<span data-ttu-id="654b6-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="654b6-167">textEncoding</span></span>|<span data-ttu-id="654b6-168">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="654b6-168">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="654b6-169">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="654b6-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="654b6-170">BigEndianUnicode Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="654b6-170">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="654b6-171">Unicode- 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="654b6-171">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="654b6-172">UTF8 8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="654b6-172">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="654b6-173">Der Standard ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="654b6-173">The default is UTF8.</span></span> <span data-ttu-id="654b6-174">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="654b6-174">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="654b6-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="654b6-175">transactionFlow</span></span>|<span data-ttu-id="654b6-176">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="654b6-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="654b6-177">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="654b6-177">The default is `false`.</span></span>|
|<span data-ttu-id="654b6-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="654b6-178">useDefaultWebProxy</span></span>|<span data-ttu-id="654b6-179">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="654b6-179">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="654b6-180">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="654b6-180">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="654b6-181">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="654b6-181">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="654b6-182">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="654b6-182">Child Elements</span></span>

|<span data-ttu-id="654b6-183">Element</span><span class="sxs-lookup"><span data-stu-id="654b6-183">Element</span></span>|<span data-ttu-id="654b6-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654b6-184">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="654b6-185">\<security></span><span class="sxs-lookup"><span data-stu-id="654b6-185">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="654b6-186">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="654b6-186">Defines the security settings for the message.</span></span> <span data-ttu-id="654b6-187">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="654b6-187">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|<span data-ttu-id="654b6-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="654b6-188">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="654b6-189">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="654b6-189">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="654b6-190">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="654b6-190">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|<span data-ttu-id="654b6-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="654b6-191">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="654b6-192">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="654b6-192">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="654b6-193">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="654b6-193">Parent Elements</span></span>

|<span data-ttu-id="654b6-194">Element</span><span class="sxs-lookup"><span data-stu-id="654b6-194">Element</span></span>|<span data-ttu-id="654b6-195">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="654b6-195">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="654b6-196">\<bindings></span><span class="sxs-lookup"><span data-stu-id="654b6-196">\<bindings></span></span>](bindings.md)|<span data-ttu-id="654b6-197">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="654b6-197">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="654b6-198">Hinweise</span><span class="sxs-lookup"><span data-stu-id="654b6-198">Remarks</span></span>

<span data-ttu-id="654b6-199">Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten auf mehreren Systemen für Authentifizierung und Autorisierung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="654b6-199">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="654b6-200">Diese Identitäten können auf Benutzer oder Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="654b6-200">These identities can refer to users or to machines.</span></span> <span data-ttu-id="654b6-201">Verbundenes HTTP unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine exklusive Verwendung von Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="654b6-201">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="654b6-202">Diese Bindung bietet Windows Communication Foundation (WCF)-Unterstützung für das WS-Federation-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="654b6-202">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="654b6-203">Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="654b6-203">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="654b6-204">Bindungen bestehen aus einem Stapel von Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="654b6-204">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="654b6-205">Der Stapel von Bindungselementen in</span><span class="sxs-lookup"><span data-stu-id="654b6-205">The stack of binding elements in</span></span>

<span data-ttu-id="654b6-206">`wsFederationHttpBinding` ist mit dem Inhalt von `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="654b6-206">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="654b6-207">Wenn<xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> [ \<die Sicherheits >](security-of-wsfederationhttpbinding.md) auf den Standardwert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="654b6-207">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="654b6-208">Steuert die Details der Nachrichten Sicherheitseinstellungen in [ \<Message >.](message-element-of-wsfederationhttpbinding.md) `wsFederationHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="654b6-208">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="654b6-209">Beachten Sie, dass das [ \<Security >](security-of-wsfederationhttpbinding.md) -Element nur den Zugriff erhält, da die von der Bindung verwendete Sicherheit nicht geändert werden kann, nachdem die Bindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="654b6-209">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="654b6-210">Bietet `wsFederationHttpBinding` auch ein privacyNoticeAt-Attribut zum Festlegen und Abrufen des URIs, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="654b6-210">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="654b6-211">Das Sichern von Richtlinien ist vor allem in Verbundszenarien wichtig.</span><span class="sxs-lookup"><span data-stu-id="654b6-211">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="654b6-212">Es wird empfohlen, Sicherheitsfunktionen wie HTTPS einzusetzen, um die Richtlinie vor bösartigen Benutzern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="654b6-212">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="654b6-213">In Verbundszenarien, die diese Bindung nutzen, enthält die Dienstrichtlinie häufig wichtige Informationen, wie z.&#160;B. den Schlüssel für die Verschlüsselung des ausgestellten (SAML-) Tokens, den Anspruchstyp für das Token usw.</span><span class="sxs-lookup"><span data-stu-id="654b6-213">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="654b6-214">Wenn diese Richtlinie missbräuchlich genutzt wird, könnte ein Angreifer den Schlüssel des ausgestellten Tokens herausfinden und Informationen offen legen und andere böswillige Handlungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="654b6-214">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="654b6-215">Um dies zu vermeiden, muss die Richtlinie sicher vom Dienst abgerufen werden (z.&#160;B. über HTTPS).</span><span class="sxs-lookup"><span data-stu-id="654b6-215">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="654b6-216">Weitere Informationen zu dieser Bindung finden [Sie unter Gewusst wie: Erstellen Sie eine WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="654b6-216">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="654b6-217">Beispiel</span><span class="sxs-lookup"><span data-stu-id="654b6-217">Example</span></span>

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="654b6-218">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="654b6-218">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="654b6-219">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="654b6-219">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="654b6-220">Bindungen</span><span class="sxs-lookup"><span data-stu-id="654b6-220">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="654b6-221">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="654b6-221">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="654b6-222">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="654b6-222">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="654b6-223">\<binding></span><span class="sxs-lookup"><span data-stu-id="654b6-223">\<binding></span></span>](../../../misc/binding.md)
