---
title: <Field> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
ms.openlocfilehash: e63dc293c42aa620b7f7ac15fc0454bc603b9dde
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251047"
---
# <a name="field-element-net-native"></a><span data-ttu-id="91ea6-102">\<Field> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="91ea6-102">\<Field> Element (.NET Native)</span></span>

<span data-ttu-id="91ea6-103">Wendet eine Laufzeitreflektionrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="91ea6-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91ea6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91ea6-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91ea6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91ea6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="91ea6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91ea6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91ea6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="91ea6-107">Attributes</span></span>  
  
|<span data-ttu-id="91ea6-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="91ea6-108">Attribute</span></span>|<span data-ttu-id="91ea6-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="91ea6-109">Attribute type</span></span>|<span data-ttu-id="91ea6-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91ea6-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="91ea6-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="91ea6-111">General</span></span>|<span data-ttu-id="91ea6-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="91ea6-112">Required attribute.</span></span> <span data-ttu-id="91ea6-113">Gibt den Feldnamen an.</span><span class="sxs-lookup"><span data-stu-id="91ea6-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="91ea6-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="91ea6-114">Reflection</span></span>|<span data-ttu-id="91ea6-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="91ea6-115">Optional attribute.</span></span> <span data-ttu-id="91ea6-116">Steuert das Abfragen nach Informationen über das Feld oder das Auflisten des Felds, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="91ea6-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="91ea6-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="91ea6-117">Reflection</span></span>|<span data-ttu-id="91ea6-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="91ea6-118">Optional attribute.</span></span> <span data-ttu-id="91ea6-119">Steuert den Laufzeitzugriff auf das Feld, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="91ea6-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="91ea6-120">Diese Richtlinie stellt sicher, dass ein Feld zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="91ea6-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="91ea6-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="91ea6-121">Serialization</span></span>|<span data-ttu-id="91ea6-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="91ea6-122">Optional attribute.</span></span> <span data-ttu-id="91ea6-123">Steuert den Laufzeitzugriff auf ein Feld, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="91ea6-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="91ea6-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="91ea6-124">Name attribute</span></span>  
  
|<span data-ttu-id="91ea6-125">Wert</span><span class="sxs-lookup"><span data-stu-id="91ea6-125">Value</span></span>|<span data-ttu-id="91ea6-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91ea6-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91ea6-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="91ea6-127">*method_name*</span></span>|<span data-ttu-id="91ea6-128">Der Feldname.</span><span class="sxs-lookup"><span data-stu-id="91ea6-128">The field name.</span></span> <span data-ttu-id="91ea6-129">Der Typ des Felds wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="91ea6-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="91ea6-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="91ea6-130">All other attributes</span></span>  
  
|<span data-ttu-id="91ea6-131">Wert</span><span class="sxs-lookup"><span data-stu-id="91ea6-131">Value</span></span>|<span data-ttu-id="91ea6-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91ea6-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="91ea6-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="91ea6-133">*policy_setting*</span></span>|<span data-ttu-id="91ea6-134">Die Einstellung, die auf diesen Richtlinientyp für das Feld angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91ea6-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="91ea6-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="91ea6-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="91ea6-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="91ea6-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91ea6-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91ea6-137">Child Elements</span></span>  

 <span data-ttu-id="91ea6-138">Keine</span><span class="sxs-lookup"><span data-stu-id="91ea6-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91ea6-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91ea6-139">Parent Elements</span></span>  
  
|<span data-ttu-id="91ea6-140">Element</span><span class="sxs-lookup"><span data-stu-id="91ea6-140">Element</span></span>|<span data-ttu-id="91ea6-141">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91ea6-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="91ea6-142">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="91ea6-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="91ea6-143">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="91ea6-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91ea6-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91ea6-144">Remarks</span></span>  

 <span data-ttu-id="91ea6-145">Wenn die Richtlinie eines Felds nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="91ea6-145">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ea6-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91ea6-146">See also</span></span>

- [<span data-ttu-id="91ea6-147">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="91ea6-147">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="91ea6-148">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="91ea6-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="91ea6-149">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="91ea6-149">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
