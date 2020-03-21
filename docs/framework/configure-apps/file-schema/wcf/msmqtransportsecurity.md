---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153008"
---
# <a name="msmqtransportsecurity"></a>\<msmqTransportSecurity>
Gibt die MSMQ-Transportsicherheitseinstellungen für eine benutzerdefinierte Bindung an.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bindungen>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<verbindliche>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.<br /><br /> Gültige Werte sind:<br /><br /> - Keine: Keine Authentifizierung.<br />- Windows: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509-Zertifikat für die SID abzubekommen, die der Nachricht zugeordnet ist. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />- Zertifikat: Der Kanal erhält das Zertifikat aus dem Zertifikatspeicher.<br /><br /> Der Standardwert lautet Windows. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Gültige Werte sind:<br /><br /> - RC4Stream<br />- AES<br /><br /> Der Standardwert ist RC4Stream. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird. Die Verschlüsselung stellt die Nachrichtenintegrität sicher, während EncryptAndSign sowohl die Nachrichtenintegrität als auch die Nichtabstreitbarkeit sicherstellt. das heißt, die Nachricht kommt in der Tat vom Absender und der Absender ist, wer sie sagen, sie sind. Gültige Werte sind:<br /><br /> - Keine: Kein Schutz.<br />- Sign: Nachrichten sind signiert.<br />- EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign. Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Gibt den Algorithmus an, der beim Berechnen des Hashwerts als Teil von Signaturen verwendet werden soll. Gültige Werte sind:<br /><br /> - MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> Der Standardwert ist SHA1. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Aufgrund von Kollisionsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder besser.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|Gibt die Einstellungen an, die für die Interaktion mit einem Message Queuing (MSMQ)-Absender oder -Empfänger erforderlich sind.|  
|[\<msmqTransport>](msmqtransport.md)|Gibt die Eigenschaften der Warteschlangenkommunikation für einen Windows Communication Foundation (WCF)-Dienst an, der das systemeigene Message Queuing (MSMQ)-Protokoll verwendet.|  
  
## <a name="remarks"></a>Bemerkungen  
 Weitere Informationen zur Verkehrssicherheit finden Sie unter [Transportsicherheit](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Transporte](../../../wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Verkehrssicherheit](../../../wcf/feature-details/transport-security.md)
