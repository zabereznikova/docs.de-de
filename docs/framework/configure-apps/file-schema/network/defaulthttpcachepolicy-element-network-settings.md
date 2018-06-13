---
title: '&lt;DefaultHttpCachePolicy&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0425711687a2f8b40f2c645e1c478d52b56ad979
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741840"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a><span data-ttu-id="8c984-102">&lt;DefaultHttpCachePolicy&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8c984-102">&lt;defaultHttpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8c984-103">Beschreibt, ob HTTP-caching aktiv ist und beschreibt die Standardcachingrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="8c984-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="8c984-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c984-104">\<configuration></span></span>  
<span data-ttu-id="8c984-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8c984-105">\<system.net></span></span>  
<span data-ttu-id="8c984-106">\<RequestCaching ></span><span class="sxs-lookup"><span data-stu-id="8c984-106">\<requestCaching></span></span>  
<span data-ttu-id="8c984-107">\<DefaultHttpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="8c984-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c984-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c984-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c984-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c984-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c984-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c984-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c984-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c984-111">Attributes</span></span>  
  
|<span data-ttu-id="8c984-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8c984-112">Attribute</span></span>|<span data-ttu-id="8c984-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c984-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="8c984-114">Gibt das maximale Zeitintervall an, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8c984-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="8c984-115">Gibt die maximale Zeit berechnete Aktualität-Verzögerung, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8c984-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="8c984-116">Gibt die minimale Zeit für ein zwischengespeichertes Objekt als aktuell angesehen.</span><span class="sxs-lookup"><span data-stu-id="8c984-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="8c984-117">Gibt an, ob die Cachingrichtlinie für automatische oder gibt an, ob der Cache umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="8c984-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="8c984-118">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="8c984-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c984-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c984-119">Child Elements</span></span>  
 <span data-ttu-id="8c984-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="8c984-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c984-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c984-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8c984-122">Element</span><span class="sxs-lookup"><span data-stu-id="8c984-122">Element</span></span>|<span data-ttu-id="8c984-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c984-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c984-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="8c984-124">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="8c984-125">Steuert den Zwischenspeichermechanismus für Anforderungen über das Netzwerk an.</span><span class="sxs-lookup"><span data-stu-id="8c984-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c984-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c984-126">Remarks</span></span>  
 <span data-ttu-id="8c984-127">Der Wert für die `policyLevel` -Attribut ist entweder `BypassCache` oder `Default`.</span><span class="sxs-lookup"><span data-stu-id="8c984-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="8c984-128">Werte für die `maximumAge`, `maximumStale`, und `minimumFresh` Elemente sind ein explizites Zeitintervall im Format *d*. *"hh"*:*mm*:*ss* (Tage, Stunden, Minuten und Sekunden), oder die Konstanten `minValue` oder `maxValue`je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="8c984-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8c984-129">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8c984-129">Configuration Files</span></span>  
 <span data-ttu-id="8c984-130">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c984-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c984-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c984-131">Example</span></span>  
 <span data-ttu-id="8c984-132">Das folgende Beispiel zeigt, wie eine neue Mindestzeit von sechs Stunden kommen, ein maximales Alter von zwei Tagen und eine maximale veraltete von vier Stunden an.</span><span class="sxs-lookup"><span data-stu-id="8c984-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c984-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c984-133">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="8c984-134">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8c984-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
