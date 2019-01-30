---
title: <AttributeImplies> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 82db7193-a860-418b-84fc-fff2fdf2e025
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be5412e323b1c4930d7e17d09faa174885611884
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254976"
---
# <a name="attributeimplies-element-net-native"></a><span data-ttu-id="b3f21-102">\<AttributeImplies > (Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="b3f21-102">\<AttributeImplies> Element (.NET Native)</span></span>
<span data-ttu-id="b3f21-103">Definiert die Richtlinie für Codeelemente, auf die das enthaltende Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3f21-103">Defines policy for code elements the containing attribute is applied to.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3f21-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3f21-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b3f21-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b3f21-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3f21-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3f21-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3f21-107">Attributes</span></span>  
  
|<span data-ttu-id="b3f21-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="b3f21-108">Attribute</span></span>|<span data-ttu-id="b3f21-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="b3f21-109">Attribute type</span></span>|<span data-ttu-id="b3f21-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3f21-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="b3f21-111">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b3f21-111">Reflection</span></span>|<span data-ttu-id="b3f21-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-112">Optional attribute.</span></span> <span data-ttu-id="b3f21-113">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b3f21-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b3f21-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b3f21-114">Reflection</span></span>|<span data-ttu-id="b3f21-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-115">Optional attribute.</span></span> <span data-ttu-id="b3f21-116">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="b3f21-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b3f21-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b3f21-117">Reflection</span></span>|<span data-ttu-id="b3f21-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-118">Optional attribute.</span></span> <span data-ttu-id="b3f21-119">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b3f21-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b3f21-120">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b3f21-120">Serialization</span></span>|<span data-ttu-id="b3f21-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-121">Optional attribute.</span></span> <span data-ttu-id="b3f21-122">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b3f21-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b3f21-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b3f21-123">Serialization</span></span>|<span data-ttu-id="b3f21-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-124">Optional attribute.</span></span> <span data-ttu-id="b3f21-125">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3f21-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b3f21-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b3f21-126">Serialization</span></span>|<span data-ttu-id="b3f21-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-127">Optional attribute.</span></span> <span data-ttu-id="b3f21-128">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3f21-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b3f21-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b3f21-129">Serialization</span></span>|<span data-ttu-id="b3f21-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-130">Optional attribute.</span></span> <span data-ttu-id="b3f21-131">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3f21-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b3f21-132">Interop</span><span class="sxs-lookup"><span data-stu-id="b3f21-132">Interop</span></span>|<span data-ttu-id="b3f21-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-133">Optional attribute.</span></span> <span data-ttu-id="b3f21-134">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="b3f21-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b3f21-135">Interop</span><span class="sxs-lookup"><span data-stu-id="b3f21-135">Interop</span></span>|<span data-ttu-id="b3f21-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-136">Optional attribute.</span></span> <span data-ttu-id="b3f21-137">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b3f21-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b3f21-138">Interop</span><span class="sxs-lookup"><span data-stu-id="b3f21-138">Interop</span></span>|<span data-ttu-id="b3f21-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b3f21-139">Optional attribute.</span></span> <span data-ttu-id="b3f21-140">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b3f21-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="b3f21-141">Alle Attribute</span><span class="sxs-lookup"><span data-stu-id="b3f21-141">All attributes</span></span>  
  
|<span data-ttu-id="b3f21-142">Wert</span><span class="sxs-lookup"><span data-stu-id="b3f21-142">Value</span></span>|<span data-ttu-id="b3f21-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3f21-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3f21-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b3f21-144">*policy_setting*</span></span>|<span data-ttu-id="b3f21-145">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b3f21-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="b3f21-146">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="b3f21-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b3f21-147">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b3f21-147">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3f21-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3f21-148">Child Elements</span></span>  
 <span data-ttu-id="b3f21-149">Keine</span><span class="sxs-lookup"><span data-stu-id="b3f21-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3f21-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3f21-150">Parent Elements</span></span>  
  
|<span data-ttu-id="b3f21-151">Element</span><span class="sxs-lookup"><span data-stu-id="b3f21-151">Element</span></span>|<span data-ttu-id="b3f21-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3f21-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3f21-153">\<Type></span><span class="sxs-lookup"><span data-stu-id="b3f21-153">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="b3f21-154">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="b3f21-154">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3f21-155">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3f21-155">Remarks</span></span>  
 <span data-ttu-id="b3f21-156">Das `<AttributeImplies>`-Element wird verwendet, wenn der enthaltende Typ ein Attribut ist (d. h. eine von <xref:System.Attribute?displayProperty=nameWithType> abgeleitete Klasse).</span><span class="sxs-lookup"><span data-stu-id="b3f21-156">The `<AttributeImplies>` element is used if its containing type is an attribute (that is, a class derived from <xref:System.Attribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="b3f21-157">Wenn das Attribut auf ein bestimmtes Programmelement angewendet wird, gilt die vom `<AttributeImplies>`-Element definierte Richtlinie für dieses Programmelement.</span><span class="sxs-lookup"><span data-stu-id="b3f21-157">If the attribute is applied to a particular program element, the policy defined by the `<AttributeImplies>` element applies to that program element.</span></span>  
  
 <span data-ttu-id="b3f21-158">Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional, obwohl mindestens eines vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="b3f21-158">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f21-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3f21-159">See also</span></span>
- [<span data-ttu-id="b3f21-160">\<Type >-Element</span><span class="sxs-lookup"><span data-stu-id="b3f21-160">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="b3f21-161">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="b3f21-161">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b3f21-162">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b3f21-162">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="b3f21-163">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b3f21-163">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
