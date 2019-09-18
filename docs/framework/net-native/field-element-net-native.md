---
title: <Field>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dfb6a07f9733ab1a01a1ce9917c6a4bb4ce793b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049779"
---
# <a name="field-element-net-native"></a><span data-ttu-id="12e28-102">\<Feld > Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="12e28-102">\<Field> Element (.NET Native)</span></span>
<span data-ttu-id="12e28-103">Wendet eine Laufzeitreflektionrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="12e28-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12e28-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12e28-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12e28-105">Attributes and Elements</span></span>  
 <span data-ttu-id="12e28-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12e28-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12e28-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="12e28-107">Attributes</span></span>  
  
|<span data-ttu-id="12e28-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="12e28-108">Attribute</span></span>|<span data-ttu-id="12e28-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="12e28-109">Attribute type</span></span>|<span data-ttu-id="12e28-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12e28-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="12e28-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="12e28-111">General</span></span>|<span data-ttu-id="12e28-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="12e28-112">Required attribute.</span></span> <span data-ttu-id="12e28-113">Gibt den Feldnamen an.</span><span class="sxs-lookup"><span data-stu-id="12e28-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="12e28-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="12e28-114">Reflection</span></span>|<span data-ttu-id="12e28-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="12e28-115">Optional attribute.</span></span> <span data-ttu-id="12e28-116">Steuert das Abfragen nach Informationen über das Feld oder das Auflisten des Felds, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="12e28-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="12e28-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="12e28-117">Reflection</span></span>|<span data-ttu-id="12e28-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="12e28-118">Optional attribute.</span></span> <span data-ttu-id="12e28-119">Steuert den Laufzeitzugriff auf das Feld, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="12e28-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="12e28-120">Diese Richtlinie stellt sicher, dass ein Feld zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="12e28-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="12e28-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="12e28-121">Serialization</span></span>|<span data-ttu-id="12e28-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="12e28-122">Optional attribute.</span></span> <span data-ttu-id="12e28-123">Steuert den Laufzeitzugriff auf ein Feld, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="12e28-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="12e28-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="12e28-124">Name attribute</span></span>  
  
|<span data-ttu-id="12e28-125">Wert</span><span class="sxs-lookup"><span data-stu-id="12e28-125">Value</span></span>|<span data-ttu-id="12e28-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12e28-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="12e28-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="12e28-127">*method_name*</span></span>|<span data-ttu-id="12e28-128">Der Feldname.</span><span class="sxs-lookup"><span data-stu-id="12e28-128">The field name.</span></span> <span data-ttu-id="12e28-129">Der Typ des Felds wird durch das übergeordnete [\<Type>](type-element-net-native.md)- oder [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="12e28-129">The type of the field is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="12e28-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="12e28-130">All other attributes</span></span>  
  
|<span data-ttu-id="12e28-131">Wert</span><span class="sxs-lookup"><span data-stu-id="12e28-131">Value</span></span>|<span data-ttu-id="12e28-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12e28-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="12e28-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="12e28-133">*policy_setting*</span></span>|<span data-ttu-id="12e28-134">Die Einstellung, die auf diesen Richtlinientyp für das Feld angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="12e28-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="12e28-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="12e28-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="12e28-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="12e28-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12e28-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12e28-137">Child Elements</span></span>  
 <span data-ttu-id="12e28-138">Keine</span><span class="sxs-lookup"><span data-stu-id="12e28-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12e28-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12e28-139">Parent Elements</span></span>  
  
|<span data-ttu-id="12e28-140">Element</span><span class="sxs-lookup"><span data-stu-id="12e28-140">Element</span></span>|<span data-ttu-id="12e28-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12e28-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12e28-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="12e28-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="12e28-143">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="12e28-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="12e28-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="12e28-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="12e28-145">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="12e28-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12e28-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12e28-146">Remarks</span></span>  
 <span data-ttu-id="12e28-147">Wenn die Richtlinie eines Felds nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="12e28-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e28-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12e28-148">See also</span></span>

- [<span data-ttu-id="12e28-149">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="12e28-149">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="12e28-150">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="12e28-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="12e28-151">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="12e28-151">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
