---
title: "&lt;Hinzufügen&gt; -Element für &lt;NamedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0000e92c89920b05e0ffc93fab58fb0bd6ea6b13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="10173-102">&lt;Hinzufügen&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="10173-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="10173-103">Fügt eine `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="10173-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="10173-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="10173-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="10173-105">\<MemoryCache ></span><span class="sxs-lookup"><span data-stu-id="10173-105">\<memoryCache></span></span>  
<span data-ttu-id="10173-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="10173-106">\<namedCaches></span></span>  
<span data-ttu-id="10173-107">\<add></span><span class="sxs-lookup"><span data-stu-id="10173-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10173-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="10173-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="10173-109">Typ</span><span class="sxs-lookup"><span data-stu-id="10173-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10173-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="10173-110">Attributes and Elements</span></span>  
 <span data-ttu-id="10173-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10173-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10173-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="10173-112">Attributes</span></span>  
  
|<span data-ttu-id="10173-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="10173-113">Attribute</span></span>|<span data-ttu-id="10173-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10173-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="10173-115">Ein Ganzzahlwert, der die maximal zulässige Größe (in Megabytes) angibt, die einer Instanz von einer <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="10173-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="10173-116">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="10173-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="10173-117">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="10173-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="10173-118">Eine ganze Zahl zwischen 0 und 100, die den maximalen Prozentsatz des Arbeitsspeichers physisch installierten Computer angibt, die vom Cache genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="10173-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="10173-119">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="10173-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="10173-120">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="10173-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="10173-121">Dieser Wert wird im Format "Hh" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="10173-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10173-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10173-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="10173-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="10173-123">Parent Elements</span></span>  
  
|<span data-ttu-id="10173-124">Element</span><span class="sxs-lookup"><span data-stu-id="10173-124">Element</span></span>|<span data-ttu-id="10173-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10173-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10173-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="10173-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="10173-127">Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="10173-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10173-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="10173-128">Remarks</span></span>  
 <span data-ttu-id="10173-129">Die `add` -Element fügt einen Eintrag in einen der `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="10173-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="10173-130">Können Sie die [deaktivieren](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) Element vor der Verwendung der `add` Element sicher, dass es keine anderen sind benannte Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="10173-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="10173-131">Dieses Element kann in der Datei "Machine.config" und in der Datei "Web.config" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10173-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10173-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10173-132">Example</span></span>  
 <span data-ttu-id="10173-133">Das folgende Beispiel zeigt, wie Einstellungen für den standardmäßigen definiert `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="10173-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10173-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10173-134">See Also</span></span>  
 [<span data-ttu-id="10173-135">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="10173-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
