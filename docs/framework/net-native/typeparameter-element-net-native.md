---
title: <TypeParameter> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
ms.openlocfilehash: dc04115914b7571b677c6d069d2d4b820b895d59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287669"
---
# <a name="typeparameter-element-net-native"></a><span data-ttu-id="1523c-102">\<TypeParameter> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="1523c-102">\<TypeParameter> Element (.NET Native)</span></span>

<span data-ttu-id="1523c-103">Wendet eine Richtlinie auf den Typ an, der durch ein an eine Methode übergebenes Typargument dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1523c-103">Applies policy to the type represented by a Type argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1523c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1523c-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1523c-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1523c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1523c-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1523c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1523c-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="1523c-107">Attributes</span></span>  
  
|<span data-ttu-id="1523c-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="1523c-108">Attribute</span></span>|<span data-ttu-id="1523c-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="1523c-109">Attribute type</span></span>|<span data-ttu-id="1523c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1523c-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="1523c-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="1523c-111">General</span></span>|<span data-ttu-id="1523c-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-112">Required attribute.</span></span> <span data-ttu-id="1523c-113">Der Name des Parameters vom Typ <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="1523c-113">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1523c-114">Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".</span><span class="sxs-lookup"><span data-stu-id="1523c-114">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
|`Activate`|<span data-ttu-id="1523c-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="1523c-115">Reflection</span></span>|<span data-ttu-id="1523c-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-116">Optional attribute.</span></span> <span data-ttu-id="1523c-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1523c-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="1523c-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="1523c-118">Reflection</span></span>|<span data-ttu-id="1523c-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-119">Optional attribute.</span></span> <span data-ttu-id="1523c-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="1523c-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="1523c-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="1523c-121">Reflection</span></span>|<span data-ttu-id="1523c-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-122">Optional attribute.</span></span> <span data-ttu-id="1523c-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1523c-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="1523c-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1523c-124">Serialization</span></span>|<span data-ttu-id="1523c-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-125">Optional attribute.</span></span> <span data-ttu-id="1523c-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1523c-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="1523c-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1523c-127">Serialization</span></span>|<span data-ttu-id="1523c-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-128">Optional attribute.</span></span> <span data-ttu-id="1523c-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="1523c-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="1523c-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1523c-130">Serialization</span></span>|<span data-ttu-id="1523c-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-131">Optional attribute.</span></span> <span data-ttu-id="1523c-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="1523c-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="1523c-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1523c-133">Serialization</span></span>|<span data-ttu-id="1523c-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-134">Optional attribute.</span></span> <span data-ttu-id="1523c-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="1523c-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="1523c-136">Interop</span><span class="sxs-lookup"><span data-stu-id="1523c-136">Interop</span></span>|<span data-ttu-id="1523c-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-137">Optional attribute.</span></span> <span data-ttu-id="1523c-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="1523c-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="1523c-139">Interop</span><span class="sxs-lookup"><span data-stu-id="1523c-139">Interop</span></span>|<span data-ttu-id="1523c-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-140">Optional attribute.</span></span> <span data-ttu-id="1523c-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="1523c-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="1523c-142">Interop</span><span class="sxs-lookup"><span data-stu-id="1523c-142">Interop</span></span>|<span data-ttu-id="1523c-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="1523c-143">Optional attribute.</span></span> <span data-ttu-id="1523c-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="1523c-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="1523c-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="1523c-145">Name attribute</span></span>  
  
|<span data-ttu-id="1523c-146">Wert</span><span class="sxs-lookup"><span data-stu-id="1523c-146">Value</span></span>|<span data-ttu-id="1523c-147">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1523c-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1523c-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="1523c-148">*parameter_name*</span></span>|<span data-ttu-id="1523c-149">Der Name des Parameters vom Typ <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="1523c-149">The name of the parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1523c-150">Z. B. lautet für die Methodensignatur `Type.GetInterfaceMap(Type interfaceType)` der Wert des `Name`-Attributs "InterfaceType".</span><span class="sxs-lookup"><span data-stu-id="1523c-150">For example, for the method signature `Type.GetInterfaceMap(Type interfaceType)`, the value of the `Name` attribute is "interfaceType".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="1523c-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="1523c-151">All other attributes</span></span>  
  
|<span data-ttu-id="1523c-152">Wert</span><span class="sxs-lookup"><span data-stu-id="1523c-152">Value</span></span>|<span data-ttu-id="1523c-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1523c-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1523c-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="1523c-154">*policy_setting*</span></span>|<span data-ttu-id="1523c-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1523c-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="1523c-156">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="1523c-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="1523c-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1523c-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1523c-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1523c-158">Child Elements</span></span>  

 <span data-ttu-id="1523c-159">Keine</span><span class="sxs-lookup"><span data-stu-id="1523c-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1523c-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1523c-160">Parent Elements</span></span>  
  
|<span data-ttu-id="1523c-161">Element</span><span class="sxs-lookup"><span data-stu-id="1523c-161">Element</span></span>|<span data-ttu-id="1523c-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1523c-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="1523c-163">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="1523c-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1523c-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1523c-164">Remarks</span></span>  

 <span data-ttu-id="1523c-165">Das- `<TypeParameter>` Element ähnelt dem- [\<Parameter>](parameter-element-net-native.md) Element, mit dem Unterschied, dass es nur auf Parameter vom Typ angewendet werden kann <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="1523c-165">The `<TypeParameter>` element is similar to the [\<Parameter>](parameter-element-net-native.md) element, except that it can be applied only to parameters of type <xref:System.Type>.</span></span> <span data-ttu-id="1523c-166">Es wendet die Richtlinie auf den Typ an, der zur Laufzeit durch das vom `Name`-Attribut angegebenen Typargument dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1523c-166">It applies policy to whatever type is represented at run time by the type argument specified by the `Name` attribute.</span></span>  
  
 <span data-ttu-id="1523c-167">Das NewtonSoft JSON-Serialisierungsprogramm enthält z. B. eine statische `JsonConvert.DeserializeObject(String value, Type type)`-Methode.</span><span class="sxs-lookup"><span data-stu-id="1523c-167">For example, the NewtonSoft JSON serializer includes a static `JsonConvert.DeserializeObject(String value, Type type)` method.</span></span> <span data-ttu-id="1523c-168">Die folgenden Reflektionsanweisungen:</span><span class="sxs-lookup"><span data-stu-id="1523c-168">The following reflection directives:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 <span data-ttu-id="1523c-169">geben an, dass Metadaten für den Laufzeittyp, der durch das `type`-Argument dargestellt wird, für die Serialisierung verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1523c-169">specify that metadata for the runtime type represented by the `type` argument should be made available for serialization.</span></span> <span data-ttu-id="1523c-170">Wenn diese Laufzeitdirektiven für ein Projekt, das den folgenden Quellcode enthält, gelten:</span><span class="sxs-lookup"><span data-stu-id="1523c-170">If these runtime directives apply to a project that includes the following source code:</span></span>  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 <span data-ttu-id="1523c-171">machen die Reflektionsdirektiven die Metadaten für den `StockQuote`-Typ zur Laufzeit für das NewtonSoft JSON-Serialisierungsprogramm verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1523c-171">the reflection directives make metadata for the `StockQuote` type available for the NewtonSoft JSON serializer at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1523c-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1523c-172">See also</span></span>

- [<span data-ttu-id="1523c-173">\<Method>-Element</span><span class="sxs-lookup"><span data-stu-id="1523c-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="1523c-174">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="1523c-174">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="1523c-175">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="1523c-175">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="1523c-176">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="1523c-176">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
