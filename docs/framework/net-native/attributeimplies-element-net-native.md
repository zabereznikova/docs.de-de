---
title: <AttributeImplies>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
ms.openlocfilehash: 2ab1fdc71bc43f61f69a0d9b7bea7acb35e14ea5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181062"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="769e2-102">\<AttributeImplies>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="769e2-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="769e2-103">Definiert die Richtlinie für Codeelemente, auf die das enthaltende Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="769e2-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="769e2-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="769e2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="769e2-105">Attributes and Elements</span></span>  
 <span data-ttu-id="769e2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="769e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="769e2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="769e2-107">Attributes</span></span>  
  
|<span data-ttu-id="769e2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="769e2-108">Attribute</span></span>|<span data-ttu-id="769e2-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="769e2-109">Attribute type</span></span>|<span data-ttu-id="769e2-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="769e2-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="769e2-111">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="769e2-111">Reflection</span></span>|<span data-ttu-id="769e2-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-112">Optional attribute.</span></span> <span data-ttu-id="769e2-113">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="769e2-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="769e2-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="769e2-114">Reflection</span></span>|<span data-ttu-id="769e2-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-115">Optional attribute.</span></span> <span data-ttu-id="769e2-116">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="769e2-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="769e2-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="769e2-117">Reflection</span></span>|<span data-ttu-id="769e2-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-118">Optional attribute.</span></span> <span data-ttu-id="769e2-119">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="769e2-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="769e2-120">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="769e2-120">Serialization</span></span>|<span data-ttu-id="769e2-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-121">Optional attribute.</span></span> <span data-ttu-id="769e2-122">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="769e2-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="769e2-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="769e2-123">Serialization</span></span>|<span data-ttu-id="769e2-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-124">Optional attribute.</span></span> <span data-ttu-id="769e2-125">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="769e2-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="769e2-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="769e2-126">Serialization</span></span>|<span data-ttu-id="769e2-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-127">Optional attribute.</span></span> <span data-ttu-id="769e2-128">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="769e2-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="769e2-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="769e2-129">Serialization</span></span>|<span data-ttu-id="769e2-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-130">Optional attribute.</span></span> <span data-ttu-id="769e2-131">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="769e2-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="769e2-132">Interop</span><span class="sxs-lookup"><span data-stu-id="769e2-132">Interop</span></span>|<span data-ttu-id="769e2-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-133">Optional attribute.</span></span> <span data-ttu-id="769e2-134">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="769e2-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="769e2-135">Interop</span><span class="sxs-lookup"><span data-stu-id="769e2-135">Interop</span></span>|<span data-ttu-id="769e2-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-136">Optional attribute.</span></span> <span data-ttu-id="769e2-137">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="769e2-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="769e2-138">Interop</span><span class="sxs-lookup"><span data-stu-id="769e2-138">Interop</span></span>|<span data-ttu-id="769e2-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="769e2-139">Optional attribute.</span></span> <span data-ttu-id="769e2-140">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="769e2-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="769e2-141">Alle Attribute</span><span class="sxs-lookup"><span data-stu-id="769e2-141">All attributes</span></span>  
  
|<span data-ttu-id="769e2-142">Wert</span><span class="sxs-lookup"><span data-stu-id="769e2-142">Value</span></span>|<span data-ttu-id="769e2-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="769e2-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="769e2-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="769e2-144">*policy_setting*</span></span>|<span data-ttu-id="769e2-145">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="769e2-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="769e2-146">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="769e2-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="769e2-147">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="769e2-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="769e2-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="769e2-148">Child Elements</span></span>  
 <span data-ttu-id="769e2-149">Keine</span><span class="sxs-lookup"><span data-stu-id="769e2-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="769e2-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="769e2-150">Parent Elements</span></span>  
  
|<span data-ttu-id="769e2-151">Element</span><span class="sxs-lookup"><span data-stu-id="769e2-151">Element</span></span>|<span data-ttu-id="769e2-152">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="769e2-152">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="769e2-153">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="769e2-153">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="769e2-154">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="769e2-154">Remarks</span></span>  
 <span data-ttu-id="769e2-155">Das `<AttributeImplies>`-Element wird verwendet, wenn der enthaltende Typ ein Attribut ist (d. h. eine von <xref:System.Attribute?displayProperty=nameWithType> abgeleitete Klasse).</span><span class="sxs-lookup"><span data-stu-id="769e2-155">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="769e2-156">Wenn das Attribut auf ein bestimmtes Programmelement angewendet wird, gilt die vom `<AttributeImplies>`-Element definierte Richtlinie für dieses Programmelement.</span><span class="sxs-lookup"><span data-stu-id="769e2-156">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="769e2-157">Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional, obwohl mindestens eines vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="769e2-157">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769e2-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="769e2-158">See also</span></span>

- [<span data-ttu-id="769e2-159">\<Type>Gewisses</span><span class="sxs-lookup"><span data-stu-id="769e2-159">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="769e2-160">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="769e2-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="769e2-161">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="769e2-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="769e2-162">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="769e2-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
