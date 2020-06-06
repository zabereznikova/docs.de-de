---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140791"
---
# \<customBinding>

<span data-ttu-id="fd44b-101">Stellt Vollzugriff auf den Nachrichtenstapel für den Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="fd44b-101">Provides full control over the messaging stack for the user.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a><span data-ttu-id="fd44b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd44b-102">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fd44b-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fd44b-103">Attributes and Elements</span></span>

<span data-ttu-id="fd44b-104">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd44b-104">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="fd44b-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="fd44b-105">Attributes</span></span>

|<span data-ttu-id="fd44b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="fd44b-106">Attribute</span></span>|<span data-ttu-id="fd44b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fd44b-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="fd44b-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="fd44b-108">closeTimeout</span></span>|<span data-ttu-id="fd44b-109">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="fd44b-110">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fd44b-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fd44b-111">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fd44b-111">The default is 00:01:00.</span></span>|
|<span data-ttu-id="fd44b-112">name</span><span class="sxs-lookup"><span data-stu-id="fd44b-112">name</span></span>|<span data-ttu-id="fd44b-113">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="fd44b-113">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="fd44b-114">Dieser Wert ist eine benutzerdefinierte Zeichenfolge, die als Identifikationszeichenfolge für die benutzerdefinierte Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="fd44b-114">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="fd44b-115">Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="fd44b-115">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="fd44b-116">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="fd44b-116">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="fd44b-117">openTimeout</span><span class="sxs-lookup"><span data-stu-id="fd44b-117">openTimeout</span></span>|<span data-ttu-id="fd44b-118">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-118">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="fd44b-119">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fd44b-119">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fd44b-120">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fd44b-120">The default is 00:01:00.</span></span>|
|<span data-ttu-id="fd44b-121">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="fd44b-121">receiveTimeout</span></span>|<span data-ttu-id="fd44b-122">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="fd44b-123">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fd44b-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fd44b-124">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fd44b-124">The default is 00:01:00.</span></span>|
|<span data-ttu-id="fd44b-125">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="fd44b-125">sendTimeout</span></span>|<span data-ttu-id="fd44b-126">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="fd44b-127">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="fd44b-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="fd44b-128">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="fd44b-128">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fd44b-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd44b-129">Child Elements</span></span>

|<span data-ttu-id="fd44b-130">Element</span><span class="sxs-lookup"><span data-stu-id="fd44b-130">Element</span></span>|<span data-ttu-id="fd44b-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd44b-131">Description</span></span>|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|<span data-ttu-id="fd44b-132">Legt bidirektionales Messaging für die benutzerdefinierte Bindung fest.</span><span class="sxs-lookup"><span data-stu-id="fd44b-132">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="fd44b-133">Das Element wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="fd44b-133">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="fd44b-134">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. </span><span class="sxs-lookup"><span data-stu-id="fd44b-134">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="fd44b-135">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="fd44b-135">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="fd44b-136">Die Clientadresse wird vom `ClientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-136">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="fd44b-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-137">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|<span data-ttu-id="fd44b-138">Gibt einen PNRP (Peer Name Resolution-Protokoll)-Peernamenresolver an.</span><span class="sxs-lookup"><span data-stu-id="fd44b-138">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="fd44b-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-139">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[\<reliableSession>](reliablesession.md)|<span data-ttu-id="fd44b-140">Legt die Einstellung für WS-Reliable Messaging fest.</span><span class="sxs-lookup"><span data-stu-id="fd44b-140">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="fd44b-141">Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fd44b-141">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="fd44b-142">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-142">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="fd44b-143">Gibt die Sicherheitsoptionen für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="fd44b-143">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="fd44b-144">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-144">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|<span data-ttu-id="fd44b-145">Gibt die Sicherheitseinstellungen für eine SSL-Streambindung an.</span><span class="sxs-lookup"><span data-stu-id="fd44b-145">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="fd44b-146">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-146">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[\<transactionFlow>](transactionflow.md)|<span data-ttu-id="fd44b-147">Legt fest, dass die Bindung Transaktionsfluss und das vom `transactionProtocol`-Attribut zu verwendende Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-147">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="fd44b-148">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-148">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|<span data-ttu-id="fd44b-149">Gibt die Optionen für die Streamingsicherheit der benutzerdefinierten Bindung an.</span><span class="sxs-lookup"><span data-stu-id="fd44b-149">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="fd44b-150">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fd44b-150">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fd44b-151">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fd44b-151">Parent Elements</span></span>

|<span data-ttu-id="fd44b-152">Element</span><span class="sxs-lookup"><span data-stu-id="fd44b-152">Element</span></span>|<span data-ttu-id="fd44b-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd44b-153">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="fd44b-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-154">bindings</span></span>|<span data-ttu-id="fd44b-155">Enthält alle Bindungen für Windows Communication Foundation-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fd44b-155">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fd44b-156">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-156">Remarks</span></span>

<span data-ttu-id="fd44b-157">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="fd44b-157">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="fd44b-158">Speziell angepasste Bindungen können durch Hinzufügen der Konfigurationselemente für bestimmte Entitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd44b-158">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="fd44b-159">Der Benutzer kann beispielsweise den Abschnitt `httpsTransport`, `reliableSession` und `security` zum Erstellen einer zuverlässigen und sicheren HTTPS-basierten Bindung kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fd44b-159">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="fd44b-160">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="fd44b-160">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="fd44b-161">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="fd44b-161">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="fd44b-162">Es muss genau ein Transportelement in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="fd44b-162">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="fd44b-163">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="fd44b-163">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="fd44b-164">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd44b-164">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="fd44b-165">Die empfohlene Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="fd44b-165">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="fd44b-166">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="fd44b-166">Transactions (optional)</span></span>

2. <span data-ttu-id="fd44b-167">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="fd44b-167">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="fd44b-168">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="fd44b-168">Security (optional)</span></span>

4. <span data-ttu-id="fd44b-169">Transport</span><span class="sxs-lookup"><span data-stu-id="fd44b-169">Transport</span></span>

5. <span data-ttu-id="fd44b-170">Encoder (optional)</span><span class="sxs-lookup"><span data-stu-id="fd44b-170">Encoder (optional)</span></span>

<span data-ttu-id="fd44b-171">Verwenden Sie eine benutzerdefinierte Bindung, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-171">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="fd44b-172">Eine benutzerdefinierte Bindung kann beispielsweise verwendet werden, um die Nutzung eines neuen Transports oder eines neuen Encoders an einem Dienstendpunkt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd44b-172">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="fd44b-173">Eine benutzerdefinierte Bindung wird durch Verwendung einer der <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> aus einer Sammlung an Bindungselementen erstellt, die in einer spezifischen Reihenfolge "gestapelt" sind:</span><span class="sxs-lookup"><span data-stu-id="fd44b-173">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="fd44b-174">Oben ist ein optionales <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, das einen Transaktionsfluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fd44b-174">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="fd44b-175">Darauf folgt ein optionales <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, das eine Sitzung und einen Sortiermechanismus bereitstellt, wie es in der WS-ReliableMessaging-Spezifikation definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fd44b-175">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="fd44b-176">Dieses Konzept einer Sitzung kann SOAP und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="fd44b-176">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="fd44b-177">Darauf folgt ein optionales Sicherheitsbindungselement, das Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fd44b-177">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="fd44b-178">Die folgenden sicherheitsbindungs Elemente werden von Windows Communication Foundation (WCF) bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="fd44b-178">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="fd44b-179">Darauf folgen die optionalen Nachrichtenmuster, die von den Bindungselementen spezifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="fd44b-179">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="fd44b-180">Darauf folgen die optionalen Transport-Upgrades/unterstützenden Bindungselemente:</span><span class="sxs-lookup"><span data-stu-id="fd44b-180">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="fd44b-181">Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="fd44b-181">Next is a required message encoding binding element.</span></span> <span data-ttu-id="fd44b-182">Sie können einen eigenen Transport verwenden oder die folgenden Nachrichten codierenden Bindungen:</span><span class="sxs-lookup"><span data-stu-id="fd44b-182">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="fd44b-183">Am Ende befindet sich ein erforderliches Transportelement.</span><span class="sxs-lookup"><span data-stu-id="fd44b-183">At the bottom is a required transport element.</span></span> <span data-ttu-id="fd44b-184">Sie können einen eigenen Transport verwenden oder eines der Transport Bindungs Elemente verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="fd44b-184">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="fd44b-185">In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fd44b-185">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="fd44b-186">Ebene</span><span class="sxs-lookup"><span data-stu-id="fd44b-186">Layer</span></span>|<span data-ttu-id="fd44b-187">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fd44b-187">Options</span></span>|<span data-ttu-id="fd44b-188">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="fd44b-188">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="fd44b-189">Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="fd44b-189">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="fd44b-190">Nein</span><span class="sxs-lookup"><span data-stu-id="fd44b-190">No</span></span>|
|<span data-ttu-id="fd44b-191">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="fd44b-191">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="fd44b-192">Nein</span><span class="sxs-lookup"><span data-stu-id="fd44b-192">No</span></span>|
|<span data-ttu-id="fd44b-193">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="fd44b-193">Security</span></span>|<span data-ttu-id="fd44b-194">Symmetrisch, asymmetrisch, auf Transportebene</span><span class="sxs-lookup"><span data-stu-id="fd44b-194">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="fd44b-195">Nein</span><span class="sxs-lookup"><span data-stu-id="fd44b-195">No</span></span>|
|<span data-ttu-id="fd44b-196">Formänderung</span><span class="sxs-lookup"><span data-stu-id="fd44b-196">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="fd44b-197">Nein</span><span class="sxs-lookup"><span data-stu-id="fd44b-197">No</span></span>|
|<span data-ttu-id="fd44b-198">Transport-Upgrades</span><span class="sxs-lookup"><span data-stu-id="fd44b-198">Transport Upgrades</span></span>|<span data-ttu-id="fd44b-199">SSL-Stream, Windows-Stream, Peerresolver</span><span class="sxs-lookup"><span data-stu-id="fd44b-199">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="fd44b-200">Nein</span><span class="sxs-lookup"><span data-stu-id="fd44b-200">No</span></span>|
|<span data-ttu-id="fd44b-201">Codieren</span><span class="sxs-lookup"><span data-stu-id="fd44b-201">Encoding</span></span>|<span data-ttu-id="fd44b-202">Text, Binärdatei, MTOM, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="fd44b-202">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="fd44b-203">Ja</span><span class="sxs-lookup"><span data-stu-id="fd44b-203">Yes</span></span>|
|<span data-ttu-id="fd44b-204">Transport</span><span class="sxs-lookup"><span data-stu-id="fd44b-204">Transport</span></span>|<span data-ttu-id="fd44b-205">TCP, Named Pipes, HTTP, HTTPS, Typen der MSMQ, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="fd44b-205">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="fd44b-206">Ja</span><span class="sxs-lookup"><span data-stu-id="fd44b-206">Yes</span></span>|

<span data-ttu-id="fd44b-207">Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="fd44b-207">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="fd44b-208">Eine Erläuterung zur Verwendung einer benutzerdefinierten Bindung zum Ändern einer vom System bereitgestellten Bindung finden Sie unter Gewusst [wie: Anpassen einer vom System bereit](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)gestellten Bindung.</span><span class="sxs-lookup"><span data-stu-id="fd44b-208">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd44b-209">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd44b-209">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [<span data-ttu-id="fd44b-210">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-210">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fd44b-211">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-211">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fd44b-212">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-212">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fd44b-213">CustomBinding-Element</span><span class="sxs-lookup"><span data-stu-id="fd44b-213">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="fd44b-214">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-214">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fd44b-215">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fd44b-215">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fd44b-216">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fd44b-216">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
