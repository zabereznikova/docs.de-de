---
title: <clear>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: d65712f091c5fb9212167b4759c70db7e5d744c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149412"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="5269b-102">\<clear>-Element für \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="5269b-102">\<clear> Element for \<namedCaches></span></span>

<span data-ttu-id="5269b-103">Löscht alle `namedCache` Einträge in der-Auflistung `namedCaches` für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="5269b-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="5269b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5269b-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="5269b-105">Typ</span><span class="sxs-lookup"><span data-stu-id="5269b-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5269b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5269b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5269b-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5269b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5269b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="5269b-108">Attributes</span></span>  

 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="5269b-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5269b-109">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="5269b-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5269b-110">Parent Elements</span></span>  
  
|<span data-ttu-id="5269b-111">Element</span><span class="sxs-lookup"><span data-stu-id="5269b-111">Element</span></span>|<span data-ttu-id="5269b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5269b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="5269b-113">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="5269b-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5269b-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5269b-114">Remarks</span></span>  

 <span data-ttu-id="5269b-115">Das- `clear` Element löscht alle `namedCache` Einträge in der benannten Cache Auflistung für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="5269b-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="5269b-116">Sie können das- `clear` Element verwenden, bevor Sie das- `add` Element verwenden, um einen neuen benannten Cache Eintrag hinzuzufügen, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5269b-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5269b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5269b-117">See also</span></span>

- [<span data-ttu-id="5269b-118">\<namedCaches> -Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="5269b-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
