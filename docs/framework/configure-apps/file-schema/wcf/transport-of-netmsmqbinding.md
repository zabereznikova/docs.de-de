---
title: <transport> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152930"
---
# <a name="transport-of-netmsmqbinding"></a>\<Transport> \<von netMsmqBinding>
Definiert die Sicherheitseinstellungen für den Transport.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bindungen>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<verbindliche>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Sicherheits->**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<Verkehr>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|msmqAuthenticationMode|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Gültige Werte sind:<br /><br /> - Keine: Keine Authentifizierung.<br />- WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509-Zertifikat für die der Nachricht zugeordnete Sicherheitskennung abzurufen. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben für die Warteschlange verfügt.<br />- Zertifikat: Der Kanal ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Der Standardwert lautet `WindowsDomain`.<br /><br /> Wenn dieses Attribut auf `None` festgelegt ist, muss das `msmqProtectionLevel`-Attribut auch auf `None` festgelegt sein. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Gültige Werte sind:<br /><br /> - RC4Stream<br />- AES<br />- Der Standardwert ist `RC4Stream`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Gibt an, wie die Nachrichten auf der Ebene des MSMQ-Transports gesichert werden. Durch die Verschlüsselung wird Nachrichtenintegrität bereitgestellt, während durch Signatur und Verschlüsselung sowohl die Nachrichtenintegrität als auch die Nachweisbarkeit sichergestellt wird. Das heißt, die Nachricht kam in der Tat vom Absender und der Absender ist, wer sie sagen, sie sind. Gültige Werte sind:<br /><br /> - Keine: Kein Schutz.<br />- Sign: Nachrichten sind signiert.<br />- EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br />- Der `Sign`Standardwert ist .|  
|msmqSecureHashAlgorithm|Gibt den Hashalgorithmus für die Berechnung des Nachrichtenhashs an. Gültige Werte sind:<br /><br /> - MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Der Standardwert lautet `SHA1`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Aufgrund von Kollisionsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder besser.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Sicherheits->](security-of-netmsmqbinding.md)|Definiert die Transportsicherheitseinstellungen für in die Warteschlange gestellte Transporte.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<verbindliche>](bindings.md)
