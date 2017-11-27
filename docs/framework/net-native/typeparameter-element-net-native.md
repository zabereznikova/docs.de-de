---
title: '&lt;TypeParameter&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c7b2fe5cf586c0f8a58d1698cdf3870b5b5c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparametergt-element-net-native"></a><span data-ttu-id="2f111-102">&lt;TypeParameter&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2f111-102">&lt;TypeParameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="2f111-103">Wendet eine Richtlinie auf den Typ an, der durch ein an eine Methode übergebenes Type-Argument dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2f111-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f111-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f111-104">Syntax</span></span>  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f111-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f111-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2f111-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f111-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f111-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f111-107">Attributes</span></span>  
  
|<span data-ttu-id="2f111-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="2f111-108">Attribute</span></span>|<span data-ttu-id="2f111-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="2f111-109">Attribute type</span></span>|<span data-ttu-id="2f111-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f111-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="2f111-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="2f111-111">General</span></span>|<span data-ttu-id="2f111-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-112">Required attribute.</span></span> <span data-ttu-id="2f111-113">Der Name des Parameters vom Typ <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="2f111-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2f111-114">Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".</span><span class="sxs-lookup"><span data-stu-id="2f111-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="2f111-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="2f111-115">Reflection</span></span>|<span data-ttu-id="2f111-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-116">Optional attribute.</span></span> <span data-ttu-id="2f111-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2f111-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="2f111-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="2f111-118">Reflection</span></span>|<span data-ttu-id="2f111-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-119">Optional attribute.</span></span> <span data-ttu-id="2f111-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="2f111-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="2f111-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="2f111-121">Reflection</span></span>|<span data-ttu-id="2f111-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-122">Optional attribute.</span></span> <span data-ttu-id="2f111-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2f111-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="2f111-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2f111-124">Serialization</span></span>|<span data-ttu-id="2f111-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-125">Optional attribute.</span></span> <span data-ttu-id="2f111-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="2f111-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="2f111-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2f111-127">Serialization</span></span>|<span data-ttu-id="2f111-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-128">Optional attribute.</span></span> <span data-ttu-id="2f111-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f111-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="2f111-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2f111-130">Serialization</span></span>|<span data-ttu-id="2f111-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-131">Optional attribute.</span></span> <span data-ttu-id="2f111-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f111-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="2f111-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2f111-133">Serialization</span></span>|<span data-ttu-id="2f111-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-134">Optional attribute.</span></span> <span data-ttu-id="2f111-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f111-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="2f111-136">Interop</span><span class="sxs-lookup"><span data-stu-id="2f111-136">Interop</span></span>|<span data-ttu-id="2f111-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-137">Optional attribute.</span></span> <span data-ttu-id="2f111-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="2f111-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="2f111-139">Interop</span><span class="sxs-lookup"><span data-stu-id="2f111-139">Interop</span></span>|<span data-ttu-id="2f111-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-140">Optional attribute.</span></span> <span data-ttu-id="2f111-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="2f111-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="2f111-142">Interop</span><span class="sxs-lookup"><span data-stu-id="2f111-142">Interop</span></span>|<span data-ttu-id="2f111-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="2f111-143">Optional attribute.</span></span> <span data-ttu-id="2f111-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="2f111-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="2f111-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="2f111-145">Name attribute</span></span>  
  
|<span data-ttu-id="2f111-146">Wert</span><span class="sxs-lookup"><span data-stu-id="2f111-146">Value</span></span>|<span data-ttu-id="2f111-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f111-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f111-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="2f111-148">*parameter_name*</span></span>|<span data-ttu-id="2f111-149">Der Name des Parameters vom Typ <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="2f111-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2f111-150">Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".</span><span class="sxs-lookup"><span data-stu-id="2f111-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="2f111-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="2f111-151">All other attributes</span></span>  
  
|<span data-ttu-id="2f111-152">Wert</span><span class="sxs-lookup"><span data-stu-id="2f111-152">Value</span></span>|<span data-ttu-id="2f111-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f111-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f111-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="2f111-154">*policy_setting*</span></span>|<span data-ttu-id="2f111-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f111-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="2f111-156">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="2f111-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="2f111-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2f111-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f111-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f111-158">Child Elements</span></span>  
 <span data-ttu-id="2f111-159">Keine</span><span class="sxs-lookup"><span data-stu-id="2f111-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f111-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f111-160">Parent Elements</span></span>  
  
|<span data-ttu-id="2f111-161">Element</span><span class="sxs-lookup"><span data-stu-id="2f111-161">Element</span></span>|<span data-ttu-id="2f111-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f111-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f111-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="2f111-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="2f111-164">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="2f111-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f111-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f111-165">Remarks</span></span>  
 <span data-ttu-id="2f111-166">Das `<TypeParameter>`-Element ähnelt dem [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)-Element, mit dem Unterschied, dass es nur auf Parameter vom Typ <xref:System.Type> angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2f111-166">The `<TypeParameter>` element is similar to the [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="2f111-167">Es wendet die Richtlinie auf den Typ an, der zur Laufzeit durch das vom `Name`-Attribut angegebenen Typargument dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2f111-167">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="2f111-168">Das NewtonSoft JSON-Serialisierungsprogramm enthält z. B. eine statische `JsonConvert.DeserializeObject(String value, Type type)`-Methode.</span><span class="sxs-lookup"><span data-stu-id="2f111-168">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="2f111-169">Die folgenden Reflektionsdirektiven:</span><span class="sxs-lookup"><span data-stu-id="2f111-169">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="2f111-170">geben an, dass Metadaten für den Laufzeittyp, der durch das `type`-Argument dargestellt wird, für die Serialisierung verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2f111-170">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="2f111-171">Wenn diese Laufzeitdirektiven für ein Projekt, das den folgenden Quellcode enthält, gelten:</span><span class="sxs-lookup"><span data-stu-id="2f111-171">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="2f111-172">machen die Reflektionsdirektiven die Metadaten für den `StockQuote`-Typ zur Laufzeit für das NewtonSoft JSON-Serialisierungsprogramm verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f111-172">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f111-173">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f111-173">See Also</span></span>  
 [<span data-ttu-id="2f111-174">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="2f111-174">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="2f111-175">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="2f111-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="2f111-176">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="2f111-176">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="2f111-177">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="2f111-177">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
