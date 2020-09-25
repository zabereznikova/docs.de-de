---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 9d28f3f08e9c3984c055567df03f2839709a1522
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204644"
---
# \<msmqTransportSecurity>

Gibt die MSMQ-Transportsicherheitseinstellungen für eine benutzerdefinierte Bindung an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
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
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.<br /><br /> Gültige Werte sind:<br /><br /> -None: keine Authentifizierung.<br />-Windows: der Authentifizierungsmechanismus verwendet Active Directory, um das X. 509-Zertifikat für die SID, die der Nachricht zugeordnet ist, zu erhalten. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />-Certificate: der Kanal Ruft das Zertifikat aus dem Zertifikat Speicher ab.<br /><br /> Der Standardwert lautet Windows. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Gültige Werte sind:<br /><br /> -RC4Stream<br />-AES<br /><br /> Der Standardwert ist RC4Stream. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird. Die Verschlüsselung gewährleistet die Nachrichten Integrität, während "verschlüsselungssign" sowohl Nachrichten Integrität als auch Nichtabstreitbarkeit sicherstellt Das heißt, die Nachricht stammt tatsächlich vom Absender, und der Absender ist die Person, die Sie sagen. Gültige Werte sind:<br /><br /> -None: kein Schutz.<br />-Sign: Nachrichten werden signiert.<br />-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign. Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Gibt den Algorithmus an, der beim Berechnen des Hashwerts als Teil von Signaturen verwendet werden soll. Gültige Werte sind:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> Der Standardwert ist SHA1. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Aufgrund von Konnektivitätsproblemen mit MD5 und SHA1 empfiehlt Microsoft SHA256 oder eine bessere.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|Gibt die Einstellungen an, die für die Interaktion mit einem Message Queuing (MSMQ)-Absender oder -Empfänger erforderlich sind.|  
|[\<msmqTransport>](msmqtransport.md)|Gibt die Eigenschaften der Warteschlangenkommunikation für einen Windows Communication Foundation (WCF)-Dienst an, der das systemeigene Message Queuing (MSMQ)-Protokoll verwendet.|  
  
## <a name="remarks"></a>Bemerkungen  

 Weitere Informationen zur Transportsicherheit finden Sie unter [Transportsicherheit](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Transportprotokolle](../../../wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Transport Sicherheit](../../../wcf/feature-details/transport-security.md)
