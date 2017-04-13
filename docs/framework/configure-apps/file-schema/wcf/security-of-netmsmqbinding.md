---
title: "&lt;security&gt; von &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# &lt;security&gt; von &lt;netMsmqBinding&gt;
Definiert die Sicherheitseinstellungen für eine MSMQ\-Bindung.  Dadurch wird angegeben, ob die Transportsicherheit oder die SOAP\-Sicherheit aktiviert sind und ggf. welcher Authentifizierungsmodus und welche Schutzebenen verwendet werden.  
  
## Syntax  
  
```  
  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Modus|Gibt den Sicherheitstyp an, der Integrität, Vertraulichkeit und Authentifizierung steuert.  Folgende Werte sind gültig:<br /><br /> -   None: Die Sicherheit wird deaktiviert.<br />-   Transport: Schutz und Authentifizierung werden vom Transport bereitgestellt.  Dies bezieht sich auf die Nachrichtensicherheit zwischen beiden Warteschlangen\-Managern.  Es besteht keine Sicherheit zwischen der Anwendung und dem Warteschlangen\-Manager.  Vorhandene Msmq\-Anwendungen sind mit diesem Typ des Sicherheitsmodus funktional äquivalent.<br />-   Message: Gibt die Ende\-Ende\-Anwendungssicherheit an.  Es wird keine Sicherheit auf Transportebene bereitgestellt.  Dies ähnelt der Sicherheit, die von anderen Standardbindungen angeboten wird.<br />-   Both: Bietet Sicherheit für die Transport\- und die SOAP\-Nachrichtenebene.  Auf beiden Ebenen sind die gleichen Anmeldeinformationen erforderlich.<br /><br /> Der Standardwert ist **Transport**.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|Definiert die SOAP\-Nachrichtensicherheitseinstellungen.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für den MSMQ\-Transport.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|Bindung|Das Bindungselement von [\<NetMsmqBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>   
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)   
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)