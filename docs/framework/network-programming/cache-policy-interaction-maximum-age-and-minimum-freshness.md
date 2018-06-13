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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d88ef1e736a16dddf156a1bc0e42f06d128d2c57
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394165"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a>Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität
Um sicherzustellen, dass die aktuellsten Inhalte an die Clientanwendung zurückgegeben werden, führt die Interaktion der Cacherichtlinie für Clients und den Anforderungen der Serverüberprüfung immer zur konservativsten Cacherichtlinie. Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert wird und am 4. Januar abläuft.  
  
 Die folgenden Beispiele veranschaulichen die Cacherichtlinie, die von der Wechselwirkung aus dem maximalen Alter (`maxAge`) und der minimalen Aktualität (`minFresh`) der Werte entsteht.  
  
-   Wenn die Cacherichtlinie `maxAge` = 2 Tage festlegt und `minFresh` nicht angegeben ist, wird der Inhalt am 3. Januar erneut überprüft.  
  
-   Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 1 Tag festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell. Entsprechend dem `minFresh`, ist der Inhalt bis zum 3. Januar aktuell. Aus diesem Grund muss der Inhalt am 3. Januar erneut überprüft werden.  
  
-   Wenn die Cacherichtlinie `maxAge` = 2 Tage und `minFresh` = 2 Tage festlegt, ist der Inhalt gemäß `maxAge` bis zum 3. Januar aktuell. Entsprechend dem `minFresh`, ist der Inhalt bis zum 2. Januar aktuell. Aus diesem Grund muss der Inhalt am 2. Januar erneut überprüft werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)  
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
