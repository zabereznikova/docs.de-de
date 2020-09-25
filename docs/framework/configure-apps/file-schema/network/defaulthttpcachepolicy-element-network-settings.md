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
ms.openlocfilehash: 4120c57fbb65da1c124414cbe9cfba7ae64388f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190318"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="288b3-102">\<defaultHttpCachePolicy>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="288b3-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="288b3-103">Beschreibt, ob HTTP-Zwischenspeicherung aktiviert ist, und beschreibt die Standard Cache Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="288b3-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="288b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="288b3-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="288b3-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="288b3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="288b3-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="288b3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="288b3-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="288b3-107">Attributes</span></span>  
  
|<span data-ttu-id="288b3-108">attribute</span><span class="sxs-lookup"><span data-stu-id="288b3-108">Attribute</span></span>|<span data-ttu-id="288b3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288b3-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="288b3-110">Gibt das maximale Zeitintervall an, nach dem ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="288b3-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="288b3-111">Gibt die maximale Zeit an, die nach der berechneten Aktualität liegt, bevor ein zwischengespeichertes Objekt als abgelaufen gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="288b3-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="288b3-112">Gibt die minimale Zeit an, für die ein zwischengespeichertes Objekt als aktuell angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="288b3-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="288b3-113">Gibt an, ob die Cachingrichtlinie automatisch erfolgt oder ob der Cache umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="288b3-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="288b3-114">Standardwert: `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="288b3-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="288b3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288b3-115">Child Elements</span></span>  

 <span data-ttu-id="288b3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="288b3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="288b3-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="288b3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="288b3-118">Element</span><span class="sxs-lookup"><span data-stu-id="288b3-118">Element</span></span>|<span data-ttu-id="288b3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="288b3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="288b3-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="288b3-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="288b3-121">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="288b3-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="288b3-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="288b3-122">Remarks</span></span>  

 <span data-ttu-id="288b3-123">Der Wert für das- `policyLevel` Attribut ist entweder `BypassCache` oder `Default` .</span><span class="sxs-lookup"><span data-stu-id="288b3-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="288b3-124">Werte für die `maximumAge` `maximumStale` Elemente, und `minimumFresh` sind entweder ein explizites Zeitintervall mit dem Format *d*.\* HH*:*mm*:*SS\* (Tage, Stunden, Minuten und Sekunden) oder die Konstanten `minValue` oder, je nach `maxValue` Bedarf.</span><span class="sxs-lookup"><span data-stu-id="288b3-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="288b3-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="288b3-125">Configuration Files</span></span>  

 <span data-ttu-id="288b3-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="288b3-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="288b3-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="288b3-127">Example</span></span>  

 <span data-ttu-id="288b3-128">Im folgenden Beispiel wird gezeigt, wie eine minimale neue Zeit von sechs Stunden, eine maximale Alters Zeit von zwei Tagen und eine maximale veraltete Zeit von vier Stunden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="288b3-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="288b3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="288b3-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="288b3-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="288b3-130">Network Settings Schema</span></span>](index.md)
