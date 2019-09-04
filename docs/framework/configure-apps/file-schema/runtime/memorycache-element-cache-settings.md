---
title: <memoryCache>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 25467fc751ad772e74ca714e6059bc5134300ed6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252485"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="9b55f-102">\<MemoryCache-> Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9b55f-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="9b55f-103">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="9b55f-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="9b55f-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> -Klasse definiert ein [memoryCache](memorycache-element-cache-settings.md) -Element, das Sie zum Konfigurieren des Caches verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9b55f-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="9b55f-105">Mehrere Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können in einer einzigen Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b55f-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="9b55f-106">Jedes `memoryCache` -Element in der Konfigurationsdatei kann Einstellungen für eine benannte <xref:System.Runtime.Caching.MemoryCache> -Instanz enthalten.</span><span class="sxs-lookup"><span data-stu-id="9b55f-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
<span data-ttu-id="9b55f-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b55f-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b55f-108">&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9b55f-108">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="9b55f-109">&nbsp;&nbsp;&nbsp;&nbsp; **\<MemoryCache->**</span><span class="sxs-lookup"><span data-stu-id="9b55f-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b55f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b55f-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="9b55f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="9b55f-111">Type</span></span>  
 <span data-ttu-id="9b55f-112"><xref:System.Runtime.Caching.MemoryCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="9b55f-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b55f-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b55f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9b55f-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b55f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b55f-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b55f-115">Attributes</span></span>  
  
|<span data-ttu-id="9b55f-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="9b55f-116">Attribute</span></span>|<span data-ttu-id="9b55f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b55f-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="9b55f-118">Die maximale Arbeitsspeichergröße in Megabyte, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> -Objekts anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="9b55f-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="9b55f-119">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b55f-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="9b55f-120">Der Name der Cachekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b55f-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="9b55f-121">Der Prozentsatz des physischen Arbeitsspeichers, der vom Cache verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9b55f-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="9b55f-122">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b55f-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="9b55f-123">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="9b55f-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="9b55f-124">Der Wert wird im Format „HH:MM:SS“ eingegeben.</span><span class="sxs-lookup"><span data-stu-id="9b55f-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b55f-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b55f-125">Child Elements</span></span>  
  
|<span data-ttu-id="9b55f-126">Element</span><span class="sxs-lookup"><span data-stu-id="9b55f-126">Element</span></span>|<span data-ttu-id="9b55f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b55f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b55f-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9b55f-128">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="9b55f-129">Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.</span><span class="sxs-lookup"><span data-stu-id="9b55f-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b55f-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b55f-130">Parent Elements</span></span>  
  
|<span data-ttu-id="9b55f-131">Element</span><span class="sxs-lookup"><span data-stu-id="9b55f-131">Element</span></span>|<span data-ttu-id="9b55f-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b55f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b55f-133">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b55f-133">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="9b55f-134">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b55f-134">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9b55f-135">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="9b55f-135">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="9b55f-136">Enthält Typen, mit denen Sie die Ausgabe Zwischenspeicherung in Anwendungen implementieren können, die in die .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="9b55f-136">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b55f-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b55f-137">Remarks</span></span>  
 <span data-ttu-id="9b55f-138">Die <xref:System.Runtime.Caching.MemoryCache> -Klasse ist eine konkrete Implementierung der abstrakten <xref:System.Runtime.Caching.ObjectCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="9b55f-138">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="9b55f-139">Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können mit Konfigurationsinformationen von Anwendungskonfigurationsdateien versorgt werden.</span><span class="sxs-lookup"><span data-stu-id="9b55f-139">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="9b55f-140">Der Abschnitt [memoryCache](memorycache-element-cache-settings.md) -Konfiguration enthält eine `namedCaches` -Konfigurationssammlung.</span><span class="sxs-lookup"><span data-stu-id="9b55f-140">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="9b55f-141">Wenn ein speicherbasierendes Cacheobjekt initialisiert wird, versucht es zuerst, einen `namedCaches` -Eintrag zu finden, der dem Namen in dem Parameter entspricht, der an den Speichercache-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9b55f-141">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="9b55f-142">Wenn ein `namedCaches` -Eintrag gefunden wird, werden Abruf- und Speicher-Management-Informationen aus der Konfigurationsdatei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9b55f-142">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="9b55f-143">Der Initialisierungsprozess bestimmt dann mithilfe der optionalen Sammlung von Name-Wert-Paaren mit Konfigurationsinformationen im Konstruktor, ob Konfigurationseinträge überschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="9b55f-143">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="9b55f-144">Wenn Sie einen oder mehrere der folgenden Werte in der Name-Wert-Paar-Sammlung übergeben, überschreiben diese Werte Informationen aus der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="9b55f-144">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="9b55f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b55f-145">Example</span></span>  
 <span data-ttu-id="9b55f-146">Im folgenden Beispiel wird gezeigt, wie der Name des <xref:System.Runtime.Caching.MemoryCache> -Objekts auf den standardmäßigen Cache Objektnamen festgelegt wird, indem das `name` -Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9b55f-146">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="9b55f-147">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryLimitPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9b55f-147">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="9b55f-148">Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b55f-148">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="9b55f-149">Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="9b55f-149">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b55f-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b55f-150">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="9b55f-151">\<System. Runtime. Caching >-Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9b55f-151">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="9b55f-152">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9b55f-152">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
