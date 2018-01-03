---
title: '&lt;Parameter&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 820c36abda104bbf748e5b3a7838f3c7715048e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltparametergt-element-net-native"></a><span data-ttu-id="6fca5-102">&lt;Parameter&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="6fca5-102">&lt;Parameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="6fca5-103">Wendet die Reflektionsrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6fca5-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fca5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fca5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fca5-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6fca5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6fca5-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6fca5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fca5-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="6fca5-107">Attributes</span></span>  
  
|<span data-ttu-id="6fca5-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="6fca5-108">Attribute</span></span>|<span data-ttu-id="6fca5-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="6fca5-109">Attribute type</span></span>|<span data-ttu-id="6fca5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fca5-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="6fca5-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="6fca5-111">General</span></span>|<span data-ttu-id="6fca5-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-112">Required attribute.</span></span> <span data-ttu-id="6fca5-113">Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="6fca5-113">The parameter name.</span></span> <span data-ttu-id="6fca5-114">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="6fca5-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="6fca5-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="6fca5-115">Reflection</span></span>|<span data-ttu-id="6fca5-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-116">Optional attribute.</span></span> <span data-ttu-id="6fca5-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6fca5-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="6fca5-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="6fca5-118">Reflection</span></span>|<span data-ttu-id="6fca5-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-119">Optional attribute.</span></span> <span data-ttu-id="6fca5-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="6fca5-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="6fca5-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="6fca5-121">Reflection</span></span>|<span data-ttu-id="6fca5-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-122">Optional attribute.</span></span> <span data-ttu-id="6fca5-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6fca5-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="6fca5-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6fca5-124">Serialization</span></span>|<span data-ttu-id="6fca5-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-125">Optional attribute.</span></span> <span data-ttu-id="6fca5-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6fca5-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="6fca5-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6fca5-127">Serialization</span></span>|<span data-ttu-id="6fca5-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-128">Optional attribute.</span></span> <span data-ttu-id="6fca5-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fca5-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="6fca5-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6fca5-130">Serialization</span></span>|<span data-ttu-id="6fca5-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-131">Optional attribute.</span></span> <span data-ttu-id="6fca5-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fca5-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="6fca5-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6fca5-133">Serialization</span></span>|<span data-ttu-id="6fca5-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-134">Optional attribute.</span></span> <span data-ttu-id="6fca5-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fca5-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="6fca5-136">Interop</span><span class="sxs-lookup"><span data-stu-id="6fca5-136">Interop</span></span>|<span data-ttu-id="6fca5-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-137">Optional attribute.</span></span> <span data-ttu-id="6fca5-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu WinRT und COM.</span><span class="sxs-lookup"><span data-stu-id="6fca5-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="6fca5-139">Interop</span><span class="sxs-lookup"><span data-stu-id="6fca5-139">Interop</span></span>|<span data-ttu-id="6fca5-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-140">Optional attribute.</span></span> <span data-ttu-id="6fca5-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="6fca5-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="6fca5-142">Interop</span><span class="sxs-lookup"><span data-stu-id="6fca5-142">Interop</span></span>|<span data-ttu-id="6fca5-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="6fca5-143">Optional attribute.</span></span> <span data-ttu-id="6fca5-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="6fca5-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="6fca5-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="6fca5-145">Name attribute</span></span>  
  
|<span data-ttu-id="6fca5-146">Wert</span><span class="sxs-lookup"><span data-stu-id="6fca5-146">Value</span></span>|<span data-ttu-id="6fca5-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fca5-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fca5-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="6fca5-148">*parameter_name*</span></span>|<span data-ttu-id="6fca5-149">Der Name des Methodenparameters, auf den die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="6fca5-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="6fca5-150">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="6fca5-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="6fca5-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="6fca5-151">All other attributes</span></span>  
  
|<span data-ttu-id="6fca5-152">Wert</span><span class="sxs-lookup"><span data-stu-id="6fca5-152">Value</span></span>|<span data-ttu-id="6fca5-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fca5-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6fca5-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="6fca5-154">*policy_setting*</span></span>|<span data-ttu-id="6fca5-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6fca5-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="6fca5-156">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="6fca5-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="6fca5-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6fca5-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fca5-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6fca5-158">Child Elements</span></span>  
 <span data-ttu-id="6fca5-159">Keine</span><span class="sxs-lookup"><span data-stu-id="6fca5-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fca5-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6fca5-160">Parent Elements</span></span>  
  
|<span data-ttu-id="6fca5-161">Element</span><span class="sxs-lookup"><span data-stu-id="6fca5-161">Element</span></span>|<span data-ttu-id="6fca5-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fca5-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fca5-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="6fca5-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="6fca5-164">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="6fca5-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fca5-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fca5-165">Remarks</span></span>  
 <span data-ttu-id="6fca5-166">Das `<Parameter>`-Element ist ein untergeordnetes Element des [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)-Elements und wird verwendet, um eine Richtlinie auf einen bestimmten Methodenparameter anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6fca5-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="6fca5-167">Der entsprechende Methodenparameter wird durch den Namen und nicht durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="6fca5-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="6fca5-168">Mindestens ein Attribut, das einen Richtlinientyp wie `Activate` oder `Dynamic` darstellt, muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6fca5-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fca5-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fca5-169">See Also</span></span>  
 [<span data-ttu-id="6fca5-170">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="6fca5-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="6fca5-171">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="6fca5-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="6fca5-172">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="6fca5-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="6fca5-173">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="6fca5-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
