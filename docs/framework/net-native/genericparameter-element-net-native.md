---
title: <GenericParameter>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2898d804f7a351045b2fbce42042f9fd322ebb0a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049743"
---
# <a name="genericparameter-element-net-native"></a><span data-ttu-id="b953f-102">\<Genericparameter-> Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="b953f-102">\<GenericParameter> Element (.NET Native)</span></span>
<span data-ttu-id="b953f-103">Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="b953f-103">Applies policy to the parameter type of a generic type or method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b953f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b953f-104">Syntax</span></span>  
  
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
                  MarshalStructure="policy_type"  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b953f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b953f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b953f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b953f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b953f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="b953f-107">Attributes</span></span>  
  
|<span data-ttu-id="b953f-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="b953f-108">Attribute</span></span>|<span data-ttu-id="b953f-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="b953f-109">Attribute type</span></span>|<span data-ttu-id="b953f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b953f-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="b953f-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="b953f-111">General</span></span>|<span data-ttu-id="b953f-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-112">Required attribute.</span></span> <span data-ttu-id="b953f-113">Der Name des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="b953f-113">The name of the generic parameter.</span></span> <span data-ttu-id="b953f-114">Z. B. muss für den generischen Delegaten <xref:System.Func%603> der Wert des `Name`-Attributs "TResult" lauten, um die Laufzeitrichtlinie auf den Rückgabewert des Delegaten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b953f-114">For example, for the generic delegate <xref:System.Func%603>, the value of the `Name` attribute is "TResult" to apply runtime policy to the delegate's return value.</span></span>|  
|`Activate`|<span data-ttu-id="b953f-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b953f-115">Reflection</span></span>|<span data-ttu-id="b953f-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-116">Optional attribute.</span></span> <span data-ttu-id="b953f-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b953f-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="b953f-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b953f-118">Reflection</span></span>|<span data-ttu-id="b953f-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-119">Optional attribute.</span></span> <span data-ttu-id="b953f-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="b953f-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="b953f-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="b953f-121">Reflection</span></span>|<span data-ttu-id="b953f-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-122">Optional attribute.</span></span> <span data-ttu-id="b953f-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b953f-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="b953f-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b953f-124">Serialization</span></span>|<span data-ttu-id="b953f-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-125">Optional attribute.</span></span> <span data-ttu-id="b953f-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b953f-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="b953f-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b953f-127">Serialization</span></span>|<span data-ttu-id="b953f-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-128">Optional attribute.</span></span> <span data-ttu-id="b953f-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b953f-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="b953f-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b953f-130">Serialization</span></span>|<span data-ttu-id="b953f-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-131">Optional attribute.</span></span> <span data-ttu-id="b953f-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b953f-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="b953f-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b953f-133">Serialization</span></span>|<span data-ttu-id="b953f-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-134">Optional attribute.</span></span> <span data-ttu-id="b953f-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="b953f-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="b953f-136">Interop</span><span class="sxs-lookup"><span data-stu-id="b953f-136">Interop</span></span>|<span data-ttu-id="b953f-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-137">Optional attribute.</span></span> <span data-ttu-id="b953f-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="b953f-138">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="b953f-139">Interop</span><span class="sxs-lookup"><span data-stu-id="b953f-139">Interop</span></span>|<span data-ttu-id="b953f-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-140">Optional attribute.</span></span> <span data-ttu-id="b953f-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b953f-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="b953f-142">Interop</span><span class="sxs-lookup"><span data-stu-id="b953f-142">Interop</span></span>|<span data-ttu-id="b953f-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-143">Optional attribute.</span></span> <span data-ttu-id="b953f-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="b953f-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="b953f-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="b953f-145">Name attribute</span></span>  
  
|<span data-ttu-id="b953f-146">Wert</span><span class="sxs-lookup"><span data-stu-id="b953f-146">Value</span></span>|<span data-ttu-id="b953f-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b953f-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b953f-148">*generic_parameter_name*</span><span class="sxs-lookup"><span data-stu-id="b953f-148">*generic_parameter_name*</span></span>|<span data-ttu-id="b953f-149">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b953f-149">Required attribute.</span></span> <span data-ttu-id="b953f-150">Der Name des generischen Typparameters.</span><span class="sxs-lookup"><span data-stu-id="b953f-150">The name of the generic type parameter.</span></span> <span data-ttu-id="b953f-151">Wendet z.B. für den generischen Delegaten <xref:System.Func%603> der *generic_parameter_name*-Wert „TResult“ die Laufzeitrichtlinie auf den Rückgabewert des Delegaten an.</span><span class="sxs-lookup"><span data-stu-id="b953f-151">For example, for the generic delegate <xref:System.Func%603>, a *generic_parameter_name* value of "TResult" applies runtime policy to the delegate's return value.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="b953f-152">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="b953f-152">All other attributes</span></span>  
  
|<span data-ttu-id="b953f-153">Wert</span><span class="sxs-lookup"><span data-stu-id="b953f-153">Value</span></span>|<span data-ttu-id="b953f-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b953f-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b953f-155">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="b953f-155">*policy_setting*</span></span>|<span data-ttu-id="b953f-156">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b953f-156">The setting to apply to this policy type.</span></span> <span data-ttu-id="b953f-157">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="b953f-157">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="b953f-158">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b953f-158">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b953f-159">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b953f-159">Child Elements</span></span>  
 <span data-ttu-id="b953f-160">Keine</span><span class="sxs-lookup"><span data-stu-id="b953f-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b953f-161">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b953f-161">Parent Elements</span></span>  
  
|<span data-ttu-id="b953f-162">Element</span><span class="sxs-lookup"><span data-stu-id="b953f-162">Element</span></span>|<span data-ttu-id="b953f-163">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b953f-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b953f-164">\<Method></span><span class="sxs-lookup"><span data-stu-id="b953f-164">\<Method></span></span>](method-element-net-native.md)|<span data-ttu-id="b953f-165">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="b953f-165">Applies runtime reflection policy to a constructor or method.</span></span>|  
|[<span data-ttu-id="b953f-166">\<Type></span><span class="sxs-lookup"><span data-stu-id="b953f-166">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="b953f-167">Wendet eine Laufzeitreflektionsrichtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.</span><span class="sxs-lookup"><span data-stu-id="b953f-167">Applies runtime reflection policy to a particular type, such as a class or structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b953f-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b953f-168">Remarks</span></span>  
 <span data-ttu-id="b953f-169">Das `<GenericParameter>`-Element ist ein untergeordnetes Element des [\<Method>](method-element-net-native.md)- oder [\<Type>](type-element-net-native.md)-Elements und dient zur Anwendung der Richtlinie auf einen bestimmten generischen Typparameter, der durch seinen Namen im generischen Typ oder der Methodensignatur angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b953f-169">The `<GenericParameter>` element is a child of either the [\<Method>](method-element-net-native.md) or [\<Type>](type-element-net-native.md) element and is used to apply policy to a particular generic type parameter, which is specified by its name in the generic type or method signature.</span></span>  
  
 <span data-ttu-id="b953f-170">Das `<GenericParameter>`-Element ist am nützlichsten, wenn es mit Serialisierungsprogrammen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b953f-170">The `<GenericParameter>` element is most useful when used with serializers.</span></span> <span data-ttu-id="b953f-171">Im folgenden Beispiel wird das Element `<GenericParameter>` verwendet, um die Richtlinie auf den Typ `T` in Aufrufen von Überladungen der Methode [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) des NewtonSoft JSON-Serialisierungsprogramms anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b953f-171">The following example uses the `<GenericParameter>` element to apply policy to the type `T` in calls to the NewtonSoft JSON serializer's [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) method overloads.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b953f-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b953f-172">See also</span></span>

- [<span data-ttu-id="b953f-173">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="b953f-173">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="b953f-174">\<Type >-Element</span><span class="sxs-lookup"><span data-stu-id="b953f-174">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="b953f-175">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="b953f-175">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="b953f-176">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b953f-176">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="b953f-177">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="b953f-177">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
