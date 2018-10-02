---
title: '&lt;RequestCaching&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3e014c7a47a53a424bbaef51c9acb28e59b43078
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028143"
---
# <a name="ltrequestcachinggt-element-network-settings"></a><span data-ttu-id="54201-102">&lt;RequestCaching&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="54201-102">&lt;requestCaching&gt; Element (Network Settings)</span></span>
<span data-ttu-id="54201-103">Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="54201-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="54201-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="54201-104">\<configuration></span></span>  
<span data-ttu-id="54201-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="54201-105">\<system.net></span></span>  
<span data-ttu-id="54201-106">\<RequestCaching ></span><span class="sxs-lookup"><span data-stu-id="54201-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54201-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="54201-107">Syntax</span></span>  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54201-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54201-108">Attributes and Elements</span></span>  
 <span data-ttu-id="54201-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54201-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54201-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="54201-110">Attributes</span></span>  
  
|<span data-ttu-id="54201-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="54201-111">Attribute</span></span>|<span data-ttu-id="54201-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54201-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="54201-113">Gibt an, ob der Cache Isolation zwischen den Daten der Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="54201-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="54201-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="54201-114">The default value is `true`.</span></span> <span data-ttu-id="54201-115">Dieser Wert sollte sein `false` für Anwendungen der mittleren Ebene.</span><span class="sxs-lookup"><span data-stu-id="54201-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="54201-116">Gibt an, dass Zwischenspeichern für alle Webantworten deaktiviert ist, und kann nicht programmgesteuert überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="54201-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="54201-117">Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="54201-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="54201-118">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="54201-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="54201-119">Gibt die Standardzeit, die nach der Inhalt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="54201-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="54201-120">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="54201-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="54201-121">Wert</span><span class="sxs-lookup"><span data-stu-id="54201-121">Value</span></span>|<span data-ttu-id="54201-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54201-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="54201-123">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource aktuell ist, die Inhaltslänge genau ist und den Ablauf, Änderungen und Content-Length-Attribute vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="54201-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="54201-124">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="54201-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="54201-125">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge vorhanden ist und der Größe des Eintrags übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="54201-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="54201-126">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhaltslänge bereitgestellt wird und der Größe des Eintrags übereinstimmt. Andernfalls wird die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="54201-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="54201-127">Gibt die zwischengespeicherte Ressource zurück, wenn es sich bei der Timestamp der zwischengespeicherten Ressource dem Timestamp der Ressource auf dem Server identisch ist; Andernfalls wird die Ressource wird vom Server ab, das im Cache gespeichert, heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="54201-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="54201-128">Lädt die Ressource vom Server herunter, speichert sie in den Cache und die Ressource an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="54201-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="54201-129">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="54201-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="54201-130">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="54201-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="54201-131">Führt eine Anforderung mithilfe die zwischengespeicherte Kopie der Ressource, wenn der Zeitstempel der Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource wird heruntergeladen, vom Server an den Aufrufer angezeigt und im Cache gespeichert wird,</span><span class="sxs-lookup"><span data-stu-id="54201-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54201-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54201-132">Child Elements</span></span>  
  
|<span data-ttu-id="54201-133">Element</span><span class="sxs-lookup"><span data-stu-id="54201-133">Element</span></span>|<span data-ttu-id="54201-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54201-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54201-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="54201-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="54201-136">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="54201-136">Optional element.</span></span><br /><br /> <span data-ttu-id="54201-137">Beschreibt, ob HTTP-Zwischenspeicherung aktiv ist und die Standardcachingrichtlinie beschreibt.</span><span class="sxs-lookup"><span data-stu-id="54201-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="54201-138">\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="54201-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="54201-139">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="54201-139">Optional element.</span></span><br /><br /> <span data-ttu-id="54201-140">Beschreibt, ob der FTP-caching ist aktiv und wird beschrieben, die Standardcachingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="54201-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54201-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54201-141">Parent Elements</span></span>  
  
|<span data-ttu-id="54201-142">Element</span><span class="sxs-lookup"><span data-stu-id="54201-142">Element</span></span>|<span data-ttu-id="54201-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54201-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54201-144">System.NET</span><span class="sxs-lookup"><span data-stu-id="54201-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="54201-145">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="54201-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54201-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54201-146">Example</span></span>  
 <span data-ttu-id="54201-147">Das folgende Beispiel zeigt, wie Zwischenspeicherung deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="54201-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54201-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54201-148">See Also</span></span>  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [<span data-ttu-id="54201-149">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="54201-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
