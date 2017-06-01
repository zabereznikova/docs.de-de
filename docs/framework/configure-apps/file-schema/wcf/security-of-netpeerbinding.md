---
title: "&lt;security&gt; von &lt;netPeerBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# &lt;security&gt; von &lt;netPeerBinding&gt;
Definiert die Sicherheitseinstellungen für die [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.  
  
## Syntax  
  
```  
  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Modus|Dies ist optional.  Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.  Der Standardwert ist `Message`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## mode\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Meldung|Durch die SOAP\-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt.|  
|TransportWithMessageCredential|HTTPS stellt Authentifizierung und Vertraulichkeit bereit.  Die SOAP\-Nachrichten bieten umfassende Anmeldeinformationstypen.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsfähigkeiten von [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Hinweise  
 Sicherheit kann entweder nachrichten\- oder transportspezifisch sein.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Wählen eines Typs von Anmeldeinformationen](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)