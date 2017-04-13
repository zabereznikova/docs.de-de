---
title: "&lt;transport&gt; von &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;transport&gt; von &lt;netMsmqBinding&gt;
Definiert die Sicherheitseinstellungen für den Transport.  
  
## Syntax  
  
```  
  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|msmqAuthenticationMode|Gibt an, wie die Nachricht vom MSMQ\-Transport authentifiziert werden muss.  Folgende Werte sind gültig:<br /><br /> -   None: Keine Authentifizierung.<br />-   WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509\-Zertifikat für die mit der Nachricht verknüpfte SID abzurufen.  Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben für die Warteschlange verfügt.<br />-   Certificate: Der Kanal ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Die Standardeinstellung ist `WindowsDomain`.<br /><br /> Wenn dieses Attribut auf `None` festgelegt ist, muss das `msmqProtectionLevel`\-Attribut auch auf `None` festgelegt sein.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen\-Managern für die Nachrichtenverschlüsselung verwendet werden soll.  Folgende Werte sind gültig:<br /><br /> -   RC4Stream<br />-   AES<br />-   Der Standardwert ist `RC4Stream`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Gibt an, wie die Nachrichten auf der Ebene des MSMQ\-Transports gesichert werden.  Durch die Verschlüsselung wird Nachrichtenintegrität bereitgestellt, während durch Signatur und Verschlüsselung sowohl die Nachrichtenintegrität als auch die Nachweisbarkeit sichergestellt wird.  Das bedeutet, dass sichergestellt werden kann, dass die Nachricht tatsächlich vom Absender stammt und der Absender die Person ist, die er vorgibt zu sein.  Folgende Werte sind gültig:<br /><br /> -   None: Kein Schutz.<br />-   Sign: Nachrichten werden signiert.<br />-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br />-   Die Standardeinstellung ist `Sign`.|  
|msmqSecureHashAlgorithm|Gibt den Hashalgorithmus für die Berechnung des Nachrichtenhashs.  Folgende Werte sind gültig:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Die Standardeinstellung ist `SHA1`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definiert die Transportsicherheitseinstellungen für in die Warteschlange gestellte Transporte.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>   
 <xref:System.ServiceModel.MsmqTransportSecurity>   
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)