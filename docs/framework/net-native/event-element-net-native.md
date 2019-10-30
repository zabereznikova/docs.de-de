---
title: <Event>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 6966caede63faafa718b760be879f6bc6cbd3ab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128493"
---
# <a name="event-element-net-native"></a><span data-ttu-id="32397-102">\<Ereignis >-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="32397-102">\<Event> Element (.NET Native)</span></span>
<span data-ttu-id="32397-103">Wendet eine Laufzeitreflektionsrichtlinie auf ein Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="32397-103">Applies runtime reflection policy to an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32397-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32397-104">Syntax</span></span>  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32397-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32397-105">Attributes and Elements</span></span>  
 <span data-ttu-id="32397-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32397-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32397-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="32397-107">Attributes</span></span>  
  
|<span data-ttu-id="32397-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="32397-108">Attribute</span></span>|<span data-ttu-id="32397-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="32397-109">Attribute type</span></span>|<span data-ttu-id="32397-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32397-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="32397-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="32397-111">General</span></span>|<span data-ttu-id="32397-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="32397-112">Required attribute.</span></span> <span data-ttu-id="32397-113">Gibt den Ereignisnamen an.</span><span class="sxs-lookup"><span data-stu-id="32397-113">Specifies the event name.</span></span>|  
|`Browse`|<span data-ttu-id="32397-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="32397-114">Reflection</span></span>|<span data-ttu-id="32397-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="32397-115">Optional attribute.</span></span> <span data-ttu-id="32397-116">Steuert das Abfragen nach Informationen über das Ereignis oder das Auflisten des Ereignisses, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="32397-116">Controls querying for information about or enumerating the event but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="32397-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="32397-117">Reflection</span></span>|<span data-ttu-id="32397-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="32397-118">Optional attribute.</span></span> <span data-ttu-id="32397-119">Steuert den Laufzeitzugriff auf das Ereignis, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="32397-119">Controls runtime access to the event to enable dynamic programming.</span></span> <span data-ttu-id="32397-120">Diese Richtlinie stellt sicher, dass ein Ereignis dynamisch zur Laufzeit behandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="32397-120">This policy ensures that an event can be handled dynamically at run time.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="32397-121">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="32397-121">Name attribute</span></span>  
  
|<span data-ttu-id="32397-122">Wert</span><span class="sxs-lookup"><span data-stu-id="32397-122">Value</span></span>|<span data-ttu-id="32397-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32397-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32397-124">*method_name*</span><span class="sxs-lookup"><span data-stu-id="32397-124">*method_name*</span></span>|<span data-ttu-id="32397-125">Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="32397-125">The event name.</span></span> <span data-ttu-id="32397-126">Der Typ des Ereignisses wird durch das übergeordnete [\<Type>](type-element-net-native.md)- oder [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="32397-126">The type of the event is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="32397-127">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="32397-127">All other attributes</span></span>  
  
|<span data-ttu-id="32397-128">Wert</span><span class="sxs-lookup"><span data-stu-id="32397-128">Value</span></span>|<span data-ttu-id="32397-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32397-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32397-130">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="32397-130">*policy_setting*</span></span>|<span data-ttu-id="32397-131">Die Einstellung, die auf diesen Richtlinientyp für das Ereignis angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="32397-131">The setting to apply to this policy type for the event.</span></span> <span data-ttu-id="32397-132">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="32397-132">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="32397-133">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="32397-133">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32397-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32397-134">Child Elements</span></span>  
 <span data-ttu-id="32397-135">Keine</span><span class="sxs-lookup"><span data-stu-id="32397-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32397-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32397-136">Parent Elements</span></span>  
  
|<span data-ttu-id="32397-137">Element</span><span class="sxs-lookup"><span data-stu-id="32397-137">Element</span></span>|<span data-ttu-id="32397-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32397-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32397-139">\<Type></span><span class="sxs-lookup"><span data-stu-id="32397-139">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="32397-140">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="32397-140">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="32397-141">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="32397-141">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="32397-142">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="32397-142">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32397-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32397-143">Remarks</span></span>  
 <span data-ttu-id="32397-144">Wenn die Richtlinie eines Ereignisses nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="32397-144">If an event's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32397-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32397-145">See also</span></span>

- [<span data-ttu-id="32397-146">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="32397-146">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="32397-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="32397-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="32397-148">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="32397-148">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
