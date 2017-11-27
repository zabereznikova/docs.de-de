---
title: '&lt;NamedCaches&gt; Element (Cacheeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bdafddcb05dd50f059c9f6804573beec085a4a2a
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2017
---
# <a name="ltnamedcachesgt-element-cache-settings"></a><span data-ttu-id="f8e18-102">&lt;NamedCaches&gt; Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f8e18-102">&lt;namedCaches&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="f8e18-103">Gibt eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="f8e18-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="f8e18-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung der Konfigurationseinstellungen von einer oder mehreren `namedCaches` Elemente der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f8e18-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="f8e18-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f8e18-105">\<configuration></span></span>  
<span data-ttu-id="f8e18-106">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="f8e18-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="f8e18-107">\<MemoryCache ></span><span class="sxs-lookup"><span data-stu-id="f8e18-107">\<memoryCache></span></span>  
<span data-ttu-id="f8e18-108">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="f8e18-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e18-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8e18-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="f8e18-110">Typ</span><span class="sxs-lookup"><span data-stu-id="f8e18-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8e18-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f8e18-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f8e18-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8e18-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8e18-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="f8e18-113">Attributes</span></span>  
  
|<span data-ttu-id="f8e18-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="f8e18-114">Attribute</span></span>|<span data-ttu-id="f8e18-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e18-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="f8e18-116">Ein Ganzzahlwert, der die maximale zulässige Größe in Megabyte angibt, die einer Instanz von einer <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="f8e18-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="f8e18-117">Der Standardwert ist 0, was bedeutet, der Heuristik Automatisches Anpassen der Größe dass der <xref:System.Runtime.Caching.MemoryCache> Klasse werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8e18-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="f8e18-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="f8e18-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="f8e18-119">Eine ganze Zahl zwischen 0 und 100, die den maximalen Prozentsatz des Arbeitsspeichers physisch installierten Computer angibt, die vom Cache genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="f8e18-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="f8e18-120">Der Standardwert ist 0, was bedeutet, der Heuristik Automatisches Anpassen der Größe dass der <xref:System.Runtime.Caching.MemoryCache> Klasse werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8e18-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="f8e18-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f8e18-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="f8e18-122">Dieser Wert wird im Format "Hh" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="f8e18-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8e18-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8e18-123">Child Elements</span></span>  
  
|<span data-ttu-id="f8e18-124">Element</span><span class="sxs-lookup"><span data-stu-id="f8e18-124">Element</span></span>|<span data-ttu-id="f8e18-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e18-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8e18-126">\<add></span><span class="sxs-lookup"><span data-stu-id="f8e18-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="f8e18-127">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8e18-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="f8e18-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="f8e18-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="f8e18-129">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="f8e18-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="f8e18-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="f8e18-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="f8e18-131">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="f8e18-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8e18-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f8e18-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f8e18-133">Element</span><span class="sxs-lookup"><span data-stu-id="f8e18-133">Element</span></span>|<span data-ttu-id="f8e18-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8e18-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8e18-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="f8e18-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="f8e18-136">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="f8e18-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8e18-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8e18-137">Remarks</span></span>  
 <span data-ttu-id="f8e18-138">Der Arbeitsspeicher Cache-Konfigurationsabschnitt der Datei "Web.config" darf `add`, `remove`, und `clear` Attribute für die `namedCaches` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f8e18-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="f8e18-139">Jede `namedCaches` Eintrag eindeutig identifiziert wird, durch die `name` Attribut.</span><span class="sxs-lookup"><span data-stu-id="f8e18-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="f8e18-140">Sie können Instanzen von Arbeitsspeichercacheeinträgen durch Verweisen auf die Informationen in den Anwendungskonfigurationsdateien abrufen.</span><span class="sxs-lookup"><span data-stu-id="f8e18-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="f8e18-141">Standardmäßig enthält nur die standardmäßige Instanz einen Eintrag in der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="f8e18-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="f8e18-142">Die Cache-Standardinstanz ist die Instanz, die von zurückgegeben wird die <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f8e18-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="f8e18-143">Wenn Sie das Name-Attribut auf "Default" festgelegt, verwendet das Element die Arbeitsspeicher-Cache Standardinstanz an.</span><span class="sxs-lookup"><span data-stu-id="f8e18-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e18-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8e18-144">Example</span></span>  
 <span data-ttu-id="f8e18-145">Im folgende Beispiel wird gezeigt, wie für den Standardnamen des Cache Eintrag den Namen des Caches festzulegen, durch Festlegen der `name` Attribut "Default".</span><span class="sxs-lookup"><span data-stu-id="f8e18-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="f8e18-146">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8e18-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="f8e18-147">Diese Attribute auf 0 (null) festlegen bedeutet, dass der Heuristik Automatisches Anpassen der Größe der <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8e18-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="f8e18-148">Der Cacheimplementierung vergleicht die aktuelle Arbeitsspeicherlast gegen die absolute und Prozentsätzen basierenden Arbeitsspeichergrenze alle zwei Minuten.</span><span class="sxs-lookup"><span data-stu-id="f8e18-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8e18-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8e18-149">See Also</span></span>  
 [<span data-ttu-id="f8e18-150">\<MemoryCache >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f8e18-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
