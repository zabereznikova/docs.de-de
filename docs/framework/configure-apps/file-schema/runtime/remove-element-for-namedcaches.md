---
title: <remove>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252339"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="3e92d-102">\<remove>-Element für \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="3e92d-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="3e92d-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="3e92d-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="3e92d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e92d-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3e92d-105">type</span><span class="sxs-lookup"><span data-stu-id="3e92d-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e92d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3e92d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3e92d-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3e92d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e92d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3e92d-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="3e92d-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e92d-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="3e92d-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3e92d-110">Parent Elements</span></span>  
  
|<span data-ttu-id="3e92d-111">Element</span><span class="sxs-lookup"><span data-stu-id="3e92d-111">Element</span></span>|<span data-ttu-id="3e92d-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3e92d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="3e92d-113">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="3e92d-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e92d-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3e92d-114">Remarks</span></span>  
 <span data-ttu-id="3e92d-115">Das- `remove` Element entfernt einen `namedCache` Eintrag aus der Auflistung benannter Caches für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="3e92d-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e92d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e92d-116">See also</span></span>

- [<span data-ttu-id="3e92d-117">\<namedCaches>-Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="3e92d-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
