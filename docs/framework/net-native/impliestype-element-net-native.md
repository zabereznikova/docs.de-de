---
title: <ImpliesType>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
ms.openlocfilehash: 57f4208233cd5e8544b4f1c254e3b0e0eaacd508
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181016"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="e1a8b-102">\<ImpliesType>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="e1a8b-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="e1a8b-103">Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1a8b-104">Syntax</span></span>  
  
```xml
<ImpliesType Name="type_name"  
             Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1a8b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1a8b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e1a8b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1a8b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1a8b-107">Attributes</span></span>  
  
|<span data-ttu-id="e1a8b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e1a8b-108">Attribute</span></span>|<span data-ttu-id="e1a8b-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="e1a8b-109">Attribute type</span></span>|<span data-ttu-id="e1a8b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1a8b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="e1a8b-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="e1a8b-111">General</span></span>|<span data-ttu-id="e1a8b-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-112">Required attribute.</span></span> <span data-ttu-id="e1a8b-113">Gibt den Namen des Typs an</span><span class="sxs-lookup"><span data-stu-id="e1a8b-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="e1a8b-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-114">Reflection</span></span>|<span data-ttu-id="e1a8b-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-115">Optional attribute.</span></span> <span data-ttu-id="e1a8b-116">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="e1a8b-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-117">Reflection</span></span>|<span data-ttu-id="e1a8b-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-118">Optional attribute.</span></span> <span data-ttu-id="e1a8b-119">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="e1a8b-120">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-120">Reflection</span></span>|<span data-ttu-id="e1a8b-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-121">Optional attribute.</span></span> <span data-ttu-id="e1a8b-122">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="e1a8b-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-123">Serialization</span></span>|<span data-ttu-id="e1a8b-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-124">Optional attribute.</span></span> <span data-ttu-id="e1a8b-125">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="e1a8b-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-126">Serialization</span></span>|<span data-ttu-id="e1a8b-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-127">Optional attribute.</span></span> <span data-ttu-id="e1a8b-128">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="e1a8b-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-129">Serialization</span></span>|<span data-ttu-id="e1a8b-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-130">Optional attribute.</span></span> <span data-ttu-id="e1a8b-131">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="e1a8b-132">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-132">Serialization</span></span>|<span data-ttu-id="e1a8b-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-133">Optional attribute.</span></span> <span data-ttu-id="e1a8b-134">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="e1a8b-135">Interop</span><span class="sxs-lookup"><span data-stu-id="e1a8b-135">Interop</span></span>|<span data-ttu-id="e1a8b-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-136">Optional attribute.</span></span> <span data-ttu-id="e1a8b-137">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="e1a8b-138">Interop</span><span class="sxs-lookup"><span data-stu-id="e1a8b-138">Interop</span></span>|<span data-ttu-id="e1a8b-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-139">Optional attribute.</span></span> <span data-ttu-id="e1a8b-140">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="e1a8b-141">Interop</span><span class="sxs-lookup"><span data-stu-id="e1a8b-141">Interop</span></span>|<span data-ttu-id="e1a8b-142">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-142">Optional attribute.</span></span> <span data-ttu-id="e1a8b-143">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="e1a8b-144">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="e1a8b-144">Name attribute</span></span>  
  
|<span data-ttu-id="e1a8b-145">Wert</span><span class="sxs-lookup"><span data-stu-id="e1a8b-145">Value</span></span>|<span data-ttu-id="e1a8b-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1a8b-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1a8b-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="e1a8b-147">*type_name*</span></span>|<span data-ttu-id="e1a8b-148">Der Typname.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-148">The type name.</span></span> <span data-ttu-id="e1a8b-149">Wenn sich der von diesem `<ImpliesType>`-Element dargestellte Typ im selben Namespace wie das enthaltende `<Type>`-Element befindet, kann *type_name* den Namen des Typs ohne den Namespace umfassen.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="e1a8b-150">Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="e1a8b-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="e1a8b-151">All other attributes</span></span>  
  
|<span data-ttu-id="e1a8b-152">Wert</span><span class="sxs-lookup"><span data-stu-id="e1a8b-152">Value</span></span>|<span data-ttu-id="e1a8b-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1a8b-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1a8b-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="e1a8b-154">*policy_setting*</span></span>|<span data-ttu-id="e1a8b-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="e1a8b-156">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="e1a8b-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e1a8b-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1a8b-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1a8b-158">Child Elements</span></span>  
 <span data-ttu-id="e1a8b-159">Keine</span><span class="sxs-lookup"><span data-stu-id="e1a8b-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1a8b-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1a8b-160">Parent Elements</span></span>  
  
|<span data-ttu-id="e1a8b-161">Element</span><span class="sxs-lookup"><span data-stu-id="e1a8b-161">Element</span></span>|<span data-ttu-id="e1a8b-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e1a8b-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="e1a8b-163">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-163">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="e1a8b-164">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-164">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="e1a8b-165">Wendet die Reflektionsrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-165">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1a8b-166">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e1a8b-166">Remarks</span></span>  
 <span data-ttu-id="e1a8b-167">Das `<ImpliesType>`-Element dient in erster Linie der Verwendung durch Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-167">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="e1a8b-168">Es wird in folgendem Szenario eingesetzt:</span><span class="sxs-lookup"><span data-stu-id="e1a8b-168">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="e1a8b-169">Wenn eine Routine einen Typ reflektieren muss, muss sie unbedingt einen zweiten Typ reflektieren.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-169">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="e1a8b-170">Die Metadaten für die implizite Instanziierung des zweiten Typs ist andernfalls nicht verfügbar, da die statische Analyse nicht angibt, dass dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-170">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="e1a8b-171">In den meisten Fällen sind die beiden Typen generische Instanziierungen mit freigegebenen Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-171">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="e1a8b-172">Das `<ImpliesType>`-Element wurde unter der Annahme definiert, dass die Notwendigkeit einer Reflektion für den Typ, der von seinem übergeordneten Element angegebenen wird, eine Notwendigkeit einer Reflektion für den Typ impliziert, der vom `<ImpliesType>`-Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-172">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="e1a8b-173">Die folgenden Reflektionsrichtlinien gelten z. B. für zwei Typen – `Explicit<T>` und `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-173">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="e1a8b-174">Diese Anweisung hat nur dann Auswirkungen, wenn eine Instanziierung von `Explicit` über eine definierte `Dynamic`-Richtlinieneinstellung verfügt.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-174">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="e1a8b-175">Wenn das z. B. für `Explicit<Int32>` der Fall ist, wird `Implicit<Int32>` mit den öffentlichen Membern instanziiert, und ihre Metadaten werden für die dynamische Programmierung verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-175">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="e1a8b-176">Folgendes ist ein praktisches Beispiel, das für mindestens ein Serialisierungsprogramm gilt.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-176">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="e1a8b-177">Die-Direktiven erfassen die Anforderung, dass die Reflektion von etwas, das als etwas typisiert ist, auch die Reflektion `IList<` *something* `>` des entsprechenden `List<` *Something* `>` -Typs erfordert, ohne dass eine anwendungsspezifische Anmerkung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-177">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="e1a8b-178">Das `<ImpliesType>`-Element kann auch innerhalb eines `<Method>`-Element angezeigt werden, da in einigen Fällen das Instanziieren einer generischen Methode die Reflektion einer Typinstanziierung impliziert.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-178">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="e1a8b-179">Stellen Sie sich zum Beispiel eine generische Methode `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` vor, auf die eine angegebene Bibliothek zusammen mit den zugehörigen <xref:System.Collections.Generic.List%601>- und <xref:System.Array>-Typen dynamisch zugreift.</span><span class="sxs-lookup"><span data-stu-id="e1a8b-179">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="e1a8b-180">Dies kann folgendermaßen ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="e1a8b-180">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public" />  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1a8b-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1a8b-181">See also</span></span>

- [<span data-ttu-id="e1a8b-182">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="e1a8b-182">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="e1a8b-183">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-183">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="e1a8b-184">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="e1a8b-184">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
