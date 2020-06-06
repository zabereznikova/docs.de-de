---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735936"
---
# <a name="transport-of-nettcpbinding"></a>\<transport> von \<netTcpBinding>
Definiert den Typ der Sicherheitsanforderungen auf Nachrichten Ebene für einen Endpunkt, der mit konfiguriert wurde [\<netTcpBinding>](nettcpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|clientCredentialType|(Optional) Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.<br /><br /> -Der Standardwert ist `Windows` .<br />: Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType> .|  
|protectionLevel|(Optional) Definiert die Sicherheit auf der Ebene des TCP-Transports. Das Signieren von Nachrichten verringert das Risiko, dass Nachrichten während der Übertragung durch Dritte manipuliert werden. Mit der Verschlüsselung können Daten während des Transports geschützt werden.<br /><br /> Der Standardwert ist `EncryptAndSign`.|  
|sslProtocols|Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden. Der Standardwert ist TLS&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.<br />3. Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Keine|Der Client ist anonym. Dies erfordert ein Zertifikat für den Dienst.|  
|Windows|Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.|  
|Zertifikat|Der Client wird mit einem Zertifikat authentifiziert. Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.|  
  
## <a name="protectionlevel-attribute"></a>protectionLevel-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Keine|Kein Schutz.|  
|Sign|Nachrichten werden signiert.|  
|EncryptAndSign|-Nachrichten werden verschlüsselt und signiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Gibt die Sicherheitsfunktionen des an [\<netTcpBinding>](nettcpbinding.md) .|  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung. Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
