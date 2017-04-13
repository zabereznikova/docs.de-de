---
title: "&lt;security&gt; von &lt;wsHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
caps.latest.revision: 18
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 18
---
# &lt;security&gt; von &lt;wsHttpBinding&gt;
Gibt die Sicherheitsfunktionen von [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) wieder.  
  
## Syntax  
  
```  
  
<security mode="Message/None/Transport/TransportWithMessageCredential">  
   <transport  
         clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string"   
      defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      defaultRealm="string" />  
   <message  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
       establishSecurityContext="Boolean"   
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Modus|-   Dies ist optional.  Gibt den angewendeten Sicherheitstyp an.  Die Standardeinstellung ist `Message`.<br />-   Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## Mode\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt.  Der Dienst muss mit SSL\-Zertifikaten konfiguriert werden.  Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL\-Zertifikat des Diensts authentifiziert.  Die Clientauthentifizierung wird durch das `ClientCredentials`\-Attribut  von [\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) gesteuert.|  
|Meldung|Sicherheit wird über die SOAP\-Nachrichtensicherheit bereitgestellt.  Standardmäßig wird der SOAP\-Nachrichtentext verschlüsselt und signiert.  Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&\#160;B., ob die Dienstanmeldeinformationen out\-of\-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad über die Security.Message\-Eigenschaft auf den Nachrichtentext angewendet werden soll.  Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
|TransportWithMessageCredential|In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP\-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.  Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|Definiert die Sicherheitseinstellungen für den Transport.  Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>\-Typ.|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht.  Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>\-Typ.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Eine sichere Bindung für HTTP\-Transportanwendungen.|  
  
## Hinweise  
 Die WSHttpBinding\-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS\-\*\-Spezifikationen implementieren.  Die Transportsicherheit für diese Bindung ist SSL \(Secure Sockets Layer\) über HTTP oder HTTPS.  
  
## Siehe auch  
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)