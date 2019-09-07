---
title: <transport> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: d6588e36a8a9420aa37837305aa904763c90781d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399359"
---
# <a name="transport-of-netmsmqbinding"></a>\<Transport > von \<NetMsmqBinding >
Definiert die Sicherheitseinstellungen für den Transport.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetMsmqBinding->** ](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**  
  
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
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|msmqAuthenticationMode|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Folgende Werte sind gültig:<br /><br /> Gar Keine Authentifizierung.<br />Windows Domain Der Authentifizierungsmechanismus verwendet Active Directory, um das X. 509-Zertifikat für die der Nachricht zugeordnete Sicherheits-ID abzurufen. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben für die Warteschlange verfügt.<br />Stellt Der Kanal Ruft das Zertifikat aus dem Zertifikat Speicher ab.<br /><br /> Die Standardeinstellung ist `WindowsDomain`.<br /><br /> Wenn dieses Attribut auf `None` festgelegt ist, muss das `msmqProtectionLevel`-Attribut auch auf `None` festgelegt sein. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -RC4Stream<br />-AES<br />-Der Standardwert ist `RC4Stream`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Gibt an, wie die Nachrichten auf der Ebene des MSMQ-Transports gesichert werden. Durch die Verschlüsselung wird Nachrichtenintegrität bereitgestellt, während durch Signatur und Verschlüsselung sowohl die Nachrichtenintegrität als auch die Nachweisbarkeit sichergestellt wird. Das bedeutet, dass sichergestellt werden kann, dass die Nachricht tatsächlich vom Absender stammt und der Absender die Person ist, die er vorgibt zu sein. Folgende Werte sind gültig:<br /><br /> Gar Kein Schutz.<br />Gebärden Nachrichten werden signiert.<br />EncryptAndSign Nachrichten werden verschlüsselt und signiert.<br />-Der Standardwert `Sign`ist.|  
|msmqSecureHashAlgorithm|Gibt den Hashalgorithmus für die Berechnung des Nachrichtenhashs an. Folgende Werte sind gültig:<br /><br /> -   MD5<br />-   SHA1<br />-SHA256<br />-   SHA512<br /><br /> Die Standardeinstellung ist `SHA1`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Aufgrund von Konnektivitätsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder eine bessere.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|Definiert die Transportsicherheitseinstellungen für in die Warteschlange gestellte Transporte.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
