---
title: <Event> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: b1cf2239e58839c5026bc375ba04568227881bdd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288098"
---
# <a name="event-element-net-native"></a><span data-ttu-id="55ce4-102">\<Event> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="55ce4-102">\<Event> Element (.NET Native)</span></span>

<span data-ttu-id="55ce4-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="55ce4-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ce4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55ce4-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"
       Browse="policy_type"
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55ce4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="55ce4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="55ce4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55ce4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55ce4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="55ce4-107">Attributes</span></span>  
  
|<span data-ttu-id="55ce4-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="55ce4-108">Attribute</span></span>|<span data-ttu-id="55ce4-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="55ce4-109">Attribute type</span></span>|<span data-ttu-id="55ce4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55ce4-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="55ce4-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="55ce4-111">General</span></span>|<span data-ttu-id="55ce4-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="55ce4-112">Required attribute.</span></span> <span data-ttu-id="55ce4-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="55ce4-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="55ce4-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="55ce4-114">Reflection</span></span>|<span data-ttu-id="55ce4-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="55ce4-115">Optional attribute.</span></span> <span data-ttu-id="55ce4-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="55ce4-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="55ce4-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="55ce4-117">Reflection</span></span>|<span data-ttu-id="55ce4-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="55ce4-118">Optional attribute.</span></span> <span data-ttu-id="55ce4-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="55ce4-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="55ce4-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="55ce4-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="55ce4-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="55ce4-121">Name attribute</span></span>  
  
|<span data-ttu-id="55ce4-122">Wert</span><span class="sxs-lookup"><span data-stu-id="55ce4-122">Value</span></span>|<span data-ttu-id="55ce4-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55ce4-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55ce4-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="55ce4-124">*method_name*</span></span>|<span data-ttu-id="55ce4-125">Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="55ce4-125">The event name.</span></span> <span data-ttu-id="55ce4-126">Der Typ des Ereignisses wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="55ce4-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="55ce4-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="55ce4-127">All other attributes</span></span>  
  
|<span data-ttu-id="55ce4-128">Wert</span><span class="sxs-lookup"><span data-stu-id="55ce4-128">Value</span></span>|<span data-ttu-id="55ce4-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55ce4-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="55ce4-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="55ce4-130">*policy_setting*</span></span>|<span data-ttu-id="55ce4-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="55ce4-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="55ce4-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="55ce4-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="55ce4-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="55ce4-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55ce4-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55ce4-134">Child Elements</span></span>  

 <span data-ttu-id="55ce4-135">Keine</span><span class="sxs-lookup"><span data-stu-id="55ce4-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55ce4-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="55ce4-136">Parent Elements</span></span>  
  
|<span data-ttu-id="55ce4-137">Element</span><span class="sxs-lookup"><span data-stu-id="55ce4-137">Element</span></span>|<span data-ttu-id="55ce4-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55ce4-138">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="55ce4-139">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="55ce4-139">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="55ce4-140">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="55ce4-140">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55ce4-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55ce4-141">Remarks</span></span>  

 <span data-ttu-id="55ce4-142">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="55ce4-142">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ce4-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55ce4-143">See also</span></span>

- [<span data-ttu-id="55ce4-144">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="55ce4-144">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="55ce4-145">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="55ce4-145">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="55ce4-146">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="55ce4-146">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
