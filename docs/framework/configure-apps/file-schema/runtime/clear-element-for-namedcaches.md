---
title: <clear>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: aaf5c2360b53a1cd6e5775a195c89c96ed6440a3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288664"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="05dd9-102">\<clear >-Element für \<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="05dd9-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="05dd9-103">Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="05dd9-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="05dd9-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="05dd9-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="05dd9-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="05dd9-105">\<memoryCache></span></span>  
<span data-ttu-id="05dd9-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="05dd9-106">\<namedCaches></span></span>  
<span data-ttu-id="05dd9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="05dd9-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05dd9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="05dd9-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="05dd9-109">Typ</span><span class="sxs-lookup"><span data-stu-id="05dd9-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05dd9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05dd9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05dd9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05dd9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05dd9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="05dd9-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="05dd9-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05dd9-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="05dd9-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05dd9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="05dd9-115">Element</span><span class="sxs-lookup"><span data-stu-id="05dd9-115">Element</span></span>|<span data-ttu-id="05dd9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05dd9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05dd9-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="05dd9-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="05dd9-118">Enthält eine Auflistung von Konfigurationseinstellungen für den benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="05dd9-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05dd9-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05dd9-119">Remarks</span></span>  
 <span data-ttu-id="05dd9-120">Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung benannter Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="05dd9-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="05dd9-121">Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, um sicherzugehen, dass sich keine weiteren benannten Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="05dd9-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05dd9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05dd9-122">See also</span></span>
- [<span data-ttu-id="05dd9-123">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="05dd9-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
