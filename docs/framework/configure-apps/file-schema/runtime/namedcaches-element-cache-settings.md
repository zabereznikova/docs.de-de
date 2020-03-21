---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153957"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="14e45-102">\<namedCaches> Element (Cache-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="14e45-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="14e45-103">Gibt eine Auflistung von Konfigurationseinstellungen <xref:System.Runtime.Caching.MemoryCache> für die benannten Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="14e45-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="14e45-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Eigenschaft verweist auf die Auflistung `namedCaches` der Konfigurationseinstellungen aus einem oder mehreren Elementen der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="14e45-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="14e45-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14e45-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14e45-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="14e45-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="14e45-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="14e45-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="14e45-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span><span class="sxs-lookup"><span data-stu-id="14e45-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e45-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="14e45-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="14e45-110">type</span><span class="sxs-lookup"><span data-stu-id="14e45-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e45-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14e45-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14e45-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14e45-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e45-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="14e45-113">Attributes</span></span>  
  
|<span data-ttu-id="14e45-114">attribute</span><span class="sxs-lookup"><span data-stu-id="14e45-114">Attribute</span></span>|<span data-ttu-id="14e45-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14e45-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="14e45-116">Ein Ganzzahlwert, der die maximal zulässige Größe in Megabyte <xref:System.Runtime.Caching.MemoryCache> angibt, auf die eine Instanz eines Werts anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="14e45-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="14e45-117">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> autoisierende Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14e45-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="14e45-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="14e45-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="14e45-119">Ein Ganzzahlwert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computerspeichers angibt, der vom Cache verbraucht werden kann.</span><span class="sxs-lookup"><span data-stu-id="14e45-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="14e45-120">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> autoisierende Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14e45-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="14e45-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="14e45-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="14e45-122">Dieser Wert wird im Format "HH:MM:SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="14e45-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e45-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14e45-123">Child Elements</span></span>  
  
|<span data-ttu-id="14e45-124">Element</span><span class="sxs-lookup"><span data-stu-id="14e45-124">Element</span></span>|<span data-ttu-id="14e45-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14e45-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e45-126">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="14e45-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="14e45-127">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="14e45-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="14e45-128">\<klare></span><span class="sxs-lookup"><span data-stu-id="14e45-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="14e45-129">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="14e45-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="14e45-130">\<entfernen sie></span><span class="sxs-lookup"><span data-stu-id="14e45-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="14e45-131">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="14e45-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14e45-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14e45-132">Parent Elements</span></span>  
  
|<span data-ttu-id="14e45-133">Element</span><span class="sxs-lookup"><span data-stu-id="14e45-133">Element</span></span>|<span data-ttu-id="14e45-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14e45-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e45-135">\<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="14e45-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="14e45-136">Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14e45-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="14e45-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="14e45-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="14e45-138">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="14e45-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="14e45-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="14e45-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="14e45-140">Enthält Typen, mit denen Sie ausgabezwischenspeichern in Anwendungen implementieren können, die in .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="14e45-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e45-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="14e45-141">Remarks</span></span>  
 <span data-ttu-id="14e45-142">Der Speichercachekonfigurationsabschnitt der Datei Web.config `remove`kann `clear` , und `namedCaches` Attribute für die Auflistung enthalten. `add`</span><span class="sxs-lookup"><span data-stu-id="14e45-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="14e45-143">Jeder `namedCaches` Eintrag wird durch `name` das Attribut eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="14e45-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="14e45-144">Sie können Instanzen von Speichercacheeinträgen abrufen, indem Sie auf die Informationen in den Anwendungskonfigurationsdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="14e45-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="14e45-145">Standardmäßig verfügt nur die Standard-Cacheinstanz über einen Eintrag in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="14e45-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="14e45-146">Die Standard-Cacheinstanz ist die Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A> Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14e45-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="14e45-147">Wenn Sie das Name-Attribut auf "default" festlegen, verwendet das Element die Standard-Speichercacheinstanz.</span><span class="sxs-lookup"><span data-stu-id="14e45-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e45-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14e45-148">Example</span></span>  
 <span data-ttu-id="14e45-149">Das folgende Beispiel zeigt, wie Sie den Namen des Caches `name` auf den Standardcacheeintragsnamen festlegen, indem Sie das Attribut auf "default" festlegen.</span><span class="sxs-lookup"><span data-stu-id="14e45-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="14e45-150">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="14e45-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="14e45-151">Das Festlegen dieser Attribute auf Null bedeutet, dass <xref:System.Runtime.Caching.MemoryCache> die autooptimierende Heuristik der Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14e45-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="14e45-152">Die Cacheimplementierung vergleicht die aktuelle Speicherauslastung alle zwei Minuten mit den absoluten und prozentualen Speicherlimits.</span><span class="sxs-lookup"><span data-stu-id="14e45-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="14e45-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14e45-153">See also</span></span>

- [<span data-ttu-id="14e45-154">\<memoryCache> Element (Cache-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="14e45-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
