---
title: "zeitbasierte Cacherichtlinien | Microsoft Docs"
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
  - "Datumsrichtlinie für die Cachesynchronisierung"
  - "Cache [.NET Framework], zeitbasierte Richtlinien"
  - "Aktualität zwischengespeicherter Ressourcen"
  - "Zeit, zwischengespeicherte Ressourcen"
  - "Richtlinie zum maximalen Alter"
  - "Synchronisierung, Cache"
  - "Überalterung zwischengespeicherter Ressourcen"
  - "zeitbasierte Standardcacherichtlinie"
  - "Richtlinie zur maximalen Überalterung"
  - "Cacherichtlinien für Inhalt"
  - "Abgelaufener Inhalt"
  - "Richtlinie zur minimalen Aktualität"
  - "Alter zwischengespeicherter Ressourcen"
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# zeitbasierte Cacherichtlinien
Eine zeitbasierte Cacherichtlinie definiert die Aktualität von zwischengespeicherten Einträgen mit der Zeit, die die Ressource abgerufen wurde, verwenden die Header mit der Ressource und der aktuellen Uhrzeit zurück.  Wenn Sie eine zeitbasierte Cacherichtlinie festlegen, können Sie entweder die zeitbasierte Richtlinie <xref:System.Net.Cache.HttpRequestCacheLevel> verwenden oder eine benutzerdefinierte zeitbasierte Richtlinie erstellen.  Als, die zeitgebundenen Richtlinie für Ressourcen verwenden, mithilfe des HTTP \(Hypertext Transfer Protocol\) entspricht, wird das genaue Cacheverhalten durch die Header bestimmt, die in der zwischengespeicherten Antwort eingeschlossen und durch das Verhalten, das in Abschnitten 13 und 14 von RFC 2616 angegeben ist, verfügbar an [http:\/\/www.ietf.org](http://www.ietf.org/).  Ein Codebeispiel, das Festlegen der standardmäßige zeitbasierten Richtlinie für HTTP\-Ressourcen veranschaulicht, finden Sie unter [Gewusst wie: Legen Sie die zeitgebundenen Cache\-Richtlinie für eine Anwendung fest](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).  Codebeispiele, die das Erstellen und Verwenden von Cachepolitischen Planerrichtlinien veranschaulicht werden, finden Sie unter [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## Kriterien, um von Aktualität von zwischengespeicherten Einträge zu bestimmen  
 Um eine zeitbasierte Cacherichtlinie anpassen können Sie angeben, dass eine oder mehrere der folgenden Kriterien verwendet werden um die Aktualität von zwischengespeicherten Einträge zu bestimmen:  
  
-   Höchstalter  
  
-   Maximale Abgestandenheit  
  
-   Minimale Aktualität  
  
-   Cachesynchronisierungsdatum  
  
> [!NOTE]
>  Verwenden der standardmäßigen zeitbasierten Cacherichtlinie sollte nicht mit dem Festlegen einer standardmäßigen Cacherichtlinie für die Anwendung verwechselt werden.  Die zeitgebundenen Richtlinie ist eine bestimmte Richtlinie, die auf Anforderung verwendet werden kann oder Anwendungsebene.  Die standardmäßige Cacherichtlinie für die Anwendung ist eine Richtlinie \(ortsbasiert oder zeitbasiert\) diese wirksam wird, wenn keine Richtlinien auf einer Anforderung festgelegt ist.  Ausführliche Informationen zum Festlegen einer standardmäßigen Cacherichtlinie für die Anwendung, finden Sie unter <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### Höchstalter  
 Das Höchstalterrichtlinienkriterium gibt die Zeit an, die eine zwischengespeicherte Kopie einer Ressource verwendet werden kann.  Wenn die zwischengespeicherte Kopie der Ressource älter als die angegebene Zeit ist, muss die Ressource erneut überprüft werden, indem sie für den Inhalt auf dem Server überprüft.  Wenn der Höchstalter die zu verwendende Ressource zulässig ist, nachdem er abläuft, wird dieses Kriterien nicht berücksichtigt, es sei denn, ein maximaler Abgestandenheitswert ebenfalls angegeben wird.  
  
### Maximale Abgestandenheit  
 Das Abgestandenheitsrichtlinienkriterium gibt die maximale Zeitspanne nach zufriedenem Ablaufzeit an, dass die zwischengespeicherte Kopie der Ressource verwendet werden kann.  Dies ist das einzige Cacherichtlinienkriterium, das Ressourcen ermöglicht, verwendet werden, nachdem sie abgelaufen sind.  
  
### Minimale Aktualität  
 Das minimale Aktualitätsrichtlinienkriterium gibt die Zeitspanne vor zufriedenem Ablaufzeit an, dass die zwischengespeicherte Kopie der Ressource verwendet werden kann.  Diese Richtlinie verfügt die Auswirkung der Beenden eines Cacheeintrags, vor dem Ablaufdatum ungültig; Daher sind die minimale Aktualität und das Maximum Abgestandenheitseinstellung gegenseitig aus.  
  
## Cache\-Synchronisierungs\-Datum  
 Das Cachesynchronisierungsdatums\-Richtlinienkriterium bestimmt, wann eine zwischengespeicherte Kopie einer Ressource erneut überprüft werden muss, indem Sie sie für den Inhalt auf dem Server überprüft.  Wenn der Inhalt geändert hat, seit das Element zwischengespeichert wurde, wird es vom Server abgerufen, im Cache gespeichert und an die Anwendung zurückgegeben.  Wenn der Inhalt nicht geändert hat, wird der Timestamp aktualisiert und die Anwendung ruft den zwischengespeicherten Inhalt ab.  
  
 Mithilfe des Cachesynchronisierungsdatums können Sie ein absolutes Datum angeben, zu dem zwischengespeicherte Inhalte erneut überprüft werden müssen.  Wenn ein neuer Cacheeintrag zuletzt vor dem Cachesynchronisierungsdatum erneut überprüft wurde, tritt die erneute Validierung mit dem Server noch auf.  Wenn der Cacheeintrag erneut überprüft wurde, nachdem das Cachesynchronisierungsdatum und dort keine zusätzlichen Anforderungen der Aktualitäts\- oder Servererneuten validierung sind, die den zwischengespeicherten Eintrag ungültig wird, wird der Eintrag im Cache verwendet.  Wenn das Cachesynchronisierungsdatum auf ein zukünftiges Datum festgelegt wurde, wird der Eintrag bei jeder Anforderung dieses Eintrags erneut überprüft, bis das Cachesynchronisierungsdatum verstrichen ist.  
  
 Die folgenden Themen enthalten Informationen über die Auswirkungen der Kombination von zeitbasierten Cacherichtlinienkriterien:  
  
-   [Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)