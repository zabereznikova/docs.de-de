---
title: '&lt;DefaultFtpCachePolicy&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6b9a5fb2f62c27d278570ad789deab30917bc432
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="361db-102">&lt;DefaultFtpCachePolicy&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="361db-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="361db-103">Beschreibt, ob der FTP-caching ist aktiv und beschreibt die Standardcachingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="361db-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="361db-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="361db-104">\<configuration></span></span>  
<span data-ttu-id="361db-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="361db-105">\<system.net></span></span>  
<span data-ttu-id="361db-106">\<RequestCaching ></span><span class="sxs-lookup"><span data-stu-id="361db-106">\<requestCaching></span></span>  
<span data-ttu-id="361db-107">\<DefaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="361db-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361db-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="361db-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="361db-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="361db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="361db-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="361db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="361db-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="361db-111">Attributes</span></span>  
  
|<span data-ttu-id="361db-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="361db-112">Attribute</span></span>|<span data-ttu-id="361db-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="361db-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="361db-114">Gibt die FTP-Cachingrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="361db-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="361db-115">Der Standardwert ist `Default`.</span><span class="sxs-lookup"><span data-stu-id="361db-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="361db-116">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="361db-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="361db-117">Wert</span><span class="sxs-lookup"><span data-stu-id="361db-117">Value</span></span>|<span data-ttu-id="361db-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="361db-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="361db-119">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource frische ist und die Inhaltslänge genau wird den Ablauf, Änderung und Content-Length-Attribute vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="361db-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="361db-120">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="361db-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="361db-121">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und der Größe des Eintrags übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="361db-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="361db-122">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge bereitgestellt werden und der Größe des Eintrags übereinstimmt. Andernfalls wird die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="361db-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="361db-123">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource identisch mit dem Zeitstempel der Ressource auf dem Server ist; Andernfalls wird die Ressource vom Server heruntergeladen im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="361db-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="361db-124">Die Ressource vom Server heruntergeladen, speichert ihn im Cache und die Ressource an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="361db-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="361db-125">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird er gelöscht.</span><span class="sxs-lookup"><span data-stu-id="361db-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="361db-126">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="361db-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="361db-127">Führt eine Anforderung mithilfe die zwischengespeicherte Kopie der Ressource, wenn der Zeitstempel der Zeitstempel der Ressource auf dem Server identisch ist. andernfalls, die Ressource vom Server heruntergeladen, an den Aufrufer angezeigt und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="361db-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="361db-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="361db-128">Child Elements</span></span>  
 <span data-ttu-id="361db-129">Keine</span><span class="sxs-lookup"><span data-stu-id="361db-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="361db-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="361db-130">Parent Elements</span></span>  
  
|<span data-ttu-id="361db-131">Element</span><span class="sxs-lookup"><span data-stu-id="361db-131">Element</span></span>|<span data-ttu-id="361db-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="361db-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="361db-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="361db-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="361db-134">Steuert den Zwischenspeichermechanismus für Anforderungen über das Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="361db-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="361db-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="361db-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="361db-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="361db-136">Example</span></span>  
 <span data-ttu-id="361db-137">Im folgende Beispiel wird gezeigt, wie ein FTP-Cachingrichtlinie an `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="361db-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="361db-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="361db-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="361db-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="361db-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
