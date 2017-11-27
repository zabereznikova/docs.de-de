---
title: '&lt;customBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f73ad4d09e085040e006102e5b44664ece98a58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustombindinggt"></a><span data-ttu-id="1cd15-102">&lt;customBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1cd15-102">&lt;customBinding&gt;</span></span>
<span data-ttu-id="1cd15-103">Stellt Vollzugriff auf den Nachrichtenstapel für den Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="1cd15-103">Provides full control over the messaging stack for the user.</span></span>  
  
 <span data-ttu-id="1cd15-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1cd15-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1cd15-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="1cd15-105">\<bindings></span></span>  
<span data-ttu-id="1cd15-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="1cd15-106">\<customBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd15-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1cd15-107">Syntax</span></span>  
  
```xml  
<customBinding>  
    <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
       <compositeDuplex clientBaseAddress="Uri"/>  
       <reliableSession acknowledgementInterval="TimeSpan"  
           advancedFlowControl="Boolean"   
           bufferedMessagesQuota="Integer"  
           inactivityTimeout="TimeSpan"  
           maxPendingChannels="Integer"  
           maxRetryCount="Integer"   
           ordered="Boolean" />  
       <pnrpPeerResolver />  
       <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
       <sslStreamSecurity requireClientCertificate="Boolean" />  
              <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
       <security   
          defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
  
<security   
      defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
<security   
   defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
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
   <GenericIssuedTokenParameters>   
      <LocalIssuerIssuedTokenParameters keyType=" SymmeticKey/PublicKey"  
        keySize="Integer"  
        tokenType="String" />  
     <IssuedTokenParametersEndpointAddress address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
     <IssuedTokenClient localIssuerChannelBehaviors="String"  
        cacheIssuedTokens="Boolean"  
        maxIssuedTokenCachingTime="TimeSpan"  
        keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />  
     <IssuedTokenClientBehavior issuerAddress="String"  
        behaviorConfiguration="String" />  
     <IssuedTokenClientBehavior address="URI"  
        bindingConfiguration="String"  
        binding="String" />  
   </GenericIssuedTokenParameters>   
</security>  
</binding>  
</customBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cd15-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1cd15-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1cd15-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cd15-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cd15-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="1cd15-110">Attributes</span></span>  
  
|<span data-ttu-id="1cd15-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="1cd15-111">Attribute</span></span>|<span data-ttu-id="1cd15-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cd15-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cd15-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="1cd15-113">closeTimeout</span></span>|<span data-ttu-id="1cd15-114">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1cd15-115">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="1cd15-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1cd15-116">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1cd15-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1cd15-117">Name</span><span class="sxs-lookup"><span data-stu-id="1cd15-117">name</span></span>|<span data-ttu-id="1cd15-118">Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="1cd15-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1cd15-119">Dieser Wert ist eine benutzerdefinierte Zeichenfolge, die als Identifikationszeichenfolge für die benutzerdefinierte Bindung fungiert.</span><span class="sxs-lookup"><span data-stu-id="1cd15-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="1cd15-120">Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1cd15-120">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1cd15-121">Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1cd15-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="1cd15-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="1cd15-122">openTimeout</span></span>|<span data-ttu-id="1cd15-123">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1cd15-124">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="1cd15-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1cd15-125">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1cd15-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1cd15-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="1cd15-126">receiveTimeout</span></span>|<span data-ttu-id="1cd15-127">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1cd15-128">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="1cd15-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1cd15-129">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1cd15-129">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1cd15-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="1cd15-130">sendTimeout</span></span>|<span data-ttu-id="1cd15-131">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1cd15-132">Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.</span><span class="sxs-lookup"><span data-stu-id="1cd15-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1cd15-133">Der Standardwert ist 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="1cd15-133">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cd15-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1cd15-134">Child Elements</span></span>  
  
|<span data-ttu-id="1cd15-135">Element</span><span class="sxs-lookup"><span data-stu-id="1cd15-135">Element</span></span>|<span data-ttu-id="1cd15-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cd15-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cd15-137">\<CompositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="1cd15-137">\<compositeDuplex></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)|<span data-ttu-id="1cd15-138">Legt bidirektionales Messaging für die benutzerdefinierte Bindung fest.</span><span class="sxs-lookup"><span data-stu-id="1cd15-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="1cd15-139">Das Element wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="1cd15-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="1cd15-140">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. </span><span class="sxs-lookup"><span data-stu-id="1cd15-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="1cd15-141">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="1cd15-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="1cd15-142">Die Clientadresse wird vom `ClientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="1cd15-143">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|  
|[<span data-ttu-id="1cd15-144">\<PnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="1cd15-144">\<pnrpPeerResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/pnrppeerresolver.md)|<span data-ttu-id="1cd15-145">Gibt einen PNRP (Peer Name Resolution-Protokoll)-Peernamenresolver an.</span><span class="sxs-lookup"><span data-stu-id="1cd15-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="1cd15-146">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|  
|[<span data-ttu-id="1cd15-147">\<ReliableSession ></span><span class="sxs-lookup"><span data-stu-id="1cd15-147">\<reliableSession></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md)|<span data-ttu-id="1cd15-148">Legt die Einstellung für WS-Reliable Messaging fest.</span><span class="sxs-lookup"><span data-stu-id="1cd15-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="1cd15-149">Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1cd15-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="1cd15-150">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|  
|[<span data-ttu-id="1cd15-151">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="1cd15-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="1cd15-152">Gibt die Sicherheitsoptionen für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="1cd15-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="1cd15-153">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|  
|[<span data-ttu-id="1cd15-154">\<SslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="1cd15-154">\<sslStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)|<span data-ttu-id="1cd15-155">Gibt die Sicherheitseinstellungen für eine SSL-Streambindung an.</span><span class="sxs-lookup"><span data-stu-id="1cd15-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="1cd15-156">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|  
|[<span data-ttu-id="1cd15-157">\<TransactionFlow ></span><span class="sxs-lookup"><span data-stu-id="1cd15-157">\<transactionFlow></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)|<span data-ttu-id="1cd15-158">Legt fest, dass die Bindung Transaktionsfluss und das vom `transactionProtocol`-Attribut zu verwendende Protokoll unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="1cd15-159">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|  
|[<span data-ttu-id="1cd15-160">\<WindowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="1cd15-160">\<windowsStreamSecurity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsstreamsecurity.md)|<span data-ttu-id="1cd15-161">Gibt die Optionen für die Streamingsicherheit der benutzerdefinierten Bindung an.</span><span class="sxs-lookup"><span data-stu-id="1cd15-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="1cd15-162">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="1cd15-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cd15-163">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1cd15-163">Parent Elements</span></span>  
  
|<span data-ttu-id="1cd15-164">Element</span><span class="sxs-lookup"><span data-stu-id="1cd15-164">Element</span></span>|<span data-ttu-id="1cd15-165">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1cd15-165">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cd15-166">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-166">bindings</span></span>|<span data-ttu-id="1cd15-167">Enthält alle Bindungen für Windows Communication Foundation-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1cd15-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cd15-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cd15-168">Remarks</span></span>  
 <span data-ttu-id="1cd15-169">Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit.</span><span class="sxs-lookup"><span data-stu-id="1cd15-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="1cd15-170">Speziell angepasste Bindungen können durch Hinzufügen der Konfigurationselemente für bestimmte Entitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd15-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="1cd15-171">Der Benutzer kann beispielsweise den Abschnitt `httpsTransport`, `reliableSession` und `security` zum Erstellen einer zuverlässigen und sicheren HTTPS-basierten Bindung kombinieren.</span><span class="sxs-lookup"><span data-stu-id="1cd15-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>  
  
 <span data-ttu-id="1cd15-172">Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels.</span><span class="sxs-lookup"><span data-stu-id="1cd15-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="1cd15-173">Jedes Element definiert und konfiguriert das eine Element des Stapels.</span><span class="sxs-lookup"><span data-stu-id="1cd15-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="1cd15-174">Es muss genau ein Transportelement in jeder benutzerdefinierten Bindung geben.</span><span class="sxs-lookup"><span data-stu-id="1cd15-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="1cd15-175">Ohne dieses Element ist der Messagingstapel unvollständig.</span><span class="sxs-lookup"><span data-stu-id="1cd15-175">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="1cd15-176">Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd15-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="1cd15-177">Die empfohlene Reihenfolge von Stapelelementen ist folgende:</span><span class="sxs-lookup"><span data-stu-id="1cd15-177">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="1cd15-178">Transaktionen (optional)</span><span class="sxs-lookup"><span data-stu-id="1cd15-178">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="1cd15-179">Zuverlässiges Messaging (optional)</span><span class="sxs-lookup"><span data-stu-id="1cd15-179">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="1cd15-180">Sicherheit (Security, optional)</span><span class="sxs-lookup"><span data-stu-id="1cd15-180">Security (optional)</span></span>  
  
4.  <span data-ttu-id="1cd15-181">Transport</span><span class="sxs-lookup"><span data-stu-id="1cd15-181">Transport</span></span>  
  
5.  <span data-ttu-id="1cd15-182">Encoder (optional)</span><span class="sxs-lookup"><span data-stu-id="1cd15-182">Encoder (optional)</span></span>  
  
 <span data-ttu-id="1cd15-183">Verwenden Sie eine benutzerdefinierte Bindung, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="1cd15-184">Eine benutzerdefinierte Bindung kann beispielsweise verwendet werden, um die Nutzung eines neuen Transports oder eines neuen Encoders an einem Dienstendpunkt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1cd15-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>  
  
 <span data-ttu-id="1cd15-185">Eine benutzerdefinierte Bindung wird durch Verwendung einer der <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> aus einer Sammlung an Bindungselementen erstellt, die in einer spezifischen Reihenfolge "gestapelt" sind:</span><span class="sxs-lookup"><span data-stu-id="1cd15-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="1cd15-186">Oben ist ein optionales <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, das einen Transaktionsfluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1cd15-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="1cd15-187">Darauf folgt ein optionales <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, das eine Sitzung und einen Sortiermechanismus bereitstellt, wie es in der WS-ReliableMessaging-Spezifikation definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1cd15-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="1cd15-188">Dieses Konzept einer Sitzung kann SOAP und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="1cd15-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="1cd15-189">Darauf folgt ein optionales Sicherheitsbindungselement, das Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1cd15-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="1cd15-190">Die folgenden Sicherheitsbindungselemente werden von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="1cd15-190">The following security binding elements are provided by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
-   <span data-ttu-id="1cd15-191">Darauf folgen die optionalen Nachrichtenmuster, die von den Bindungselementen spezifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="1cd15-191">Next are the optional message-patterns specified by binding elements:</span></span>  
  
-   <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>  
  
-   <span data-ttu-id="1cd15-192">Darauf folgen die optionalen Transport-Upgrades/unterstützenden Bindungselemente:</span><span class="sxs-lookup"><span data-stu-id="1cd15-192">Next are the optional transport upgrades/helpers binding elements:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="1cd15-193">Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="1cd15-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="1cd15-194">Sie können einen eigenen Transport verwenden oder die folgenden Nachrichten codierenden Bindungen:</span><span class="sxs-lookup"><span data-stu-id="1cd15-194">You can use your own transport or use one of the following message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
-   <span data-ttu-id="1cd15-195">Am Ende befindet sich ein erforderliches Transportelement.</span><span class="sxs-lookup"><span data-stu-id="1cd15-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="1cd15-196">Sie können einen eigenen Transport verwenden oder eines der Transportbindungselemente von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1cd15-196">You can use your own transport or use one of transport binding elements provided by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
    -   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
 <span data-ttu-id="1cd15-197">In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1cd15-197">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="1cd15-198">Ebene</span><span class="sxs-lookup"><span data-stu-id="1cd15-198">Layer</span></span>|<span data-ttu-id="1cd15-199">Optionen</span><span class="sxs-lookup"><span data-stu-id="1cd15-199">Options</span></span>|<span data-ttu-id="1cd15-200">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="1cd15-200">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="1cd15-201">Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="1cd15-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="1cd15-202">Nein</span><span class="sxs-lookup"><span data-stu-id="1cd15-202">No</span></span>|  
|<span data-ttu-id="1cd15-203">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="1cd15-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="1cd15-204">Nein</span><span class="sxs-lookup"><span data-stu-id="1cd15-204">No</span></span>|  
|<span data-ttu-id="1cd15-205">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1cd15-205">Security</span></span>|<span data-ttu-id="1cd15-206">Symmetrisch, asymmetrisch, auf Transportebene</span><span class="sxs-lookup"><span data-stu-id="1cd15-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="1cd15-207">Nein</span><span class="sxs-lookup"><span data-stu-id="1cd15-207">No</span></span>|  
|<span data-ttu-id="1cd15-208">Formänderung</span><span class="sxs-lookup"><span data-stu-id="1cd15-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="1cd15-209">Nein</span><span class="sxs-lookup"><span data-stu-id="1cd15-209">No</span></span>|  
|<span data-ttu-id="1cd15-210">Transport-Upgrades</span><span class="sxs-lookup"><span data-stu-id="1cd15-210">Transport Upgrades</span></span>|<span data-ttu-id="1cd15-211">SSL-Stream, Windows-Stream, Peerresolver</span><span class="sxs-lookup"><span data-stu-id="1cd15-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="1cd15-212">Nein</span><span class="sxs-lookup"><span data-stu-id="1cd15-212">No</span></span>|  
|<span data-ttu-id="1cd15-213">Codierung</span><span class="sxs-lookup"><span data-stu-id="1cd15-213">Encoding</span></span>|<span data-ttu-id="1cd15-214">Text, Binärdatei, MTOM, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="1cd15-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="1cd15-215">Ja</span><span class="sxs-lookup"><span data-stu-id="1cd15-215">Yes</span></span>|  
|<span data-ttu-id="1cd15-216">Transport</span><span class="sxs-lookup"><span data-stu-id="1cd15-216">Transport</span></span>|<span data-ttu-id="1cd15-217">TCP, Named Pipes, HTTP, HTTPS, Typen der MSMQ, benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="1cd15-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="1cd15-218">Ja</span><span class="sxs-lookup"><span data-stu-id="1cd15-218">Yes</span></span>|  
  
 <span data-ttu-id="1cd15-219">Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="1cd15-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
 <span data-ttu-id="1cd15-220">Eine Erläuterung zum Verwenden einer benutzerdefiniertes Bindung für eine vom System bereitgestellte Bindung zu ändern, finden Sie unter [wie: Anpassen einer Bindung sicherheitsbindungsarten](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="1cd15-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
1.  
  
## <a name="see-also"></a><span data-ttu-id="1cd15-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cd15-221">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1cd15-222">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="1cd15-222">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="1cd15-223">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-223">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1cd15-224">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-224">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1cd15-225">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-225">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1cd15-226">CustomBinding-Element</span><span class="sxs-lookup"><span data-stu-id="1cd15-226">customBinding Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="1cd15-227">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-227">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1cd15-228">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="1cd15-228">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1cd15-229">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1cd15-229">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)
