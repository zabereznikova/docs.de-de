---
title: <transport> von <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152956"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<Transport> \<von msmqIntegrationBinding>
Definiert die Sicherheitseinstellungen für Message Queuing-Integration und -Transport.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bindungen>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<verbindliche>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Sicherheits->**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Verkehr>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.<br /><br /> Gültige Werte sind:<br /><br /> - Keine: Keine Authentifizierung.<br />- WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509-Zertifikat für die SID abzubekommen, die der Nachricht zugeordnet ist. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />- Zertifikat: Der Kanal erhält das Zertifikat aus dem Zertifikatspeicher.<br /><br /> Der Standardwert ist WindowsDomain. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Gültige Werte sind:<br /><br /> - RC4Stream<br />- AES<br /><br /> Der Standardwert ist RC4Stream. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird. Die Verschlüsselung stellt die Nachrichtenintegrität sicher, während EncryptAndSign sowohl die Nachrichtenintegrität als auch die Nichtabstreitbarkeit sicherstellt. das heißt, die Nachricht kommt in der Tat vom Absender und der Absender ist, wer sie sagen, sie sind.<br /><br /> - Gültige Werte umfassen:<br />- Keine: Kein Schutz.<br />- Sign: Nachrichten sind signiert.<br />- EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign. Dieses Attribut ist vom Typ ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|- Gibt den Algorithmus an, der beim Berechnen des Digests als Teil von Signaturen verwendet werden soll. Gültige Werte sind:<br />- MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Der Standardwert ist SHA1. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Aufgrund von Kollisionsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder besser.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Sicherheits->](security-of-basichttpbinding.md)|Definiert die Sicherheitseinstellungen für eine MSMQ-Bindung.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieses Element kapselt die Sicherheitseinstellungen für den Message Queuing-Integrationstransport ein. Die Einstellungen für die Message Queuing-Integration und Transporte in der Warteschlange sind die gleichen. Es ermöglicht das Festlegen des Authentifizierungsmodus, des Verschlüsselungsalgorithmus, des Secure Hash-Algorithmus sowie der Schutzebene.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<verbindliche>](bindings.md)
