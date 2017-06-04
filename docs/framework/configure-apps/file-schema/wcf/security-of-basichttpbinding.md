---
title: "&lt;security&gt; von &lt;basicHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
caps.latest.revision: 16
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 16
---
# &lt;security&gt; von &lt;basicHttpBinding&gt;
Definiert die Sicherheitsfunktionen für [\<basicHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
## Syntax  
  
```  
  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Modus|Dies ist optional.  Gibt den verwendeten Sicherheitstyp an.  Die Standardeinstellung ist `None`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.|  
  
## mode\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Keine|-   Nachrichten werden nicht während der Übertragung gesichert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt.  Die SOAP\-Nachrichten werden über HTTPS gesichert.  Der Dienst wird über das X.509\-Zertifikat beim Client authentifiziert.  Der Client wird über ClientCredentialType authentifiziert.  Weitere Informationen zu diesem Thema finden Sie im [\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).|  
|Meldung|Sicherheit wird über die SOAP\-Nachrichtensicherheit bereitgestellt.  Standardmäßig wird der Text verschlüsselt und signiert.  Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out\-of\-band zur Verfügung gestellt wird.  Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.|  
|TransportWithMessageCredential|Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.  Die Clientauthentifizierung wird über die SOAP\-Nachrichtensicherheit bereitgestellt.  Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername\/Kennwort authentifiziert und eine vorhandene HTTP\-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.|  
|TransportCredentialOnly|Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.  Er bietet dagegen HTTP\-basierte Clientauthentifizierung.  Dieser Modus sollte mit Vorsicht angewendet werden.  Er ist nur für Umgebungen geeignet, in denen die Transportsicherheit mit anderen Mitteln sichergestellt wird \(z.&\#160;B. durch IPSec\) und nur die Clientauthentifizierung über die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Infrastruktur bereitgestellt wird.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|Definiert die Transportsicherheitseinstellungen für einen Standard\-HTTP\-Dienst.  Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|Definiert die Nachrichtensicherheitseinstellungen für einen Standard\-HTTP\-Dienst.  Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|Bindung|Das Bindungselement von [\<basicHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## Hinweise  
 Standardmäßig wird die SOAP\-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.  Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`\-Element zu konfigurieren.  
  
## Siehe auch  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>   
 <xref:System.ServiceModel.BasicHttpSecurity>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Wählen eines Typs von Anmeldeinformationen](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)