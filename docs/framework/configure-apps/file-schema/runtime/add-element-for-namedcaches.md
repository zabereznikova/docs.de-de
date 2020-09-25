---
title: <add>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cd920b58290050fcc30ea5d0a1ac113a333902fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195362"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="9d5c7-102">\<add>-Element für \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9d5c7-102">\<add> Element for \<namedCaches></span></span>

<span data-ttu-id="9d5c7-103">Fügt der-Auflistung einen `namedCache` Eintrag `namedCaches` für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="9d5c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d5c7-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="9d5c7-105">Typ</span><span class="sxs-lookup"><span data-stu-id="9d5c7-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d5c7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5c7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9d5c7-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d5c7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d5c7-108">Attributes</span></span>  
  
|<span data-ttu-id="9d5c7-109">attribute</span><span class="sxs-lookup"><span data-stu-id="9d5c7-109">Attribute</span></span>|<span data-ttu-id="9d5c7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5c7-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="9d5c7-111">Ein ganzzahliger Wert, der die maximal zulässige Größe (in Megabyte) angibt, auf die eine Instanz eines <xref:System.Runtime.Caching.MemoryCache> anwachsen kann.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="9d5c7-112">Der Standardwert ist 0 (null), was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="9d5c7-113">Der Name des Caches.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="9d5c7-114">Ein ganzzahliger Wert zwischen 0 und 100, der den maximalen Prozentsatz des physisch installierten Computer Arbeitsspeichers angibt, der vom Cache genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="9d5c7-115">Der Standardwert ist 0 (null), was bedeutet, dass die <xref:System.Runtime.Caching.MemoryCache> Automatisches Anpassen-Heuristik der Klasse standardmäßig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="9d5c7-116">Ein Wert, der das Zeitintervall angibt, in dem die Cacheimplementierung die aktuelle Auslastung des Arbeitsspeichers mit den absoluten und prozentualen Speichergrenzen vergleicht, die für die Cacheinstanz festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="9d5c7-117">Dieser Wert wird im Format "hh: mm: SS" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d5c7-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5c7-118">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="9d5c7-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d5c7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9d5c7-120">Element</span><span class="sxs-lookup"><span data-stu-id="9d5c7-120">Element</span></span>|<span data-ttu-id="9d5c7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d5c7-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="9d5c7-122">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d5c7-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d5c7-123">Remarks</span></span>  

 <span data-ttu-id="9d5c7-124">Das- `add` Element fügt der-Auflistung einen Eintrag `namedCaches` für einen Speicher Cache hinzu.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="9d5c7-125">Sie können das [Clear](clear-element-for-namedcaches.md) -Element verwenden, bevor Sie das- `add` Element verwenden, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="9d5c7-126">Dieses Element kann in der machine.config-Datei und in der Web.config Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d5c7-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d5c7-127">Example</span></span>  

 <span data-ttu-id="9d5c7-128">Im folgenden Beispiel wird gezeigt, wie Sie Einstellungen für den Standard `namedCache` Eintrag für die-Auflistung `namedCaches` für einen Speicher Cache definieren.</span><span class="sxs-lookup"><span data-stu-id="9d5c7-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d5c7-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d5c7-129">See also</span></span>

- [<span data-ttu-id="9d5c7-130">\<namedCaches> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="9d5c7-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
