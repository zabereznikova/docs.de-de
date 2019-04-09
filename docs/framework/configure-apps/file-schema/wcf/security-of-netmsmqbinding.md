---
title: <security> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: acb4d04663d841a9b494153caa180855959c145e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206511"
---
# <a name="security-of-netmsmqbinding"></a>\<security> of \<netMsmqBinding>
Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung. Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netMsmqBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert. Folgende Werte sind gültig:<br /><br /> – None: Dadurch werden die Sicherheitsfunktionen deaktiviert.<br />-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt. Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern. Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager. Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.<br />-Meldung: Gibt die Ende-Ende-anwendungssicherheit an. Es wird keine Sicherheit auf Transportebene bereitgestellt. Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.<br />– Beides: Bietet Sicherheit auf der Transport- und SOAP-Messagingebene. Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.<br /><br /> Der Standardwert ist Transport. Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|Definiert die SOAP-Nachrichtensicherheitseinstellungen. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für den MSMQ-Transport. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Bindung|Das Bindungselement, das von der [ \<NetMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
- [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
