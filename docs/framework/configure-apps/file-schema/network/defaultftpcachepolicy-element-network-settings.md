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
ms.openlocfilehash: e081882aa8df89c0a1bf5d4c60f1395a3319c417
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190370"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="b76c1-102">\<defaultFtpCachePolicy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b76c1-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="b76c1-103">Beschreibt, ob das FTP-Caching aktiv ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b76c1-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="b76c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b76c1-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b76c1-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b76c1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b76c1-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b76c1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b76c1-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b76c1-107">Attributes</span></span>  
  
|<span data-ttu-id="b76c1-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b76c1-108">Attribute</span></span>|<span data-ttu-id="b76c1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b76c1-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="b76c1-110">Gibt die FTP-Caching-Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="b76c1-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="b76c1-111">Standardwert: `Default`.</span><span class="sxs-lookup"><span data-stu-id="b76c1-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="b76c1-112">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="b76c1-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="b76c1-113">Wert</span><span class="sxs-lookup"><span data-stu-id="b76c1-113">Value</span></span>|<span data-ttu-id="b76c1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b76c1-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="b76c1-115">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource neu ist, die Länge des Inhalts genau ist und die Attribute für die Ablauf-, Änderungs-und Inhalts Länge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b76c1-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="b76c1-116">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="b76c1-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="b76c1-117">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge vorhanden ist und mit der Eingabe Größe übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b76c1-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="b76c1-118">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge angegeben wird und mit der Eintrags Größe übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b76c1-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b76c1-119">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b76c1-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="b76c1-120">Lädt die Ressource vom Server herunter, speichert Sie im Cache und gibt die Ressource an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="b76c1-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="b76c1-121">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird Sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b76c1-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="b76c1-122">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b76c1-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="b76c1-123">Erfüllt eine Anforderung, indem die zwischengespeicherte Kopie der Ressource zurückgegeben wird, wenn der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server entspricht. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer dargestellt und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b76c1-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b76c1-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b76c1-124">Child Elements</span></span>  

 <span data-ttu-id="b76c1-125">Keine</span><span class="sxs-lookup"><span data-stu-id="b76c1-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b76c1-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b76c1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b76c1-127">Element</span><span class="sxs-lookup"><span data-stu-id="b76c1-127">Element</span></span>|<span data-ttu-id="b76c1-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b76c1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b76c1-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="b76c1-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="b76c1-130">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="b76c1-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b76c1-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b76c1-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="b76c1-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b76c1-132">Example</span></span>  

 <span data-ttu-id="b76c1-133">Im folgenden Beispiel wird gezeigt, wie eine FTP-Cachingrichtlinie von angegeben wird `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="b76c1-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b76c1-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b76c1-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="b76c1-135">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b76c1-135">Network Settings Schema</span></span>](index.md)
