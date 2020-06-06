---
title: <Field>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: 2a63b88c399a999cd00750dee1614352cea10e80
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128418"
---
# <a name="field-element-net-native"></a><span data-ttu-id="42284-102">\<Field>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="42284-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="42284-103">Wendet eine Laufzeitreflektionrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="42284-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42284-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42284-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42284-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="42284-105">Attributes and Elements</span></span>  
 <span data-ttu-id="42284-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42284-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42284-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="42284-107">Attributes</span></span>  
  
|<span data-ttu-id="42284-108">attribute</span><span class="sxs-lookup"><span data-stu-id="42284-108">Attribute</span></span>|<span data-ttu-id="42284-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="42284-109">Attribute type</span></span>|<span data-ttu-id="42284-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42284-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="42284-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="42284-111">General</span></span>|<span data-ttu-id="42284-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="42284-112">Required attribute.</span></span> <span data-ttu-id="42284-113">Gibt den Feldnamen an.</span><span class="sxs-lookup"><span data-stu-id="42284-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="42284-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="42284-114">Reflection</span></span>|<span data-ttu-id="42284-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="42284-115">Optional attribute.</span></span> <span data-ttu-id="42284-116">Steuert das Abfragen nach Informationen über das Feld oder das Auflisten des Felds, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="42284-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="42284-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="42284-117">Reflection</span></span>|<span data-ttu-id="42284-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="42284-118">Optional attribute.</span></span> <span data-ttu-id="42284-119">Steuert den Laufzeitzugriff auf das Feld, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="42284-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="42284-120">Diese Richtlinie stellt sicher, dass ein Feld zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="42284-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="42284-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="42284-121">Serialization</span></span>|<span data-ttu-id="42284-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="42284-122">Optional attribute.</span></span> <span data-ttu-id="42284-123">Steuert den Laufzeitzugriff auf ein Feld, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="42284-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="42284-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="42284-124">Name attribute</span></span>  
  
|<span data-ttu-id="42284-125">Wert</span><span class="sxs-lookup"><span data-stu-id="42284-125">Value</span></span>|<span data-ttu-id="42284-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42284-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42284-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="42284-127">*method_name*</span></span>|<span data-ttu-id="42284-128">Der Name des Felds.</span><span class="sxs-lookup"><span data-stu-id="42284-128">The field name.</span></span> <span data-ttu-id="42284-129">Der Typ des Felds wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="42284-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="42284-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="42284-130">All other attributes</span></span>  
  
|<span data-ttu-id="42284-131">Wert</span><span class="sxs-lookup"><span data-stu-id="42284-131">Value</span></span>|<span data-ttu-id="42284-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42284-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="42284-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="42284-133">*policy_setting*</span></span>|<span data-ttu-id="42284-134">Die Einstellung, die auf diesen Richtlinientyp für das Feld angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="42284-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="42284-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="42284-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="42284-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="42284-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42284-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42284-137">Child Elements</span></span>  
 <span data-ttu-id="42284-138">Keine</span><span class="sxs-lookup"><span data-stu-id="42284-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42284-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="42284-139">Parent Elements</span></span>  
  
|<span data-ttu-id="42284-140">Element</span><span class="sxs-lookup"><span data-stu-id="42284-140">Element</span></span>|<span data-ttu-id="42284-141">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42284-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="42284-142">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="42284-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="42284-143">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="42284-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42284-144">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="42284-144">Remarks</span></span>  
 <span data-ttu-id="42284-145">Wenn die Richtlinie eines Felds nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="42284-145">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42284-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42284-146">See also</span></span>

- [<span data-ttu-id="42284-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="42284-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="42284-148">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="42284-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="42284-149">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="42284-149">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
