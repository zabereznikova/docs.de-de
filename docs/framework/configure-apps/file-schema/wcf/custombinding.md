---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: 1fd0a12b62c416ce71946e59e7868abc7638a274
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398126"
---
# <a name="custombinding"></a><span data-ttu-id="e9ec5-101">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e9ec5-101">\<customBinding></span></span>

<span data-ttu-id="e9ec5-102">Stellt Vollzugriff auf den Nachrichtenstapel für den Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="e9ec5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9ec5-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e9ec5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e9ec5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<CustomBinding->**</span><span class="sxs-lookup"><span data-stu-id="e9ec5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="e9ec5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9ec5-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e9ec5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9ec5-108">Attributes and Elements</span></span>

<span data-ttu-id="e9ec5-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-109">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="e9ec5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9ec5-110">Attributes</span></span>

|<span data-ttu-id="e9ec5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e9ec5-111">Attribute</span></span>|<span data-ttu-id="e9ec5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9ec5-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e9ec5-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="e9ec5-113">closeTimeout</span></span>|<span data-ttu-id="e9ec5-114">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="e9ec5-115">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e9ec5-116">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-116">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e9ec5-117">Name</span><span class="sxs-lookup"><span data-stu-id="e9ec5-117">name</span></span>|<span data-ttu-id="e9ec5-118">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="e9ec5-119">Dieser Wert ist eine benutzerdefinierte Zeichenfolge, die als Identifikationszeichenfolge für die benutzerdefinierte Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="e9ec5-120">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="e9ec5-121">Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9ec5-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="e9ec5-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="e9ec5-122">openTimeout</span></span>|<span data-ttu-id="e9ec5-123">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="e9ec5-124">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e9ec5-125">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-125">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e9ec5-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="e9ec5-126">receiveTimeout</span></span>|<span data-ttu-id="e9ec5-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="e9ec5-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e9ec5-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-129">The default is 00:01:00.</span></span>|
|<span data-ttu-id="e9ec5-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="e9ec5-130">sendTimeout</span></span>|<span data-ttu-id="e9ec5-131">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="e9ec5-132">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="e9ec5-133">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-133">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e9ec5-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9ec5-134">Child Elements</span></span>

|<span data-ttu-id="e9ec5-135">Element</span><span class="sxs-lookup"><span data-stu-id="e9ec5-135">Element</span></span>|<span data-ttu-id="e9ec5-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9ec5-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9ec5-137">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="e9ec5-137">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="e9ec5-138">Legt bidirektionales Messaging für die benutzerdefinierte Bindung fest.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="e9ec5-139">Das Element wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="e9ec5-140">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="e9ec5-141">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="e9ec5-142">Die Clientadresse wird vom `ClientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="e9ec5-143">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="e9ec5-144">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="e9ec5-144">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="e9ec5-145">Gibt einen PNRP (Peer Name Resolution-Protokoll)-Peernamenresolver an.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="e9ec5-146">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="e9ec5-147">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="e9ec5-147">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="e9ec5-148">Legt die Einstellung für WS-Reliable Messaging fest.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="e9ec5-149">Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="e9ec5-150">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="e9ec5-151">\<security></span><span class="sxs-lookup"><span data-stu-id="e9ec5-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="e9ec5-152">Gibt die Sicherheitsoptionen für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="e9ec5-153">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="e9ec5-154">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e9ec5-154">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="e9ec5-155">Gibt die Sicherheitseinstellungen für eine SSL-Streambindung an.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="e9ec5-156">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="e9ec5-157">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="e9ec5-157">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="e9ec5-158">Legt fest, dass die Bindung Transaktionsfluss und das vom `transactionProtocol`-Attribut zu verwendende Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="e9ec5-159">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="e9ec5-160">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e9ec5-160">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="e9ec5-161">Gibt die Optionen für die Streamingsicherheit der benutzerdefinierten Bindung an.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="e9ec5-162">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e9ec5-163">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9ec5-163">Parent Elements</span></span>

|<span data-ttu-id="e9ec5-164">Element</span><span class="sxs-lookup"><span data-stu-id="e9ec5-164">Element</span></span>|<span data-ttu-id="e9ec5-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9ec5-165">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="e9ec5-166">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-166">bindings</span></span>|<span data-ttu-id="e9ec5-167">Enthält alle Bindungen für Windows Communication Foundation-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9ec5-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9ec5-168">Remarks</span></span>

<span data-ttu-id="e9ec5-169">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="e9ec5-170">Speziell angepasste Bindungen können durch Hinzufügen der Konfigurationselemente für bestimmte Entitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="e9ec5-171">Der Benutzer kann beispielsweise den Abschnitt `httpsTransport`, `reliableSession` und `security` zum Erstellen einer zuverlässigen und sicheren HTTPS-basierten Bindung kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="e9ec5-172">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="e9ec5-173">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="e9ec5-174">Es muss genau ein Transportelement in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="e9ec5-175">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-175">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="e9ec5-176">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="e9ec5-177">Die empfohlene Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-177">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="e9ec5-178">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-178">Transactions (optional)</span></span>

2. <span data-ttu-id="e9ec5-179">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-179">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="e9ec5-180">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-180">Security (optional)</span></span>

4. <span data-ttu-id="e9ec5-181">Transport</span><span class="sxs-lookup"><span data-stu-id="e9ec5-181">Transport</span></span>

5. <span data-ttu-id="e9ec5-182">Encoder (optional)</span><span class="sxs-lookup"><span data-stu-id="e9ec5-182">Encoder (optional)</span></span>

<span data-ttu-id="e9ec5-183">Verwenden Sie eine benutzerdefinierte Bindung, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="e9ec5-184">Eine benutzerdefinierte Bindung kann beispielsweise verwendet werden, um die Nutzung eines neuen Transports oder eines neuen Encoders an einem Dienstendpunkt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="e9ec5-185">Eine benutzerdefinierte Bindung wird durch Verwendung einer der <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> aus einer Sammlung an Bindungselementen erstellt, die in einer spezifischen Reihenfolge "gestapelt" sind:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="e9ec5-186">Oben ist ein optionales <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, das einen Transaktionsfluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="e9ec5-187">Darauf folgt ein optionales <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, das eine Sitzung und einen Sortiermechanismus bereitstellt, wie es in der WS-ReliableMessaging-Spezifikation definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="e9ec5-188">Dieses Konzept einer Sitzung kann SOAP und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="e9ec5-189">Darauf folgt ein optionales Sicherheitsbindungselement, das Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="e9ec5-190">Die folgenden sicherheitsbindungs Elemente werden von Windows Communication Foundation (WCF) bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-190">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="e9ec5-191">Darauf folgen die optionalen Nachrichtenmuster, die von den Bindungselementen spezifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-191">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="e9ec5-192">Darauf folgen die optionalen Transport-Upgrades/unterstützenden Bindungselemente:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-192">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="e9ec5-193">Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="e9ec5-194">Sie können einen eigenen Transport verwenden oder die folgenden Nachrichten codierenden Bindungen:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-194">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="e9ec5-195">Am Ende befindet sich ein erforderliches Transportelement.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="e9ec5-196">Sie können einen eigenen Transport verwenden oder eines der Transport Bindungs Elemente verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="e9ec5-196">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="e9ec5-197">In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-197">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="e9ec5-198">Ebene</span><span class="sxs-lookup"><span data-stu-id="e9ec5-198">Layer</span></span>|<span data-ttu-id="e9ec5-199">Optionen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-199">Options</span></span>|<span data-ttu-id="e9ec5-200">Required</span><span class="sxs-lookup"><span data-stu-id="e9ec5-200">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="e9ec5-201">Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="e9ec5-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="e9ec5-202">Nein</span><span class="sxs-lookup"><span data-stu-id="e9ec5-202">No</span></span>|
|<span data-ttu-id="e9ec5-203">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="e9ec5-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="e9ec5-204">Nein</span><span class="sxs-lookup"><span data-stu-id="e9ec5-204">No</span></span>|
|<span data-ttu-id="e9ec5-205">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e9ec5-205">Security</span></span>|<span data-ttu-id="e9ec5-206">Symmetrisch, asymmetrisch, auf Transportebene</span><span class="sxs-lookup"><span data-stu-id="e9ec5-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="e9ec5-207">Nein</span><span class="sxs-lookup"><span data-stu-id="e9ec5-207">No</span></span>|
|<span data-ttu-id="e9ec5-208">Formänderung</span><span class="sxs-lookup"><span data-stu-id="e9ec5-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="e9ec5-209">Nein</span><span class="sxs-lookup"><span data-stu-id="e9ec5-209">No</span></span>|
|<span data-ttu-id="e9ec5-210">Transport-Upgrades</span><span class="sxs-lookup"><span data-stu-id="e9ec5-210">Transport Upgrades</span></span>|<span data-ttu-id="e9ec5-211">SSL-Stream, Windows-Stream, Peerresolver</span><span class="sxs-lookup"><span data-stu-id="e9ec5-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="e9ec5-212">Nein</span><span class="sxs-lookup"><span data-stu-id="e9ec5-212">No</span></span>|
|<span data-ttu-id="e9ec5-213">Codierung</span><span class="sxs-lookup"><span data-stu-id="e9ec5-213">Encoding</span></span>|<span data-ttu-id="e9ec5-214">Text, Binärdatei, MTOM, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="e9ec5-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="e9ec5-215">Ja</span><span class="sxs-lookup"><span data-stu-id="e9ec5-215">Yes</span></span>|
|<span data-ttu-id="e9ec5-216">Transport</span><span class="sxs-lookup"><span data-stu-id="e9ec5-216">Transport</span></span>|<span data-ttu-id="e9ec5-217">TCP, Named Pipes, HTTP, HTTPS, Typen der MSMQ, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="e9ec5-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="e9ec5-218">Ja</span><span class="sxs-lookup"><span data-stu-id="e9ec5-218">Yes</span></span>|

<span data-ttu-id="e9ec5-219">Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="e9ec5-220">Eine Erläuterung zur Verwendung einer benutzerdefinierten Bindung zum Ändern einer vom System bereitgestellten Bindung finden [Sie unter Gewusst wie: Passen Sie eine vom System bereit](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)gestellte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="e9ec5-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9ec5-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9ec5-221">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e9ec5-222">\<binding></span><span class="sxs-lookup"><span data-stu-id="e9ec5-222">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="e9ec5-223">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-223">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e9ec5-224">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-224">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e9ec5-225">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-225">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e9ec5-226">CustomBinding-Element</span><span class="sxs-lookup"><span data-stu-id="e9ec5-226">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="e9ec5-227">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-227">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e9ec5-228">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e9ec5-228">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e9ec5-229">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e9ec5-229">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
