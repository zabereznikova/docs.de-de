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
ms.openlocfilehash: bdfa608b5169755b2b4daaaa26e562308ae2be01
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250605"
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="ec022-102">Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung</span><span class="sxs-lookup"><span data-stu-id="ec022-102">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>

<span data-ttu-id="ec022-103">Um sicherzustellen, dass die aktuellsten Inhalte an die Clientanwendung zurückgegeben werden, führt die Interaktion der Cacherichtlinie für Clients und den Anforderungen der Serverüberprüfung immer zur konservativsten Cacherichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ec022-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="ec022-104">Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert wird und am 4. Januar abläuft.</span><span class="sxs-lookup"><span data-stu-id="ec022-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="ec022-105">In den folgenden Beispielen wird der Wert für die maximale Überalterung (`maxStale`) in Verbindung mit einem maximalen Alter (`maxAge`) verwendet:</span><span class="sxs-lookup"><span data-stu-id="ec022-105">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
- <span data-ttu-id="ec022-106">Wenn die Cacherichtlinie `maxAge` = 5 Tage festlegt und keinen `maxStale`-Wert angibt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-106">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="ec022-107">Allerdings läuft der Inhalt gemäß den Anforderungen der Serverüberprüfung am 4. Januar ab.</span><span class="sxs-lookup"><span data-stu-id="ec022-107">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="ec022-108">Da das Ablaufdatum des Inhalts konservativer (früher) ist, hat es Vorrang vor der `maxAge`-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ec022-108">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="ec022-109">Aus diesem Grund läuft der Inhalt am 4. Januar ab und muss erneut überprüft werden, obwohl sein maximales Alter nicht erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="ec022-109">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
- <span data-ttu-id="ec022-110">Wenn die Cacherichtlinie `maxAge` = 5 Tage und `maxStale` = 3 Tage festlegt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-110">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="ec022-111">Entsprechend dem `maxStale`-Wert kann der Inhalt bis zum 7. Januar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-111">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="ec022-112">Aus diesem Grund muss der Inhalt am 6. Januar erneut überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-112">Therefore, the content gets revalidated on January 6.</span></span>  
  
- <span data-ttu-id="ec022-113">Wenn die Cacherichtlinie `maxAge` = 5 Tage und `maxStale` = 1 Tag festlegt, kann der Inhalt gemäß dem `maxAge`-Wert bis zum 6. Januar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-113">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="ec022-114">Entsprechend dem `maxStale`-Wert kann der Inhalt bis zum 5. Januar verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-114">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="ec022-115">Aus diesem Grund muss der Inhalt am 5. Januar erneut überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="ec022-115">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="ec022-116">Wenn das maximale Alter kleiner als das Ablaufdatum des Inhalts ist, hat immer das konservativere Cachingverhalten Vorrang, und der Wert der maximalen Überalterung hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ec022-116">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="ec022-117">Die folgenden Beispiele veranschaulichen die Auswirkung der Einstellung eines Wert für die maximale Überalterung (`maxStale`), wenn das maximale Alter (`maxAge`) erreicht wird, bevor der Inhalt abläuft:</span><span class="sxs-lookup"><span data-stu-id="ec022-117">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
- <span data-ttu-id="ec022-118">Wenn die Cacherichtlinie `maxAge` = 1 Tag festlegt, und keinen Wert für den `maxStale`-Wert angibt, wird der Inhalt am 2. Januar erneut überprüft, obwohl er nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="ec022-118">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
- <span data-ttu-id="ec022-119">Wenn die Cacherichtlinie `maxAge` = 1 Tag und `maxStale` = 3 Tage festlegt, wird der Inhalt am 2. Januar erneut überprüft, um die konservativere Richtlinie zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ec022-119">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
- <span data-ttu-id="ec022-120">Wenn die Cacherichtlinie `maxAge` = 1 Tage und `maxStale` = 1 Tag festlegt, wird der Inhalt am 2. Januar erneut überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec022-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec022-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec022-121">See also</span></span>

- [<span data-ttu-id="ec022-122">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="ec022-122">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="ec022-123">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="ec022-123">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="ec022-124">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec022-124">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="ec022-125">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="ec022-125">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="ec022-126">Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="ec022-126">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="ec022-127">Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität</span><span class="sxs-lookup"><span data-stu-id="ec022-127">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](cache-policy-interaction-maximum-age-and-minimum-freshness.md)
