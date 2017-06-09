---
title: "Cacherichtlinie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "zeitbasierte Cacherichtlinien"
  - "standortbasierte Cacherichtlinien"
  - "Cache [.NET Framework], Richtlinien"
  - "Anforderung von Cacherichtlinien"
  - "Aktualität zwischengespeicherter Ressourcen"
  - "Cacherichtlinien für Inhalt"
  - "abgelaufener Inhalt"
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Cacherichtlinie
Mithilfe einer Cacherichtlinie werden Regeln definiert, die bestimmen, ob für eine Anforderung eine zwischengespeicherte Kopie der Ressource zurückgegeben werden kann.  Anwendungen geben Clientcacheanforderungen für Aktualität an, aber die effektive Cacherichtlinie wird durch die Clientcacheanforderungen, den Inhalt Ablaufanforderungen des Servers und die Anforderungen der erneuten Validierung des Servers bestimmt.  Die Interaktion von Clientcacherichtlinien\- und \-Serveranforderungen führt immer die konservativste Cacherichtlinie, um zu helfen, sicherzustellen, dass der neuste Inhalt an die Clientanwendung zurückgegeben wird.  
  
 Cacherichtlinien sind entweder ortsbasiert oder zeitbasiert.  Ziehen Sie eine ortsbasierte Cacherichtlinie definiert die Aktualität von zwischengespeicherten Einträgen auf Grundlage, wo die angeforderte Ressource verwiesen werden kann.  Eine zeitbasierte Cacherichtlinie definiert die Aktualität von zwischengespeicherten Einträgen mit der Zeit, die die Ressource abgerufen wurde, Header, die der Ressource zurückgegeben werden, und der aktuellen Zeit.  Die meisten Anwendungen können die zeitgebundenen Cacherichtlinie verwenden, die die Cachingrichtlinie implementiert, die in RFC 2616 angegeben ist, verfügbar an [http:\/\/www.ietf.org](http://www.ietf.org/).  
  
 Die Klassen, die in der folgenden Tabelle beschrieben werden, werden verwendet, um Cacherichtlinien anzugeben.  
  
|Klassenname|Description|  
|-----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Stellt die ortsbasierten und zeitbasierten Cacherichtlinien für die Ressourcen dar, die mit <xref:System.Net.HttpWebRequest>\-Objekte angefordert werden.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Stellt ortsbasierte Cacherichtlinien dar, oder die zeitbasierte Cacherichtlinie <xref:System.Net.Cache.RequestCacheLevel> für die Ressourcen, die mit <xref:System.Net.WebRequest> angefordert werden, Objekte ein.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Gibt die Werte an, die verwendet werden, um zeitbasierte <xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekte zu erstellen.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Gibt die Werte an, die verwendet werden, um ortsbasierte und zeitbasierte <xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekte zu erstellen.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Gibt die Werte an, die verwendet werden, um ortsbasiert zu erstellen oder die zeitbasierten <xref:System.Net.Cache.RequestCachePolicy>\-Objekte <xref:System.Net.Cache.RequestCacheLevel>.|  
  
 Sie können eine Cacherichtlinie definieren für alle Anforderungen, die von der Anwendung gemacht oder für einzelne Anforderungen.  Wenn Sie eine Cacherichtlinie auf Anwendungsebene angeben und eine AnforderungEbene Richtlinie zwischenspeichern, wird die AnforderungEbene Richtlinie verwendet.  Sie können eine Cacherichtlinie programmgesteuert angeben oder indem Sie auf Anwendungsebene die Anwendung oder die Computerkonfigurationsdateien verwenden.  Weitere Informationen finden Sie unter [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Um eine Cacherichtlinie zu erstellen, müssen Sie ein Richtlinienobjekt erstellen mithilfe einer Instanz der <xref:System.Net.Cache.RequestCachePolicy> oder <xref:System.Net.Cache.HttpRequestCachePolicy>\-Klasse erstellen.  Um die Richtlinien auf einer Anforderung anzugeben, legen Sie die <xref:System.Net.WebRequest.CachePolicy%2A>\-Eigenschaft der Anforderung an den Richtlinienobjekt fest.  Als, eine Richtlinie programmgesteuert Festlegen auf Anwendungsebene, legen Sie die <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A>\-Eigenschaft auf das Richtlinienobjekt fest.  
  
 Codebeispiele, die das Erstellen und Verwenden von Cachepolitischen Planerrichtlinien veranschaulicht werden, finden Sie unter [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)