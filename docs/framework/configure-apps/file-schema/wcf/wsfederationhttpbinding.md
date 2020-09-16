---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: a57b5ff0b4a8186ffc4c01b5e0824100f265551c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557280"
---
# \<wsFederationHttpBinding>

<span data-ttu-id="e1852-101">Definiert eine Bindung, die WS-Federation unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1852-101">Defines a binding that supports WS-Federation.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a><span data-ttu-id="e1852-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1852-102">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e1852-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1852-103">Attributes and Elements</span></span>

<span data-ttu-id="e1852-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1852-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e1852-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1852-105">Attributes</span></span>

|<span data-ttu-id="e1852-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e1852-106">Attribute</span></span>|<span data-ttu-id="e1852-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1852-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e1852-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="e1852-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="e1852-109">Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1852-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="e1852-110">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e1852-110">The default is `false`.</span></span>|
|<span data-ttu-id="e1852-111">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e1852-111">closeTimeout</span></span>|<span data-ttu-id="e1852-112">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e1852-113">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e1852-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1852-114">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1852-114">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e1852-115">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="e1852-115">hostnameComparisonMode</span></span>|<span data-ttu-id="e1852-116">Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="e1852-116">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="e1852-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1852-117">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="e1852-118">Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="e1852-118">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|
|<span data-ttu-id="e1852-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="e1852-119">maxBufferPoolSize</span></span>|<span data-ttu-id="e1852-120">Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="e1852-121">Der Standardwert ist 524.288 Byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="e1852-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="e1852-122">Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="e1852-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="e1852-123">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="e1852-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="e1852-124">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="e1852-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="e1852-125">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="e1852-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|
|<span data-ttu-id="e1852-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="e1852-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="e1852-127">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e1852-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="e1852-128">Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler.</span><span class="sxs-lookup"><span data-stu-id="e1852-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="e1852-129">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="e1852-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="e1852-130">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="e1852-130">The default is 65536.</span></span>|
|<span data-ttu-id="e1852-131">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="e1852-131">messageEncoding</span></span>|<span data-ttu-id="e1852-132">Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren.</span><span class="sxs-lookup"><span data-stu-id="e1852-132">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="e1852-133">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e1852-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e1852-134">-Text: Verwenden Sie einen Textnachrichten Encoder.</span><span class="sxs-lookup"><span data-stu-id="e1852-134">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="e1852-135">-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).</span><span class="sxs-lookup"><span data-stu-id="e1852-135">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="e1852-136">Der Standardwert ist Text.</span><span class="sxs-lookup"><span data-stu-id="e1852-136">The default is Text.</span></span><br /><br /> <span data-ttu-id="e1852-137">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="e1852-137">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|
|<span data-ttu-id="e1852-138">name</span><span class="sxs-lookup"><span data-stu-id="e1852-138">name</span></span>|<span data-ttu-id="e1852-139">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="e1852-139">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e1852-140">Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1852-140">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="e1852-141">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="e1852-141">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e1852-142">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e1852-142">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="e1852-143">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e1852-143">openTimeout</span></span>|<span data-ttu-id="e1852-144">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-144">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e1852-145">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e1852-145">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1852-146">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1852-146">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e1852-147">privacyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="e1852-147">privacyNoticeAt</span></span>|<span data-ttu-id="e1852-148">Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="e1852-148">A String that specifies a URI at which the privacy notice is located.</span></span>|
|<span data-ttu-id="e1852-149">privacyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="e1852-149">privacyNoticeVersion</span></span>|<span data-ttu-id="e1852-150">Eine ganze Zahl, die die Version des aktuellen Datenschutzhinweises angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-150">An integer that specifies the version of the current privacy notice.</span></span>|
|<span data-ttu-id="e1852-151">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="e1852-151">proxyAddress</span></span>|<span data-ttu-id="e1852-152">Ein URI, der die Adresse des HTTP-Proxys angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-152">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="e1852-153">Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten.</span><span class="sxs-lookup"><span data-stu-id="e1852-153">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="e1852-154">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="e1852-154">The default is `null`.</span></span>|
|<span data-ttu-id="e1852-155">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e1852-155">receiveTimeout</span></span>|<span data-ttu-id="e1852-156">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e1852-157">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e1852-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1852-158">Der Standardwert ist 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="e1852-158">The default is 00:10:00.</span></span>|
|<span data-ttu-id="e1852-159">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e1852-159">sendTimeout</span></span>|<span data-ttu-id="e1852-160">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e1852-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e1852-161">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e1852-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e1852-162">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e1852-162">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e1852-163">textEncoding</span><span class="sxs-lookup"><span data-stu-id="e1852-163">textEncoding</span></span>|<span data-ttu-id="e1852-164">Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1852-164">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e1852-165">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e1852-165">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e1852-166">-BigEndianUnicode: Unicode bigEndian-Codierung.</span><span class="sxs-lookup"><span data-stu-id="e1852-166">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="e1852-167">-Unicode: 16-Bit-Codierung.</span><span class="sxs-lookup"><span data-stu-id="e1852-167">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="e1852-168">-UTF8:8-Bit-Codierung</span><span class="sxs-lookup"><span data-stu-id="e1852-168">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="e1852-169">Der Standardwert ist UTF8.</span><span class="sxs-lookup"><span data-stu-id="e1852-169">The default is UTF8.</span></span> <span data-ttu-id="e1852-170">Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="e1852-170">This attribute is of type <xref:System.Text.Encoding>..</span></span>|
|<span data-ttu-id="e1852-171">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="e1852-171">transactionFlow</span></span>|<span data-ttu-id="e1852-172">Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1852-172">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="e1852-173">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e1852-173">The default is `false`.</span></span>|
|<span data-ttu-id="e1852-174">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="e1852-174">useDefaultWebProxy</span></span>|<span data-ttu-id="e1852-175">Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1852-175">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="e1852-176">Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="e1852-176">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="e1852-177">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="e1852-177">The default is `true`.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e1852-178">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1852-178">Child Elements</span></span>

|<span data-ttu-id="e1852-179">Element</span><span class="sxs-lookup"><span data-stu-id="e1852-179">Element</span></span>|<span data-ttu-id="e1852-180">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1852-180">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="e1852-181">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e1852-181">Defines the security settings for the message.</span></span> <span data-ttu-id="e1852-182">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e1852-182">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="e1852-183">Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="e1852-183">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e1852-184">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e1852-184">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="e1852-185">Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="e1852-185">Specifies if reliable sessions are established between channel endpoints.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e1852-186">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1852-186">Parent Elements</span></span>

|<span data-ttu-id="e1852-187">Element</span><span class="sxs-lookup"><span data-stu-id="e1852-187">Element</span></span>|<span data-ttu-id="e1852-188">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1852-188">Description</span></span>|
|-------------|-----------------|
|[\<bindings>](bindings.md)|<span data-ttu-id="e1852-189">Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.</span><span class="sxs-lookup"><span data-stu-id="e1852-189">This element holds a collection of standard and custom bindings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e1852-190">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1852-190">Remarks</span></span>

<span data-ttu-id="e1852-191">Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten auf mehreren Systemen für Authentifizierung und Autorisierung freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e1852-191">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="e1852-192">Diese Identitäten können auf Benutzer oder Computer verweisen.</span><span class="sxs-lookup"><span data-stu-id="e1852-192">These identities can refer to users or to machines.</span></span> <span data-ttu-id="e1852-193">Verbundenes HTTP unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine exklusive Verwendung von Transportsicherheit.</span><span class="sxs-lookup"><span data-stu-id="e1852-193">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="e1852-194">Diese Bindung bietet Windows Communication Foundation (WCF)-Unterstützung für das WS-Federation-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e1852-194">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="e1852-195">Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1852-195">Services configured with this binding must use the HTTP transport.</span></span>

<span data-ttu-id="e1852-196">Bindungen bestehen aus einem Stapel von Bindungselementen.</span><span class="sxs-lookup"><span data-stu-id="e1852-196">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="e1852-197">Der Stapel von Bindungselementen in</span><span class="sxs-lookup"><span data-stu-id="e1852-197">The stack of binding elements in</span></span>

<span data-ttu-id="e1852-198">`wsFederationHttpBinding` ist mit dem Inhalt von `wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="e1852-198">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>

<span data-ttu-id="e1852-199">Wenn [\<security>](security-of-wsfederationhttpbinding.md) auf den Standardwert festgelegt ist <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> .</span><span class="sxs-lookup"><span data-stu-id="e1852-199">when [\<security>](security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>

<span data-ttu-id="e1852-200">`wsFederationHttpBinding`Steuert die Details der Nachrichten Sicherheitseinstellungen in [\<message>](message-element-of-wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e1852-200">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="e1852-201">Beachten Sie, dass das- [\<security>](security-of-wsfederationhttpbinding.md) Element nur den Zugriff erhält, da die von der Bindung verwendete Sicherheit nicht geändert werden kann, nachdem die Bindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e1852-201">Note that the [\<security>](security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>

<span data-ttu-id="e1852-202">`wsFederationHttpBinding`Bietet auch ein privacyNoticeAt-Attribut zum Festlegen und Abrufen des URIs, an dem sich der Datenschutzhinweis befindet.</span><span class="sxs-lookup"><span data-stu-id="e1852-202">The `wsFederationHttpBinding` also provides a privacyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>

<span data-ttu-id="e1852-203">Das Sichern von Richtlinien ist vor allem in Verbundszenarien wichtig.</span><span class="sxs-lookup"><span data-stu-id="e1852-203">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="e1852-204">Es wird empfohlen, Sicherheitsfunktionen wie HTTPS einzusetzen, um die Richtlinie vor bösartigen Benutzern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e1852-204">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>

<span data-ttu-id="e1852-205">In Verbundszenarien, die diese Bindung nutzen, enthält die Dienstrichtlinie häufig wichtige Informationen, wie z.&#160;B. den Schlüssel für die Verschlüsselung des ausgestellten (SAML-) Tokens, den Anspruchstyp für das Token usw.</span><span class="sxs-lookup"><span data-stu-id="e1852-205">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="e1852-206">Wenn diese Richtlinie missbräuchlich genutzt wird, könnte ein Angreifer den Schlüssel des ausgestellten Tokens herausfinden und Informationen offen legen und andere böswillige Handlungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e1852-206">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="e1852-207">Um dies zu vermeiden, muss die Richtlinie sicher vom Dienst abgerufen werden (z.&#160;B. über HTTPS).</span><span class="sxs-lookup"><span data-stu-id="e1852-207">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>

<span data-ttu-id="e1852-208">Weitere Informationen zu dieser Bindung finden Sie unter Gewusst [wie: Erstellen einer WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e1852-208">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>

## <a name="example"></a><span data-ttu-id="e1852-209">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1852-209">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e1852-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1852-210">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [<span data-ttu-id="e1852-211">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e1852-211">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="e1852-212">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e1852-212">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e1852-213">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e1852-213">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e1852-214">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e1852-214">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
