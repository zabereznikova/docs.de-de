---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659034"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="7e80e-102">\<Fügen Sie >- \<Element für NamedCaches hinzu ></span><span class="sxs-lookup"><span data-stu-id="7e80e-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="7e80e-103">Fügt der `namedCache` `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e80e-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="7e80e-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="7e80e-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="7e80e-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="7e80e-105">\<memoryCache></span></span>  
<span data-ttu-id="7e80e-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="7e80e-106">\<namedCaches></span></span>  
<span data-ttu-id="7e80e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7e80e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e80e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e80e-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="7e80e-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7e80e-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e80e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7e80e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e80e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e80e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e80e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7e80e-112">Attributes</span></span>  
  
|<span data-ttu-id="7e80e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7e80e-113">Attribute</span></span>|<span data-ttu-id="7e80e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e80e-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="7e80e-115">Ein ganzzahliger Wert, der die maximal zulässige Größe (in Megabyte) angibt, auf die <xref:System.Runtime.Caching.MemoryCache> eine Instanz eines anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="7e80e-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="7e80e-116">Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e80e-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="7e80e-117">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="7e80e-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="7e80e-118">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7e80e-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="7e80e-119">Der Standardwert ist 0 (null), was <xref:System.Runtime.Caching.MemoryCache> bedeutet, dass die Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e80e-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="7e80e-120">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7e80e-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="7e80e-121">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="7e80e-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e80e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e80e-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="7e80e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e80e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7e80e-124">Element</span><span class="sxs-lookup"><span data-stu-id="7e80e-124">Element</span></span>|<span data-ttu-id="7e80e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e80e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e80e-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="7e80e-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="7e80e-127">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="7e80e-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e80e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e80e-128">Remarks</span></span>  
 <span data-ttu-id="7e80e-129">Das `add` -Element fügt der `namedCaches` -Auflistung einen Eintrag für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e80e-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="7e80e-130">Sie können das [Clear](clear-element-for-namedcaches.md) -Element verwenden, bevor Sie `add` das-Element verwenden, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7e80e-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="7e80e-131">Dieses Element kann in der Datei "Machine. config" und in der Datei "Web. config" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e80e-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e80e-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e80e-132">Example</span></span>  
 <span data-ttu-id="7e80e-133">Im folgenden Beispiel wird gezeigt, wie Sie Einstellungen für den `namedCache` Standardeintrag für `namedCaches` die-Auflistung für einen Speicher Cache definieren.</span><span class="sxs-lookup"><span data-stu-id="7e80e-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e80e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e80e-134">See also</span></span>

- [<span data-ttu-id="7e80e-135">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="7e80e-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
