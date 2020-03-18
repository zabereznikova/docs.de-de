---
title: Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung
ms.date: 03/30/2017
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
ms.openlocfilehash: e21cfc28407ba67afdce8d72e5e52c12ab359059
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048842"
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a>Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung
Um sicherzustellen, dass die aktuellsten Inhalte an die Clientanwendung zurückgegeben werden, führt die Interaktion der Cacherichtlinie für Clients und den Anforderungen der Serverüberprüfung immer zur konservativsten Cacherichtlinie. Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert wird und am 4. Januar abläuft.  
  
 In den folgenden Beispielen wird der Wert für die maximale Überalterung (`maxStale`) in Verbindung mit einem maximalen Alter (`maxAge`) verwendet:  
  
- Wenn die Cacherichtlinie `maxAge` = 5 Tage festlegt und keinen `maxStale`-Wert angibt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden. Allerdings läuft der Inhalt gemäß den Anforderungen der Serverüberprüfung am 4. Januar ab. Da das Ablaufdatum des Inhalts konservativer (früher) ist, hat es Vorrang vor der `maxAge`-Richtlinie. Aus diesem Grund läuft der Inhalt am 4. Januar ab und muss erneut überprüft werden, obwohl sein maximales Alter nicht erreicht wurde.  
  
- Wenn die Cacherichtlinie `maxAge` = 5 Tage und `maxStale` = 3 Tage festlegt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden. Entsprechend dem `maxStale`-Wert kann der Inhalt bis zum 7. Januar verwendet werden. Aus diesem Grund muss der Inhalt am 6. Januar erneut überprüft werden.  
  
- Wenn die Cacherichtlinie `maxAge` = 5 Tage und `maxStale` = 1 Tag festlegt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden. Entsprechend dem `maxStale`-Wert kann der Inhalt bis zum 5. Januar verwendet werden. Aus diesem Grund muss der Inhalt am 5. Januar erneut überprüft werden.  
  
 Wenn das maximale Alter kleiner als das Ablaufdatum des Inhalts ist, hat immer das konservativere Cachingverhalten Vorrang, und der Wert der maximalen Überalterung hat keine Auswirkungen. Die folgenden Beispiele veranschaulichen die Auswirkung der Einstellung eines Wert für die maximale Überalterung (`maxStale`), wenn das maximale Alter (`maxAge`) erreicht wird, bevor der Inhalt abläuft:  
  
- Wenn die Cacherichtlinie `maxAge` = 1 Tag festlegt, und keinen Wert für den `maxStale`-Wert angibt, wird der Inhalt am 2. Januar erneut überprüft, obwohl er nicht abgelaufen ist.  
  
- Wenn die Cacherichtlinie `maxAge` = 1 Tag und `maxStale` = 3 Tage festlegt, wird der Inhalt am 2. Januar erneut überprüft, um die konservativere Richtlinie zu erzwingen.  
  
- Wenn die Cacherichtlinie `maxAge` = 1 Tage und `maxStale` = 1 Tag festlegt, wird der Inhalt am 2. Januar erneut überprüft.  
  
## <a name="see-also"></a>Weitere Informationen

- [Cacheverwaltung für Netzwerkanwendungen](cache-management-for-network-applications.md)
- [Cacherichtlinie](cache-policy.md)
- [Speicherortbasierte Cacherichtlinien](location-based-cache-policies.md)
- [Zeitbasierte Cacherichtlinien](time-based-cache-policies.md)
- [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](configuring-caching-in-network-applications.md)
- [Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität](cache-policy-interaction-maximum-age-and-minimum-freshness.md)
