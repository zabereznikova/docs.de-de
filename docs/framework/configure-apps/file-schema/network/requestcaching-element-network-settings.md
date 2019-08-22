---
title: <requestCaching>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: 2a3d0b182acad2351ed095934ca97c6194d344fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659138"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="c1299-102">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1299-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="c1299-103">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="c1299-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="c1299-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c1299-104">\<configuration></span></span>  
<span data-ttu-id="c1299-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c1299-105">\<system.net></span></span>  
<span data-ttu-id="c1299-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="c1299-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1299-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1299-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1299-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1299-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c1299-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1299-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1299-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1299-110">Attributes</span></span>  
  
|<span data-ttu-id="c1299-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1299-111">Attribute</span></span>|<span data-ttu-id="c1299-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1299-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="c1299-113">Gibt an, ob der Cache eine Isolation zwischen den Informationen verschiedener Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c1299-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="c1299-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="c1299-114">The default value is `true`.</span></span> <span data-ttu-id="c1299-115">Dieser Wert sollte für `false` Anwendungen der mittleren Ebene sein.</span><span class="sxs-lookup"><span data-stu-id="c1299-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="c1299-116">Gibt an, dass das Zwischenspeichern für alle Webanwendungen deaktiviert ist und nicht Programm gesteuert überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1299-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="c1299-117">Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c1299-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="c1299-118">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="c1299-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="c1299-119">Gibt die Standardzeit an, nach der der Inhalt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c1299-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="c1299-120">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="c1299-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="c1299-121">Wert</span><span class="sxs-lookup"><span data-stu-id="c1299-121">Value</span></span>|<span data-ttu-id="c1299-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1299-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="c1299-123">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource neu ist, die Länge des Inhalts genau ist und die Attribute für die Ablauf-, Änderungs-und Inhalts Länge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c1299-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="c1299-124">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="c1299-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="c1299-125">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge vorhanden ist und mit der Eingabe Größe übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c1299-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="c1299-126">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge angegeben wird und mit der Eintrags Größe übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1299-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="c1299-127">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1299-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="c1299-128">Lädt die Ressource vom Server herunter, speichert Sie im Cache und gibt die Ressource an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="c1299-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="c1299-129">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird Sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="c1299-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="c1299-130">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c1299-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="c1299-131">Erfüllt eine Anforderung mithilfe der zwischengespeicherten Kopie der Ressource, wenn der Zeitstempel mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer präsentiert und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c1299-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1299-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1299-132">Child Elements</span></span>  
  
|<span data-ttu-id="c1299-133">Element</span><span class="sxs-lookup"><span data-stu-id="c1299-133">Element</span></span>|<span data-ttu-id="c1299-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1299-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1299-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="c1299-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="c1299-136">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c1299-136">Optional element.</span></span><br /><br /> <span data-ttu-id="c1299-137">Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c1299-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="c1299-138">\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1299-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="c1299-139">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c1299-139">Optional element.</span></span><br /><br /> <span data-ttu-id="c1299-140">Beschreibt, ob das FTP-Caching aktiv ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="c1299-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1299-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1299-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c1299-142">Element</span><span class="sxs-lookup"><span data-stu-id="c1299-142">Element</span></span>|<span data-ttu-id="c1299-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1299-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1299-144">system.net</span><span class="sxs-lookup"><span data-stu-id="c1299-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c1299-145">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c1299-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1299-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1299-146">Example</span></span>  
 <span data-ttu-id="c1299-147">Im folgenden Beispiel wird gezeigt, wie alle zwischen Speicherungen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c1299-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1299-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1299-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="c1299-149">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1299-149">Network Settings Schema</span></span>](index.md)
