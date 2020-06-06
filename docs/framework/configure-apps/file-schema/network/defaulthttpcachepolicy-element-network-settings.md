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
ms.openlocfilehash: c5029a7d1e53c28d0abb232efdc3e0bd2c9658d4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088422"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="498a0-102">\<defaultHttpCachePolicy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="498a0-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="498a0-103">Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="498a0-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="498a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="498a0-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="498a0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="498a0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="498a0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="498a0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="498a0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="498a0-107">Attributes</span></span>  
  
|<span data-ttu-id="498a0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="498a0-108">Attribute</span></span>|<span data-ttu-id="498a0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="498a0-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="498a0-110">Gibt das maximale Zeitintervall an, nach dem ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="498a0-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="498a0-111">Gibt die maximale Zeit an, die nach der berechneten Aktualität liegt, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="498a0-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="498a0-112">Gibt die minimale Zeit an, für die ein zwischengespeichertes Objekt als aktuell angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="498a0-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="498a0-113">Gibt an, ob die Cachingrichtlinie automatisch erfolgt oder ob der Cache umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="498a0-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="498a0-114">Der Standardwert ist `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="498a0-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="498a0-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="498a0-115">Child Elements</span></span>  
 <span data-ttu-id="498a0-116">Keine</span><span class="sxs-lookup"><span data-stu-id="498a0-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="498a0-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="498a0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="498a0-118">Element</span><span class="sxs-lookup"><span data-stu-id="498a0-118">Element</span></span>|<span data-ttu-id="498a0-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="498a0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="498a0-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="498a0-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="498a0-121">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="498a0-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="498a0-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="498a0-122">Remarks</span></span>  
 <span data-ttu-id="498a0-123">Der Wert für das- `policyLevel` Attribut ist entweder `BypassCache` oder `Default` .</span><span class="sxs-lookup"><span data-stu-id="498a0-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="498a0-124">Werte für die `maximumAge` `maximumStale` Elemente, und `minimumFresh` sind entweder ein explizites Zeitintervall mit dem Format *d*.\* HH*:*mm*:*SS\* (Tage, Stunden, Minuten und Sekunden) oder die Konstanten `minValue` oder, je nach `maxValue` Bedarf.</span><span class="sxs-lookup"><span data-stu-id="498a0-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="498a0-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="498a0-125">Configuration Files</span></span>  
 <span data-ttu-id="498a0-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="498a0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="498a0-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="498a0-127">Example</span></span>  
 <span data-ttu-id="498a0-128">Im folgenden Beispiel wird gezeigt, wie eine minimale neue Zeit von sechs Stunden, eine maximale Alters Zeit von zwei Tagen und eine maximale veraltete Zeit von vier Stunden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="498a0-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="498a0-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="498a0-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="498a0-130">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="498a0-130">Network Settings Schema</span></span>](index.md)
