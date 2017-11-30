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
ms.openlocfilehash: f603f795682c7ea1f48e5d9356af6e0477246da1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt-element-net-native"></a><span data-ttu-id="d7b81-102">&lt;Parameter&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="d7b81-102">&lt;Parameter&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d7b81-103">Wendet die Reflektionsrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7b81-103">Applies reflection policy to the type of the argument passed to a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7b81-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7b81-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d7b81-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d7b81-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7b81-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7b81-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d7b81-107">Attributes</span></span>  
  
|<span data-ttu-id="d7b81-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="d7b81-108">Attribute</span></span>|<span data-ttu-id="d7b81-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="d7b81-109">Attribute type</span></span>|<span data-ttu-id="d7b81-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7b81-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d7b81-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="d7b81-111">General</span></span>|<span data-ttu-id="d7b81-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-112">Required attribute.</span></span> <span data-ttu-id="d7b81-113">Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="d7b81-113">The parameter name.</span></span> <span data-ttu-id="d7b81-114">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="d7b81-114">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
|`Activate`|<span data-ttu-id="d7b81-115">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d7b81-115">Reflection</span></span>|<span data-ttu-id="d7b81-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-116">Optional attribute.</span></span> <span data-ttu-id="d7b81-117">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d7b81-117">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="d7b81-118">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d7b81-118">Reflection</span></span>|<span data-ttu-id="d7b81-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-119">Optional attribute.</span></span> <span data-ttu-id="d7b81-120">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="d7b81-120">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="d7b81-121">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="d7b81-121">Reflection</span></span>|<span data-ttu-id="d7b81-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-122">Optional attribute.</span></span> <span data-ttu-id="d7b81-123">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d7b81-123">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="d7b81-124">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d7b81-124">Serialization</span></span>|<span data-ttu-id="d7b81-125">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-125">Optional attribute.</span></span> <span data-ttu-id="d7b81-126">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d7b81-126">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="d7b81-127">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d7b81-127">Serialization</span></span>|<span data-ttu-id="d7b81-128">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-128">Optional attribute.</span></span> <span data-ttu-id="d7b81-129">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7b81-129">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="d7b81-130">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d7b81-130">Serialization</span></span>|<span data-ttu-id="d7b81-131">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-131">Optional attribute.</span></span> <span data-ttu-id="d7b81-132">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7b81-132">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="d7b81-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="d7b81-133">Serialization</span></span>|<span data-ttu-id="d7b81-134">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-134">Optional attribute.</span></span> <span data-ttu-id="d7b81-135">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7b81-135">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="d7b81-136">Interop</span><span class="sxs-lookup"><span data-stu-id="d7b81-136">Interop</span></span>|<span data-ttu-id="d7b81-137">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-137">Optional attribute.</span></span> <span data-ttu-id="d7b81-138">Steuert die Richtlinie für das Marshalling von Verweistypen zu WinRT und COM.</span><span class="sxs-lookup"><span data-stu-id="d7b81-138">Controls policy for marshaling reference types to WinRT and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="d7b81-139">Interop</span><span class="sxs-lookup"><span data-stu-id="d7b81-139">Interop</span></span>|<span data-ttu-id="d7b81-140">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-140">Optional attribute.</span></span> <span data-ttu-id="d7b81-141">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="d7b81-141">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="d7b81-142">Interop</span><span class="sxs-lookup"><span data-stu-id="d7b81-142">Interop</span></span>|<span data-ttu-id="d7b81-143">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="d7b81-143">Optional attribute.</span></span> <span data-ttu-id="d7b81-144">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="d7b81-144">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d7b81-145">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="d7b81-145">Name attribute</span></span>  
  
|<span data-ttu-id="d7b81-146">Wert</span><span class="sxs-lookup"><span data-stu-id="d7b81-146">Value</span></span>|<span data-ttu-id="d7b81-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7b81-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7b81-148">*parameter_name*</span><span class="sxs-lookup"><span data-stu-id="d7b81-148">*parameter_name*</span></span>|<span data-ttu-id="d7b81-149">Der Name des Methodenparameters, auf den die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7b81-149">The name of the method parameter to which policy is applied.</span></span> <span data-ttu-id="d7b81-150">Für die Methodensignatur `String.CompareTo(Object value)` ist der Wert des `Name`-Attributs beispielsweise "value".</span><span class="sxs-lookup"><span data-stu-id="d7b81-150">For example, for the method signature `String.CompareTo(Object value)`, the value of the `Name` attribute is "value".</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d7b81-151">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="d7b81-151">All other attributes</span></span>  
  
|<span data-ttu-id="d7b81-152">Wert</span><span class="sxs-lookup"><span data-stu-id="d7b81-152">Value</span></span>|<span data-ttu-id="d7b81-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7b81-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7b81-154">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d7b81-154">*policy_setting*</span></span>|<span data-ttu-id="d7b81-155">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7b81-155">The setting to apply to this policy type.</span></span> <span data-ttu-id="d7b81-156">Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="d7b81-156">Possible values are `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="d7b81-157">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d7b81-157">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d7b81-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7b81-158">Child Elements</span></span>  
 <span data-ttu-id="d7b81-159">Keine</span><span class="sxs-lookup"><span data-stu-id="d7b81-159">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d7b81-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d7b81-160">Parent Elements</span></span>  
  
|<span data-ttu-id="d7b81-161">Element</span><span class="sxs-lookup"><span data-stu-id="d7b81-161">Element</span></span>|<span data-ttu-id="d7b81-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7b81-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7b81-163">\<Method></span><span class="sxs-lookup"><span data-stu-id="d7b81-163">\<Method></span></span>](../../../docs/framework/net-native/method-element-net-native.md)|<span data-ttu-id="d7b81-164">Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.</span><span class="sxs-lookup"><span data-stu-id="d7b81-164">Applies runtime reflection policy to a constructor or method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7b81-165">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7b81-165">Remarks</span></span>  
 <span data-ttu-id="d7b81-166">Das `<Parameter>`-Element ist ein untergeordnetes Element des [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)-Elements und wird verwendet, um eine Richtlinie auf einen bestimmten Methodenparameter anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="d7b81-166">The `<Parameter>` element is a child of the [\<Method>](../../../docs/framework/net-native/method-element-net-native.md) element and is used to apply policy to a particular method parameter.</span></span> <span data-ttu-id="d7b81-167">Der entsprechende Methodenparameter wird durch den Namen und nicht durch den Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="d7b81-167">The specific method parameter is specified by name rather than by type.</span></span> <span data-ttu-id="d7b81-168">Mindestens ein Attribut, das einen Richtlinientyp wie `Activate` oder `Dynamic` darstellt, muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d7b81-168">At least one attribute that represents a policy type, such as `Activate` or `Dynamic`, must be present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b81-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7b81-169">See Also</span></span>  
 [<span data-ttu-id="d7b81-170">\<Method> Element (Element <Method>)</span><span class="sxs-lookup"><span data-stu-id="d7b81-170">\<Method> Element</span></span>](../../../docs/framework/net-native/method-element-net-native.md)  
 [<span data-ttu-id="d7b81-171">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="d7b81-171">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="d7b81-172">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="d7b81-172">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  
 [<span data-ttu-id="d7b81-173">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="d7b81-173">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
