---
title: '&lt;Feld&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b713eefa4f23aec34b5f55c0c3457381f54ef931
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394620"
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="33e76-102">&lt;Feld&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="33e76-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="33e76-103">Wendet eine Laufzeitreflektionrichtlinie auf ein Feld an.</span><span class="sxs-lookup"><span data-stu-id="33e76-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33e76-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33e76-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="33e76-105">Attributes and Elements</span></span>  
 <span data-ttu-id="33e76-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="33e76-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33e76-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="33e76-107">Attributes</span></span>  
  
|<span data-ttu-id="33e76-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="33e76-108">Attribute</span></span>|<span data-ttu-id="33e76-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="33e76-109">Attribute type</span></span>|<span data-ttu-id="33e76-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e76-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="33e76-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="33e76-111">General</span></span>|<span data-ttu-id="33e76-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="33e76-112">Required attribute.</span></span> <span data-ttu-id="33e76-113">Gibt den Feldnamen an.</span><span class="sxs-lookup"><span data-stu-id="33e76-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="33e76-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="33e76-114">Reflection</span></span>|<span data-ttu-id="33e76-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="33e76-115">Optional attribute.</span></span> <span data-ttu-id="33e76-116">Steuert das Abfragen nach Informationen über das Feld oder das Auflisten des Felds, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="33e76-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="33e76-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="33e76-117">Reflection</span></span>|<span data-ttu-id="33e76-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="33e76-118">Optional attribute.</span></span> <span data-ttu-id="33e76-119">Steuert den Laufzeitzugriff auf das Feld, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="33e76-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="33e76-120">Diese Richtlinie stellt sicher, dass ein Feld zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="33e76-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="33e76-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="33e76-121">Serialization</span></span>|<span data-ttu-id="33e76-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="33e76-122">Optional attribute.</span></span> <span data-ttu-id="33e76-123">Steuert den Laufzeitzugriff auf ein Feld, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="33e76-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="33e76-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="33e76-124">Name attribute</span></span>  
  
|<span data-ttu-id="33e76-125">Wert</span><span class="sxs-lookup"><span data-stu-id="33e76-125">Value</span></span>|<span data-ttu-id="33e76-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e76-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33e76-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="33e76-127">*method_name*</span></span>|<span data-ttu-id="33e76-128">Der Feldname.</span><span class="sxs-lookup"><span data-stu-id="33e76-128">The field name.</span></span> <span data-ttu-id="33e76-129">Der Typ des Felds wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="33e76-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="33e76-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="33e76-130">All other attributes</span></span>  
  
|<span data-ttu-id="33e76-131">Wert</span><span class="sxs-lookup"><span data-stu-id="33e76-131">Value</span></span>|<span data-ttu-id="33e76-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e76-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33e76-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="33e76-133">*policy_setting*</span></span>|<span data-ttu-id="33e76-134">Die Einstellung, die auf diesen Richtlinientyp für das Feld angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="33e76-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="33e76-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="33e76-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="33e76-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="33e76-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33e76-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33e76-137">Child Elements</span></span>  
 <span data-ttu-id="33e76-138">Keine</span><span class="sxs-lookup"><span data-stu-id="33e76-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33e76-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="33e76-139">Parent Elements</span></span>  
  
|<span data-ttu-id="33e76-140">Element</span><span class="sxs-lookup"><span data-stu-id="33e76-140">Element</span></span>|<span data-ttu-id="33e76-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e76-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33e76-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="33e76-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="33e76-143">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="33e76-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="33e76-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="33e76-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="33e76-145">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="33e76-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33e76-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33e76-146">Remarks</span></span>  
 <span data-ttu-id="33e76-147">Wenn die Richtlinie eines Felds nicht explizit definiert ist, erbt es die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="33e76-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e76-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33e76-148">See Also</span></span>  
 [<span data-ttu-id="33e76-149">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="33e76-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="33e76-150">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="33e76-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="33e76-151">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="33e76-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
