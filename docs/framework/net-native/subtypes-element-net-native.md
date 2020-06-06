---
title: <Subtypes>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: fb854070-248b-46cf-9dab-c322e2b4d624
ms.openlocfilehash: bb719449f3769c5dbbde6d05efdb865c18bb4ab2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180936"
---
# <a name="subtypes-element-net-native"></a><span data-ttu-id="4e35a-102">\<Subtypes>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="4e35a-102">\<Subtypes> Element (.NET Native)</span></span>
<span data-ttu-id="4e35a-103">Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.</span><span class="sxs-lookup"><span data-stu-id="4e35a-103">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e35a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e35a-104">Syntax</span></span>  
  
```xml  
<Subtypes Activate="policy_type"  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e35a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4e35a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4e35a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e35a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e35a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="4e35a-107">Attributes</span></span>  
  
|<span data-ttu-id="4e35a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4e35a-108">Attribute</span></span>|<span data-ttu-id="4e35a-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="4e35a-109">Attribute type</span></span>|<span data-ttu-id="4e35a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e35a-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Activate`|<span data-ttu-id="4e35a-111">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4e35a-111">Reflection</span></span>|<span data-ttu-id="4e35a-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-112">Optional attribute.</span></span> <span data-ttu-id="4e35a-113">Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4e35a-113">Controls runtime access to constructors to enable activation of instances.</span></span>|  
|`Browse`|<span data-ttu-id="4e35a-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4e35a-114">Reflection</span></span>|<span data-ttu-id="4e35a-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-115">Optional attribute.</span></span> <span data-ttu-id="4e35a-116">Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.</span><span class="sxs-lookup"><span data-stu-id="4e35a-116">Controls querying for information about program elements, but does not enable any runtime access.</span></span>|  
|`Dynamic`|<span data-ttu-id="4e35a-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="4e35a-117">Reflection</span></span>|<span data-ttu-id="4e35a-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-118">Optional attribute.</span></span> <span data-ttu-id="4e35a-119">Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4e35a-119">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>|  
|`Serialize`|<span data-ttu-id="4e35a-120">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4e35a-120">Serialization</span></span>|<span data-ttu-id="4e35a-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-121">Optional attribute.</span></span> <span data-ttu-id="4e35a-122">Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4e35a-122">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span>|  
|`DataContractSerializer`|<span data-ttu-id="4e35a-123">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4e35a-123">Serialization</span></span>|<span data-ttu-id="4e35a-124">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-124">Optional attribute.</span></span> <span data-ttu-id="4e35a-125">Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e35a-125">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>|  
|`DataContractJsonSerializer`|<span data-ttu-id="4e35a-126">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4e35a-126">Serialization</span></span>|<span data-ttu-id="4e35a-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-127">Optional attribute.</span></span> <span data-ttu-id="4e35a-128">Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e35a-128">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType> class.</span></span>|  
|`XmlSerializer`|<span data-ttu-id="4e35a-129">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="4e35a-129">Serialization</span></span>|<span data-ttu-id="4e35a-130">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-130">Optional attribute.</span></span> <span data-ttu-id="4e35a-131">Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e35a-131">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>|  
|`MarshalObject`|<span data-ttu-id="4e35a-132">Interop</span><span class="sxs-lookup"><span data-stu-id="4e35a-132">Interop</span></span>|<span data-ttu-id="4e35a-133">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-133">Optional attribute.</span></span> <span data-ttu-id="4e35a-134">Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.</span><span class="sxs-lookup"><span data-stu-id="4e35a-134">Controls policy for marshaling reference types to Windows Runtime and COM.</span></span>|  
|`MarshalDelegate`|<span data-ttu-id="4e35a-135">Interop</span><span class="sxs-lookup"><span data-stu-id="4e35a-135">Interop</span></span>|<span data-ttu-id="4e35a-136">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-136">Optional attribute.</span></span> <span data-ttu-id="4e35a-137">Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="4e35a-137">Controls policy for marshaling delegate types as function pointers to native code.</span></span>|  
|`MarshalStructure`|<span data-ttu-id="4e35a-138">Interop</span><span class="sxs-lookup"><span data-stu-id="4e35a-138">Interop</span></span>|<span data-ttu-id="4e35a-139">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="4e35a-139">Optional attribute.</span></span> <span data-ttu-id="4e35a-140">Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="4e35a-140">Controls policy for marshaling value types to native code.</span></span>|  
  
## <a name="all-attributes"></a><span data-ttu-id="4e35a-141">Alle Attribute</span><span class="sxs-lookup"><span data-stu-id="4e35a-141">All attributes</span></span>  
  
|<span data-ttu-id="4e35a-142">Wert</span><span class="sxs-lookup"><span data-stu-id="4e35a-142">Value</span></span>|<span data-ttu-id="4e35a-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e35a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4e35a-144">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="4e35a-144">*policy_setting*</span></span>|<span data-ttu-id="4e35a-145">Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e35a-145">The setting to apply to this policy type.</span></span> <span data-ttu-id="4e35a-146">Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`.</span><span class="sxs-lookup"><span data-stu-id="4e35a-146">Possible values are `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal`, and `Required All`.</span></span> <span data-ttu-id="4e35a-147">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4e35a-147">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e35a-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e35a-148">Child Elements</span></span>  
 <span data-ttu-id="4e35a-149">Keine</span><span class="sxs-lookup"><span data-stu-id="4e35a-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e35a-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e35a-150">Parent Elements</span></span>  
  
|<span data-ttu-id="4e35a-151">Element</span><span class="sxs-lookup"><span data-stu-id="4e35a-151">Element</span></span>|<span data-ttu-id="4e35a-152">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e35a-152">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="4e35a-153">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="4e35a-153">Applies reflection policy to a type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e35a-154">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4e35a-154">Remarks</span></span>  
 <span data-ttu-id="4e35a-155">Das `<Subtypes>`-Element wendet die Richtlinie auf alle Untertypen des enthaltenden Typs an.</span><span class="sxs-lookup"><span data-stu-id="4e35a-155">The `<Subtypes>` element applies policy to all the subtypes of its containing type.</span></span> <span data-ttu-id="4e35a-156">Sie verwenden es, wenn Sie verschiedene Richtlinien auf abgeleitete Typen und deren Basisklassen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4e35a-156">You use it when you want to apply different policies to derived types and their base classes.</span></span>  
  
 <span data-ttu-id="4e35a-157">Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional, obwohl mindestens eines vorhanden sein sollte.</span><span class="sxs-lookup"><span data-stu-id="4e35a-157">The reflection, serialization, and interop attributes are all optional, although at least one should be present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e35a-158">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e35a-158">Example</span></span>  
 <span data-ttu-id="4e35a-159">Im folgenden Beispiel werden eine Klasse namens `BaseClass` und eine Unterklasse namens `Derived1` definiert.</span><span class="sxs-lookup"><span data-stu-id="4e35a-159">The following example defines a class named `BaseClass` and a subclass named `Derived1`.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#4)]  
  
 <span data-ttu-id="4e35a-160">Wie im folgenden Code dargestellt, legt die Laufzeitdirektivendatei die `Dynamic`- und `Activate`-Richtlinien für `BaseClass` explizit auf `Excluded` fest.</span><span class="sxs-lookup"><span data-stu-id="4e35a-160">As shown in the following code, the runtime directives file explicitly sets the `Dynamic` and `Activate` policies for `BaseClass` to `Excluded`.</span></span> <span data-ttu-id="4e35a-161">Daher können Objekte vom Typ `BaseClass` nicht dynamisch oder durch Aufrufe des `BaseClass`-Klassenkonstruktors instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e35a-161">Because of this, objects of type `BaseClass` cannot be instantiated dynamically or by calls to the `BaseClass` class constructor.</span></span> <span data-ttu-id="4e35a-162">Allerdings lässt das `<Subtypes>`-Element zu, dass von `BaseClass` abgeleitete Klassen dynamisch und über Aufrufe von deren Klassenkonstruktoren instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="4e35a-162">However, the `<Subtypes>` element allows classes derived from `BaseClass` to be instantiated dynamically and through calls to their class constructors.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
   <Assembly Name="*Application*" Dynamic="Required All" />  
     <Type Name="Examples.Libraries.BaseClass" Activate ="Excluded" Dynamic="Excluded" >  
        <Subtypes Activate="Public" Dynamic ="Public"/>  
     </Type>  
  </Application>  
</Directives>  
```  
  
 <span data-ttu-id="4e35a-163">Aufgrund der `<Subtypes>`-Direktive wird der folgende Code, der eine `Derived1`-Instanz dynamisch durch Aufrufen der <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType>-Methode instanziiert, erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e35a-163">Because of the `<Subtypes>` directive, the following code that instantiates a `Derived1` instance dynamically by calling the <xref:System.Activator.CreateInstance%28System.Type%29?displayProperty=nameWithType> method executes successfully.</span></span>  <span data-ttu-id="4e35a-164">Die Blockvariable ist hier ein <xref:System.Windows.Controls.TextBlock>-Objekt in einer leeren Windows Store-App.</span><span class="sxs-lookup"><span data-stu-id="4e35a-164">The block variable here is a <xref:System.Windows.Controls.TextBlock> object in a blank Windows Store app.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/subtypes.cs#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4e35a-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e35a-165">See also</span></span>

- [<span data-ttu-id="4e35a-166">\<Type>Gewisses</span><span class="sxs-lookup"><span data-stu-id="4e35a-166">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="4e35a-167">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="4e35a-167">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="4e35a-168">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="4e35a-168">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="4e35a-169">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="4e35a-169">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
