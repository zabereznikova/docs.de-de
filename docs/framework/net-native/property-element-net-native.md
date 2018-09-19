---
title: '&lt;Eigenschaft&gt; Element (.NET Native)'
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ed75d377814a740edece2b6a69e44acbd8ef0c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004350"
---
# <a name="ltpropertygt-element-net-native"></a><span data-ttu-id="38a0a-102">&lt;Eigenschaft&gt; Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="38a0a-102">&lt;Property&gt; Element (.NET Native)</span></span>
<span data-ttu-id="38a0a-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="38a0a-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a0a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38a0a-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38a0a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38a0a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="38a0a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38a0a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38a0a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="38a0a-107">Attributes</span></span>  
  
|<span data-ttu-id="38a0a-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="38a0a-108">Attribute</span></span>|<span data-ttu-id="38a0a-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="38a0a-109">Attribute type</span></span>|<span data-ttu-id="38a0a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38a0a-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="38a0a-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="38a0a-111">General</span></span>|<span data-ttu-id="38a0a-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="38a0a-112">Required attribute.</span></span> <span data-ttu-id="38a0a-113">Gibt den Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="38a0a-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="38a0a-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="38a0a-114">Reflection</span></span>|<span data-ttu-id="38a0a-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="38a0a-115">Optional attribute.</span></span> <span data-ttu-id="38a0a-116">Steuert das Abfragen nach Informationen über die Eigenschaft oder das Auflisten der Eigenschaft, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="38a0a-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="38a0a-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="38a0a-117">Reflection</span></span>|<span data-ttu-id="38a0a-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="38a0a-118">Optional attribute.</span></span> <span data-ttu-id="38a0a-119">Steuert den Laufzeitzugriff auf die Eigenschaft, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="38a0a-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="38a0a-120">Diese Richtlinie stellt sicher, dass eine Eigenschaft zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="38a0a-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="38a0a-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="38a0a-121">Serialization</span></span>|<span data-ttu-id="38a0a-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="38a0a-122">Optional attribute.</span></span> <span data-ttu-id="38a0a-123">Steuert den Laufzeitzugriff auf eine Eigenschaft, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="38a0a-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="38a0a-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="38a0a-124">Name attribute</span></span>  
  
|<span data-ttu-id="38a0a-125">Wert</span><span class="sxs-lookup"><span data-stu-id="38a0a-125">Value</span></span>|<span data-ttu-id="38a0a-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38a0a-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38a0a-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="38a0a-127">*method_name*</span></span>|<span data-ttu-id="38a0a-128">Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="38a0a-128">The property name.</span></span> <span data-ttu-id="38a0a-129">Der Typ der Eigenschaft wird durch das übergeordnete [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="38a0a-129">The type of the property is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="38a0a-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="38a0a-130">All other attributes</span></span>  
  
|<span data-ttu-id="38a0a-131">Wert</span><span class="sxs-lookup"><span data-stu-id="38a0a-131">Value</span></span>|<span data-ttu-id="38a0a-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38a0a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38a0a-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="38a0a-133">*policy_setting*</span></span>|<span data-ttu-id="38a0a-134">Die Einstellung, die auf diesen Richtlinientyp für die Eigenschaft angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="38a0a-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="38a0a-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="38a0a-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="38a0a-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="38a0a-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38a0a-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38a0a-137">Child Elements</span></span>  
 <span data-ttu-id="38a0a-138">Keine</span><span class="sxs-lookup"><span data-stu-id="38a0a-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38a0a-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38a0a-139">Parent Elements</span></span>  
  
|<span data-ttu-id="38a0a-140">Element</span><span class="sxs-lookup"><span data-stu-id="38a0a-140">Element</span></span>|<span data-ttu-id="38a0a-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38a0a-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38a0a-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="38a0a-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="38a0a-143">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="38a0a-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="38a0a-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="38a0a-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="38a0a-145">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="38a0a-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38a0a-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38a0a-146">Remarks</span></span>  
 <span data-ttu-id="38a0a-147">Wenn die Richtlinie einer Eigenschaft nicht explizit definiert ist, erbt sie die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="38a0a-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38a0a-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38a0a-148">Example</span></span>  
 <span data-ttu-id="38a0a-149">Im folgenden Beispiel wird Reflektion zum Instanziieren eines `Book`-Objekts und zum Anzeigen seiner Eigenschaftenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="38a0a-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="38a0a-150">Die ursprüngliche Datei default.rd.xml für das Projekt sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="38a0a-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="38a0a-151">Die Datei wendet den Wert `All` auf die `Activate`-Richtlinie für die `Book`-Klasse an, die den Zugriff auf Klassenkonstruktoren über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="38a0a-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="38a0a-152">Die `Browse`-Richtlinie für die `Book`-Klasse wird vom übergeordneten Namespace geerbt.</span><span class="sxs-lookup"><span data-stu-id="38a0a-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="38a0a-153">Diese wird auf `Required Public` festgelegt, wodurch Metadaten zur Laufzeit verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="38a0a-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="38a0a-154">Der Quellcode für das Beispiel lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="38a0a-154">The following is the source code for the example.</span></span> <span data-ttu-id="38a0a-155">Die `outputBlock`-Variable stellt ein [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx)-Steuerelement dar.</span><span class="sxs-lookup"><span data-stu-id="38a0a-155">The `outputBlock` variable represents a [TextBlock](https://msdn.microsoft.com/library/windows.ui.xaml.controls.textblock.aspx) control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="38a0a-156">Das Kompilieren und Ausführen dieses Beispiels löst jedoch eine [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="38a0a-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="38a0a-157">Obwohl wir Metadaten für den `Book`-Typ verfügbar gemacht haben, haben wir keine Implementierungen der Eigenschaftengetter dynamisch zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="38a0a-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="38a0a-158">Wir können diesen Fehler auf eine von zwei Arten beheben:</span><span class="sxs-lookup"><span data-stu-id="38a0a-158">We can correct this error by either in one of two ways:</span></span>  
  
-   <span data-ttu-id="38a0a-159">Durch Definieren der `Dynamic`-Richtlinie für den `Book`-Typ in dessen [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)-Element.</span><span class="sxs-lookup"><span data-stu-id="38a0a-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) element.</span></span>  
  
-   <span data-ttu-id="38a0a-160">Durch Hinzufügen eines verschachtelten [\<Property>](../../../docs/framework/net-native/property-element-net-native.md)-Elements für jede Eigenschaft, deren Getter wir wie in der folgenden Datei „default.rd.xml“ aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="38a0a-160">By adding a nested [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="38a0a-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38a0a-161">See Also</span></span>  
 [<span data-ttu-id="38a0a-162">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="38a0a-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="38a0a-163">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="38a0a-163">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="38a0a-164">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="38a0a-164">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
