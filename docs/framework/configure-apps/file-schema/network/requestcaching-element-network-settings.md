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
ms.openlocfilehash: f0979d2e0caeb0b22b90572aef0ad53235020f1d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697829"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="f971d-102">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f971d-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="f971d-103">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f971d-103">Controls the caching mechanism for network requests.</span></span>  
  
[<span data-ttu-id="f971d-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f971d-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f971d-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f971d-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="f971d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<requestCaching >**</span><span class="sxs-lookup"><span data-stu-id="f971d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f971d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f971d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f971d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f971d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f971d-109">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f971d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f971d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="f971d-110">Attributes</span></span>  
  
|<span data-ttu-id="f971d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="f971d-111">Attribute</span></span>|<span data-ttu-id="f971d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f971d-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="f971d-113">Gibt an, ob der Cache eine Isolation zwischen den Informationen verschiedener Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f971d-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="f971d-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f971d-114">The default value is `true`.</span></span> <span data-ttu-id="f971d-115">Dieser Wert sollte für Anwendungen der mittleren Ebene `false` werden.</span><span class="sxs-lookup"><span data-stu-id="f971d-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="f971d-116">Gibt an, dass das Zwischenspeichern für alle Webanwendungen deaktiviert ist und nicht Programm gesteuert überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f971d-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="f971d-117">Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="f971d-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="f971d-118">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="f971d-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="f971d-119">Gibt die Standardzeit an, nach der der Inhalt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f971d-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="f971d-120">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="f971d-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="f971d-121">Wert</span><span class="sxs-lookup"><span data-stu-id="f971d-121">Value</span></span>|<span data-ttu-id="f971d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f971d-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="f971d-123">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource neu ist, die Länge des Inhalts genau ist und die Attribute für die Ablauf-, Änderungs-und Inhalts Länge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f971d-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="f971d-124">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="f971d-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="f971d-125">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge vorhanden ist und mit der Eingabe Größe übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f971d-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="f971d-126">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge angegeben wird und mit der Eintrags Größe übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f971d-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f971d-127">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f971d-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="f971d-128">Lädt die Ressource vom Server herunter, speichert Sie im Cache und gibt die Ressource an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="f971d-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="f971d-129">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird Sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f971d-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="f971d-130">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f971d-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f971d-131">Erfüllt eine Anforderung mithilfe der zwischengespeicherten Kopie der Ressource, wenn der Zeitstempel mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer präsentiert und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f971d-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f971d-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f971d-132">Child Elements</span></span>  
  
|<span data-ttu-id="f971d-133">Element</span><span class="sxs-lookup"><span data-stu-id="f971d-133">Element</span></span>|<span data-ttu-id="f971d-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f971d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f971d-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="f971d-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="f971d-136">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f971d-136">Optional element.</span></span><br /><br /> <span data-ttu-id="f971d-137">Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f971d-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="f971d-138">\<DefaultFtpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f971d-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="f971d-139">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f971d-139">Optional element.</span></span><br /><br /> <span data-ttu-id="f971d-140">Beschreibt, ob das FTP-Caching aktiv ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f971d-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f971d-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f971d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f971d-142">Element</span><span class="sxs-lookup"><span data-stu-id="f971d-142">Element</span></span>|<span data-ttu-id="f971d-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f971d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f971d-144">system.net</span><span class="sxs-lookup"><span data-stu-id="f971d-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f971d-145">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f971d-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f971d-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f971d-146">Example</span></span>  
 <span data-ttu-id="f971d-147">Im folgenden Beispiel wird gezeigt, wie alle zwischen Speicherungen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f971d-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f971d-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f971d-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="f971d-149">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f971d-149">Network Settings Schema</span></span>](index.md)
