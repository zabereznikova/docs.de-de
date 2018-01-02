---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09496add0adcc11756b6aae01a0236fe590f819f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltchannelpoolsettingsgt"></a>&lt;channelPoolSettings&gt;
Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.  
  
 \<system.serviceModel >  
\<Bindungen >  
\<CustomBinding >  
\<Binden von >  
\<OneWay >  
\<ChannelPoolSettings >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`idleTimeout`|Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden. Der Standardwert ist 00:02:00.|  
|`leaseTimeout`|Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird. Der Standardwert ist 00:10:00.|  
|`maxOutboundChannelsPerEndpoint`|Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können. Der Standard ist 10.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<OneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|Aktiviert Paketrouting für eine benutzerdefinierte Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern. Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind. Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.  
  
 `ChannelPoolSettings` gibt drei Kontingente an:  
  
-   Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden. Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen. Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen. Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
-   Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet. Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen. Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
-   Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet. Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [\<OneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<CustomBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
