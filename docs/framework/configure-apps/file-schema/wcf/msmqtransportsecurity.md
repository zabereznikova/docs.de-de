---
title: '&lt;msmqTransportSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: eee2cb916d79bf3b79e882cd757b10344121f6b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmsmqtransportsecuritygt"></a>&lt;msmqTransportSecurity&gt;
Gibt die MSMQ-Transportsicherheitseinstellungen für eine benutzerdefinierte Bindung an.  
  
 \<system.serviceModel >  
\<Bindungen >  
\<CustomBinding >  
\<Binden von >  
\<MsmqIntegration >  
\<MsmqTransportSecurity >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ-Transport authentifiziert werden muss. Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`-Attributs auch auf `None` festgelegt sein.<br /><br /> Folgende Werte sind gültig:<br /><br /> -Keine: Keine Authentifizierung.<br />-Windows: Der Authentifizierungsmechanismus verwendet Active Directory, um das x. 509-Zertifikat abzurufen, für die mit der Nachricht SID verknüpfte. Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />-Certificate: Der Kanal Ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Der Standardwert lautet Windows. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen-Managern für die Nachrichtenverschlüsselung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -RC4Stream<br />-AES<br /><br /> Der Standardwert ist RC4Stream. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ-Transports gesichert wird. Mit der Verschlüsselung wird die Nachrichtenintegrität sichergestellt, während EncryptAndSign sowohl Nachrichtenintegrität als auch Nachweisbarkeit sicherstellt. Dabei wird geprüft, ob die Nachricht wirklich vom Absender kommt und der Absender wirklich der ist, der er vorgibt zu sein. Folgende Werte sind gültig:<br /><br /> -None: Kein Schutz.<br />-Sign: Nachrichten werden signiert.<br />-EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign. Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Gibt den Algorithmus an, der beim Berechnen des Digests als Teil von Signaturen verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-"SHA512" VERWENDET<br /><br /> Der Standardwert ist SHA1. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<MsmqIntegration >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Gibt die Einstellungen an, die für die Interaktion mit einem Message Queuing (MSMQ)-Absender oder -Empfänger erforderlich sind.|  
|[\<MsmqTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Gibt die Eigenschaften der Warteschlangenkommunikation für einen Windows Communication Foundation (WCF)-Dienst an, der das systemeigene Message Queuing (MSMQ)-Protokoll verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zur transportsicherheit finden Sie unter [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<CustomBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md)
