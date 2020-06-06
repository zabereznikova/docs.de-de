---
title: <Event>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181038"
---
# <a name="event-element-net-native"></a><span data-ttu-id="da6a0-102">\<Event>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="da6a0-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="da6a0-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="da6a0-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da6a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da6a0-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da6a0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da6a0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da6a0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da6a0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da6a0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="da6a0-107">Attributes</span></span>  
  
|<span data-ttu-id="da6a0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="da6a0-108">Attribute</span></span>|<span data-ttu-id="da6a0-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="da6a0-109">Attribute type</span></span>|<span data-ttu-id="da6a0-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da6a0-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="da6a0-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="da6a0-111">General</span></span>|<span data-ttu-id="da6a0-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="da6a0-112">Required attribute.</span></span> <span data-ttu-id="da6a0-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="da6a0-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="da6a0-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="da6a0-114">Reflection</span></span>|<span data-ttu-id="da6a0-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="da6a0-115">Optional attribute.</span></span> <span data-ttu-id="da6a0-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="da6a0-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="da6a0-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="da6a0-117">Reflection</span></span>|<span data-ttu-id="da6a0-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="da6a0-118">Optional attribute.</span></span> <span data-ttu-id="da6a0-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="da6a0-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="da6a0-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="da6a0-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="da6a0-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="da6a0-121">Name attribute</span></span>  
  
|<span data-ttu-id="da6a0-122">Wert</span><span class="sxs-lookup"><span data-stu-id="da6a0-122">Value</span></span>|<span data-ttu-id="da6a0-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da6a0-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="da6a0-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="da6a0-124">*method_name*</span></span>|<span data-ttu-id="da6a0-125">Der Ereignisname.</span><span class="sxs-lookup"><span data-stu-id="da6a0-125">The event name.</span></span> <span data-ttu-id="da6a0-126">Der Typ des Ereignisses wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="da6a0-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="da6a0-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="da6a0-127">All other attributes</span></span>  
  
|<span data-ttu-id="da6a0-128">Wert</span><span class="sxs-lookup"><span data-stu-id="da6a0-128">Value</span></span>|<span data-ttu-id="da6a0-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da6a0-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="da6a0-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="da6a0-130">*policy_setting*</span></span>|<span data-ttu-id="da6a0-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="da6a0-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="da6a0-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="da6a0-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="da6a0-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="da6a0-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da6a0-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da6a0-134">Child Elements</span></span>  
 <span data-ttu-id="da6a0-135">Keine</span><span class="sxs-lookup"><span data-stu-id="da6a0-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da6a0-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da6a0-136">Parent Elements</span></span>  
  
|<span data-ttu-id="da6a0-137">Element</span><span class="sxs-lookup"><span data-stu-id="da6a0-137">Element</span></span>|<span data-ttu-id="da6a0-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da6a0-138">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="da6a0-139">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="da6a0-139">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="da6a0-140">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="da6a0-140">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da6a0-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="da6a0-141">Remarks</span></span>  
 <span data-ttu-id="da6a0-142">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="da6a0-142">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6a0-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da6a0-143">See also</span></span>

- [<span data-ttu-id="da6a0-144">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="da6a0-144">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="da6a0-145">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="da6a0-145">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="da6a0-146">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="da6a0-146">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
