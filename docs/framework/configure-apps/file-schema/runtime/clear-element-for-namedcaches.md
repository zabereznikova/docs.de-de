---
title: '&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cdd6e4a4849a031dc6bcad909509498406fcb129
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="3879e-102">&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="3879e-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="3879e-103">Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="3879e-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="3879e-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="3879e-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="3879e-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="3879e-105">\<memoryCache></span></span>  
<span data-ttu-id="3879e-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="3879e-106">\<namedCaches></span></span>  
<span data-ttu-id="3879e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3879e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3879e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="3879e-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3879e-109">Typ</span><span class="sxs-lookup"><span data-stu-id="3879e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3879e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3879e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3879e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3879e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3879e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3879e-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="3879e-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3879e-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="3879e-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3879e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3879e-115">Element</span><span class="sxs-lookup"><span data-stu-id="3879e-115">Element</span></span>|<span data-ttu-id="3879e-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3879e-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3879e-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="3879e-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="3879e-118">Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3879e-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3879e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3879e-119">Remarks</span></span>  
 <span data-ttu-id="3879e-120">Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung des benannten Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="3879e-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="3879e-121">Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, damit stellen Sie sicher, dass es sind keine anderen benannte Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="3879e-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3879e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3879e-122">See Also</span></span>  
 [<span data-ttu-id="3879e-123">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="3879e-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
