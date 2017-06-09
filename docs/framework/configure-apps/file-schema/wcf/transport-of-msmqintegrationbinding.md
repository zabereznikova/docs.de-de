---
title: "&lt;transport&gt; von &lt;msmqIntegrationBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# &lt;transport&gt; von &lt;msmqIntegrationBinding&gt;
Definiert die Sicherheitseinstellungen für Message Queuing\-Integration und \-Transport.  
  
## Syntax  
  
```  
  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`msmqAuthenticationMode`|Gibt an, wie die Nachricht vom MSMQ\-Transport authentifiziert werden muss.  Wenn dies auf `None` festgelegt ist, muss der Wert des `msmqProtectionLevel`\-Attributs auch auf `None` festgelegt sein.<br /><br /> Folgende Werte sind gültig:<br /><br /> -   None: Keine Authentifizierung.<br />-   WindowsDomain: Der Authentifizierungsmechanismus verwendet Active Directory, um das X.509\-Zertifikat für die mit der Nachricht verknüpfte SID abzurufen.  Dies wird anschließend zum Prüfen der ACL der Warteschlange verwendet, um sicherzustellen, dass der Benutzer über Berechtigungen zum Schreiben in die Warteschlange verfügt.<br />-   Certificate: Der Kanal ruft das Zertifikat aus dem Zertifikatspeicher ab.<br /><br /> Der Standardwert ist WindowsDomain.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Gibt den Algorithmus an, der beim Übertragen von Nachrichten zwischen Warteschlangen\-Managern für die Nachrichtenverschlüsselung verwendet werden soll.  Folgende Werte sind gültig:<br /><br /> -   RC4Stream<br />-   AES<br /><br /> Der Standardwert ist RC4Stream.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Gibt an, wie die Nachricht auf der Ebene des MSMQ\-Transports gesichert wird.  Mit der Verschlüsselung wird die Nachrichtenintegrität sichergestellt, während EncryptAndSign sowohl Nachrichtenintegrität als auch Nachweisbarkeit sicherstellt. Dabei wird geprüft, ob die Nachricht wirklich vom Absender kommt und der Absender wirklich der ist, der er vorgibt zu sein.<br /><br /> -   Folgende Werte sind gültig:<br />-   None: Kein Schutz.<br />-   Sign: Nachrichten werden signiert.<br />-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.<br /><br /> Der Standardwert ist Sign.  Dieses Attribut ist vom Typ ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|-   Gibt den Algorithmus an, der beim Berechnen des Digests als Teil von Signaturen verwendet werden soll.  Folgende Werte sind gültig:<br />-   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Der Standardwert ist SHA1.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definiert die Sicherheitseinstellungen für eine MSMQ\-Bindung.|  
  
## Hinweise  
 Dieses Element kapselt die Sicherheitseinstellungen für den Message Queuing\-Integrationstransport ein.  Die Einstellungen für die Message Queuing\-Integration und Transporte in der Warteschlange sind die gleichen.  Es ermöglicht das Festlegen des Authentifizierungsmodus, des Verschlüsselungsalgorithmus, des Secure Hash\-Algorithmus sowie der Schutzebene.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.MsmqTransportSecurity>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)