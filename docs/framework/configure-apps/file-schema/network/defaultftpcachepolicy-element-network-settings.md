---
title: <defaultFtpCachePolicy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: eda246c93660c1a37f7db3a6a38144a44a0ae1d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279707"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="e1b16-102">\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e1b16-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="e1b16-103">Beschreibt, ob der FTP-caching ist aktiv und wird beschrieben, die Standardcachingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="e1b16-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="e1b16-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e1b16-104">\<configuration></span></span>  
<span data-ttu-id="e1b16-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e1b16-105">\<system.net></span></span>  
<span data-ttu-id="e1b16-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="e1b16-106">\<requestCaching></span></span>  
<span data-ttu-id="e1b16-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="e1b16-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b16-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1b16-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1b16-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1b16-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e1b16-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1b16-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1b16-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1b16-111">Attributes</span></span>  
  
|<span data-ttu-id="e1b16-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e1b16-112">Attribute</span></span>|<span data-ttu-id="e1b16-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1b16-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="e1b16-114">Gibt die FTP-Cachingrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="e1b16-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="e1b16-115">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="e1b16-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="e1b16-116">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="e1b16-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="e1b16-117">Wert</span><span class="sxs-lookup"><span data-stu-id="e1b16-117">Value</span></span>|<span data-ttu-id="e1b16-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1b16-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="e1b16-119">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource aktuell ist, die Inhaltslänge genau ist und den Ablauf, Änderungen und Content-Length-Attribute vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e1b16-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="e1b16-120">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="e1b16-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="e1b16-121">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und der Größe des Eintrags übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e1b16-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="e1b16-122">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge bereitgestellt wird und der Größe des Eintrags übereinstimmt. Andernfalls wird die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e1b16-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e1b16-123">Gibt die zwischengespeicherte Ressource zurück, wenn es sich bei der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server identisch ist; Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e1b16-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="e1b16-124">Lädt die Ressource vom Server herunter, speichert sie in den Cache und die Ressource an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e1b16-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="e1b16-125">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e1b16-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="e1b16-126">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e1b16-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="e1b16-127">Führt eine Anforderung mithilfe die zwischengespeicherte Kopie der Ressource, wenn der Zeitstempel der Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls ist die Ressource vom Server heruntergeladen, an den Aufrufer angezeigt und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e1b16-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1b16-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1b16-128">Child Elements</span></span>  
 <span data-ttu-id="e1b16-129">Keine</span><span class="sxs-lookup"><span data-stu-id="e1b16-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1b16-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1b16-130">Parent Elements</span></span>  
  
|<span data-ttu-id="e1b16-131">Element</span><span class="sxs-lookup"><span data-stu-id="e1b16-131">Element</span></span>|<span data-ttu-id="e1b16-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1b16-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1b16-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="e1b16-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="e1b16-134">Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="e1b16-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1b16-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1b16-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1b16-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1b16-136">Example</span></span>  
 <span data-ttu-id="e1b16-137">Das folgende Beispiel zeigt, wie Sie eine FTP-Cachingrichtlinie angeben `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="e1b16-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1b16-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1b16-138">See also</span></span>
- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="e1b16-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e1b16-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
