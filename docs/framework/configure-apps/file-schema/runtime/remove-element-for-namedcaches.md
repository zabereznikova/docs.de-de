---
title: <remove>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252339"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="4755d-102">\<Entfernen Sie >- \<Element für NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="4755d-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="4755d-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="4755d-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="4755d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4755d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4755d-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4755d-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="4755d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MemoryCache->** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4755d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="4755d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NamedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4755d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="4755d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="4755d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4755d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4755d-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="4755d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="4755d-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4755d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4755d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4755d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4755d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4755d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4755d-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="4755d-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4755d-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="4755d-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4755d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4755d-116">Element</span><span class="sxs-lookup"><span data-stu-id="4755d-116">Element</span></span>|<span data-ttu-id="4755d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4755d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4755d-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4755d-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="4755d-119">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="4755d-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4755d-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4755d-120">Remarks</span></span>  
 <span data-ttu-id="4755d-121">Das `remove` -Element entfernt `namedCache` einen Eintrag aus der Auflistung benannter Caches für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="4755d-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4755d-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4755d-122">See also</span></span>

- [<span data-ttu-id="4755d-123">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="4755d-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
