---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252464"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="398af-102">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="398af-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="398af-103">Gibt eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="398af-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="398af-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung von Konfigurationseinstellungen von einem `namedCaches` oder mehreren Elementen der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="398af-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="398af-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="398af-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="398af-106">&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="398af-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="398af-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MemoryCache->** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="398af-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="398af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<NamedCaches >**</span><span class="sxs-lookup"><span data-stu-id="398af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="398af-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="398af-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="398af-110">Typ</span><span class="sxs-lookup"><span data-stu-id="398af-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="398af-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="398af-111">Attributes and Elements</span></span>  
 <span data-ttu-id="398af-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="398af-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="398af-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="398af-113">Attributes</span></span>  
  
|<span data-ttu-id="398af-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="398af-114">Attribute</span></span>|<span data-ttu-id="398af-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="398af-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="398af-116">Ein ganzzahliger Wert, der die maximale zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="398af-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="398af-117">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="398af-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="398af-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="398af-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="398af-119">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="398af-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="398af-120">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="398af-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="398af-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="398af-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="398af-122">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="398af-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="398af-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="398af-123">Child Elements</span></span>  
  
|<span data-ttu-id="398af-124">Element</span><span class="sxs-lookup"><span data-stu-id="398af-124">Element</span></span>|<span data-ttu-id="398af-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="398af-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="398af-126">\<add></span><span class="sxs-lookup"><span data-stu-id="398af-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="398af-127">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="398af-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="398af-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="398af-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="398af-129">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="398af-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="398af-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="398af-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="398af-131">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="398af-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="398af-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="398af-132">Parent Elements</span></span>  
  
|<span data-ttu-id="398af-133">Element</span><span class="sxs-lookup"><span data-stu-id="398af-133">Element</span></span>|<span data-ttu-id="398af-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="398af-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="398af-135">\<configuration></span><span class="sxs-lookup"><span data-stu-id="398af-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="398af-136">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="398af-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="398af-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="398af-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="398af-138">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="398af-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="398af-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="398af-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="398af-140">Enthält Typen, mit denen Sie die Ausgabe Zwischenspeicherung in Anwendungen implementieren können, die in die .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="398af-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="398af-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="398af-141">Remarks</span></span>  
 <span data-ttu-id="398af-142">Der Konfigurations Abschnitt für den Arbeitsspeicher Cache der Datei "Web. `add`config `remove`" kann `clear` die Attribute, `namedCaches` und für die Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="398af-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="398af-143">Jeder `namedCaches` Eintrag wird durch das `name` -Attribut eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="398af-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="398af-144">Sie können Instanzen von Arbeitsspeicher-Cache Einträgen abrufen, indem Sie auf die Informationen in den Anwendungs Konfigurationsdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="398af-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="398af-145">Standardmäßig verfügt nur die Standard Cache Instanz über einen Eintrag in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="398af-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="398af-146">Die Standard Cache Instanz ist die-Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A> -Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="398af-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="398af-147">Wenn Sie das Name-Attribut auf "Default" festlegen, verwendet das-Element die Standard-Speicher Cache Instanz.</span><span class="sxs-lookup"><span data-stu-id="398af-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="398af-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="398af-148">Example</span></span>  
 <span data-ttu-id="398af-149">Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cache Eintrags Namen festgelegt `name` wird, indem das-Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="398af-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="398af-150">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="398af-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="398af-151">Wenn diese Attribute auf 0 (null) festgelegt werden, wird die Heuristik für die automatische Größenänderung der <xref:System.Runtime.Caching.MemoryCache> -Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="398af-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="398af-152">Die Cache Implementierung vergleicht die aktuelle Arbeitsspeicher Last alle zwei Minuten mit den absoluten und prozentualen Arbeitsspeicher Limits.</span><span class="sxs-lookup"><span data-stu-id="398af-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="398af-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="398af-153">See also</span></span>

- [<span data-ttu-id="398af-154">\<MemoryCache-> Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="398af-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
