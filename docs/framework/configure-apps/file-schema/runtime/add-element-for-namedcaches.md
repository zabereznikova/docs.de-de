---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252891"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="fa7af-102">\<Fügen Sie >- \<Element für NamedCaches hinzu ></span><span class="sxs-lookup"><span data-stu-id="fa7af-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="fa7af-103">Fügt der `namedCache` `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa7af-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="fa7af-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa7af-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa7af-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fa7af-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="fa7af-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MemoryCache->** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fa7af-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="fa7af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NamedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="fa7af-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="fa7af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="fa7af-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7af-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa7af-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="fa7af-110">Typ</span><span class="sxs-lookup"><span data-stu-id="fa7af-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa7af-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa7af-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa7af-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa7af-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa7af-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa7af-113">Attributes</span></span>  
  
|<span data-ttu-id="fa7af-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa7af-114">Attribute</span></span>|<span data-ttu-id="fa7af-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa7af-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="fa7af-116">Ein ganzzahliger Wert, der die maximal zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="fa7af-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="fa7af-117">Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa7af-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="fa7af-118">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="fa7af-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="fa7af-119">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa7af-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="fa7af-120">Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa7af-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="fa7af-121">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="fa7af-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="fa7af-122">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="fa7af-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa7af-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa7af-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="fa7af-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa7af-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fa7af-125">Element</span><span class="sxs-lookup"><span data-stu-id="fa7af-125">Element</span></span>|<span data-ttu-id="fa7af-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa7af-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa7af-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="fa7af-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="fa7af-128">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="fa7af-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa7af-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa7af-129">Remarks</span></span>  
 <span data-ttu-id="fa7af-130">Das `add` -Element fügt der `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="fa7af-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="fa7af-131">Sie können das [Clear](clear-element-for-namedcaches.md) -Element verwenden, bevor Sie `add` das-Element verwenden, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fa7af-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="fa7af-132">Dieses Element kann in der Datei "Machine. config" und in der Datei "Web. config" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa7af-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7af-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa7af-133">Example</span></span>  
 <span data-ttu-id="fa7af-134">Im folgenden Beispiel wird gezeigt, wie Sie Einstellungen für den `namedCache` Standardeintrag für `namedCaches` die-Auflistung für einen Speicher Cache definieren.</span><span class="sxs-lookup"><span data-stu-id="fa7af-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa7af-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa7af-135">See also</span></span>

- [<span data-ttu-id="fa7af-136">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="fa7af-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
