---
title: Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
ms.openlocfilehash: d4182268341f4a4334a627fc8c9e24fa235f003f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287552"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a>Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität

Um sicherzustellen, dass die aktuellsten Inhalte an die Clientanwendung zurückgegeben werden, führt die Interaktion der Cacherichtlinie für Clients und den Anforderungen der Serverüberprüfung immer zur konservativsten Cacherichtlinie. Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert wird und am 4. Januar abläuft.  
  
 Die folgenden Beispiele veranschaulichen die Cacherichtlinie, die von der Wechselwirkung aus dem maximalen Alter (`maxAge`) und der minimalen Aktualität (`minFresh`) der Werte entsteht.  
  
- Wenn die Cacherichtlinie `maxAge` = 2 Tage festlegt und `minFresh` nicht angegeben ist, wird der Inhalt am 3. Januar erneut überprüft.  
  
- Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 1 Tag festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell. Entsprechend dem `minFresh`, ist der Inhalt bis zum 3. Januar aktuell. Aus diesem Grund muss der Inhalt am 3. Januar erneut überprüft werden.  
  
- Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 2 Tage festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell. Entsprechend dem `minFresh`, ist der Inhalt bis zum 2. Januar aktuell. Aus diesem Grund muss der Inhalt am 2. Januar erneut überprüft werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Cacheverwaltung für Netzwerkanwendungen](cache-management-for-network-applications.md)
- [Cacherichtlinie](cache-policy.md)
- [Speicherortbasierte Cacherichtlinien](location-based-cache-policies.md)
- [Zeitbasierte Cacherichtlinien](time-based-cache-policies.md)
- [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](configuring-caching-in-network-applications.md)
- [Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung](cache-policy-interaction-maximum-age-and-maximum-staleness.md)
