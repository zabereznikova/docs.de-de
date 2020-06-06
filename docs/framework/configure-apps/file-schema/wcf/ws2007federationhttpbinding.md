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

Eine sichere und interoperable Bindung, die von abgeleitet ist [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) und Verbund Sicherheit unterstützt.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007FederationHttpBinding>**  
  
## <a name="syntax"></a>Syntax

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

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`bypassProxyOnLocal`|Ein Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll. Der Standardwert lautet `false`.|
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|`hostNameComparisonMode`|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird. Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|
|`maxBufferPoolSize`|Die maximale Pufferpoolgröße dieser Bindung. Der Standardwert ist 524.288 Byte (512 * 1024). Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer. Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer. Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen. So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.|
|`maxReceivedMessageSize`|Die maximale Nachrichtengröße in Byte einschließlich Header, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist. Der Absender einer Nachricht, die diesen Grenzwert überschreitet, erhält einen SOAP-Fehler. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standard ist 65536.|
|`messageEncoding`|Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren. Gültige Werte sind:<br /><br /> -Text: Verwenden Sie einen Textnachrichten Encoder.<br />-MTOM: Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).<br /><br /> Der Standardwert ist Text.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.|
|`name`|Der Konfigurationsname der Bindung. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|`privacyNoticeAt`|Ein URI, an dem sich der Datenschutzhinweis befindet.|
|`privacyNoticeVersion`|Die Version des aktuellen Datenschutzhinweises.|
|`proxyAddress`|Ein URI, der die Adresse des HTTP-Proxys angibt. Wenn `useDefaultWebProxy``true` ist, muss diese Einstellung `null` lauten. Der Standardwert lautet `null`.|
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|
|`textEncoding`|Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Gültige Werte sind:<br /><br /> -BigEndianUnicode: Unicode Big Endian-Codierung.<br />-Unicode: 16-Bit-Codierung.<br />-UTF8:8-Bit-Codierung.<br /><br /> Der Standardwert ist UTF8. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|
|`transactionFlow`|Ein Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt. Der Standardwert lautet `false`.|
|`useDefaultWebProxy`|Ein Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems verwendet wird. Die Proxyadresse muss `null` sein (das heißt, sie ist nicht festgelegt), wenn dieses Attribut den Wert `true` hat. Der Standardwert lautet `true`.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<bindings>](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|

## <a name="remarks"></a>Bemerkungen

Ein Verbund zeichnet sich durch die Möglichkeit aus, Identitäten in mehreren Unternehmen oder vertrauenswürdigen Domänen für Authentifizierung und Autorisierung freizugeben. Er verwendet das WS-Trust-Protokoll, um die Identitätsdarstellung von einer vertrauenswürdigen Domäne zu einer anderen zuzuordnen. Eine verbundene HTTP-Bindung unterstützt sowohl SOAP-Sicherheit als auch Sicherheit im gemischten Modus, jedoch keine Transportsicherheit. Mit dieser Bindung konfigurierte Dienste müssen den HTTP-Transport verwenden. Weitere Informationen finden Sie unter [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).

## <a name="example"></a>Beispiel

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WS2007FederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>
- [\<wsFederationHttpBinding>](wsfederationhttpbinding.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
