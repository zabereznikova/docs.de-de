---
title: "&lt;peer&gt; von &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;peer&gt; von &lt;serviceCredentials&gt;
Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.  
  
## Syntax  
  
```  
  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|Gibt ein X.509\-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer\-to\-Peer\-Dienste verwendet wird.  .|  
|[\<messageSenderAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.|  
|[\<peerAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|Gibt die Authentifizierungsoptionen für Peerdienste an.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Überprüfung der Clientanmeldeinformationen.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>   
 <xref:System.ServiceModel.Security.PeerCredential>   
 [Peer\-to\-Peer\-Netzwerke](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/de-de/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/de-de/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)