---
title: <Parameter> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 7e812ab60eb0a89eb868346733a8ea74e2f76d3e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287864"
---
# <a name="parameter-element-net-native"></a><span data-ttu-id="d64e4-102">\<Parameter> -Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="d64e4-102">\<Parameter> Element (.NET Native)</span></span>

<span data-ttu-id="d64e4-103">Wendet die Reflektionsrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d64e4-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d64e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d64e4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d64e4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d64e4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d64e4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d64e4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d64e4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d64e4-107">Attributes</span></span>  
  
|<span data-ttu-id="d64e4-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="d64e4-108">Attribute</span></span>|<span data-ttu-id="d64e4-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="d64e4-109">Attribute type</span></span>|<span data-ttu-id="d64e4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d64e4-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d64e4-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="d64e4-111">General</span></span>|<span data-ttu-id="d64e4-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-112">Required attribute.</span></span> <span data-ttu-id="d64e4-113">Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="d64e4-113">The parameter name.</span></span> <span data-ttu-id="d64e4-114">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="d64e4-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="d64e4-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d64e4-115">Reflection</span></span>|<span data-ttu-id="d64e4-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-116">Optional attribute.</span></span> <span data-ttu-id="d64e4-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d64e4-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="d64e4-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d64e4-118">Reflection</span></span>|<span data-ttu-id="d64e4-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-119">Optional attribute.</span></span> <span data-ttu-id="d64e4-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="d64e4-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="d64e4-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d64e4-121">Reflection</span></span>|<span data-ttu-id="d64e4-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-122">Optional attribute.</span></span> <span data-ttu-id="d64e4-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d64e4-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="d64e4-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d64e4-124">Serialization</span></span>|<span data-ttu-id="d64e4-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-125">Optional attribute.</span></span> <span data-ttu-id="d64e4-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d64e4-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="d64e4-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d64e4-127">Serialization</span></span>|<span data-ttu-id="d64e4-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-128">Optional attribute.</span></span> <span data-ttu-id="d64e4-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d64e4-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="d64e4-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d64e4-130">Serialization</span></span>|<span data-ttu-id="d64e4-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-131">Optional attribute.</span></span> <span data-ttu-id="d64e4-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d64e4-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="d64e4-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d64e4-133">Serialization</span></span>|<span data-ttu-id="d64e4-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-134">Optional attribute.</span></span> <span data-ttu-id="d64e4-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d64e4-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="d64e4-136">Interop</span><span class="sxs-lookup"><span data-stu-id="d64e4-136">Interop</span></span>|<span data-ttu-id="d64e4-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-137">Optional attribute.</span></span> <span data-ttu-id="d64e4-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu WinRT und COM.</span><span class="sxs-lookup"><span data-stu-id="d64e4-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="d64e4-139">Interop</span><span class="sxs-lookup"><span data-stu-id="d64e4-139">Interop</span></span>|<span data-ttu-id="d64e4-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-140">Optional attribute.</span></span> <span data-ttu-id="d64e4-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="d64e4-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="d64e4-142">Interop</span><span class="sxs-lookup"><span data-stu-id="d64e4-142">Interop</span></span>|<span data-ttu-id="d64e4-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d64e4-143">Optional attribute.</span></span> <span data-ttu-id="d64e4-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="d64e4-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d64e4-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="d64e4-145">Name attribute</span></span>  
  
|<span data-ttu-id="d64e4-146">Wert</span><span class="sxs-lookup"><span data-stu-id="d64e4-146">Value</span></span>|<span data-ttu-id="d64e4-147">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d64e4-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d64e4-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="d64e4-148">*parameter_name*</span></span>|<span data-ttu-id="d64e4-149">Der Name des Methodenparameters, auf den die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d64e4-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="d64e4-150">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="d64e4-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d64e4-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="d64e4-151">All other attributes</span></span>  
  
|<span data-ttu-id="d64e4-152">Wert</span><span class="sxs-lookup"><span data-stu-id="d64e4-152">Value</span></span>|<span data-ttu-id="d64e4-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d64e4-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d64e4-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d64e4-154">*policy_setting*</span></span>|<span data-ttu-id="d64e4-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d64e4-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="d64e4-156">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="d64e4-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="d64e4-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d64e4-157">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d64e4-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d64e4-158">Child Elements</span></span>  

 <span data-ttu-id="d64e4-159">Keine</span><span class="sxs-lookup"><span data-stu-id="d64e4-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d64e4-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d64e4-160">Parent Elements</span></span>  
  
|<span data-ttu-id="d64e4-161">Element</span><span class="sxs-lookup"><span data-stu-id="d64e4-161">Element</span></span>|<span data-ttu-id="d64e4-162">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d64e4-162">Description</span></span>|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|<span data-ttu-id="d64e4-163">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="d64e4-163">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d64e4-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d64e4-164">Remarks</span></span>  

 <span data-ttu-id="d64e4-165">Das `<Parameter>` -Element ist ein untergeordnetes [\<Method>](method-element-net-native.md) Element des-Elements und wird verwendet, um die Richtlinie auf einen bestimmten Methoden Parameter anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d64e4-165">The `<Parameter>` element is a child of the [\<Method>](method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="d64e4-166">Der entsprechende Methodenparameter wird durch den Namen und nicht durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="d64e4-166">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="d64e4-167">Mindestens ein Attribut, das einen Richtlinientyp wie `Activate` oder `Dynamic` darstellt, muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d64e4-167">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64e4-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d64e4-168">See also</span></span>

- [<span data-ttu-id="d64e4-169">\<Method>-Element</span><span class="sxs-lookup"><span data-stu-id="d64e4-169">\<Method> Element</span></span>](method-element-net-native.md)
- [<span data-ttu-id="d64e4-170">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="d64e4-170">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="d64e4-171">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="d64e4-171">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
- [<span data-ttu-id="d64e4-172">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="d64e4-172">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
