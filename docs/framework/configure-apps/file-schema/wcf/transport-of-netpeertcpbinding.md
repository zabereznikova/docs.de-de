---
title: "&lt;transport&gt; von &lt;netPeerTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;transport&gt; von &lt;netPeerTcpBinding&gt;
Gibt die Einstellungen für die Transportebenensicherheit beim Verwenden von [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md) an.  
  
## Syntax  
  
```  
  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|credentialType|Dies ist optional.  Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## credentialType\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Zertifikat|Zur Authentifizierung des Peerkanaltransports ist ein X509\-Zertifikat erforderlich.|  
|Kennwort|Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|Definiert die Sicherheitseinstellungen für [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)