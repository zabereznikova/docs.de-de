---
title: Cacheverwaltung für Netzwerkanwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
ms.openlocfilehash: 7e131963999db3e3d5e0e6f3fa110da36e6452a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048873"
---
# <a name="cache-management-for-network-applications"></a><span data-ttu-id="5eb4a-102">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="5eb4a-102">Cache Management for Network Applications</span></span>
<span data-ttu-id="5eb4a-103">Dieses Thema und seine zugehörigen Unterthemen beschreiben die Zwischenspeicherung von Ressourcen, die mithilfe der <xref:System.Net.WebClient>-, <xref:System.Net.WebRequest>-, <xref:System.Net.HttpWebRequest>- und <xref:System.Net.FtpWebRequest>-Klassen erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-103">This topic and its related subtopics describe caching for resources obtained using the <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>  
  
 <span data-ttu-id="5eb4a-104">Ein Zwischenspeicher dient als temporärer Speicher von Ressourcen, die von einer Anwendung angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-104">A cache provides temporary storage of resources that have been requested by an application.</span></span> <span data-ttu-id="5eb4a-105">Wenn eine Anwendung mehrere Male die gleiche Ressource anfordert, kann die Ressource aus dem Zwischenspeicher zurückgegeben werden. Der Mehraufwand einer erneuten Aufforderung vom Server wird somit verhindert.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-105">If an application requests the same resource more than once, the resource can be returned from the cache, avoiding the overhead of re-requesting it from the server.</span></span> <span data-ttu-id="5eb4a-106">Zwischenspeichern kann die Anwendungsleistung durch Verringern des Zeitaufwands für den Abruf einer angeforderten Ressource verbessern.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-106">Caching can improve application performance by reducing the time required to get a requested resource.</span></span> <span data-ttu-id="5eb4a-107">Zwischenspeichern kann auch den Netzwerkverkehr verringern, indem die Anzahl der Roundtrips zum Server reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-107">Caching can also decrease network traffic by reducing the number of trips to the server.</span></span> <span data-ttu-id="5eb4a-108">Bei der Zwischenspeicherung wird die Leistung verbessert, aber sie erhöht auch das Risiko, dass die an die Anwendung zurückgegebene Ressource veraltet ist, was bedeutet, dass sie nicht identisch zu der Ressource ist, die vom Server gesendet worden wäre, wenn das Zwischenspeichern nicht in Gebrauch wäre.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-108">While caching improves performance, it increases the risk that the resource returned to the application is stale, meaning that it is not identical to the resource that would have been sent by the server if caching were not in use.</span></span>  
  
 <span data-ttu-id="5eb4a-109">Durch Zwischenspeichern können nicht autorisierte Benutzer vertrauliche Daten lesen oder verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-109">Caching may allow unauthorized users or processes to read sensitive data.</span></span> <span data-ttu-id="5eb4a-110">Eine authentifizierte Antwort, die zwischengespeichert ist, kann möglicherweise ohne eine zusätzliche Autorisierung aus dem Zwischenspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-110">An authenticated response that is cached may be retrieved from the cache without an additional authorization.</span></span> <span data-ttu-id="5eb4a-111">Wenn das Zwischenspeichern aktiviert wurde, ändern Sie <xref:System.Net.WebRequest.CachePolicy%2A> auf <xref:System.Net.Cache.RequestCacheLevel.BypassCache> oder <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore>, um es für diese Anforderung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-111">If caching is enabled, change to <xref:System.Net.WebRequest.CachePolicy%2A> to <xref:System.Net.Cache.RequestCacheLevel.BypassCache> or <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> to disable caching for this request.</span></span>  
  
 <span data-ttu-id="5eb4a-112">Aus Sicherheitsgründen wird das Zwischenspeichern **nicht** für Szenarios der mittleren Ebene empfohlen.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-112">Due to security concerns, caching is **not** recommended for middle tier scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5eb4a-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5eb4a-113">In This Section</span></span>  
 [<span data-ttu-id="5eb4a-114">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="5eb4a-114">Cache Policy</span></span>](cache-policy.md)  
 <span data-ttu-id="5eb4a-115">Erläutert, was eine Cacherichtlinie ist und wie sie definiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-115">Explains what a cache policy is and how to define one.</span></span>  
  
 [<span data-ttu-id="5eb4a-116">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="5eb4a-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)  
 <span data-ttu-id="5eb4a-117">Definiert jeden Typ von verfügbaren speicherortbasierten Cacherichtlinien für Ressourcen von Hypertext Transfer Protocol (http und https).</span><span class="sxs-lookup"><span data-stu-id="5eb4a-117">Defines each type of location-based cache policy available for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
 [<span data-ttu-id="5eb4a-118">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="5eb4a-118">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)  
 <span data-ttu-id="5eb4a-119">Beschreibt die Kriterien, die zum Anpassen einer zeitbasierten Cacherichtlinie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-119">Describes the criteria that can be used to customize a time-based cache policy.</span></span>  
  
 [<span data-ttu-id="5eb4a-120">Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="5eb4a-120">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)  
 <span data-ttu-id="5eb4a-121">Beschreibt, wie Sie programmgesteuert Cacherichtlinien und Anforderungen erstellen, die Zwischenspeicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-121">Describes how to programmatically create cache policies and requests that use caching.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5eb4a-122">Verweis</span><span class="sxs-lookup"><span data-stu-id="5eb4a-122">Reference</span></span>  
 <xref:System.Net.Cache>  
 <span data-ttu-id="5eb4a-123">Definiert die Typen und Enumerationen, mit denen Cacherichtlinien für Ressourcen definiert werden, die mithilfe der Klassen <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> und <xref:System.Net.FtpWebRequest> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5eb4a-123">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>
