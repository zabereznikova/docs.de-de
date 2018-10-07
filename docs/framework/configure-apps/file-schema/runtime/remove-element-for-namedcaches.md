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
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838220"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="c8440-102">&lt;Entfernen Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="c8440-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="c8440-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="c8440-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="c8440-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="c8440-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="c8440-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="c8440-105">\<memoryCache></span></span>  
<span data-ttu-id="c8440-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="c8440-106">\<namedCaches></span></span>  
<span data-ttu-id="c8440-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="c8440-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8440-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8440-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="c8440-109">Typ</span><span class="sxs-lookup"><span data-stu-id="c8440-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8440-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8440-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8440-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8440-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8440-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8440-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="c8440-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8440-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="c8440-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8440-114">Parent Elements</span></span>  
  
|<span data-ttu-id="c8440-115">Element</span><span class="sxs-lookup"><span data-stu-id="c8440-115">Element</span></span>|<span data-ttu-id="c8440-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8440-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8440-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="c8440-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="c8440-118">Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="c8440-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8440-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8440-119">Remarks</span></span>  
 <span data-ttu-id="c8440-120">Die `remove` -Element entfernt eine `namedCache` Eintrag aus der Auflistung benannter Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="c8440-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8440-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8440-121">See Also</span></span>  
 [<span data-ttu-id="c8440-122">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c8440-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
