---
title: <AttributeImplies>Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181062"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="638c4-102">\<AttributeImplies> Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="638c4-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="638c4-103">Definiert die Richtlinie für Codeelemente, auf die das enthaltende Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="638c4-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="638c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="638c4-104">Syntax</span></span>  
  
```xml  
<AttributeImplies Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"
                  DataContractSerializer="policy_setting"  
                  DataContractJsonSerializer="policy_setting"  
                  XmlSerializer="policy_setting"  
                  MarshalObject="policy_setting"  
                  MarshalDelegate="policy_setting"  
                  MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="638c4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="638c4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="638c4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="638c4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="638c4-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="638c4-107">Attributes</span></span>  
  
|<span data-ttu-id="638c4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="638c4-108">Attribute</span></span>|<span data-ttu-id="638c4-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="638c4-109">Attribute type</span></span>|<span data-ttu-id="638c4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="638c4-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="638c4-111">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="638c4-111">Reflection</span></span>|<span data-ttu-id="638c4-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-112">Optional attribute.</span></span> <span data-ttu-id="638c4-113">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="638c4-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="638c4-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="638c4-114">Reflection</span></span>|<span data-ttu-id="638c4-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-115">Optional attribute.</span></span> <span data-ttu-id="638c4-116">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="638c4-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="638c4-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="638c4-117">Reflection</span></span>|<span data-ttu-id="638c4-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-118">Optional attribute.</span></span> <span data-ttu-id="638c4-119">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="638c4-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="638c4-120">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="638c4-120">Serialization</span></span>|<span data-ttu-id="638c4-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-121">Optional attribute.</span></span> <span data-ttu-id="638c4-122">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="638c4-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="638c4-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="638c4-123">Serialization</span></span>|<span data-ttu-id="638c4-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-124">Optional attribute.</span></span> <span data-ttu-id="638c4-125">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="638c4-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="638c4-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="638c4-126">Serialization</span></span>|<span data-ttu-id="638c4-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-127">Optional attribute.</span></span> <span data-ttu-id="638c4-128">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="638c4-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="638c4-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="638c4-129">Serialization</span></span>|<span data-ttu-id="638c4-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-130">Optional attribute.</span></span> <span data-ttu-id="638c4-131">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="638c4-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="638c4-132">Interop</span><span class="sxs-lookup"><span data-stu-id="638c4-132">Interop</span></span>|<span data-ttu-id="638c4-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-133">Optional attribute.</span></span> <span data-ttu-id="638c4-134">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="638c4-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="638c4-135">Interop</span><span class="sxs-lookup"><span data-stu-id="638c4-135">Interop</span></span>|<span data-ttu-id="638c4-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-136">Optional attribute.</span></span> <span data-ttu-id="638c4-137">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="638c4-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="638c4-138">Interop</span><span class="sxs-lookup"><span data-stu-id="638c4-138">Interop</span></span>|<span data-ttu-id="638c4-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="638c4-139">Optional attribute.</span></span> <span data-ttu-id="638c4-140">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="638c4-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="638c4-141">Alle Attribute</span><span class="sxs-lookup"><span data-stu-id="638c4-141">All attributes</span></span>  
  
|<span data-ttu-id="638c4-142">value</span><span class="sxs-lookup"><span data-stu-id="638c4-142">Value</span></span>|<span data-ttu-id="638c4-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="638c4-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="638c4-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="638c4-144">*policy_setting*</span></span>|<span data-ttu-id="638c4-145">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="638c4-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="638c4-146">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="638c4-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="638c4-147">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="638c4-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="638c4-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="638c4-148">Child Elements</span></span>  
 <span data-ttu-id="638c4-149">Keine.</span><span class="sxs-lookup"><span data-stu-id="638c4-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="638c4-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="638c4-150">Parent Elements</span></span>  
  
|<span data-ttu-id="638c4-151">Element</span><span class="sxs-lookup"><span data-stu-id="638c4-151">Element</span></span>|<span data-ttu-id="638c4-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="638c4-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="638c4-153">\<Typ></span><span class="sxs-lookup"><span data-stu-id="638c4-153">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="638c4-154">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="638c4-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="638c4-155">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="638c4-155">Remarks</span></span>  
 <span data-ttu-id="638c4-156">Das `<AttributeImplies>`-Element wird verwendet, wenn der enthaltende Typ ein Attribut ist (d. h. eine von <xref:System.Attribute?displayProperty=nameWithType> abgeleitete Klasse).</span><span class="sxs-lookup"><span data-stu-id="638c4-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="638c4-157">Wenn das Attribut auf ein bestimmtes Programmelement angewendet wird, gilt die vom `<AttributeImplies>`-Element definierte Richtlinie für dieses Programmelement.</span><span class="sxs-lookup"><span data-stu-id="638c4-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="638c4-158">Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional, obwohl mindestens eines vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="638c4-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638c4-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="638c4-159">See also</span></span>

- [<span data-ttu-id="638c4-160">\<Typ> Element</span><span class="sxs-lookup"><span data-stu-id="638c4-160">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="638c4-161">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="638c4-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="638c4-162">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="638c4-162">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="638c4-163">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="638c4-163">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
