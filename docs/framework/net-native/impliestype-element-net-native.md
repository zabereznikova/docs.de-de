---
title: '&lt;ImpliesType&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90e079b593ed124da79f5f87b5189d199bc4572a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltimpliestypegt-element-net-native"></a><span data-ttu-id="0b5d0-102">&lt;ImpliesType&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="0b5d0-102">&lt;ImpliesType&gt; Element (.NET Native)</span></span>
<span data-ttu-id="0b5d0-103">Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-103">Applies policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b5d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b5d0-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b5d0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b5d0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0b5d0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b5d0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b5d0-107">Attributes</span></span>  
  
|<span data-ttu-id="0b5d0-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="0b5d0-108">Attribute</span></span>|<span data-ttu-id="0b5d0-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="0b5d0-109">Attribute type</span></span>|<span data-ttu-id="0b5d0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="0b5d0-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="0b5d0-111">General</span></span>|<span data-ttu-id="0b5d0-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-112">Required attribute.</span></span> <span data-ttu-id="0b5d0-113">Gibt den Typnamen an.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-113">Specifies the type name.</span></span>|  
|`Activate`|<span data-ttu-id="0b5d0-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-114">Reflection</span></span>|<span data-ttu-id="0b5d0-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-115">Optional attribute.</span></span> <span data-ttu-id="0b5d0-116">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-116">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="0b5d0-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-117">Reflection</span></span>|<span data-ttu-id="0b5d0-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-118">Optional attribute.</span></span> <span data-ttu-id="0b5d0-119">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-119">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="0b5d0-120">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-120">Reflection</span></span>|<span data-ttu-id="0b5d0-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-121">Optional attribute.</span></span> <span data-ttu-id="0b5d0-122">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-122">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="0b5d0-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-123">Serialization</span></span>|<span data-ttu-id="0b5d0-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-124">Optional attribute.</span></span> <span data-ttu-id="0b5d0-125">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-125">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="0b5d0-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-126">Serialization</span></span>|<span data-ttu-id="0b5d0-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-127">Optional attribute.</span></span> <span data-ttu-id="0b5d0-128">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-128">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="0b5d0-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-129">Serialization</span></span>|<span data-ttu-id="0b5d0-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-130">Optional attribute.</span></span> <span data-ttu-id="0b5d0-131">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-131">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="0b5d0-132">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-132">Serialization</span></span>|<span data-ttu-id="0b5d0-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-133">Optional attribute.</span></span> <span data-ttu-id="0b5d0-134">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-134">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="0b5d0-135">Interop</span><span class="sxs-lookup"><span data-stu-id="0b5d0-135">Interop</span></span>|<span data-ttu-id="0b5d0-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-136">Optional attribute.</span></span> <span data-ttu-id="0b5d0-137">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-137">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="0b5d0-138">Interop</span><span class="sxs-lookup"><span data-stu-id="0b5d0-138">Interop</span></span>|<span data-ttu-id="0b5d0-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-139">Optional attribute.</span></span> <span data-ttu-id="0b5d0-140">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-140">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="0b5d0-141">Interop</span><span class="sxs-lookup"><span data-stu-id="0b5d0-141">Interop</span></span>|<span data-ttu-id="0b5d0-142">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-142">Optional attribute.</span></span> <span data-ttu-id="0b5d0-143">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-143">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="0b5d0-144">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="0b5d0-144">Name attribute</span></span>  
  
|<span data-ttu-id="0b5d0-145">Wert</span><span class="sxs-lookup"><span data-stu-id="0b5d0-145">Value</span></span>|<span data-ttu-id="0b5d0-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b5d0-147">*type_name*</span><span class="sxs-lookup"><span data-stu-id="0b5d0-147">*type_name*</span></span>|<span data-ttu-id="0b5d0-148">Der Typname.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-148">The type name.</span></span> <span data-ttu-id="0b5d0-149">Wenn sich der von diesem `<ImpliesType>`-Element dargestellte Typ im selben Namespace wie das enthaltende `<Type>`-Element befindet, kann *type_name* den Namen des Typs ohne den Namespace umfassen.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-149">If the type represented by this `<ImpliesType>` element is located in the same namespace as its containing `<Type>` element, *type_name* can include the name of the type without its namespace.</span></span> <span data-ttu-id="0b5d0-150">Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-150">Otherwise, *type_name* must include the fully qualified type name.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="0b5d0-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="0b5d0-151">All other attributes</span></span>  
  
|<span data-ttu-id="0b5d0-152">Wert</span><span class="sxs-lookup"><span data-stu-id="0b5d0-152">Value</span></span>|<span data-ttu-id="0b5d0-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b5d0-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="0b5d0-154">*policy_setting*</span></span>|<span data-ttu-id="0b5d0-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="0b5d0-156">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-156">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="0b5d0-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0b5d0-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b5d0-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b5d0-158">Child Elements</span></span>  
 <span data-ttu-id="0b5d0-159">Keine</span><span class="sxs-lookup"><span data-stu-id="0b5d0-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b5d0-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b5d0-160">Parent Elements</span></span>  
  
|<span data-ttu-id="0b5d0-161">Element</span><span class="sxs-lookup"><span data-stu-id="0b5d0-161">Element</span></span>|<span data-ttu-id="0b5d0-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b5d0-163">\<Type></span><span class="sxs-lookup"><span data-stu-id="0b5d0-163">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="0b5d0-164">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-164">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="0b5d0-165">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="0b5d0-165">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="0b5d0-166">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-166">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
|[<span data-ttu-id="0b5d0-167">\<Method></span><span class="sxs-lookup"><span data-stu-id="0b5d0-167">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="0b5d0-168">Wendet die Reflektionsrichtlinie auf eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-168">Applies reflection policy to a method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b5d0-169">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b5d0-169">Remarks</span></span>  
 <span data-ttu-id="0b5d0-170">Das `<ImpliesType>`-Element dient in erster Linie der Verwendung durch Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-170">The `<ImpliesType>` element is primarily intended for use by libraries.</span></span> <span data-ttu-id="0b5d0-171">Es wird in folgendem Szenario eingesetzt:</span><span class="sxs-lookup"><span data-stu-id="0b5d0-171">It addresses the following scenario:</span></span>  
  
-   <span data-ttu-id="0b5d0-172">Wenn eine Routine einen Typ reflektieren muss, muss sie unbedingt einen zweiten Typ reflektieren.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-172">If a routine needs to reflect on one type, it necessarily needs to reflect on a second type.</span></span>  
  
-   <span data-ttu-id="0b5d0-173">Die Metadaten für die implizite Instanziierung des zweiten Typs ist andernfalls nicht verfügbar, da die statische Analyse nicht angibt, dass dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-173">The metadata for the implied instantiation of the second type is otherwise unavailable, because static analysis doesn't indicate that it's necessary.</span></span>  
  
 <span data-ttu-id="0b5d0-174">In den meisten Fällen sind die beiden Typen generische Instanziierungen mit freigegebenen Typargumenten.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-174">Most commonly, the two types are generic instantiations with shared type arguments.</span></span>  
  
 <span data-ttu-id="0b5d0-175">Das `<ImpliesType>`-Element wurde unter der Annahme definiert, dass die Notwendigkeit einer Reflektion für den Typ, der von seinem übergeordneten Element angegebenen wird, eine Notwendigkeit einer Reflektion für den Typ impliziert, der vom `<ImpliesType>`-Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-175">The `<ImpliesType>` element was defined with the assumption that a need for reflection on the type specified by its parent element implies a need for reflection on the type specified by the `<ImpliesType>` element.</span></span> <span data-ttu-id="0b5d0-176">Die folgenden Reflektionsrichtlinien gelten z. B. für zwei Typen – `Explicit<T>` und `Implicit<T>`.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-176">For example, the following reflection directives apply to two types, `Explicit<T>` and `Implicit<T>`.</span></span>  
  
```xml  
<Type Name="Explicit{ET}">  
    <ImpliesType Name="Implicit{ET}" Dynamic="Required Public" />  
</Type>  
```  
  
 <span data-ttu-id="0b5d0-177">Diese Richtlinie hat nur dann eine Auswirkungen, wenn eine Instanziierung von `Explicit` über eine definierte `Dynamic`-Richtlinieneinstellung verfügt.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-177">This directive has no effect unless an instantiation of `Explicit` has a defined `Dynamic` policy setting.</span></span> <span data-ttu-id="0b5d0-178">Wenn das z. B. für `Explicit<Int32>` der Fall ist, wird `Implicit<Int32>` mit den öffentlichen Membern instanziiert, und ihre Metadaten werden für die dynamische Programmierung verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-178">For example, if that's the case for `Explicit<Int32>`, `Implicit<Int32>` is instantiated with its public members rooted, and their metadata is made accessible for dynamic programming.</span></span>  
  
 <span data-ttu-id="0b5d0-179">Folgendes ist ein praktisches Beispiel, das für mindestens ein Serialisierungsprogramm gilt.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-179">The following is a real-world example that applies to at least one serializer.</span></span> <span data-ttu-id="0b5d0-180">Die Anweisungen erkennen den Bedarf, dass die Reflektion von etwas, das als `IList<`*something*`>` typisiert ist, auch die Reflektion des entsprechenden `List<`*something*`>`-Typs umfasst, ohne dass anwendungsbasierte Anmerkungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-180">The directives capture the requirement that reflecting on something typed as `IList<`*something*`>` also involves reflecting on the corresponding `List<`*something*`>` type without requiring any per-application annotation.</span></span>  
  
```xml  
<Type Name="System.Collections.Generic.IList{T}">  
   <ImpliesType Name="System.Collections.Generic.List{T}" Serialize="Public" />  
</Type>  
```  
  
 <span data-ttu-id="0b5d0-181">Das `<ImpliesType>`-Element kann auch innerhalb eines `<Method>`-Element angezeigt werden, da in einigen Fällen das Instanziieren einer generischen Methode die Reflektion einer Typinstanziierung impliziert.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-181">The `<ImpliesType>` element can also appear within a `<Method>` element, because in some cases instantiating a generic method implies reflecting on a type instantiation.</span></span> <span data-ttu-id="0b5d0-182">Stellen Sie sich zum Beispiel eine generische Methode `IEnumerable<T> MakeEnumerable<T>(string``spelling``, T``defaultValue``)` vor, auf die eine angegebene Bibliothek zusammen mit den zugehörigen <xref:System.Collections.Generic.List%601>- und <xref:System.Array>-Typen dynamisch zugreift.</span><span class="sxs-lookup"><span data-stu-id="0b5d0-182">For example, imagine a generic method `IEnumerable<T> MakeEnumerable<T>(string` `spelling``, T` `defaultValue``)` that a given library will access dynamically along with the associated <xref:System.Collections.Generic.List%601> and <xref:System.Array> types.</span></span> <span data-ttu-id="0b5d0-183">Dies kann folgendermaßen ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="0b5d0-183">This can be expressed as:</span></span>  
  
```xml  
<Type Name="MyType">  
    <Method Name="MakeEnumerable{T}" Signature="(System.String, T)" Dynamic="Included">  
        <ImpliesType Name="T[]" Dynamic="Public" />  
        <ImpliesType Name="System.Collections.Generic.List{T}" Dynamic="Public">  
    </Method>  
</Type>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b5d0-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b5d0-184">See Also</span></span>  
 [<span data-ttu-id="0b5d0-185">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="0b5d0-185">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="0b5d0-186">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-186">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="0b5d0-187">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="0b5d0-187">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
