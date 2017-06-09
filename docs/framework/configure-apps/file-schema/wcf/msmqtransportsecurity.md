---
title: "&lt;msmqTransportSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;msmqTransportSecurity&gt;
Gibt die MSMQ\-Transportsicherheitseinstellungen für eine benutzerdefinierte Bindung an.  
  
## Syntax  
  
```  
  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ\-Transport authentifiziert werden muss.  Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`\-Attributs auch auf `None` festgelegt sein.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   None: Keine Authentifizierung.<br />-   Windows: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509\-Zertifikat für die mit der Nachricht verknüpfte SID abzurufen.  Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />-   Certificate: Der Kanal ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Der Standardwert lautet Windows.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen\-Managern für die Nachrichtenverschlüsselung verwendet werden soll.  Folgende Werte sind gültig:<br /><br /> -   RC4Stream<br />-   AES<br /><br /> Der Standardwert ist RC4Stream.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ\-Transports gesichert wird.  Mit der Verschlüsselung wird die Nachrichtenintegrität sichergestellt, während EncryptAndSign sowohl Nachrichtenintegrität als auch Nachweisbarkeit sicherstellt. Dabei wird geprüft, ob die Nachricht wirklich vom Absender kommt und der Absender wirklich der ist, der er vorgibt zu sein.  Folgende Werte sind gültig:<br /><br /> -   None: Kein Schutz.<br />-   Sign: Nachrichten werden signiert.<br />-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign.  Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Gibt den Algorithmus an, der beim Berechnen des Digests als Teil von Signaturen verwendet werden soll.  Folgende Werte sind gültig:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Der Standardwert ist SHA1.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<msmqIntegration\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Gibt die Einstellungen an, die für die Interaktion mit einem Message Queuing \(MSMQ\)\-Absender oder \-Empfänger erforderlich sind.|  
|[\<msmqTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Gibt die Eigenschaften der Warteschlangenkommunikation für einen Windows Communication Foundation \(WCF\)\-Dienst an, der das systemeigene Message Queuing \(MSMQ\)\-Protokoll verwendet.|  
  
## Hinweise  
 Weitere Informationen zur Transportsicherheit finden Sie unter [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md)