---
title: "&lt;oneWay&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;oneWay&gt;
Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.  
  
## Syntax  
  
```  
  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint=”Integer” />  
```  
  
```  
  
</oneWay>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`packetRoutable`|Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.  Die Standardeinstellung ist `false`.|  
|`MaxAcceptedChannels`|Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<channelPoolSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>\-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.  Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs\-\/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.  Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.  Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>   
 <xref:System.ServiceModel.Configuration.OneWayElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)