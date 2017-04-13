---
title: "&lt;namedPipeTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;namedPipeTransport&gt;
Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.  
  
## Syntax  
  
```  
  
<namedPipeTransport>  
      <connectionPoolSettings  
         groupName=”String”  
          idleTimeout"TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
</namedPipeTransport>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<connectionPoolSettings\> von \<namedPipeTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe\-Bindung an.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Dieser Transport verwendet URIs im Format "net.pipe:\/\/hostname\/path".  Andere URI\-Komponenten sind optional.  
  
 Das `namedPipeTransport`\-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes\-Transportprotokoll implementiert.  Dieser Transport wird für Windows Communication Foundation \(WCF\)\-zu\-WCF\-Kommunikation auf dem Computer verwendet.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)