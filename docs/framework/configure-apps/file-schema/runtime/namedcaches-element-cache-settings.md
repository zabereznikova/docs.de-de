---
title: <namedCaches>-Element (Cacheeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 9cedd462aa539745ddab844dff158912914cb024
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663580"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="d187b-102">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d187b-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="d187b-103">Gibt eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen an.</span><span class="sxs-lookup"><span data-stu-id="d187b-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="d187b-104">Die <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> -Eigenschaft verweist auf die Auflistung von Konfigurationseinstellungen von einem `namedCaches` oder mehreren Elementen der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d187b-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="d187b-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d187b-105">\<configuration></span></span>  
<span data-ttu-id="d187b-106">\<System. Runtime. Caching-></span><span class="sxs-lookup"><span data-stu-id="d187b-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="d187b-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d187b-107">\<memoryCache></span></span>  
<span data-ttu-id="d187b-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d187b-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d187b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d187b-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d187b-110">Typ</span><span class="sxs-lookup"><span data-stu-id="d187b-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d187b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d187b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d187b-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d187b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d187b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d187b-113">Attributes</span></span>  
  
|<span data-ttu-id="d187b-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d187b-114">Attribute</span></span>|<span data-ttu-id="d187b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d187b-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="d187b-116">Ein ganzzahliger Wert, der die maximale zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="d187b-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="d187b-117">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d187b-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="d187b-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="d187b-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="d187b-119">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d187b-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="d187b-120">Der Standardwert ist 0 (null). Dies bedeutet, dass die automatische Größenanpassung <xref:System.Runtime.Caching.MemoryCache> der-Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d187b-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="d187b-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d187b-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="d187b-122">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="d187b-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d187b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d187b-123">Child Elements</span></span>  
  
|<span data-ttu-id="d187b-124">Element</span><span class="sxs-lookup"><span data-stu-id="d187b-124">Element</span></span>|<span data-ttu-id="d187b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d187b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d187b-126">\<add></span><span class="sxs-lookup"><span data-stu-id="d187b-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="d187b-127">Fügt der `namedCaches`-Sammlung für einen Speichercache einen benannten Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="d187b-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="d187b-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="d187b-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="d187b-129">Löscht die `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="d187b-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="d187b-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="d187b-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="d187b-131">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="d187b-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d187b-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d187b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="d187b-133">Element</span><span class="sxs-lookup"><span data-stu-id="d187b-133">Element</span></span>|<span data-ttu-id="d187b-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d187b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d187b-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="d187b-135">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="d187b-136">Definiert ein Element, das für die Konfiguration des Cache verwendet wird, der auf der <xref:System.Runtime.Caching.MemoryCache> -Klasse basiert.</span><span class="sxs-lookup"><span data-stu-id="d187b-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d187b-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d187b-137">Remarks</span></span>  
 <span data-ttu-id="d187b-138">Der Konfigurations Abschnitt für den Arbeitsspeicher Cache der Datei "Web. `add`config `remove`" kann `clear` die Attribute, `namedCaches` und für die Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d187b-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="d187b-139">Jeder `namedCaches` Eintrag wird durch das `name` -Attribut eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d187b-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="d187b-140">Sie können Instanzen von Arbeitsspeicher-Cache Einträgen abrufen, indem Sie auf die Informationen in den Anwendungs Konfigurationsdateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="d187b-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="d187b-141">Standardmäßig verfügt nur die Standard Cache Instanz über einen Eintrag in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d187b-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="d187b-142">Die Standard Cache Instanz ist die-Instanz, die von der <xref:System.Runtime.Caching.MemoryCache.Default%2A> -Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d187b-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="d187b-143">Wenn Sie das Name-Attribut auf "Default" festlegen, verwendet das-Element die Standard-Speicher Cache Instanz.</span><span class="sxs-lookup"><span data-stu-id="d187b-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d187b-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d187b-144">Example</span></span>  
 <span data-ttu-id="d187b-145">Im folgenden Beispiel wird gezeigt, wie der Name des Caches auf den standardmäßigen Cache Eintrags Namen festgelegt `name` wird, indem das-Attribut auf "Default" festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d187b-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="d187b-146">Das `cacheMemoryLimitMegabytes` - und das `physicalMemoryPercentage` -Attribut werden auf 0 (Null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d187b-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="d187b-147">Wenn diese Attribute auf 0 (null) festgelegt werden, wird die Heuristik für die automatische Größenänderung der <xref:System.Runtime.Caching.MemoryCache> -Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d187b-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="d187b-148">Die Cache Implementierung vergleicht die aktuelle Arbeitsspeicher Last alle zwei Minuten mit den absoluten und prozentualen Arbeitsspeicher Limits.</span><span class="sxs-lookup"><span data-stu-id="d187b-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d187b-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d187b-149">See also</span></span>

- [<span data-ttu-id="d187b-150">\<MemoryCache-> Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d187b-150">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
