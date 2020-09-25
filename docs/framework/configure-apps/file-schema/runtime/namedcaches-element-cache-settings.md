---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: ad76c01bba859934be399d73262bd974309efe98
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192398"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="beb40-102">\<namedCaches>-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="beb40-102">\<namedCaches> Element (Cache Settings)</span></span>

<span data-ttu-id="beb40-103">Gibt eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="beb40-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="beb40-104">Die- <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> Eigenschaft verweist auf die Auflistung von Konfigurationseinstellungen von einem oder mehreren `namedCaches` Elementen der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="beb40-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a><span data-ttu-id="beb40-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="beb40-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="beb40-106">Typ</span><span class="sxs-lookup"><span data-stu-id="beb40-106">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beb40-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="beb40-107">Attributes and Elements</span></span>  

 <span data-ttu-id="beb40-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="beb40-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beb40-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="beb40-109">Attributes</span></span>  
  
|<span data-ttu-id="beb40-110">attribute</span><span class="sxs-lookup"><span data-stu-id="beb40-110">Attribute</span></span>|<span data-ttu-id="beb40-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beb40-111">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="beb40-112">Ein ganzzahliger Wert, der die maximale zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="beb40-112">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="beb40-113">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung der- <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beb40-113">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="beb40-114">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="beb40-114">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="beb40-115">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="beb40-115">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="beb40-116">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung der- <xref:System.Runtime.Caching.MemoryCache> Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beb40-116">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="beb40-117">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="beb40-117">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="beb40-118">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="beb40-118">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beb40-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beb40-119">Child Elements</span></span>  
  
|<span data-ttu-id="beb40-120">Element</span><span class="sxs-lookup"><span data-stu-id="beb40-120">Element</span></span>|<span data-ttu-id="beb40-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beb40-121">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|<span data-ttu-id="beb40-122">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="beb40-122">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[\<clear>](clear-element-for-namedcaches.md)|<span data-ttu-id="beb40-123">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="beb40-123">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[\<remove>](remove-element-for-namedcaches.md)|<span data-ttu-id="beb40-124">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="beb40-124">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="beb40-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beb40-125">Parent Elements</span></span>  
  
|<span data-ttu-id="beb40-126">Element</span><span class="sxs-lookup"><span data-stu-id="beb40-126">Element</span></span>|<span data-ttu-id="beb40-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beb40-127">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="beb40-128">Gibt das Stamm Element in jeder Konfigurationsdatei an, die von den Common Language Runtime-und .NET Framework Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beb40-128">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="beb40-129">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="beb40-129">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="beb40-130">Enthält Typen, mit denen Sie die Ausgabe Zwischenspeicherung in Anwendungen implementieren können, die in die .NET Framework integriert sind.</span><span class="sxs-lookup"><span data-stu-id="beb40-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beb40-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="beb40-131">Remarks</span></span>  

 <span data-ttu-id="beb40-132">Der Arbeitsspeicher-Cache Konfigurations Abschnitt der Web.config Datei kann `add` die `remove` Attribute, und für die Auflistung enthalten `clear` `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="beb40-132">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="beb40-133">Jeder `namedCaches` Eintrag wird durch das-Attribut eindeutig identifiziert `name` .</span><span class="sxs-lookup"><span data-stu-id="beb40-133">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="beb40-134">Sie können Instanzen von Arbeitsspeicher-Cache Einträgen abrufen, indem Sie auf die Informationen in den Anwendungs Konfigurationsdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="beb40-134">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="beb40-135">Standardmäßig verfügt nur die Standard Cache Instanz über einen Eintrag in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="beb40-135">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="beb40-136">Die Standard Cache Instanz ist die-Instanz, die von der-Eigenschaft zurückgegeben wird <xref:System.Runtime.Caching.MemoryCache.Default%2A> .</span><span class="sxs-lookup"><span data-stu-id="beb40-136">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="beb40-137">Wenn Sie das Name-Attribut auf "Default" festlegen, verwendet das-Element die Standard-Speicher Cache Instanz.</span><span class="sxs-lookup"><span data-stu-id="beb40-137">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb40-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="beb40-138">Example</span></span>  

 <span data-ttu-id="beb40-139">Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cache Eintrags Namen festgelegt wird, indem das- `name` Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="beb40-139">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="beb40-140">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="beb40-140">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="beb40-141">Wenn diese Attribute auf 0 (null) festgelegt werden, wird die Heuristik für die automatische Größenänderung der- <xref:System.Runtime.Caching.MemoryCache> Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="beb40-141">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="beb40-142">Die Cache Implementierung vergleicht die aktuelle Arbeitsspeicher Last alle zwei Minuten mit den absoluten und prozentualen Arbeitsspeicher Limits.</span><span class="sxs-lookup"><span data-stu-id="beb40-142">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="beb40-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="beb40-143">See also</span></span>

- [<span data-ttu-id="beb40-144">\<memoryCache> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="beb40-144">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
