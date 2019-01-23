---
title: '&lt;NamedCaches&gt; -Element (Cacheeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a824e958a2b75b28aa66a15212e0276d6c127739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536528"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="eec2c-102">&lt;NamedCaches&gt; -Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="eec2c-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="eec2c-103">Gibt eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="eec2c-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="eec2c-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung der Konfigurationseinstellungen von einer oder mehreren `namedCaches` Elemente der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="eec2c-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="eec2c-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eec2c-105">\<configuration></span></span>  
<span data-ttu-id="eec2c-106">\< system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="eec2c-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="eec2c-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="eec2c-107">\<memoryCache></span></span>  
<span data-ttu-id="eec2c-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="eec2c-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec2c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="eec2c-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="eec2c-110">Typ</span><span class="sxs-lookup"><span data-stu-id="eec2c-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eec2c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eec2c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eec2c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eec2c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eec2c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="eec2c-113">Attributes</span></span>  
  
|<span data-ttu-id="eec2c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="eec2c-114">Attribute</span></span>|<span data-ttu-id="eec2c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eec2c-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="eec2c-116">Ein ganzzahliger Wert, der angibt, die maximale zulässige Größe in Megabyte, die eine Instanz von einem <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="eec2c-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="eec2c-117">Der Standardwert ist 0 (null) und das bedeutet, die-Heuristik von dass der <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eec2c-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="eec2c-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="eec2c-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="eec2c-119">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz der physisch installierten Arbeitsspeichers angibt, die vom Cache genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="eec2c-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="eec2c-120">Der Standardwert ist 0 (null) und das bedeutet, die-Heuristik von dass der <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eec2c-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="eec2c-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="eec2c-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="eec2c-122">Dieser Wert wird im-Format "Hh" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="eec2c-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eec2c-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eec2c-123">Child Elements</span></span>  
  
|<span data-ttu-id="eec2c-124">Element</span><span class="sxs-lookup"><span data-stu-id="eec2c-124">Element</span></span>|<span data-ttu-id="eec2c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eec2c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eec2c-126">\<add></span><span class="sxs-lookup"><span data-stu-id="eec2c-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="eec2c-127">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="eec2c-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="eec2c-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="eec2c-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="eec2c-129">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="eec2c-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="eec2c-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="eec2c-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="eec2c-131">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="eec2c-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eec2c-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eec2c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="eec2c-133">Element</span><span class="sxs-lookup"><span data-stu-id="eec2c-133">Element</span></span>|<span data-ttu-id="eec2c-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eec2c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eec2c-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="eec2c-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="eec2c-136">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="eec2c-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eec2c-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eec2c-137">Remarks</span></span>  
 <span data-ttu-id="eec2c-138">Der Abschnitt Configuration der Datei "Web.config" darf `add`, `remove`, und `clear` Attribute für die `namedCaches` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="eec2c-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="eec2c-139">Jede `namedCaches` Eintrag eindeutig durch die `name` Attribut.</span><span class="sxs-lookup"><span data-stu-id="eec2c-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="eec2c-140">Sie können Instanzen von Cacheeinträgen Speicher verweisen auf die Informationen in den Konfigurationsdateien der Anwendung abrufen.</span><span class="sxs-lookup"><span data-stu-id="eec2c-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="eec2c-141">Standardmäßig enthält nur die Standard-Cache-Instanz einen Eintrag in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="eec2c-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="eec2c-142">Die Standard-Cache-Instanz ist die Instanz, die von zurückgegeben wird das <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="eec2c-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="eec2c-143">Wenn Sie das Name-Attribut auf "Standard" festlegen, verwendet das Element die Standard-Memory-Cache-Instanz.</span><span class="sxs-lookup"><span data-stu-id="eec2c-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec2c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eec2c-144">Example</span></span>  
 <span data-ttu-id="eec2c-145">Im folgende Beispiel veranschaulicht die legen Sie des Namens des Caches, der Name des Standard-Cache-Eintrags durch Festlegen der `name` Attribut auf "Standard".</span><span class="sxs-lookup"><span data-stu-id="eec2c-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="eec2c-146">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eec2c-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="eec2c-147">Festlegen von dieser Attribute auf 0 (null) bedeutet, dass die-Heuristik von der <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eec2c-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="eec2c-148">Die Cacheimplementierung vergleicht die aktuelle Arbeitsspeicherlast mit den absoluten und prozentualen Speichergrenzen alle zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="eec2c-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eec2c-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eec2c-149">See also</span></span>
- [<span data-ttu-id="eec2c-150">\<MemoryCache >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="eec2c-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
