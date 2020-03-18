---
title: zeitbasierte Cacherichtlinien
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
ms.openlocfilehash: 0edde8e716d5ce3b1444e994234def5835341475
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047123"
---
# <a name="time-based-cache-policies"></a>zeitbasierte Cacherichtlinien
Eine zeitbasierten Cacherichtlinie definiert die Aktualität der zwischengespeicherten Einträge mithilfe der Uhrzeit, zu der die Ressource abgerufen wurde, der Header, die mit der Ressource zurückgegeben wurden und der aktuellen Uhrzeit. Wenn Sie eine zeitbasierte Cacherichtlinie festlegen, können Sie entweder die zeitbasierte Richtlinie <xref:System.Net.Cache.HttpRequestCacheLevel.Default> verwenden, oder eine benutzerdefinierte zeitbasierte Richtlinie erstellen. Bei Verwendung der zeitbasierten Standardrichtlinie für Ressourcen, die mithilfe des Hypertext Transfer Protocol (HTTP) abgerufen wurde, wird das exakte Cacheverhalten von den Headern bestimmt, die in der zwischengespeicherten Antwort enthalten sind, und von den Verhaltensweisen in den Abschnitten 13 und 14 des RFC 2616, verfügbar auf der Webseite der [Internet Engineering Task Force (IETF)](https://www.ietf.org/). Ein Codebeispiel, das das Festlegen der zeitbasierten Standardrichtlinie für HTTP-Ressourcen veranschaulicht, finden Sie unter [Vorgehensweise: Festlegen der standardmäßigen zeitbasierten Cacherichtlinie für eine Anwendung](how-to-set-the-default-time-based-cache-policy-for-an-application.md). Codebeispiele, die das Erstellen und Verwenden von Cacherichtlinien veranschaulichen, finden Sie unter [Konfigurieren der Zwischenspeicherung in Netzwerkanwendungen](configuring-caching-in-network-applications.md).  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a>Kriterien zum Bestimmen der Aktualität der zwischengespeicherten Einträge  
 Zum Anpassen einer zeitbasierten Cacherichtlinie können Sie angeben, dass eine oder mehrere der folgenden Kriterien verwendet werden, um die Aktualität der zwischengespeicherten Einträge zu bestimmen:  
  
- Maximales Alter  
  
- Maximale Überalterung  
  
- Minimale Aktualität  
  
- Datum für die Cachesynchronisierung  
  
> [!NOTE]
> Die Verwendung der zeitbasierten Standardcacherichtlinie darf nicht mit dem Festlegen einer Standardcacherichtlinie für Ihre Anwendung verwechselt werden. Die zeitbasierte Standardrichtlinie ist eine bestimmte Richtlinie, die auf Ebene der Anforderung oder einer Anwendung verwendet werden kann. Die Standardcacherichtlinie für Ihre Anwendung ist eine Richtlinie (standortbasiert oder zeitbasiert), die wirksam wird, wenn keine Richtlinie für eine Anforderung festgelegt ist. Weitere Informationen zum Festlegen einer Standardcacherichtlinie für Ihre Anwendung finden Sie unter <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### <a name="maximum-age"></a>Maximales Alter  
 Das Kriterium der Richtlinie zum maximalen Alter gibt die Zeitspanne an, in der eine zwischengespeicherte Kopie einer Ressource verwendet werden kann. Wenn die zwischengespeicherte Kopie der Ressource älter als die angegebene Zeitspanne ist, muss die Ressource anhand der Inhalte auf dem Server erneut überprüft werden. Wenn das maximale Alter erlauben würde, dass die Ressource nach dem Ablaufdatum verwendet werden könnte, wird dieses Kriterium nicht berücksichtigt, außer es ist auch ein Wert für die maximale Überalterung angegeben.  
  
### <a name="maximum-staleness"></a>Maximale Überalterung  
 Das Kriterium der Richtlinie zur maximalen Überalterung gibt die Zeitdauer nach dem Ablauf von Inhalten an, in der die zwischengespeicherte Kopie der Ressource verwendet werden kann. Dies ist das einzige Kriterium der Cacherichtlinie, mit dem Ressourcen verwendet werden können, nachdem sie abgelaufen sind.  
  
### <a name="minimum-freshness"></a>Minimale Aktivität  
 Das Kriterium der Richtlinie zur minimalen Aktualität gibt die Zeitdauer vor dem Ablauf von Inhalten an, in der die zwischengespeicherte Kopie der Ressource verwendet werden kann. Diese Richtlinie bewirkt, dass ein Cacheeintrag vor seinem Ablaufdatum abläuft. Daher schließen sich die Einstellungen für die minimale Aktualität und maximale Überalterung gegenseitig aus.  
  
## <a name="cache-synchronization-date"></a>Datum für die Cachesynchronisierung  
 Das Kriterium der Richtlinie zum Datum für die Cachesynchronisierung bestimmt anhand der Inhalte auf dem Server, wann eine zwischengespeicherte Kopie einer Ressource erneut überprüft werden muss. Wenn der Inhalt seit der Zwischenspeicherung des Elements geändert wurde, wird er vom Server abgerufen, im Cache gespeichert und an die Anwendung zurückgegeben. Wenn der Inhalt nicht geändert wurde, wird stattdessen der Zeitstempel aktualisiert, und die Anwendung ruft den zwischengespeicherten Inhalt ab.  
  
 Durch das Datum der Cachesynchronisierung können Sie ein absolutes Datum angeben, an dem die zwischengespeicherten Inhalte erneut überprüft werden müssen. Wenn ein neuer Cacheeintrag zuletzt vor dem Datum der Cachesynchronisierung erneut überprüft wurde, wird die erneute Überprüfung mit dem Server weiterhin ausgeführt. Wenn der Cacheeintrag nach dem Datum der Cachesynchronisierung erneut überprüft wurde, und es keine zusätzlichen Anforderungen an die Aktualität oder erneute Überprüfung gibt, die den zwischengespeicherten Eintrag ungültig machen, wird der Eintrag aus dem Cache verwendet. Wenn das Datum der Cachesynchronisierung auf ein Datum in der Zukunft festgelegt ist, wird der Eintrag bei jedem Aufruf erneut überprüft, bis das Datum der Cachesynchronisierung vorüber ist.  
  
 Die folgenden Themen enthalten Informationen zu den Auswirkungen einer Kombination der Kriterien der zeitbasierten Cacherichtlinie:  
  
- [Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung](cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
- [Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität](cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Cacheverwaltung für Netzwerkanwendungen](cache-management-for-network-applications.md)
- [Cacherichtlinie](cache-policy.md)
- [Speicherortbasierte Cacherichtlinien](location-based-cache-policies.md)
- [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](configuring-caching-in-network-applications.md)
- [\<requestCaching>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
