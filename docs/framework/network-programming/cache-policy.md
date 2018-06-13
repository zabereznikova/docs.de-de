---
title: Cacherichtlinie
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 36cf61982bb5a83e6031c35a19ba8ebf0b94aa6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393983"
---
# <a name="cache-policy"></a>Cacherichtlinie
Eine Cacherichtlinie definiert die Regeln, die verwendet werden, um zu bestimmen, ob eine Anforderung mit der zwischengespeicherten Kopie der angeforderten Ressource erfüllt werden kann. Anwendungen geben Cache-Clientanforderungen für die Aktualität an, aber die effektive Cacherichtlinie richtet sich nach den Cache-Clientanforderungen, den Inhaltsablaufanforderungen des Servers sowie den Anforderungen zur erneuten Überprüfung des Servers. Die Interaktion der Cacherichtlinie und des Cacheservers für Clients resultiert immer in der konservativsten Cacherichtlinie, um sicherzustellen, dass die aktuellsten Inhalten an die Clientanwendung zurückgegeben werden.  
  
 Cacherichtlinien sind speicherortbasiert oder zeitbasiert. Eine speicherortbasierte Cacherichtlinie definiert die Aktualität der zwischengespeicherten Einträge auf Grundlage der Speicherorte der angeforderten Ressource. Eine zeitbasierte Cacherichtlinie definiert die Aktualität der zwischengespeicherten Einträge mithilfe der Uhrzeit, zu der die Ressource abgerufen wurde, des Headers, der mit der Ressource zurückgegeben wurde und mit der aktuellen Uhrzeit. Die meisten Anwendungen können die zeitbasierte Standardcacherichtlinie verwenden, die die in RFC 2616 angegebene Cacherichtlinie implementiert, verfügbar unter [http://www.ietf.org](http://www.ietf.org/).  
  
 Die in der folgenden Tabelle beschriebenen Klassen werden verwendet, um Cacherichtlinien anzugeben.  
  
|Klassenname|description|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Stellt speicherortbasierte und zeitbasierte Cacherichtlinien für mithilfe von <xref:System.Net.HttpWebRequest>-Objekten angeforderte Ressourcen dar.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Stellt die speicherortbasierten oder die <xref:System.Net.Cache.RequestCacheLevel.Default>-zeitbasierten Cacherichtlinien für Ressourcen dar, die mithilfe von <xref:System.Net.WebRequest>-Objekten angefordert werden.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Gibt Werte an, die zum Erstellen von zeitbasierten <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekten verwendet werden.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Gibt Werte an, die zum Erstellen von speicherort- und zeitbasierten <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekten verwendet werden.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Gibt Werte an, die zum Erstellen von speicherort- oder <xref:System.Net.Cache.RequestCacheLevel.Default> zeitbasierten <xref:System.Net.Cache.RequestCachePolicy>-Objekten verwendet werden.|  
  
 Sie können eine Cacherichtlinie für alle Anforderungen der Anwendung oder für einzelne Anforderungen definieren. Wenn Sie eine Cacherichtlinie auf Anwendungsebene und eine Cacherichtlinie auf Anforderungsebene angeben, wird die Richtlinie für die Anforderungsebenen verwendet. Sie können eine Cacherichtlinie auf Anwendungsebene programmgesteuert oder mithilfe der Anwendung oder Computerkonfigurationsdateien angeben. Weitere Informationen finden Sie unter [\<requestCaching>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Um eine Cacherichtlinie zu erstellen, müssen Sie ein Richtlinienobjekt erstellen, indem Sie die Instanz der <xref:System.Net.Cache.RequestCachePolicy>- oder <xref:System.Net.Cache.HttpRequestCachePolicy>-Klasse erstellen. Um die Richtlinie für eine Anforderung anzugeben, legen Sie die <xref:System.Net.WebRequest.CachePolicy%2A>-Eigenschaft der Anforderung auf das Richtlinienobjekt fest. Wenn Sie eine Richtlinie auf Anwendungsebene programmgesteuert festlegen, legen Sie die <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A>-Eigenschaft auf das Richtlinienobjekt fest.  
  
 Codebeispiele, die das Erstellen und Verwenden von Cacherichtlinien veranschaulichen, finden Sie unter [Konfigurieren der Zwischenspeicherung in Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
