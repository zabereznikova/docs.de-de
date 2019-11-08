---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 011a46c15785b7ffa832db57925c7e7b5f76c67a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732508"
---
# <a name="wsfederationhttpbinding"></a>\<WSFederationHttpBinding >

Definiert eine Bindung, die WS-Federation unterstützt.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WSFederationHttpBinding >**  

## <a name="syntax"></a>Syntax

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

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|bypassProxyOnLocal|Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll. Der Standardwert ist `false`.|
|closeTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|hostnameComparisonMode|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird. Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|
|maxBufferPoolSize|Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt. Der Standardwert ist 524.288 Byte (512 * 1024). Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer. Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer. Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen. So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.|
|maxReceivedMessageSize|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist. Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standard ist 65536.|
|messageEncoding|Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren. Folgende Werte sind gültig:<br /><br /> -Text: Verwenden Sie einen Textnachrichten Encoder.<br />-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).<br /><br /> Der Standardwert ist Text.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.|
|Name|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|
|openTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|privacyNoticeAt|Eine Zeichenfolge mit dem URI, an dem sich der Datenschutzhinweis befindet.|
|privacyNoticeVersion|Eine ganze Zahl, die die Version des aktuellen Datenschutzhinweises angibt.|
|proxyAddress|Ein URI, der die Adresse des HTTP-Proxys angibt. Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten. Der Standardwert ist `null`.|
|receiveTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|
|sendTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|textEncoding|Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -BigEndianUnicode: Unicode bigEndian-Codierung.<br />-Unicode: 16-Bit-Codierung.<br />-UTF8:8-Bit-Codierung<br /><br /> Der Standard ist UTF8. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|
|transactionFlow|Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt. Der Standardwert ist `false`.|
|useDefaultWebProxy|Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird. Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat. Der Standardwert ist `true`.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<Security >](security-of-wsfederationhttpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.|
|[\<von Readerkontingenten >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|
|[\<ReliableSession->](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<-Bindungen >](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|

## <a name="remarks"></a>Hinweise

Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten auf mehreren Systemen für Authentifizierung und Autorisierung freizugeben. Diese Identitäten können auf Benutzer oder Computer verweisen. Verbundenes HTTP unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine exklusive Verwendung von Transportsicherheit. Diese Bindung bietet Windows Communication Foundation (WCF)-Unterstützung für das WS-Federation-Protokoll. Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden.

Bindungen bestehen aus einem Stapel von Bindungselementen. Der Stapel von Bindungselementen in

`wsFederationHttpBinding` ist mit dem Inhalt von `wsHttpBinding`

Wenn [\<Sicherheits >](security-of-wsfederationhttpbinding.md) auf den Standardwert <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>festgelegt ist.

Der `wsFederationHttpBinding` steuert die Details der Nachrichten Sicherheitseinstellungen in [\<Message->](message-element-of-wsfederationhttpbinding.md). Beachten Sie, dass das [\<Security >](security-of-wsfederationhttpbinding.md) -Element nur den Zugriff erhält, da die von der Bindung verwendete Sicherheit nicht geändert werden kann, nachdem die Bindung erstellt wurde.

Der `wsFederationHttpBinding` bietet auch ein privacyNoticeAt-Attribut zum Festlegen und Abrufen des URIs, an dem sich der Datenschutzhinweis befindet.

Das Sichern von Richtlinien ist vor allem in Verbundszenarien wichtig. Es wird empfohlen, Sicherheitsfunktionen wie HTTPS einzusetzen, um die Richtlinie vor bösartigen Benutzern zu schützen.

In Verbundszenarien, die diese Bindung nutzen, enthält die Dienstrichtlinie häufig wichtige Informationen, wie z.&#160;B. den Schlüssel für die Verschlüsselung des ausgestellten (SAML-) Tokens, den Anspruchstyp für das Token usw. Wenn diese Richtlinie missbräuchlich genutzt wird, könnte ein Angreifer den Schlüssel des ausgestellten Tokens herausfinden und Informationen offen legen und andere böswillige Handlungen vornehmen. Um dies zu vermeiden, muss die Richtlinie sicher vom Dienst abgerufen werden (z.&#160;B. über HTTPS).

Weitere Informationen zu dieser Bindung finden Sie unter Gewusst [wie: Erstellen einer WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).

## <a name="example"></a>Beispiel

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

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [Vorgehensweise: Erstellen einer WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding >](bindings.md)
