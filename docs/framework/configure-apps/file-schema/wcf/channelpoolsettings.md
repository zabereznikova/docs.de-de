---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398159"
---
# \<channelPoolSettings>
Gibt die Kanalpool-Einstellungen für eine benutzerdefinierte Bindung an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`idleTimeout`|Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, für die die Kanäle im Pool im Leerlauf sein können, bevor sie unterbrochen werden. Der Standardwert ist 00:02:00.|  
|`leaseTimeout`|Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, nach dem ein Kanal nach der Rückkehr zum Pool geschlossen wird. Der Standardwert ist 00:10:00.|  
|`maxOutboundChannelsPerEndpoint`|Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Pool für jeden Remoteendpunkt gespeichert werden können. Der Standardwert ist 10.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|Aktiviert Paketrouting für eine benutzerdefinierte Bindung.|  
  
## <a name="remarks"></a>Bemerkungen  
 Kontingente werden als Richtlinienmechanismus verwendet, um den Verbrauch übermäßiger Ressourcen zu verhindern. Sie verhindern Denial-of-Service-Angriffe (DoS), die entweder böswillig oder unbeabsichtigt sind. Verwenden Sie dieses Element, wenn Sie Kanalkontingente auf einem benutzerdefinierten Kanal festlegen.  
  
 `ChannelPoolSettings` gibt drei Kontingente an:  
  
- Das `idleTimeout`-Kontingent wird verwendet, um Denial-of-Service-Angriffe (DOS) auf den Server zu mildern, die Ressourcen für längere Zeit binden. Auf dem Client kann die Einrichtung des korrekten Werts die Zuverlässigkeit bei der Verbindung mit dem Dienst erhöhen. Der Standardwert basiert auf einer moderaten Zuweisung von Ressourcen. Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
- Das `leaseTimeout`-Kontingent wird für die Integration mit Lastenausgleichsmodulen und für die Verbesserung der Zuverlässigkeit verwendet. Der Standardwert basiert auf einer konservativen Zuweisung von Ressourcen. Er ist für eine Entwicklungsumgebung und für kleine Installationsszenarien geeignet. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
- Das `maxOutboundChannelsPerEndpoint`-Kontingent richtet sowohl auf dem Server als auch auf dem Client Cachelimits ein und wird für die Verbesserung der Zuverlässigkeit verwendet. Der Standardwert basiert auf einer moderaten Zuordnung von Ressourcen, die für eine Entwicklungsumgebung und für kleine Installationsszenarien ausreichend sind. Dienstadministratoren sollten den Wert prüfen, wenn einer Installation die Ressourcen ausgehen oder wenn Verbindungen eingeschränkt werden, obwohl zusätzliche Ressourcen zur Verfügung stehen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
