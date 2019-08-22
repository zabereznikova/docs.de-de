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
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659424"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="c23a5-102">\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c23a5-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="c23a5-103">Beschreibt, ob das FTP-Caching aktiv ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c23a5-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="c23a5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c23a5-104">\<configuration></span></span>  
<span data-ttu-id="c23a5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c23a5-105">\<system.net></span></span>  
<span data-ttu-id="c23a5-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="c23a5-106">\<requestCaching></span></span>  
<span data-ttu-id="c23a5-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="c23a5-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23a5-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c23a5-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c23a5-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c23a5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c23a5-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c23a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c23a5-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c23a5-111">Attributes</span></span>  
  
|<span data-ttu-id="c23a5-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c23a5-112">Attribute</span></span>|<span data-ttu-id="c23a5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c23a5-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="c23a5-114">Gibt die FTP-Caching-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="c23a5-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="c23a5-115">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="c23a5-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="c23a5-116">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="c23a5-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="c23a5-117">Wert</span><span class="sxs-lookup"><span data-stu-id="c23a5-117">Value</span></span>|<span data-ttu-id="c23a5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c23a5-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="c23a5-119">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource neu ist, die Länge des Inhalts genau ist und die Attribute für die Ablauf-, Änderungs-und Inhalts Länge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c23a5-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="c23a5-120">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="c23a5-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="c23a5-121">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge vorhanden ist und mit der Eingabe Größe übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c23a5-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="c23a5-122">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge angegeben wird und mit der Eintrags Größe übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c23a5-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="c23a5-123">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c23a5-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="c23a5-124">Lädt die Ressource vom Server herunter, speichert Sie im Cache und gibt die Ressource an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="c23a5-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="c23a5-125">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird Sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c23a5-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="c23a5-126">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c23a5-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="c23a5-127">Erfüllt eine Anforderung mithilfe der zwischengespeicherten Kopie der Ressource, wenn der Zeitstempel mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer angezeigt und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c23a5-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c23a5-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c23a5-128">Child Elements</span></span>  
 <span data-ttu-id="c23a5-129">Keine</span><span class="sxs-lookup"><span data-stu-id="c23a5-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c23a5-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c23a5-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c23a5-131">Element</span><span class="sxs-lookup"><span data-stu-id="c23a5-131">Element</span></span>|<span data-ttu-id="c23a5-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c23a5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c23a5-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="c23a5-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="c23a5-134">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c23a5-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c23a5-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c23a5-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="c23a5-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c23a5-136">Example</span></span>  
 <span data-ttu-id="c23a5-137">Im folgenden Beispiel wird gezeigt, wie eine FTP-Cachingrichtlinie von `NoCacheNoStore`angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c23a5-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c23a5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c23a5-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="c23a5-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c23a5-139">Network Settings Schema</span></span>](index.md)
