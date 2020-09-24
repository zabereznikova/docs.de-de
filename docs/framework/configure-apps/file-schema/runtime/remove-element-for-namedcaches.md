---
title: <remove>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: c8ad5a0ce6d7a3059943b3962b9255385cea6e15
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183987"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="05cc4-102">\<remove>-Element für \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="05cc4-102">\<remove> Element for \<namedCaches></span></span>

<span data-ttu-id="05cc4-103">Entfernt einen benannten Cacheeintrag aus der `namedCaches`-Sammlung für einen Speichercache.</span><span class="sxs-lookup"><span data-stu-id="05cc4-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="05cc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05cc4-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="05cc4-105">Typ</span><span class="sxs-lookup"><span data-stu-id="05cc4-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05cc4-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="05cc4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="05cc4-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05cc4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05cc4-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="05cc4-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="05cc4-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05cc4-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="05cc4-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="05cc4-110">Parent Elements</span></span>  
  
|<span data-ttu-id="05cc4-111">Element</span><span class="sxs-lookup"><span data-stu-id="05cc4-111">Element</span></span>|<span data-ttu-id="05cc4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05cc4-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="05cc4-113">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="05cc4-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05cc4-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="05cc4-114">Remarks</span></span>  

 <span data-ttu-id="05cc4-115">Das- `remove` Element entfernt einen `namedCache` Eintrag aus der Auflistung benannter Caches für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="05cc4-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cc4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05cc4-116">See also</span></span>

- [<span data-ttu-id="05cc4-117">\<namedCaches> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="05cc4-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
