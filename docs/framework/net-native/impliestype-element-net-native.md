---
title: <ImpliesType>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10fa3a0ac04038bb686311a4d86c99442c0fcf26
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049677"
---
# <a name="impliestype-element-net-native"></a><span data-ttu-id="53e6a-102">\<Impliestype-> Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="53e6a-102">\<ImpliesType> Element (.NET Native)</span></span>
<span data-ttu-id="53e6a-103">Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="53e6a-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53e6a-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53e6a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="53e6a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53e6a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="53e6a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53e6a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="53e6a-107">Attributes</span></span>  
  
|<span data-ttu-id="53e6a-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="53e6a-108">Attribute</span></span>|<span data-ttu-id="53e6a-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="53e6a-109">Attribute type</span></span>|<span data-ttu-id="53e6a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53e6a-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="53e6a-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="53e6a-111">General</span></span>|<span data-ttu-id="53e6a-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-112">Required attribute.</span></span> <span data-ttu-id="53e6a-113">Gibt den Typnamen an.</span><span class="sxs-lookup"><span data-stu-id="53e6a-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="53e6a-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="53e6a-114">Reflection</span></span>|<span data-ttu-id="53e6a-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-115">Optional attribute.</span></span> <span data-ttu-id="53e6a-116">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="53e6a-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="53e6a-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="53e6a-117">Reflection</span></span>|<span data-ttu-id="53e6a-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-118">Optional attribute.</span></span> <span data-ttu-id="53e6a-119">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="53e6a-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="53e6a-120">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="53e6a-120">Reflection</span></span>|<span data-ttu-id="53e6a-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-121">Optional attribute.</span></span> <span data-ttu-id="53e6a-122">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="53e6a-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="53e6a-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="53e6a-123">Serialization</span></span>|<span data-ttu-id="53e6a-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-124">Optional attribute.</span></span> <span data-ttu-id="53e6a-125">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="53e6a-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="53e6a-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="53e6a-126">Serialization</span></span>|<span data-ttu-id="53e6a-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-127">Optional attribute.</span></span> <span data-ttu-id="53e6a-128">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="53e6a-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="53e6a-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="53e6a-129">Serialization</span></span>|<span data-ttu-id="53e6a-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-130">Optional attribute.</span></span> <span data-ttu-id="53e6a-131">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="53e6a-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="53e6a-132">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="53e6a-132">Serialization</span></span>|<span data-ttu-id="53e6a-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-133">Optional attribute.</span></span> <span data-ttu-id="53e6a-134">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="53e6a-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="53e6a-135">Interop</span><span class="sxs-lookup"><span data-stu-id="53e6a-135">Interop</span></span>|<span data-ttu-id="53e6a-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-136">Optional attribute.</span></span> <span data-ttu-id="53e6a-137">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="53e6a-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="53e6a-138">Interop</span><span class="sxs-lookup"><span data-stu-id="53e6a-138">Interop</span></span>|<span data-ttu-id="53e6a-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-139">Optional attribute.</span></span> <span data-ttu-id="53e6a-140">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="53e6a-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="53e6a-141">Interop</span><span class="sxs-lookup"><span data-stu-id="53e6a-141">Interop</span></span>|<span data-ttu-id="53e6a-142">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="53e6a-142">Optional attribute.</span></span> <span data-ttu-id="53e6a-143">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="53e6a-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="53e6a-144">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="53e6a-144">Name attribute</span></span>  
  
|<span data-ttu-id="53e6a-145">Wert</span><span class="sxs-lookup"><span data-stu-id="53e6a-145">Value</span></span>|<span data-ttu-id="53e6a-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53e6a-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53e6a-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="53e6a-147">*type_name*</span></span>|<span data-ttu-id="53e6a-148">Der Typname.</span><span class="sxs-lookup"><span data-stu-id="53e6a-148">The type name.</span></span> <span data-ttu-id="53e6a-149">Wenn sich der von diesem `<ImpliesType>`-Element dargestellte Typ im selben Namespace wie das enthaltende `<Type>`-Element befindet, kann *type_name* den Namen des Typs ohne den Namespace umfassen.</span><span class="sxs-lookup"><span data-stu-id="53e6a-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="53e6a-150">Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="53e6a-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="53e6a-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="53e6a-151">All other attributes</span></span>  
  
|<span data-ttu-id="53e6a-152">Wert</span><span class="sxs-lookup"><span data-stu-id="53e6a-152">Value</span></span>|<span data-ttu-id="53e6a-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53e6a-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53e6a-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="53e6a-154">*policy_setting*</span></span>|<span data-ttu-id="53e6a-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="53e6a-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="53e6a-156">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="53e6a-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="53e6a-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="53e6a-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53e6a-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53e6a-158">Child Elements</span></span>  
 <span data-ttu-id="53e6a-159">Keine</span><span class="sxs-lookup"><span data-stu-id="53e6a-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53e6a-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="53e6a-160">Parent Elements</span></span>  
  
|<span data-ttu-id="53e6a-161">Element</span><span class="sxs-lookup"><span data-stu-id="53e6a-161">Element</span></span>|<span data-ttu-id="53e6a-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53e6a-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53e6a-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="53e6a-163">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="53e6a-164">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="53e6a-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="53e6a-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="53e6a-165">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="53e6a-166">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="53e6a-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="53e6a-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="53e6a-167">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="53e6a-168">Wendet die Reflektionsrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="53e6a-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53e6a-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53e6a-169">Remarks</span></span>  
 <span data-ttu-id="53e6a-170">Das `<ImpliesType>`-Element dient in erster Linie der Verwendung durch Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="53e6a-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="53e6a-171">Es wird in folgendem Szenario eingesetzt:</span><span class="sxs-lookup"><span data-stu-id="53e6a-171">It addresses the following scenario:</span></span>  
  
- <span data-ttu-id="53e6a-172">Wenn eine Routine einen Typ reflektieren muss, muss sie unbedingt einen zweiten Typ reflektieren.</span><span class="sxs-lookup"><span data-stu-id="53e6a-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
- <span data-ttu-id="53e6a-173">Die Metadaten für die implizite Instanziierung des zweiten Typs ist andernfalls nicht verfügbar, da die statische Analyse nicht angibt, dass dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="53e6a-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="53e6a-174">In den meisten Fällen sind die beiden Typen generische Instanziierungen mit freigegebenen Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="53e6a-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="53e6a-175">Das `<ImpliesType>`-Element wurde unter der Annahme definiert, dass die Notwendigkeit einer Reflektion für den Typ, der von seinem übergeordneten Element angegebenen wird, eine Notwendigkeit einer Reflektion für den Typ impliziert, der vom `<ImpliesType>`-Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="53e6a-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="53e6a-176">Die folgenden Reflektionsrichtlinien gelten z. B. für zwei Typen – `Explicit<T>` und `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="53e6a-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="53e6a-177">Diese Anweisung hat nur dann Auswirkungen, wenn eine Instanziierung von `Explicit` über eine definierte `Dynamic`-Richtlinieneinstellung verfügt.</span><span class="sxs-lookup"><span data-stu-id="53e6a-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="53e6a-178">Wenn das z. B. für `Explicit<Int32>` der Fall ist, wird `Implicit<Int32>` mit den öffentlichen Membern instanziiert, und ihre Metadaten werden für die dynamische Programmierung verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="53e6a-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="53e6a-179">Folgendes ist ein praktisches Beispiel, das für mindestens ein Serialisierungsprogramm gilt.</span><span class="sxs-lookup"><span data-stu-id="53e6a-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="53e6a-180">Die Anweisungen erkennen den Bedarf, dass die Reflektion von etwas, das als `IList<`*something*`>` typisiert ist, auch die Reflektion des entsprechenden `List<`*something*`>`-Typs umfasst, ohne dass anwendungsbasierte Anmerkungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="53e6a-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="53e6a-181">Das `<ImpliesType>`-Element kann auch innerhalb eines `<Method>`-Element angezeigt werden, da in einigen Fällen das Instanziieren einer generischen Methode die Reflektion einer Typinstanziierung impliziert.</span><span class="sxs-lookup"><span data-stu-id="53e6a-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="53e6a-182">Stellen Sie sich zum Beispiel eine generische `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` Methode vor, auf die eine bestimmte Bibliothek zusammen mit den <xref:System.Collections.Generic.List%601> zugehörigen <xref:System.Array> -und-Typen dynamisch zugreift.</span><span class="sxs-lookup"><span data-stu-id="53e6a-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string spelling, T defaultValue)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="53e6a-183">Dies kann folgendermaßen ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="53e6a-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public">  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53e6a-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53e6a-184">See also</span></span>

- [<span data-ttu-id="53e6a-185">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="53e6a-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="53e6a-186">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="53e6a-186">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="53e6a-187">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="53e6a-187">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
