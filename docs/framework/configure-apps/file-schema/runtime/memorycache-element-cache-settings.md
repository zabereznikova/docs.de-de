---
title: <memoryCache>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 14480682c5d221216df5da3844897855d1d92a0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192424"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="39b24-102">\<memoryCache>-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="39b24-102">\<memoryCache> Element (Cache Settings)</span></span>

<span data-ttu-id="39b24-103">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="39b24-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="39b24-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> -Klasse definiert ein [memoryCache](memorycache-element-cache-settings.md) -Element, das Sie zum Konfigurieren des Caches verwenden können.</span><span class="sxs-lookup"><span data-stu-id="39b24-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="39b24-105">Mehrere Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können in einer einzigen Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39b24-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="39b24-106">Jedes `memoryCache` -Element in der Konfigurationsdatei kann Einstellungen für eine benannte <xref:System.Runtime.Caching.MemoryCache> -Instanz enthalten.</span><span class="sxs-lookup"><span data-stu-id="39b24-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a><span data-ttu-id="39b24-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="39b24-107">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="39b24-108">Typ</span><span class="sxs-lookup"><span data-stu-id="39b24-108">Type</span></span>  

 <span data-ttu-id="39b24-109"><xref:System.Runtime.Caching.MemoryCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="39b24-109"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39b24-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39b24-110">Attributes and Elements</span></span>  

 <span data-ttu-id="39b24-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39b24-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39b24-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="39b24-112">Attributes</span></span>  
  
|<span data-ttu-id="39b24-113">attribute</span><span class="sxs-lookup"><span data-stu-id="39b24-113">Attribute</span></span>|<span data-ttu-id="39b24-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b24-114">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="39b24-115">Die maximale Arbeitsspeichergröße in Megabyte, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> -Objekts anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="39b24-115">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="39b24-116">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39b24-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="39b24-117">Der Name der Cachekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="39b24-117">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="39b24-118">Der Prozentsatz des physischen Arbeitsspeichers, der vom Cache verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="39b24-118">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="39b24-119">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Klasse Autosize-Heuristik als Standard verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39b24-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="39b24-120">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="39b24-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="39b24-121">Der Wert wird im Format „HH:MM:SS“ eingegeben.</span><span class="sxs-lookup"><span data-stu-id="39b24-121">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39b24-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39b24-122">Child Elements</span></span>  
  
|<span data-ttu-id="39b24-123">Element</span><span class="sxs-lookup"><span data-stu-id="39b24-123">Element</span></span>|<span data-ttu-id="39b24-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b24-124">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="39b24-125">Enthält eine Sammlung von Konfigurationseigenschaften für die `namedCache` -Instanz.</span><span class="sxs-lookup"><span data-stu-id="39b24-125">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39b24-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39b24-126">Parent Elements</span></span>  
  
|<span data-ttu-id="39b24-127">Element</span><span class="sxs-lookup"><span data-stu-id="39b24-127">Element</span></span>|<span data-ttu-id="39b24-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b24-128">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="39b24-129">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39b24-129">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="39b24-130">Enthält Typen, mit denen Sie die Ausgabe Zwischenspeicherung in Anwendungen implementieren können, die in die .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="39b24-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b24-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="39b24-131">Remarks</span></span>  

 <span data-ttu-id="39b24-132">Die <xref:System.Runtime.Caching.MemoryCache> -Klasse ist eine konkrete Implementierung der abstrakten <xref:System.Runtime.Caching.ObjectCache> -Klasse.</span><span class="sxs-lookup"><span data-stu-id="39b24-132">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="39b24-133">Instanzen der <xref:System.Runtime.Caching.MemoryCache> -Klasse können mit Konfigurationsinformationen von Anwendungskonfigurationsdateien versorgt werden.</span><span class="sxs-lookup"><span data-stu-id="39b24-133">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="39b24-134">Der Abschnitt [memoryCache](memorycache-element-cache-settings.md) -Konfiguration enthält eine `namedCaches` -Konfigurationssammlung.</span><span class="sxs-lookup"><span data-stu-id="39b24-134">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="39b24-135">Wenn ein speicherbasierendes Cacheobjekt initialisiert wird, versucht es zuerst, einen `namedCaches` -Eintrag zu finden, der dem Namen in dem Parameter entspricht, der an den Speichercache-Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="39b24-135">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="39b24-136">Wenn ein `namedCaches` -Eintrag gefunden wird, werden Abruf- und Speicher-Management-Informationen aus der Konfigurationsdatei abgerufen.</span><span class="sxs-lookup"><span data-stu-id="39b24-136">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="39b24-137">Der Initialisierungsprozess bestimmt dann mithilfe der optionalen Sammlung von Name-Wert-Paaren mit Konfigurationsinformationen im Konstruktor, ob Konfigurationseinträge überschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="39b24-137">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="39b24-138">Wenn Sie einen oder mehrere der folgenden Werte in der Name-Wert-Paar-Sammlung übergeben, überschreiben diese Werte Informationen aus der Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="39b24-138">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="39b24-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39b24-139">Example</span></span>  

 <span data-ttu-id="39b24-140">Im folgenden Beispiel wird gezeigt, wie der Name des- <xref:System.Runtime.Caching.MemoryCache> Objekts auf den standardmäßigen Cache Objektnamen festgelegt wird, indem das- `name` Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="39b24-140">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="39b24-141">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryLimitPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="39b24-141">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="39b24-142">Werden diese Attribute auf 0 (Null) festgelegt, wird die <xref:System.Runtime.Caching.MemoryCache> -Heuristik zum automatischen Anpassen als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="39b24-142">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="39b24-143">Die Cacheimplementierung sollte die aktuelle Auslastung des Arbeitsspeichers alle zwei Minuten mit den absoluten und prozentualen Speichergrenzen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="39b24-143">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39b24-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39b24-144">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="39b24-145">\<system.runtime.caching> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="39b24-145">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="39b24-146">\<namedCaches> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="39b24-146">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
