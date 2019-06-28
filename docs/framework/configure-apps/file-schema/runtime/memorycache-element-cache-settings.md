---
title: <memoryCache>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 4f1dd270ee1b317ec0d3a32e341680646ff0b69d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423289"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="64bba-102">\<MemoryCache >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64bba-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="64bba-103">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="64bba-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="64bba-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> -Klasse definiert ein [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) -Element, das Sie zum Konfigurieren des Caches verwenden können.</span><span class="sxs-lookup"><span data-stu-id="64bba-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="64bba-105">Mehrere Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können in einer einzigen Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64bba-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="64bba-106">Jedes `memoryCache` -Element in der Konfigurationsdatei kann Einstellungen für eine benannte <xref:System.Runtime.Caching.MemoryCache> -Instanz enthalten.</span><span class="sxs-lookup"><span data-stu-id="64bba-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="64bba-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64bba-107">\<configuration></span></span>  
<span data-ttu-id="64bba-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="64bba-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="64bba-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="64bba-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64bba-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="64bba-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="64bba-111">Typ</span><span class="sxs-lookup"><span data-stu-id="64bba-111">Type</span></span>  
 <span data-ttu-id="64bba-112"><xref:System.Runtime.Caching.MemoryCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="64bba-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64bba-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="64bba-113">Attributes and Elements</span></span>  
 <span data-ttu-id="64bba-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64bba-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64bba-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="64bba-115">Attributes</span></span>  
  
|<span data-ttu-id="64bba-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="64bba-116">Attribute</span></span>|<span data-ttu-id="64bba-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64bba-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="64bba-118">Die maximale Arbeitsspeichergröße in Megabyte, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> -Objekts anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="64bba-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="64bba-119">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64bba-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="64bba-120">Der Name der Cachekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="64bba-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="64bba-121">Der Prozentsatz des physischen Arbeitsspeichers, der vom Cache verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="64bba-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="64bba-122">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64bba-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="64bba-123">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="64bba-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="64bba-124">Der Wert wird im Format „HH:MM:SS“ eingegeben.</span><span class="sxs-lookup"><span data-stu-id="64bba-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64bba-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64bba-125">Child Elements</span></span>  
  
|<span data-ttu-id="64bba-126">Element</span><span class="sxs-lookup"><span data-stu-id="64bba-126">Element</span></span>|<span data-ttu-id="64bba-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64bba-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64bba-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="64bba-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="64bba-129">Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.</span><span class="sxs-lookup"><span data-stu-id="64bba-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64bba-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="64bba-130">Parent Elements</span></span>  
  
|<span data-ttu-id="64bba-131">Element</span><span class="sxs-lookup"><span data-stu-id="64bba-131">Element</span></span>|<span data-ttu-id="64bba-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64bba-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64bba-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="64bba-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="64bba-134">Enthält Typen, mit denen Sie die implementieren Zwischenspeichern der Ausgabe in Anwendungen, die in .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="64bba-134">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64bba-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64bba-135">Remarks</span></span>  
 <span data-ttu-id="64bba-136">Die <xref:System.Runtime.Caching.MemoryCache> -Klasse ist eine konkrete Implementierung der abstrakten <xref:System.Runtime.Caching.ObjectCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="64bba-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="64bba-137">Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können mit Konfigurationsinformationen von Anwendungskonfigurationsdateien versorgt werden.</span><span class="sxs-lookup"><span data-stu-id="64bba-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="64bba-138">Der Abschnitt [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) -Konfiguration enthält eine `namedCaches` -Konfigurationssammlung.</span><span class="sxs-lookup"><span data-stu-id="64bba-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="64bba-139">Wenn ein speicherbasierendes Cacheobjekt initialisiert wird, versucht es zuerst, einen `namedCaches` -Eintrag zu finden, der dem Namen in dem Parameter entspricht, der an den Speichercache-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="64bba-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="64bba-140">Wenn ein `namedCaches` -Eintrag gefunden wird, werden Abruf- und Speicher-Management-Informationen aus der Konfigurationsdatei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="64bba-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="64bba-141">Der Initialisierungsprozess bestimmt dann mithilfe der optionalen Sammlung von Name-Wert-Paaren mit Konfigurationsinformationen im Konstruktor, ob Konfigurationseinträge überschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="64bba-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="64bba-142">Wenn Sie einen oder mehrere der folgenden Werte in der Name-Wert-Paar-Sammlung übergeben, überschreiben diese Werte Informationen aus der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="64bba-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="64bba-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64bba-143">Example</span></span>  
 <span data-ttu-id="64bba-144">Das folgende Beispiel zeigt, wie der Name des der <xref:System.Runtime.Caching.MemoryCache> Objekt, das den Cache-Standardobjektnamen durch Festlegen der `name` -Attribut auf "Default".</span><span class="sxs-lookup"><span data-stu-id="64bba-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="64bba-145">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryLimitPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="64bba-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="64bba-146">Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="64bba-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="64bba-147">Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="64bba-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64bba-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64bba-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="64bba-149">\<System.Runtime.Caching >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64bba-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="64bba-150">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="64bba-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
