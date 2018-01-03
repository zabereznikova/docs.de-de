---
title: '&lt;Ereignis&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a37758ed497211ba0550666ec4857666041c5285
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lteventgt-element-net-native"></a><span data-ttu-id="41518-102">&lt;Ereignis&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="41518-102">&lt;Event&gt; Element (.NET Native)</span></span>
<span data-ttu-id="41518-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="41518-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41518-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41518-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41518-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41518-105">Attributes and Elements</span></span>  
 <span data-ttu-id="41518-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41518-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41518-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="41518-107">Attributes</span></span>  
  
|<span data-ttu-id="41518-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="41518-108">Attribute</span></span>|<span data-ttu-id="41518-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="41518-109">Attribute type</span></span>|<span data-ttu-id="41518-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41518-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="41518-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="41518-111">General</span></span>|<span data-ttu-id="41518-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="41518-112">Required attribute.</span></span> <span data-ttu-id="41518-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="41518-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="41518-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="41518-114">Reflection</span></span>|<span data-ttu-id="41518-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="41518-115">Optional attribute.</span></span> <span data-ttu-id="41518-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="41518-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="41518-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="41518-117">Reflection</span></span>|<span data-ttu-id="41518-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="41518-118">Optional attribute.</span></span> <span data-ttu-id="41518-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="41518-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="41518-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="41518-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="41518-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="41518-121">Name attribute</span></span>  
  
|<span data-ttu-id="41518-122">Wert</span><span class="sxs-lookup"><span data-stu-id="41518-122">Value</span></span>|<span data-ttu-id="41518-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41518-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41518-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="41518-124">*method_name*</span></span>|<span data-ttu-id="41518-125">Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="41518-125">The event name.</span></span> <span data-ttu-id="41518-126">Der Typ des Ereignisses wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="41518-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="41518-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="41518-127">All other attributes</span></span>  
  
|<span data-ttu-id="41518-128">Wert</span><span class="sxs-lookup"><span data-stu-id="41518-128">Value</span></span>|<span data-ttu-id="41518-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41518-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41518-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="41518-130">*policy_setting*</span></span>|<span data-ttu-id="41518-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="41518-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="41518-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="41518-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="41518-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="41518-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41518-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41518-134">Child Elements</span></span>  
 <span data-ttu-id="41518-135">Keine</span><span class="sxs-lookup"><span data-stu-id="41518-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41518-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41518-136">Parent Elements</span></span>  
  
|<span data-ttu-id="41518-137">Element</span><span class="sxs-lookup"><span data-stu-id="41518-137">Element</span></span>|<span data-ttu-id="41518-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41518-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41518-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="41518-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="41518-140">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="41518-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="41518-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="41518-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="41518-142">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="41518-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41518-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41518-143">Remarks</span></span>  
 <span data-ttu-id="41518-144">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="41518-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41518-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41518-145">See Also</span></span>  
 [<span data-ttu-id="41518-146">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="41518-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="41518-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="41518-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="41518-148">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="41518-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
