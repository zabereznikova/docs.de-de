---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 9a7e370f9cce0e9ddf6dbe49984b7597e041eb84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094527"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="6747e-102">\<Hinzufügen >-Element für \<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="6747e-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="6747e-103">Fügt eine `namedCache` einen Eintrag in der `namedCaches` Auflistung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="6747e-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="6747e-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="6747e-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="6747e-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="6747e-105">\<memoryCache></span></span>  
<span data-ttu-id="6747e-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6747e-106">\<namedCaches></span></span>  
<span data-ttu-id="6747e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6747e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6747e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6747e-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="6747e-109">Typ</span><span class="sxs-lookup"><span data-stu-id="6747e-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6747e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6747e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6747e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6747e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6747e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6747e-112">Attributes</span></span>  
  
|<span data-ttu-id="6747e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6747e-113">Attribute</span></span>|<span data-ttu-id="6747e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6747e-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="6747e-115">Ein ganzzahliger Wert, der angibt, die maximal zulässige Größe (in MB), die eine Instanz von einem <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="6747e-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="6747e-116">Der Standardwert ist 0. das bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Heuristik-Klasse, die standardmäßig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6747e-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="6747e-117">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="6747e-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="6747e-118">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz der physisch installierten Arbeitsspeichers angibt, die vom Cache genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="6747e-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="6747e-119">Der Standardwert ist 0. das bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> -Heuristik-Klasse, die standardmäßig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6747e-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="6747e-120">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="6747e-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="6747e-121">Dieser Wert wird im-Format "Hh" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6747e-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6747e-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6747e-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="6747e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6747e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6747e-124">Element</span><span class="sxs-lookup"><span data-stu-id="6747e-124">Element</span></span>|<span data-ttu-id="6747e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6747e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6747e-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6747e-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="6747e-127">Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="6747e-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6747e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6747e-128">Remarks</span></span>  
 <span data-ttu-id="6747e-129">Die `add` -Element fügt einen Eintrag in einen der `namedCaches` Auflistung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="6747e-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="6747e-130">Können Sie die [löschen](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) Element vor der Verwendung der `add` Element sicher sein, dass es keine andere gibt benannte Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6747e-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="6747e-131">Dieses Element kann in der Datei "Machine.config" und in der Datei "Web.config" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6747e-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6747e-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6747e-132">Example</span></span>  
 <span data-ttu-id="6747e-133">Das folgende Beispiel zeigt, wie Einstellungen für den standardmäßigen definiert `namedCache` einen Eintrag in der `namedCaches` Auflistung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="6747e-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6747e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6747e-134">See also</span></span>

- [<span data-ttu-id="6747e-135">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6747e-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
