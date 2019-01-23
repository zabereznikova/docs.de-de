---
title: '&lt;transport&gt; von &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 6cd930a2ab097e50edfb9bc4eba5c8d29484ad29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550551"
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a>&lt;transport&gt; von &lt;msmqIntegrationBinding&gt;
Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.  
  
 \<system.ServiceModel>  
\<bindings>  
msmqIntegrationBinding  
\<binding>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.<br /><br /> Folgende Werte sind gültig:<br /><br /> – None: Keine Authentifizierung.<br />-   WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das x. 509-Zertifikat für die mit der Nachricht SID verknüpfte zu erhalten. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />-Zertifikat: Der Kanal Ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Der Standardwert ist WindowsDomain. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -RC4Stream<br />-   AES<br /><br /> Der Standardwert ist RC4Stream. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird. Mit der Verschlüsselung wird die Nachrichtenintegrität sichergestellt, während EncryptAndSign sowohl Nachrichtenintegrität als auch Nachweisbarkeit sicherstellt. Dabei wird geprüft, ob die Nachricht wirklich vom Absender kommt und der Absender wirklich der ist, der er vorgibt zu sein.<br /><br /> -Die folgenden: Gültige Werte<br />– None: Kein Schutz.<br />-Anmeldung: Nachrichten werden signiert.<br />-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign. Dieses Attribut ist vom Typ ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|-Gibt den Algorithmus zum Berechnen des Digests als Teil von Signaturen verwendet werden. Folgende Werte sind gültig:<br />-   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Der Standardwert ist SHA1. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element kapselt die Sicherheitseinstellungen für den Message Queuing-Integrationstransport ein. Die Einstellungen für die Message Queuing-Integration und Transporte in der Warteschlange sind die gleichen. Es ermöglicht das Festlegen des Authentifizierungsmodus, des Verschlüsselungsalgorithmus, des Secure Hash-Algorithmus sowie der Schutzebene.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
