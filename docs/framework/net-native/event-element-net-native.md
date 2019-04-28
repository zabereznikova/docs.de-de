---
title: <Event> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89e8ddf9ea72db63c72bfb5393709b4c20de2a14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868576"
---
# <a name="event-element-net-native"></a><span data-ttu-id="cce29-102">\<Ereignis > (Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="cce29-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="cce29-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="cce29-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cce29-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cce29-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cce29-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cce29-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cce29-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cce29-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="cce29-107">Attributes</span></span>  
  
|<span data-ttu-id="cce29-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="cce29-108">Attribute</span></span>|<span data-ttu-id="cce29-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="cce29-109">Attribute type</span></span>|<span data-ttu-id="cce29-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cce29-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="cce29-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="cce29-111">General</span></span>|<span data-ttu-id="cce29-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cce29-112">Required attribute.</span></span> <span data-ttu-id="cce29-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="cce29-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="cce29-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="cce29-114">Reflection</span></span>|<span data-ttu-id="cce29-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="cce29-115">Optional attribute.</span></span> <span data-ttu-id="cce29-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="cce29-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="cce29-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="cce29-117">Reflection</span></span>|<span data-ttu-id="cce29-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="cce29-118">Optional attribute.</span></span> <span data-ttu-id="cce29-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="cce29-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="cce29-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cce29-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="cce29-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="cce29-121">Name attribute</span></span>  
  
|<span data-ttu-id="cce29-122">Wert</span><span class="sxs-lookup"><span data-stu-id="cce29-122">Value</span></span>|<span data-ttu-id="cce29-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cce29-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cce29-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="cce29-124">*method_name*</span></span>|<span data-ttu-id="cce29-125">Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="cce29-125">The event name.</span></span> <span data-ttu-id="cce29-126">Der Typ des Ereignisses wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="cce29-126">The type of the event is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="cce29-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="cce29-127">All other attributes</span></span>  
  
|<span data-ttu-id="cce29-128">Wert</span><span class="sxs-lookup"><span data-stu-id="cce29-128">Value</span></span>|<span data-ttu-id="cce29-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cce29-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cce29-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="cce29-130">*policy_setting*</span></span>|<span data-ttu-id="cce29-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cce29-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="cce29-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="cce29-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="cce29-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="cce29-133">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cce29-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cce29-134">Child Elements</span></span>  
 <span data-ttu-id="cce29-135">Keine</span><span class="sxs-lookup"><span data-stu-id="cce29-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cce29-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cce29-136">Parent Elements</span></span>  
  
|<span data-ttu-id="cce29-137">Element</span><span class="sxs-lookup"><span data-stu-id="cce29-137">Element</span></span>|<span data-ttu-id="cce29-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cce29-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cce29-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="cce29-139">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="cce29-140">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="cce29-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="cce29-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="cce29-141">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="cce29-142">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="cce29-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cce29-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cce29-143">Remarks</span></span>  
 <span data-ttu-id="cce29-144">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="cce29-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce29-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cce29-145">See also</span></span>

- [<span data-ttu-id="cce29-146">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="cce29-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="cce29-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="cce29-147">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="cce29-148">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="cce29-148">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
