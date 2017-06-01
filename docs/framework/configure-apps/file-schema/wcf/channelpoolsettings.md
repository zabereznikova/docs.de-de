---
title: "&lt;channelPoolSettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;channelPoolSettings&gt;
Gibt die Kanalpool\-Einstellungen für eine benutzerdefinierte Bindung an.  
  
## Syntax  
  
```  
  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint=”Integer” />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`idleTimeout`|Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden.  Der Standardwert ist 00:02:00.|  
|`leaseTimeout`|Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird.  Der Standardwert ist 00:10:00.|  
|`maxOutboundChannelsPerEndpoint`|Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können.  Der Standard ist 10.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<oneWay\>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|Aktiviert Paketrouting für eine benutzerdefinierte Bindung.|  
  
## Hinweise  
 Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern.  Sie verhindern Denial\-of\-Service\-Angriffe \(DoS\), die entweder böswillig oder unbeabsichtigt sind.  Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.  
  
 `ChannelPoolSettings` gibt drei Kontingente an:  
  
-   Das `idleTimeout`\-Kontingent wird verwendet, um Denial\-of\-Service\-Angriffe \(DOS\) auf den Server zu mildern, die Ressourcen für längere Zeit binden.  Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen.  Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen.  Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.  Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
-   Das `leaseTimeout`\-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet.  Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen.  Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet.  Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
-   Das `maxOutboundChannelsPerEndpoint`\-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet.  Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind.  Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>   
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>   
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>   
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [\<oneWay\>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)