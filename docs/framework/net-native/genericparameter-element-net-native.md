---
title: <GenericParameter> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
ms.openlocfilehash: 1400fb7029df533d54e87a1c534f4ac3b0a5fc68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288020"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="b9a5b-102">\<GenericParameter> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="b9a5b-102">\<GenericParameter> Element (.NET Native)</span></span>

<span data-ttu-id="b9a5b-103">Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9a5b-104">Syntax</span></span>  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9a5b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b9a5b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b9a5b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9a5b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b9a5b-107">Attributes</span></span>  
  
|<span data-ttu-id="b9a5b-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="b9a5b-108">Attribute</span></span>|<span data-ttu-id="b9a5b-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="b9a5b-109">Attribute type</span></span>|<span data-ttu-id="b9a5b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b9a5b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b9a5b-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b9a5b-111">General</span></span>|<span data-ttu-id="b9a5b-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-112">Required attribute.</span></span> <span data-ttu-id="b9a5b-113">Der Name des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-113">The name of the generic parameter.</span></span> <span data-ttu-id="b9a5b-114">Z. B. muss für den generischen Delegaten <xref:System.Func%603> der Wert des `Name`-Attributs "TResult" lauten, um die Laufzeitrichtlinie auf den Rückgabewert des Delegaten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="b9a5b-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-115">Reflection</span></span>|<span data-ttu-id="b9a5b-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-116">Optional attribute.</span></span> <span data-ttu-id="b9a5b-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b9a5b-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-118">Reflection</span></span>|<span data-ttu-id="b9a5b-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-119">Optional attribute.</span></span> <span data-ttu-id="b9a5b-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b9a5b-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-121">Reflection</span></span>|<span data-ttu-id="b9a5b-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-122">Optional attribute.</span></span> <span data-ttu-id="b9a5b-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b9a5b-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-124">Serialization</span></span>|<span data-ttu-id="b9a5b-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-125">Optional attribute.</span></span> <span data-ttu-id="b9a5b-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b9a5b-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-127">Serialization</span></span>|<span data-ttu-id="b9a5b-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-128">Optional attribute.</span></span> <span data-ttu-id="b9a5b-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b9a5b-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-130">Serialization</span></span>|<span data-ttu-id="b9a5b-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-131">Optional attribute.</span></span> <span data-ttu-id="b9a5b-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b9a5b-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-133">Serialization</span></span>|<span data-ttu-id="b9a5b-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-134">Optional attribute.</span></span> <span data-ttu-id="b9a5b-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b9a5b-136">Interop</span><span class="sxs-lookup"><span data-stu-id="b9a5b-136">Interop</span></span>|<span data-ttu-id="b9a5b-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-137">Optional attribute.</span></span> <span data-ttu-id="b9a5b-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b9a5b-139">Interop</span><span class="sxs-lookup"><span data-stu-id="b9a5b-139">Interop</span></span>|<span data-ttu-id="b9a5b-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-140">Optional attribute.</span></span> <span data-ttu-id="b9a5b-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b9a5b-142">Interop</span><span class="sxs-lookup"><span data-stu-id="b9a5b-142">Interop</span></span>|<span data-ttu-id="b9a5b-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-143">Optional attribute.</span></span> <span data-ttu-id="b9a5b-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b9a5b-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="b9a5b-145">Name attribute</span></span>  
  
|<span data-ttu-id="b9a5b-146">Wert</span><span class="sxs-lookup"><span data-stu-id="b9a5b-146">Value</span></span>|<span data-ttu-id="b9a5b-147">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b9a5b-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b9a5b-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b9a5b-148">*generic_parameter_name*</span></span>|<span data-ttu-id="b9a5b-149">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-149">Required attribute.</span></span> <span data-ttu-id="b9a5b-150">Der Name des generischen Typparameters.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-150">The name of the generic type parameter.</span></span> <span data-ttu-id="b9a5b-151">Wendet z.B. für den generischen Delegaten <xref:System.Func%603> der *generic_parameter_name*-Wert „TResult“ die Laufzeitrichtlinie auf den Rückgabewert des Delegaten an.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b9a5b-152">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="b9a5b-152">All other attributes</span></span>  
  
|<span data-ttu-id="b9a5b-153">Wert</span><span class="sxs-lookup"><span data-stu-id="b9a5b-153">Value</span></span>|<span data-ttu-id="b9a5b-154">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b9a5b-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b9a5b-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b9a5b-155">*policy_setting*</span></span>|<span data-ttu-id="b9a5b-156">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="b9a5b-157">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b9a5b-158">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b9a5b-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9a5b-159">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9a5b-159">Child Elements</span></span>  

 <span data-ttu-id="b9a5b-160">Keine</span><span class="sxs-lookup"><span data-stu-id="b9a5b-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9a5b-161">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b9a5b-161">Parent Elements</span></span>  
  
|<span data-ttu-id="b9a5b-162">Element</span><span class="sxs-lookup"><span data-stu-id="b9a5b-162">Element</span></span>|<span data-ttu-id="b9a5b-163">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b9a5b-163">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="b9a5b-164">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="b9a5b-165">Wendet eine Laufzeitreflektionsrichtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-165">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a5b-166">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9a5b-166">Remarks</span></span>  

 <span data-ttu-id="b9a5b-167">Das `<GenericParameter>` -Element ist ein untergeordnetes Element [\<Method>](method-element-net-native.md) des [\<Type>](type-element-net-native.md) -Elements oder des-Elements und wird verwendet, um die Richtlinie auf einen bestimmten generischen Typparameter anzuwenden, der durch seinen Namen in der generischen Typ-oder Methoden Signatur angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-167">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="b9a5b-168">Das `<GenericParameter>`-Element ist am nützlichsten, wenn es mit Serialisierungsprogrammen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-168">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="b9a5b-169">Im folgenden Beispiel wird das `<GenericParameter>` -Element verwendet, um eine Richtlinie auf den Typ `T` in Aufrufen der Methoden Überladungen " [JsonConvert. DeserializeObject" \<T> (String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) des Newton Soft JSON-Serialisierungsprogramms anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b9a5b-169">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9a5b-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9a5b-170">See also</span></span>

- [<span data-ttu-id="b9a5b-171">\<Method>-Element</span><span class="sxs-lookup"><span data-stu-id="b9a5b-171">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="b9a5b-172">\<Type>-Element</span><span class="sxs-lookup"><span data-stu-id="b9a5b-172">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="b9a5b-173">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="b9a5b-173">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b9a5b-174">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-174">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="b9a5b-175">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b9a5b-175">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
