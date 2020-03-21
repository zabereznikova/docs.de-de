---
title: <Event>Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181038"
---
# <a name="event-element-net-native"></a><span data-ttu-id="82968-102">\<Ereignis> Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="82968-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="82968-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="82968-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82968-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82968-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82968-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="82968-105">Attributes and Elements</span></span>  
 <span data-ttu-id="82968-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82968-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82968-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="82968-107">Attributes</span></span>  
  
|<span data-ttu-id="82968-108">attribute</span><span class="sxs-lookup"><span data-stu-id="82968-108">Attribute</span></span>|<span data-ttu-id="82968-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="82968-109">Attribute type</span></span>|<span data-ttu-id="82968-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82968-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="82968-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="82968-111">General</span></span>|<span data-ttu-id="82968-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="82968-112">Required attribute.</span></span> <span data-ttu-id="82968-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="82968-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="82968-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="82968-114">Reflection</span></span>|<span data-ttu-id="82968-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="82968-115">Optional attribute.</span></span> <span data-ttu-id="82968-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="82968-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="82968-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="82968-117">Reflection</span></span>|<span data-ttu-id="82968-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="82968-118">Optional attribute.</span></span> <span data-ttu-id="82968-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="82968-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="82968-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="82968-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="82968-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="82968-121">Name attribute</span></span>  
  
|<span data-ttu-id="82968-122">value</span><span class="sxs-lookup"><span data-stu-id="82968-122">Value</span></span>|<span data-ttu-id="82968-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82968-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82968-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="82968-124">*method_name*</span></span>|<span data-ttu-id="82968-125">Der Ereignisname.</span><span class="sxs-lookup"><span data-stu-id="82968-125">The event name.</span></span> <span data-ttu-id="82968-126">Der Typ des Ereignisses wird [ \<](type-element-net-native.md) durch das übergeordnete Type>oder [ \<TypeInstantiation>-Element](typeinstantiation-element-net-native.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="82968-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="82968-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="82968-127">All other attributes</span></span>  
  
|<span data-ttu-id="82968-128">value</span><span class="sxs-lookup"><span data-stu-id="82968-128">Value</span></span>|<span data-ttu-id="82968-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82968-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82968-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="82968-130">*policy_setting*</span></span>|<span data-ttu-id="82968-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="82968-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="82968-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="82968-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="82968-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="82968-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82968-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82968-134">Child Elements</span></span>  
 <span data-ttu-id="82968-135">Keine.</span><span class="sxs-lookup"><span data-stu-id="82968-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82968-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="82968-136">Parent Elements</span></span>  
  
|<span data-ttu-id="82968-137">Element</span><span class="sxs-lookup"><span data-stu-id="82968-137">Element</span></span>|<span data-ttu-id="82968-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82968-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82968-139">\<Typ></span><span class="sxs-lookup"><span data-stu-id="82968-139">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="82968-140">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="82968-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="82968-141">\<TypInstanziierung></span><span class="sxs-lookup"><span data-stu-id="82968-141">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="82968-142">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="82968-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82968-143">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="82968-143">Remarks</span></span>  
 <span data-ttu-id="82968-144">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="82968-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82968-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82968-145">See also</span></span>

- [<span data-ttu-id="82968-146">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="82968-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="82968-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="82968-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="82968-148">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="82968-148">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
