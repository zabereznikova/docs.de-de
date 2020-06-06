---
title: <security> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738676"
---
# <a name="security-of-netmsmqbinding"></a>\<security> von \<netMsmqBinding>
Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung. Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|Modus|Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert. Gültige Werte sind:<br /><br /> -None: Dadurch wird die Sicherheit deaktiviert.<br />-Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt. Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen-Managern. Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen-Manager. Vorhandene Msmq-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.<br />-Message: gibt die End-End-Anwendungssicherheit an. Es wird keine Sicherheit auf Transportebene bereitgestellt. Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.<br />-Both: bietet Sicherheit auf Transport-und SOAP-Messaging Ebene. Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.<br /><br /> Der Standardwert ist Transport. Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|Definiert die SOAP-Nachrichtensicherheitseinstellungen. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<transport>](transport-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für den MSMQ-Transport. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|binding|Das Bindungs Element des[\<netMsmqBinding>](netmsmqbinding.md)|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
