---
title: '&lt;Ereignis&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11cc51eb12edc36331bd7a2d3bb1ecfdc267985e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536749"
---
# <a name="lteventgt-element-net-native"></a><span data-ttu-id="61a14-102">&lt;Ereignis&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="61a14-102">&lt;Event&gt; Element (.NET Native)</span></span>
<span data-ttu-id="61a14-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="61a14-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61a14-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61a14-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="61a14-105">Attributes and Elements</span></span>  
 <span data-ttu-id="61a14-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="61a14-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61a14-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="61a14-107">Attributes</span></span>  
  
|<span data-ttu-id="61a14-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="61a14-108">Attribute</span></span>|<span data-ttu-id="61a14-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="61a14-109">Attribute type</span></span>|<span data-ttu-id="61a14-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a14-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="61a14-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="61a14-111">General</span></span>|<span data-ttu-id="61a14-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="61a14-112">Required attribute.</span></span> <span data-ttu-id="61a14-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="61a14-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="61a14-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="61a14-114">Reflection</span></span>|<span data-ttu-id="61a14-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="61a14-115">Optional attribute.</span></span> <span data-ttu-id="61a14-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="61a14-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="61a14-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="61a14-117">Reflection</span></span>|<span data-ttu-id="61a14-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="61a14-118">Optional attribute.</span></span> <span data-ttu-id="61a14-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="61a14-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="61a14-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="61a14-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="61a14-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="61a14-121">Name attribute</span></span>  
  
|<span data-ttu-id="61a14-122">Wert</span><span class="sxs-lookup"><span data-stu-id="61a14-122">Value</span></span>|<span data-ttu-id="61a14-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a14-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="61a14-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="61a14-124">*method_name*</span></span>|<span data-ttu-id="61a14-125">Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="61a14-125">The event name.</span></span> <span data-ttu-id="61a14-126">Der Typ des Ereignisses wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="61a14-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="61a14-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="61a14-127">All other attributes</span></span>  
  
|<span data-ttu-id="61a14-128">Wert</span><span class="sxs-lookup"><span data-stu-id="61a14-128">Value</span></span>|<span data-ttu-id="61a14-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a14-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="61a14-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="61a14-130">*policy_setting*</span></span>|<span data-ttu-id="61a14-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="61a14-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="61a14-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="61a14-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="61a14-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="61a14-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61a14-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a14-134">Child Elements</span></span>  
 <span data-ttu-id="61a14-135">Keine</span><span class="sxs-lookup"><span data-stu-id="61a14-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61a14-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="61a14-136">Parent Elements</span></span>  
  
|<span data-ttu-id="61a14-137">Element</span><span class="sxs-lookup"><span data-stu-id="61a14-137">Element</span></span>|<span data-ttu-id="61a14-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61a14-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61a14-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="61a14-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="61a14-140">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="61a14-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="61a14-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="61a14-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="61a14-142">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="61a14-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61a14-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61a14-143">Remarks</span></span>  
 <span data-ttu-id="61a14-144">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="61a14-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a14-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a14-145">See also</span></span>
- [<span data-ttu-id="61a14-146">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="61a14-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="61a14-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="61a14-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="61a14-148">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="61a14-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
