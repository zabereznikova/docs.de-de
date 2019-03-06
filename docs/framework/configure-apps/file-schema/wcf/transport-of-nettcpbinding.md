---
title: <transport> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: de1f87d8074bbf3d85f6092a4ac316f5fd20052c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355591"
---
# <a name="transport-of-nettcpbinding"></a>\<transport> of \<netTcpBinding>
Definiert den Typ der sicherheitsanforderungen auf Nachrichtenebene für einen Endpunkt konfiguriert, mit der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 \<system.ServiceModel>  
\<bindings>  
\<netTcpBinding>  
\<binding>  
\<security>  
\<transport>  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|clientCredentialType|Dies ist optional. Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.<br /><br /> – Der Standardwert ist `Windows`.<br />– Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Dies ist optional. Definiert die Sicherheit auf der Ebene des TCP-Transports. Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann. Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.<br /><br /> Der Standardwert ist `EncryptAndSign`.|  
|sslProtocols|Ein SslProtocols Enum-Flagwert, der angibt, welche SslProtocols unterstützt werden. Der Standardwert ist Tls&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Der Client ist anonym. Dies erfordert ein Zertifikat für den Dienst.|  
|Windows|Gibt die Windows-Authentifizierung des Clients mit SP-Aushandlung (Kerberos-Aushandlung) an.|  
|Zertifikat|Der Client wird mit einem Zertifikat authentifiziert. Dabei wird SSL-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.|  
  
## <a name="protectionlevel-attribute"></a>protectionLevel-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Kein Schutz.|  
|Sign|Nachrichten werden signiert.|  
|EncryptAndSign|-Nachrichten werden verschlüsselt und signiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Gibt an, die Sicherheitsfunktionen des der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP-Nachricht und für gegenseitige Authentifizierung. Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP-Nachrichten werden mit Transportsicherheit geschützt, wie zum Beispiel Windows (Aushandeln) oder SSL über TCP.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
