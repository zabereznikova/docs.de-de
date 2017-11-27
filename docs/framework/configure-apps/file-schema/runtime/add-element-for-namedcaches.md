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
ms.openlocfilehash: 0baafcb53bf79a25618dad56c2dcf1412e48624b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="ac472-102">&lt;Hinzufügen&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="ac472-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="ac472-103">Fügt eine `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="ac472-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="ac472-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="ac472-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="ac472-105">\<MemoryCache ></span><span class="sxs-lookup"><span data-stu-id="ac472-105">\<memoryCache></span></span>  
<span data-ttu-id="ac472-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="ac472-106">\<namedCaches></span></span>  
<span data-ttu-id="ac472-107">\<add></span><span class="sxs-lookup"><span data-stu-id="ac472-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac472-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac472-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="ac472-109">Typ</span><span class="sxs-lookup"><span data-stu-id="ac472-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac472-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ac472-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac472-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac472-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac472-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac472-112">Attributes</span></span>  
  
|<span data-ttu-id="ac472-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ac472-113">Attribute</span></span>|<span data-ttu-id="ac472-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac472-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="ac472-115">Ein Ganzzahlwert, der die maximal zulässige Größe (in Megabytes) angibt, die einer Instanz von einer <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="ac472-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="ac472-116">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac472-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="ac472-117">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="ac472-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="ac472-118">Eine ganze Zahl zwischen 0 und 100, die den maximalen Prozentsatz des Arbeitsspeichers physisch installierten Computer angibt, die vom Cache genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="ac472-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="ac472-119">Der Standardwert ist 0, was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Klasse Automatisches Anpassen der Größe Heuristik werden standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac472-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="ac472-120">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="ac472-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="ac472-121">Dieser Wert wird im Format "Hh" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="ac472-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac472-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac472-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="ac472-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ac472-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ac472-124">Element</span><span class="sxs-lookup"><span data-stu-id="ac472-124">Element</span></span>|<span data-ttu-id="ac472-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac472-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac472-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="ac472-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="ac472-127">Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="ac472-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac472-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac472-128">Remarks</span></span>  
 <span data-ttu-id="ac472-129">Die `add` -Element fügt einen Eintrag in einen der `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="ac472-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="ac472-130">Können Sie die [deaktivieren](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) Element vor der Verwendung der `add` Element sicher, dass es keine anderen sind benannte Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ac472-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="ac472-131">Dieses Element kann in der Datei "Machine.config" und in der Datei "Web.config" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac472-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac472-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac472-132">Example</span></span>  
 <span data-ttu-id="ac472-133">Das folgende Beispiel zeigt, wie Einstellungen für den standardmäßigen definiert `namedCache` Eintrags, der die `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="ac472-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac472-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac472-134">See Also</span></span>  
 [<span data-ttu-id="ac472-135">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ac472-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
