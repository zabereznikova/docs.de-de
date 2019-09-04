---
title: <clear>-Element für <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252760"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="dcc52-102">\<Löschen Sie > Element \<für NamedCaches ></span><span class="sxs-lookup"><span data-stu-id="dcc52-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="dcc52-103">Löscht alle `namedCache` Einträge in der `namedCaches` -Auflistung für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="dcc52-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="dcc52-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dcc52-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dcc52-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching->** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dcc52-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="dcc52-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<MemoryCache->** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dcc52-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="dcc52-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NamedCaches >** ](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dcc52-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="dcc52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**</span><span class="sxs-lookup"><span data-stu-id="dcc52-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc52-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcc52-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="dcc52-110">Typ</span><span class="sxs-lookup"><span data-stu-id="dcc52-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcc52-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dcc52-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dcc52-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dcc52-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcc52-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dcc52-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="dcc52-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dcc52-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="dcc52-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dcc52-115">Parent Elements</span></span>  
  
|<span data-ttu-id="dcc52-116">Element</span><span class="sxs-lookup"><span data-stu-id="dcc52-116">Element</span></span>|<span data-ttu-id="dcc52-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dcc52-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcc52-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="dcc52-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="dcc52-119">Enthält eine Sammlung von Konfigurationseinstellungen für die benannten <xref:System.Runtime.Caching.MemoryCache> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="dcc52-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcc52-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcc52-120">Remarks</span></span>  
 <span data-ttu-id="dcc52-121">Das `clear` -Element löscht `namedCache` alle Einträge in der benannten Cache Auflistung für einen Speicher Cache.</span><span class="sxs-lookup"><span data-stu-id="dcc52-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="dcc52-122">Sie können das `clear` -Element verwenden, bevor Sie `add` das-Element verwenden, um einen neuen benannten Cache Eintrag hinzuzufügen, um sicherzustellen, dass keine anderen benannten Caches in der Auflistung vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="dcc52-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc52-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcc52-123">See also</span></span>

- [<span data-ttu-id="dcc52-124">\<NamedCaches > Element (Cache Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="dcc52-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
