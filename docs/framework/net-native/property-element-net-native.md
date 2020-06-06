---
title: <Property>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: b9bc89804a872dddf1a56c2a3dadc9c3df4f5fd1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128213"
---
# <a name="property-element-net-native"></a><span data-ttu-id="c62fe-102">\<Property>-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="c62fe-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="c62fe-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c62fe-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c62fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c62fe-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c62fe-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c62fe-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c62fe-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c62fe-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c62fe-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c62fe-107">Attributes</span></span>  
  
|<span data-ttu-id="c62fe-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c62fe-108">Attribute</span></span>|<span data-ttu-id="c62fe-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="c62fe-109">Attribute type</span></span>|<span data-ttu-id="c62fe-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c62fe-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="c62fe-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="c62fe-111">General</span></span>|<span data-ttu-id="c62fe-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c62fe-112">Required attribute.</span></span> <span data-ttu-id="c62fe-113">Gibt den Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="c62fe-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="c62fe-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="c62fe-114">Reflection</span></span>|<span data-ttu-id="c62fe-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="c62fe-115">Optional attribute.</span></span> <span data-ttu-id="c62fe-116">Steuert das Abfragen nach Informationen über die Eigenschaft oder das Auflisten der Eigenschaft, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c62fe-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="c62fe-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="c62fe-117">Reflection</span></span>|<span data-ttu-id="c62fe-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="c62fe-118">Optional attribute.</span></span> <span data-ttu-id="c62fe-119">Steuert den Laufzeitzugriff auf die Eigenschaft, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c62fe-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="c62fe-120">Diese Richtlinie stellt sicher, dass eine Eigenschaft zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c62fe-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="c62fe-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c62fe-121">Serialization</span></span>|<span data-ttu-id="c62fe-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="c62fe-122">Optional attribute.</span></span> <span data-ttu-id="c62fe-123">Steuert den Laufzeitzugriff auf eine Eigenschaft, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c62fe-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="c62fe-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="c62fe-124">Name attribute</span></span>  
  
|<span data-ttu-id="c62fe-125">Wert</span><span class="sxs-lookup"><span data-stu-id="c62fe-125">Value</span></span>|<span data-ttu-id="c62fe-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c62fe-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c62fe-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="c62fe-127">*method_name*</span></span>|<span data-ttu-id="c62fe-128">Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="c62fe-128">The property name.</span></span> <span data-ttu-id="c62fe-129">Der Typ der Eigenschaft wird durch das übergeordnete- [\<Type>](type-element-net-native.md) oder- [\<TypeInstantiation>](typeinstantiation-element-net-native.md) Element definiert.</span><span class="sxs-lookup"><span data-stu-id="c62fe-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="c62fe-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="c62fe-130">All other attributes</span></span>  
  
|<span data-ttu-id="c62fe-131">Wert</span><span class="sxs-lookup"><span data-stu-id="c62fe-131">Value</span></span>|<span data-ttu-id="c62fe-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c62fe-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c62fe-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="c62fe-133">*policy_setting*</span></span>|<span data-ttu-id="c62fe-134">Die Einstellung, die auf diesen Richtlinientyp für die Eigenschaft angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c62fe-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="c62fe-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="c62fe-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="c62fe-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c62fe-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c62fe-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c62fe-137">Child Elements</span></span>  
 <span data-ttu-id="c62fe-138">Keine</span><span class="sxs-lookup"><span data-stu-id="c62fe-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c62fe-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c62fe-139">Parent Elements</span></span>  
  
|<span data-ttu-id="c62fe-140">Element</span><span class="sxs-lookup"><span data-stu-id="c62fe-140">Element</span></span>|<span data-ttu-id="c62fe-141">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c62fe-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="c62fe-142">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="c62fe-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="c62fe-143">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="c62fe-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c62fe-144">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c62fe-144">Remarks</span></span>  
 <span data-ttu-id="c62fe-145">Wenn die Richtlinie einer Eigenschaft nicht explizit definiert ist, erbt sie die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="c62fe-145">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c62fe-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c62fe-146">Example</span></span>  
 <span data-ttu-id="c62fe-147">Im folgenden Beispiel wird Reflektion zum Instanziieren eines `Book`-Objekts und zum Anzeigen seiner Eigenschaftenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c62fe-147">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="c62fe-148">Die ursprüngliche Datei default.rd.xml für das Projekt sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="c62fe-148">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="c62fe-149">Die Datei wendet den Wert `All` auf die `Activate`-Richtlinie für die `Book`-Klasse an, die den Zugriff auf Klassenkonstruktoren über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c62fe-149">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="c62fe-150">Die `Browse`-Richtlinie für die `Book`-Klasse wird vom übergeordneten Namespace geerbt.</span><span class="sxs-lookup"><span data-stu-id="c62fe-150">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="c62fe-151">Diese wird auf `Required Public` festgelegt, wodurch Metadaten zur Laufzeit verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="c62fe-151">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="c62fe-152">Der Quellcode für das Beispiel lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c62fe-152">The following is the source code for the example.</span></span> <span data-ttu-id="c62fe-153">Die- `outputBlock` Variable stellt ein-Steuerelement dar <xref:Windows.UI.Xaml.Controls.TextBlock> .</span><span class="sxs-lookup"><span data-stu-id="c62fe-153">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="c62fe-154">Das Kompilieren und Ausführen dieses Beispiels löst jedoch eine [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="c62fe-154">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="c62fe-155">Obwohl wir Metadaten für den `Book`-Typ verfügbar gemacht haben, haben wir keine Implementierungen der Eigenschaftengetter dynamisch zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="c62fe-155">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="c62fe-156">Wir können diesen Fehler auf eine von zwei Arten beheben:</span><span class="sxs-lookup"><span data-stu-id="c62fe-156">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="c62fe-157">durch Definieren der `Dynamic` Richtlinie für den- `Book` Typ im- [\<Type>](type-element-net-native.md) Element.</span><span class="sxs-lookup"><span data-stu-id="c62fe-157">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="c62fe-158">Durch Hinzufügen eines [\<Property>](property-element-net-native.md) für jede Eigenschaft, deren Getter wir aufrufen möchten, wie in der folgenden default. rd. XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="c62fe-158">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c62fe-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c62fe-159">See also</span></span>

- [<span data-ttu-id="c62fe-160">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="c62fe-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c62fe-161">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="c62fe-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c62fe-162">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="c62fe-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
