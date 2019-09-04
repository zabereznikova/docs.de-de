---
title: <system.runtime.caching>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36e2ed96a0748a69f2bd9ee32432901f0bf0898
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252290"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="3a62f-102">\<System. Runtime. Caching >-Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="3a62f-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="3a62f-103">Stellt die Konfiguration für die standardmäßige speicherinterne Implementierung <xref:System.Runtime.Caching.ObjectCache> über den `memoryCache` -Eintrag in der Konfigurationsdatei bereit.</span><span class="sxs-lookup"><span data-stu-id="3a62f-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="3a62f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a62f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a62f-105">&nbsp;&nbsp; **\<System. Runtime. Caching->**</span><span class="sxs-lookup"><span data-stu-id="3a62f-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a62f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a62f-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a62f-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a62f-107">Attributes and Elements</span></span>

<span data-ttu-id="3a62f-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a62f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a62f-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a62f-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="3a62f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a62f-110">Child Elements</span></span>

|<span data-ttu-id="3a62f-111">Element</span><span class="sxs-lookup"><span data-stu-id="3a62f-111">Element</span></span>|<span data-ttu-id="3a62f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a62f-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a62f-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="3a62f-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="3a62f-114">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="3a62f-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a62f-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a62f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3a62f-116">Element</span><span class="sxs-lookup"><span data-stu-id="3a62f-116">Element</span></span>|<span data-ttu-id="3a62f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a62f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a62f-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3a62f-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="3a62f-119">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a62f-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a62f-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a62f-120">Remarks</span></span>

<span data-ttu-id="3a62f-121">Die Klassen in diesem Namespace bieten eine Möglichkeit, Zwischenspeicherfunktionen wie jene in ASP.NET zu verwenden, jedoch ohne eine Abhängigkeit von der `System.Web` -Assembly.</span><span class="sxs-lookup"><span data-stu-id="3a62f-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="3a62f-122">Weitere Informationen finden Sie unter [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="3a62f-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a62f-123">Die Ausgabe zwischen Speicherungs Funktionen und- <xref:System.Runtime.Caching> Typen im-Namespace sind neu in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3a62f-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a62f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a62f-124">Example</span></span>

<span data-ttu-id="3a62f-125">Das folgende Beispiel zeigt die Konfiguration eines Cache, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="3a62f-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="3a62f-126">Das Beispiel veranschaulicht, wie eine Instanz des `namedCaches` -Eintrags für den Arbeitsspeichercache konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="3a62f-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="3a62f-127">Der Name des Caches wird auf den Standardnamen des Cache Eintrags festgelegt, `name` indem das-Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3a62f-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="3a62f-128">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3a62f-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="3a62f-129">Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a62f-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="3a62f-130">Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3a62f-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a62f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a62f-131">See also</span></span>

- [<span data-ttu-id="3a62f-132">\<MemoryCache-> Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="3a62f-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
