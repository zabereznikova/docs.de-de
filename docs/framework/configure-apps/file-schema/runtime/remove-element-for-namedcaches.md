---
title: '&lt;Entfernen Sie&gt; -Element für &lt;NamedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f885416629ae58949cc688f4e6fbd41e77e872aa
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781673"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="a25b6-102">&lt;Entfernen Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="a25b6-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="a25b6-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="a25b6-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="a25b6-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="a25b6-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="a25b6-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="a25b6-105">\<memoryCache></span></span>  
<span data-ttu-id="a25b6-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="a25b6-106">\<namedCaches></span></span>  
<span data-ttu-id="a25b6-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="a25b6-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25b6-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a25b6-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="a25b6-109">Typ</span><span class="sxs-lookup"><span data-stu-id="a25b6-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a25b6-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a25b6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a25b6-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a25b6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a25b6-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a25b6-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="a25b6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a25b6-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="a25b6-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a25b6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a25b6-115">Element</span><span class="sxs-lookup"><span data-stu-id="a25b6-115">Element</span></span>|<span data-ttu-id="a25b6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a25b6-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a25b6-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="a25b6-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="a25b6-118">Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="a25b6-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a25b6-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a25b6-119">Remarks</span></span>  
 <span data-ttu-id="a25b6-120">Die `remove` -Element entfernt eine `namedCache` Eintrag aus der Auflistung benannter Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="a25b6-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25b6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a25b6-121">See Also</span></span>  
 [<span data-ttu-id="a25b6-122">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a25b6-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
