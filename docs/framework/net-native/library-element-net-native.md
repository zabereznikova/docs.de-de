---
title: <Library> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda4f8d3819af05b022e0633d6883cca940f67e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100261"
---
# <a name="library-element-net-native"></a><span data-ttu-id="2d1b6-102">\<Library > (Element (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="2d1b6-102">\<Library> Element (.NET Native)</span></span>
<span data-ttu-id="2d1b6-103">Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-103">Defines the assembly that contains types and type members whose metadata is available for reflection at run time.</span></span>  
  
 <span data-ttu-id="2d1b6-104">\<Directives>-Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-104">\<Directives> Element</span></span>  
<span data-ttu-id="2d1b6-105">\<Library>-Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-105">\<Library> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1b6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d1b6-106">Syntax</span></span>  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d1b6-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2d1b6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="2d1b6-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d1b6-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="2d1b6-109">Attributes</span></span>  
  
|<span data-ttu-id="2d1b6-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="2d1b6-110">Attribute</span></span>|<span data-ttu-id="2d1b6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d1b6-111">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="2d1b6-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-112">Required attribute.</span></span> <span data-ttu-id="2d1b6-113">Gibt den Namen einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-113">Specifies the name of an assembly.</span></span> <span data-ttu-id="2d1b6-114">Untergeordnete Elemente dieses `<Library>`-Elements definieren die Laufzeitreflektionsrichtlinie für Typen und Typmember in dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-114">Child elements of this `<Library>` element define the runtime reflection policy for types and type members found in this assembly.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="2d1b6-115">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="2d1b6-115">Name attribute</span></span>  
  
|<span data-ttu-id="2d1b6-116">Wert</span><span class="sxs-lookup"><span data-stu-id="2d1b6-116">Value</span></span>|<span data-ttu-id="2d1b6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d1b6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d1b6-118">*assembly_name*</span><span class="sxs-lookup"><span data-stu-id="2d1b6-118">*assembly_name*</span></span>|<span data-ttu-id="2d1b6-119">Der einfache Name der Assembly ohne Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-119">The simple name of the assembly, without its file extension.</span></span> <span data-ttu-id="2d1b6-120">Dieses Attribut entspricht der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-120">This attribute corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2d1b6-121">Der Name einer Assembly namens Extensions.dll lautet beispielsweise "Extensions".</span><span class="sxs-lookup"><span data-stu-id="2d1b6-121">For example, the name of an assembly named Extensions.dll is "Extensions".</span></span> <span data-ttu-id="2d1b6-122">Im Abschnitt „Hinweise“ ist eine besondere Form von *assembly_name* beschrieben, die den bedingten Einschluss von Metadaten aus der Assembly unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-122">See the Remarks section for a special form of *assembly_name* that supports conditional inclusion of metadata from the assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d1b6-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d1b6-123">Child Elements</span></span>  
  
|<span data-ttu-id="2d1b6-124">Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-124">Element</span></span>|<span data-ttu-id="2d1b6-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d1b6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d1b6-126">\<Assembly></span><span class="sxs-lookup"><span data-stu-id="2d1b6-126">\<Assembly></span></span>](../../../docs/framework/net-native/assembly-element-net-native.md)|<span data-ttu-id="2d1b6-127">Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-127">Applies policy to all the types in a particular assembly.</span></span>|  
|[<span data-ttu-id="2d1b6-128">\<Namespace></span><span class="sxs-lookup"><span data-stu-id="2d1b6-128">\<Namespace></span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)|<span data-ttu-id="2d1b6-129">Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-129">Applies policy to all the types in a particular namespace.</span></span>|  
|[<span data-ttu-id="2d1b6-130">\<Type></span><span class="sxs-lookup"><span data-stu-id="2d1b6-130">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="2d1b6-131">Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-131">Applies policy to a particular type, such as a class or structure.</span></span>|  
|[<span data-ttu-id="2d1b6-132">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="2d1b6-132">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="2d1b6-133">Wendet die Richtlinie auf einen konstruierten generischen Typ an.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-133">Applies policy to a constructed generic type.</span></span> <span data-ttu-id="2d1b6-134">Zum Beispiel kann ein [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element verwendet werden, um Richtlinien für einen `List<String>`-Typ zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-134">For example, a [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element could be used to define policy for a `List<String>` type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d1b6-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2d1b6-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2d1b6-136">Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-136">Element</span></span>|<span data-ttu-id="2d1b6-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d1b6-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d1b6-138">\<Directives></span><span class="sxs-lookup"><span data-stu-id="2d1b6-138">\<Directives></span></span>](../../../docs/framework/net-native/directives-element-net-native.md)|<span data-ttu-id="2d1b6-139">Das Stammelement einer Laufzeitanweisungsdatei.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-139">The root element of a runtime directives file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d1b6-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d1b6-140">Remarks</span></span>  
 <span data-ttu-id="2d1b6-141">Das [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)-Element kann null (0), ein oder mehrere `<Library>`-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-141">The [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) element can contain zero, one, or more `<Library>` elements.</span></span>  
  
 <span data-ttu-id="2d1b6-142">Das `<Library>`-Element dient als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. Dieses Element drückt keine Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-142">The `<Library>` element serves as a container to define the program elements whose metadata is needed at run time; this element doesn't express policy.</span></span> <span data-ttu-id="2d1b6-143">Zur Kompilierzeit durchsuchen die Compilertools nur die im `<Library>`-Element bezeichnete Bibliothek nach Programmelementen, die durch seine untergeordneten Elemente identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-143">At compile time, compiler tools search only the library designated by the `<Library>` element for program elements identified by its child elements.</span></span> <span data-ttu-id="2d1b6-144">Im Gegensatz dazu durchsuchen Compilertools alle Bibliotheken, auch die .NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Elements identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-144">In contrast, compiler tools search all libraries, including.NET Framework core libraries, for program elements identified by child elements of the [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element.</span></span>  
  
 <span data-ttu-id="2d1b6-145">`<Library>`-Direktiven können bedingt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-145">`<Library>` directives may be conditionally utilized.</span></span> <span data-ttu-id="2d1b6-146">Wenn der Name des der `<Library>` Element beginnt und endet mit einem Sternchen (\*), wird die `<Library>` Richtlinie wirkt sich nur dann, wenn die app zwischen den Sternchen angegebene Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-146">If the name of the `<Library>` element starts and ends with an asterisk (\*), the `<Library>` directive has an effect only if the assembly specified between the asterisks is referenced by the app.</span></span> <span data-ttu-id="2d1b6-147">Beispielsweise gilt die folgende Laufzeitdirektive nur dann, wenn von der App auf die Assembly Utillities.dll verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2d1b6-147">For example, the following runtime directive applies only if the Utillities.dll assembly is referenced by the app.</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d1b6-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d1b6-148">See also</span></span>

- [<span data-ttu-id="2d1b6-149">\<Anwendung > Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-149">\<Application> Element</span></span>](../../../docs/framework/net-native/application-element-net-native.md)
- [<span data-ttu-id="2d1b6-150">\<Directives >-Element</span><span class="sxs-lookup"><span data-stu-id="2d1b6-150">\<Directives> Element</span></span>](../../../docs/framework/net-native/directives-element-net-native.md)
- [<span data-ttu-id="2d1b6-151">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="2d1b6-151">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="2d1b6-152">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="2d1b6-152">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
