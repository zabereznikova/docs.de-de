---
title: <defaultHttpCachePolicy>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 20d9b92ca2bbffd6b98b8641e5cef5e567cb84cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177377"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="ff5db-102">\<DefaultHttpCachePolicy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ff5db-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="ff5db-103">Beschreibt, ob HTTP-Zwischenspeicherung aktiv ist und die Standardcachingrichtlinie beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ff5db-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="ff5db-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ff5db-104">\<configuration></span></span>  
<span data-ttu-id="ff5db-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ff5db-105">\<system.net></span></span>  
<span data-ttu-id="ff5db-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="ff5db-106">\<requestCaching></span></span>  
<span data-ttu-id="ff5db-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="ff5db-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5db-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff5db-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff5db-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff5db-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ff5db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff5db-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ff5db-111">Attributes</span></span>  
  
|<span data-ttu-id="ff5db-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ff5db-112">Attribute</span></span>|<span data-ttu-id="ff5db-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff5db-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="ff5db-114">Gibt das maximale Zeitintervall an, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ff5db-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="ff5db-115">Gibt die maximale Zeit nach der berechneten Aktualitätszeit, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ff5db-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="ff5db-116">Gibt die minimale Zeit für ein zwischengespeichertes Objekt, das als aktuell angesehen.</span><span class="sxs-lookup"><span data-stu-id="ff5db-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="ff5db-117">Gibt an, ob die Cachingrichtlinie für automatische oder gibt an, ob der Cache umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="ff5db-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="ff5db-118">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="ff5db-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff5db-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5db-119">Child Elements</span></span>  
 <span data-ttu-id="ff5db-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="ff5db-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff5db-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ff5db-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ff5db-122">Element</span><span class="sxs-lookup"><span data-stu-id="ff5db-122">Element</span></span>|<span data-ttu-id="ff5db-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff5db-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff5db-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="ff5db-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="ff5db-125">Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ff5db-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff5db-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff5db-126">Remarks</span></span>  
 <span data-ttu-id="ff5db-127">Der Wert für die `policyLevel` -Attribut ist entweder `BypassCache` oder `Default`.</span><span class="sxs-lookup"><span data-stu-id="ff5db-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="ff5db-128">Werte für die `maximumAge`, `maximumStale`, und `minimumFresh` Elemente sind ein explizites Zeitintervall im Format *d*. *Hh*:*mm*:*ss* (Tage, Stunden, Minuten und Sekunden), oder die Konstanten `minValue` oder `maxValue`je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ff5db-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ff5db-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="ff5db-129">Configuration Files</span></span>  
 <span data-ttu-id="ff5db-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff5db-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff5db-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff5db-131">Example</span></span>  
 <span data-ttu-id="ff5db-132">Das folgende Beispiel zeigt, wie Sie eine neue Zeit von sechs Stunden, ein maximales Alter zwei Tage, bis eine maximale veraltete Zeit von vier Stunden angeben.</span><span class="sxs-lookup"><span data-stu-id="ff5db-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff5db-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff5db-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="ff5db-134">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ff5db-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
