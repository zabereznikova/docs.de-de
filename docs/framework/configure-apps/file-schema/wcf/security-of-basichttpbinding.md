---
title: <security> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183662"
---
# <a name="security-of-basichttpbinding"></a>\<security> von \<basicHttpBinding>

Definiert die Sicherheitsfunktionen von [\<basicHttpBinding>](basichttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|Modus|Dies ist optional. Gibt den verwendeten Sicherheitstyp an. Der Standardwert lautet `None`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>mode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|-Nachrichten werden während der Übertragung nicht gesichert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt. Die SOAP-Nachrichten werden bei der Verwendung von HTTPS gesichert. Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert. Der Client wird über ClientCredentialType authentifiziert. Siehe [\<transport>](transport-of-basichttpbinding.md) .|  
|`Message`|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt. Standardmäßig wird der Text verschlüsselt und signiert. Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird. Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.|  
|TransportWithMessageCredential|Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt. Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt. Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.|  
|TransportCredentialOnly|Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit. Er bietet dagegen HTTP-basierte Clientauthentifizierung. Dieser Modus sollte mit Vorsicht angewendet werden. Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst. Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<message>](message-of-basichttpbinding.md)|Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst. Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|binding|Das Bindungs Element von [\<basicHttpBinding>](basichttpbinding.md) .|  
  
## <a name="remarks"></a>Bemerkungen  

 Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert. Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`-Element zu konfigurieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Wählen eines Typs von Anmeldeinformationen](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
