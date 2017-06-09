---
title: "&lt;transport&gt; von &lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;transport&gt; von &lt;peerTransport&gt;
Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.  
  
## Syntax  
  
```  
  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
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
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Definiert die Sicherheitseinstellungen für einen Peertransport.|  
  
## Hinweise  
 Dieses Element ist nur festgelegt, wenn das mode\-Attribut von [\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) auf `Transport` oder `TransportWithMessageCredential` festgelegt ist.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)