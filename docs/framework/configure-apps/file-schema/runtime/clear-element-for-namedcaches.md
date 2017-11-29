---
title: "&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0819141b2135a2de99a2801a1888f7b0e1cd19fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="96fb9-102">&lt;Deaktivieren Sie&gt; -Element für &lt;NamedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="96fb9-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="96fb9-103">Löscht alle `namedCache` Einträge in der `namedCaches` Auflistung für einen Arbeitsspeichercache.</span><span class="sxs-lookup"><span data-stu-id="96fb9-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="96fb9-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="96fb9-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="96fb9-105">\<MemoryCache ></span><span class="sxs-lookup"><span data-stu-id="96fb9-105">\<memoryCache></span></span>  
<span data-ttu-id="96fb9-106">\<NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="96fb9-106">\<namedCaches></span></span>  
<span data-ttu-id="96fb9-107">\<add></span><span class="sxs-lookup"><span data-stu-id="96fb9-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96fb9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="96fb9-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="96fb9-109">Typ</span><span class="sxs-lookup"><span data-stu-id="96fb9-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96fb9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="96fb9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96fb9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="96fb9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96fb9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="96fb9-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="96fb9-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96fb9-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="96fb9-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96fb9-114">Parent Elements</span></span>  
  
|<span data-ttu-id="96fb9-115">Element</span><span class="sxs-lookup"><span data-stu-id="96fb9-115">Element</span></span>|<span data-ttu-id="96fb9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96fb9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96fb9-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="96fb9-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="96fb9-118">Enthält eine Auflistung von Konfigurationseinstellungen für die benannte <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="96fb9-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96fb9-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96fb9-119">Remarks</span></span>  
 <span data-ttu-id="96fb9-120">Die `clear` Element löscht alle `namedCache` Einträge in der Auflistung des benannten Caches für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="96fb9-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="96fb9-121">Können Sie die `clear` Element vor der Verwendung der `add` Element um einen neuen Eintrag für den benannten Cache hinzufügen, damit stellen Sie sicher, dass es sind keine anderen benannte Caches in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="96fb9-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96fb9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96fb9-122">See Also</span></span>  
 [<span data-ttu-id="96fb9-123">\<NamedCaches >-Element (Cacheeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="96fb9-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
