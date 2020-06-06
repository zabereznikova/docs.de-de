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
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802128"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="f032e-102">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f032e-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="f032e-103">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f032e-103">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="f032e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f032e-104">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f032e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f032e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f032e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f032e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f032e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="f032e-107">Attributes</span></span>  
  
|<span data-ttu-id="f032e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f032e-108">Attribute</span></span>|<span data-ttu-id="f032e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f032e-109">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="f032e-110">Gibt an, ob der Cache eine Isolation zwischen den Informationen verschiedener Benutzer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f032e-110">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="f032e-111">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f032e-111">The default value is `true`.</span></span> <span data-ttu-id="f032e-112">Dieser Wert sollte `false` für Anwendungen der mittleren Ebene sein.</span><span class="sxs-lookup"><span data-stu-id="f032e-112">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="f032e-113">Gibt an, dass das Zwischenspeichern für alle Webanwendungen deaktiviert ist und nicht Programm gesteuert überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f032e-113">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="f032e-114">Einer der Werte in der <xref:System.Net.Cache.RequestCacheLevel>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="f032e-114">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="f032e-115">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="f032e-115">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="f032e-116">Gibt die Standardzeit an, nach der der Inhalt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f032e-116">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="f032e-117">PolicyLevel-Attribut</span><span class="sxs-lookup"><span data-stu-id="f032e-117">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="f032e-118">Wert</span><span class="sxs-lookup"><span data-stu-id="f032e-118">Value</span></span>|<span data-ttu-id="f032e-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f032e-119">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="f032e-120">Gibt die zwischengespeicherte Ressource zurück, wenn die Ressource neu ist, die Länge des Inhalts genau ist und die Attribute für die Ablauf-, Änderungs-und Inhalts Länge vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f032e-120">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="f032e-121">Gibt die Ressource vom Server zurück.</span><span class="sxs-lookup"><span data-stu-id="f032e-121">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="f032e-122">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge vorhanden ist und mit der Eingabe Größe übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f032e-122">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="f032e-123">Gibt die zwischengespeicherte Ressource zurück, wenn die Inhalts Länge angegeben wird und mit der Eintrags Größe übereinstimmt. Andernfalls wird die Ressource vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f032e-123">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f032e-124">Gibt die zwischengespeicherte Ressource zurück, wenn der Zeitstempel der zwischengespeicherten Ressource mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, im Cache gespeichert und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f032e-124">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="f032e-125">Lädt die Ressource vom Server herunter, speichert Sie im Cache und gibt die Ressource an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="f032e-125">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="f032e-126">Wenn eine zwischengespeicherte Ressource vorhanden ist, wird Sie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f032e-126">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="f032e-127">Die Ressource wird vom Server heruntergeladen und an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f032e-127">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="f032e-128">Erfüllt eine Anforderung mithilfe der zwischengespeicherten Kopie der Ressource, wenn der Zeitstempel mit dem Zeitstempel der Ressource auf dem Server identisch ist. Andernfalls wird die Ressource vom Server heruntergeladen, dem Aufrufer präsentiert und im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f032e-128">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f032e-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f032e-129">Child Elements</span></span>  
  
|<span data-ttu-id="f032e-130">Element</span><span class="sxs-lookup"><span data-stu-id="f032e-130">Element</span></span>|<span data-ttu-id="f032e-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f032e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f032e-132">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="f032e-132">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="f032e-133">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f032e-133">Optional element.</span></span><br /><br /> <span data-ttu-id="f032e-134">Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f032e-134">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="f032e-135">\<defaultFtpCachePolicy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f032e-135">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="f032e-136">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f032e-136">Optional element.</span></span><br /><br /> <span data-ttu-id="f032e-137">Beschreibt, ob das FTP-Caching aktiv ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f032e-137">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f032e-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f032e-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f032e-139">Element</span><span class="sxs-lookup"><span data-stu-id="f032e-139">Element</span></span>|<span data-ttu-id="f032e-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f032e-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f032e-141">system.net</span><span class="sxs-lookup"><span data-stu-id="f032e-141">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="f032e-142">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f032e-142">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f032e-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f032e-143">Example</span></span>  
 <span data-ttu-id="f032e-144">Im folgenden Beispiel wird gezeigt, wie alle zwischen Speicherungen deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f032e-144">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f032e-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f032e-145">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="f032e-146">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="f032e-146">Network Settings Schema</span></span>](index.md)
