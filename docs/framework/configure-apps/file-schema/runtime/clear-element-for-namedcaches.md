---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: dd521e3afa7584cadb28829028a5ecfd1cb55a92
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612298"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="561cb-102">&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="561cb-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="561cb-103">Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="561cb-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="561cb-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="561cb-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="561cb-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="561cb-105">\<memoryCache></span></span>  
<span data-ttu-id="561cb-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="561cb-106">\<namedCaches></span></span>  
<span data-ttu-id="561cb-107">\<add></span><span class="sxs-lookup"><span data-stu-id="561cb-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="561cb-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="561cb-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="561cb-109">Typ</span><span class="sxs-lookup"><span data-stu-id="561cb-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="561cb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="561cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="561cb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="561cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="561cb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="561cb-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="561cb-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="561cb-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="561cb-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="561cb-114">Parent Elements</span></span>  
  
|<span data-ttu-id="561cb-115">Element</span><span class="sxs-lookup"><span data-stu-id="561cb-115">Element</span></span>|<span data-ttu-id="561cb-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="561cb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="561cb-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="561cb-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="561cb-118">Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="561cb-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="561cb-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="561cb-119">Remarks</span></span>  
 <span data-ttu-id="561cb-120">Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung benannter Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="561cb-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="561cb-121">Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, um sicherzugehen, dass sich keine weiteren benannten Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="561cb-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561cb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="561cb-122">See Also</span></span>  
- [<span data-ttu-id="561cb-123">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="561cb-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
