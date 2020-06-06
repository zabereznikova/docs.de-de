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

Stellt Vollzugriff auf den Nachrichtenstapel für den Benutzer bereit.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**  

## <a name="syntax"></a>Syntax

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

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|closeTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|name|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert ist eine benutzerdefinierte Zeichenfolge, die als Identifikationszeichenfolge für die benutzerdefinierte Bindung fungiert. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|
|openTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|receiveTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|sendTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<compositeDuplex>](compositeduplex.md)|Legt bidirektionales Messaging für die benutzerdefinierte Bindung fest. Das Element wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP. Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. <br /><br /> Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen. Die Clientadresse wird vom `ClientBaseAddress`-Attribut bereitgestellt.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.|
|[\<pnrpPeerResolver>](pnrppeerresolver.md)|Gibt einen PNRP (Peer Name Resolution-Protokoll)-Peernamenresolver an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.|
|[\<reliableSession>](reliablesession.md)|Legt die Einstellung für WS-Reliable Messaging fest. Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.ReliableSessionElement>.|
|[\<security>](security-of-custombinding.md)|Gibt die Sicherheitsoptionen für die benutzerdefinierte Bindung an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecurityElement>.|
|[\<sslStreamSecurity>](sslstreamsecurity.md)|Gibt die Sicherheitseinstellungen für eine SSL-Streambindung an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.|
|[\<transactionFlow>](transactionflow.md)|Legt fest, dass die Bindung Transaktionsfluss und das vom `transactionProtocol`-Attribut zu verwendende Protokoll unterstützt. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TransactionFlowElement>.|
|[\<windowsStreamSecurity>](windowsstreamsecurity.md)|Gibt die Optionen für die Streamingsicherheit der benutzerdefinierten Bindung an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|Bindungen|Enthält alle Bindungen für Windows Communication Foundation-Anwendungen.|

## <a name="remarks"></a>Bemerkungen

Benutzerdefinierte Bindungen stellen Vollzugriff auf den WCF-Messagingstapel bereit. Speziell angepasste Bindungen können durch Hinzufügen der Konfigurationselemente für bestimmte Entitäten erstellt werden. Der Benutzer kann beispielsweise den Abschnitt `httpsTransport`, `reliableSession` und `security` zum Erstellen einer zuverlässigen und sicheren HTTPS-basierten Bindung kombinieren.

Eine individuelle Bindung definiert den Nachrichtenstapel durch Angeben der Konfigurationselemente für Stapelelemente in der Reihenfolge des Stapels. Jedes Element definiert und konfiguriert das eine Element des Stapels. Es muss genau ein Transportelement in jeder benutzerdefinierten Bindung geben. Ohne dieses Element ist der Messagingstapel unvollständig.

Die Reihenfolge der Elemente im Stapel ist von Belang, da sie der Reihenfolge entspricht, in der Vorgänge auf die Meldung angewendet werden. Die empfohlene Reihenfolge von Stapelelementen ist folgende:

1. Transaktionen (optional)

2. Zuverlässiges Messaging (optional)

3. Sicherheit (Security, optional)

4. Transport

5. Encoder (optional)

Verwenden Sie eine benutzerdefinierte Bindung, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt. Eine benutzerdefinierte Bindung kann beispielsweise verwendet werden, um die Nutzung eines neuen Transports oder eines neuen Encoders an einem Dienstendpunkt zu aktivieren.

Eine benutzerdefinierte Bindung wird durch Verwendung einer der <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> aus einer Sammlung an Bindungselementen erstellt, die in einer spezifischen Reihenfolge "gestapelt" sind:

- Oben ist ein optionales <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, das einen Transaktionsfluss ermöglicht.

- Darauf folgt ein optionales <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>, das eine Sitzung und einen Sortiermechanismus bereitstellt, wie es in der WS-ReliableMessaging-Spezifikation definiert ist. Dieses Konzept einer Sitzung kann SOAP und Transportvermittler überqueren.

- Darauf folgt ein optionales Sicherheitsbindungselement, das Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt. Die folgenden sicherheitsbindungs Elemente werden von Windows Communication Foundation (WCF) bereitgestellt:

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- Darauf folgen die optionalen Nachrichtenmuster, die von den Bindungselementen spezifiziert werden:

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- Darauf folgen die optionalen Transport-Upgrades/unterstützenden Bindungselemente:

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement. Sie können einen eigenen Transport verwenden oder die folgenden Nachrichten codierenden Bindungen:

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- Am Ende befindet sich ein erforderliches Transportelement. Sie können einen eigenen Transport verwenden oder eines der Transport Bindungs Elemente verwenden, die von Windows Communication Foundation (WCF) bereitgestellt werden:

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.

|Ebene|Tastatur|Erforderlich|
|-----------|-------------|--------------|
|Transaktionsfluss|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|Nein|
|Zuverlässigkeit|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|Nein|
|Sicherheit|Symmetrisch, asymmetrisch, auf Transportebene|Nein|
|Formänderung|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|Nein|
|Transport-Upgrades|SSL-Stream, Windows-Stream, Peerresolver|Nein|
|Codieren|Text, Binärdatei, MTOM, benutzerdefiniert|Ja|
|Transport|TCP, Named Pipes, HTTP, HTTPS, Typen der MSMQ, benutzerdefiniert|Ja|

Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.

Eine Erläuterung zur Verwendung einer benutzerdefinierten Bindung zum Ändern einer vom System bereitgestellten Bindung finden Sie unter Gewusst [wie: Anpassen einer vom System bereit](../../../wcf/extending/how-to-customize-a-system-provided-binding.md)gestellten Bindung.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<binding>](bindings.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [CustomBinding-Element](custombinding.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
