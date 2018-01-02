---
title: "&lt;Entfernen Sie&gt; -Element für &lt;NamedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4b360b206586b263627ab6f6b7e0309f3055f38a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="7ec42-102">&lt;Entfernen Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="7ec42-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="7ec42-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="7ec42-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="7ec42-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="7ec42-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="7ec42-105">\<MemoryCache ></span><span class="sxs-lookup"><span data-stu-id="7ec42-105">\<memoryCache></span></span>  
<span data-ttu-id="7ec42-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="7ec42-106">\<namedCaches></span></span>  
<span data-ttu-id="7ec42-107">\<Entfernen ></span><span class="sxs-lookup"><span data-stu-id="7ec42-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec42-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ec42-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="7ec42-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7ec42-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec42-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ec42-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ec42-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ec42-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec42-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ec42-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="7ec42-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ec42-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec42-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ec42-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec42-115">Element</span><span class="sxs-lookup"><span data-stu-id="7ec42-115">Element</span></span>|<span data-ttu-id="7ec42-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ec42-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ec42-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="7ec42-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="7ec42-118">Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="7ec42-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ec42-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ec42-119">Remarks</span></span>  
 <span data-ttu-id="7ec42-120">Die `remove` Element entfernt eine `namedCache` Eintrag aus der Auflistung des benannten Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="7ec42-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec42-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ec42-121">See Also</span></span>  
 [<span data-ttu-id="7ec42-122">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7ec42-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
