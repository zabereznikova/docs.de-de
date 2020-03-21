---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154504"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="3089c-102">\<Hinzufügen> \<Elements für namedCaches></span><span class="sxs-lookup"><span data-stu-id="3089c-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="3089c-103">Fügt `namedCache` der `namedCaches` Auflistung einen Eintrag für einen Speichercache hinzu.</span><span class="sxs-lookup"><span data-stu-id="3089c-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="3089c-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3089c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3089c-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3089c-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="3089c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3089c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="3089c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3089c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="3089c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="3089c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3089c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3089c-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3089c-110">type</span><span class="sxs-lookup"><span data-stu-id="3089c-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3089c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3089c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3089c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3089c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3089c-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="3089c-113">Attributes</span></span>  
  
|<span data-ttu-id="3089c-114">attribute</span><span class="sxs-lookup"><span data-stu-id="3089c-114">Attribute</span></span>|<span data-ttu-id="3089c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3089c-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="3089c-116">Ein Ganzzahlwert, der die maximal zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines Instance sanieren <xref:System.Runtime.Caching.MemoryCache> kann.</span><span class="sxs-lookup"><span data-stu-id="3089c-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="3089c-117">Der Standardwert ist 0, <xref:System.Runtime.Caching.MemoryCache> was bedeutet, dass die autoisierende Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3089c-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="3089c-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="3089c-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="3089c-119">Ein Ganzzahlwert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computerspeichers angibt, der vom Cache verbraucht werden kann.</span><span class="sxs-lookup"><span data-stu-id="3089c-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="3089c-120">Der Standardwert ist 0, <xref:System.Runtime.Caching.MemoryCache> was bedeutet, dass die autoisierende Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3089c-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="3089c-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3089c-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="3089c-122">Dieser Wert wird im Format "HH:MM:SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="3089c-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3089c-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3089c-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="3089c-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3089c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3089c-125">Element</span><span class="sxs-lookup"><span data-stu-id="3089c-125">Element</span></span>|<span data-ttu-id="3089c-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3089c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3089c-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="3089c-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="3089c-128">Enthält eine Auflistung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3089c-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3089c-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3089c-129">Remarks</span></span>  
 <span data-ttu-id="3089c-130">Das `add` Element fügt der `namedCaches` Auflistung einen Eintrag für einen Speichercache hinzu.</span><span class="sxs-lookup"><span data-stu-id="3089c-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="3089c-131">Sie können das [clear-Element](clear-element-for-namedcaches.md) `add` verwenden, bevor Sie das Element verwenden, um sicher zu sein, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3089c-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="3089c-132">Dieses Element kann in der Datei machine.config und in der Datei Web.config verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3089c-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3089c-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3089c-133">Example</span></span>  
 <span data-ttu-id="3089c-134">Das folgende Beispiel zeigt, wie `namedCache` Sie Einstellungen `namedCaches` für den Standardeintrag für die Auflistung für einen Speichercache definieren.</span><span class="sxs-lookup"><span data-stu-id="3089c-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3089c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3089c-135">See also</span></span>

- [<span data-ttu-id="3089c-136">\<namedCaches> Element (Cache-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="3089c-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
